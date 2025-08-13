# SPL Queries for SOC Monitoring Reponse Report

These are the SPL queries I used for analyzing the security logs in Splunk.

## 1. Severity Classification
To classify events into severity levels (High, Medium, Low) based on the type of action and threat detected.

```
index=main 
| rex "user=(?<user>\w+)\s+\|\s+ip=(?<ip>[\d\.]+)\s+\|\s+action=(?<action>[^\|]+)(?:\s+\|\s+threat=(?<threat>.+))?"
| eval action=trim(action), threat=trim(threat), ip=trim(ip)
| eval severity=case(
    action="malware detected" AND like(threat, "%Rootkit%"), "High",
    action="malware detected" AND like(threat, "%Ransomware%"), "High",
    action="malware detected" AND like(threat, "%Worm%"), "High",
    action="login failed", "Medium",
    action="file accessed" AND (ip LIKE "198.%" OR ip LIKE "203.%"), "Medium",
    1=1, "Low"
)
| stats count by severity
```
Explanation:<br>
Uses rex to extract fields: user, ip, action, and threat.<br>
Then assign the severity levels:<br>
High = Malware detected <br>
Medium = Login failures or file access from suspicious IPs <br>
Low = Everything else nthat may possibly be a false positive


## 2. IP Address Analysis
To identify the IP addresses associated with the most incidents.

```
index=main 
| rex "ip=(?<ip>[\d\.]+)"
| stats count by ip
| sort - count
```
Explanation:<br>
This extracts the IP field from log entries.<br>
Counts the number of events per IP address.<br>
Sorts results to show the most frequent offenders.


## 3. Threat Type Frequency

The count of how many times each type of threat shows up in the logs.

```
index=main 
| rex "threat=(?<threat>.+)"
| stats count by threat
| sort - count
```
Explanation:<br>
Pulls the threat value from log entries.<br>
Groups results to see how many times each threat type occurred.<br>
Helps prioritize which threats are most active.


## 4. Top User Activity
Finds which users are most frequently involved in security events.

```
index=main
| rex "user=(?<user>\w+)"
| stats count by user
| sort - count
```
Explanation:<br>
Extracts the user field.<br>
Counts events per user to identify potential insider threats or compromised accounts.
