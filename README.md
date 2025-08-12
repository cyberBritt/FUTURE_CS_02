# SOC Analysis & Incident Reporting

## Project Overview
This task involved analyzing simulated security logs and network events using Splunk to detect, investigate, and document potential security incidents. The goal was to identify suspicious activity, correlate events, and generate actionable incident reports following SOC (Security Operations Center) best practices.

## Skills Gained
- Log analysis and event correlation
- Splunk query creation and dashboard development
- Incident triage and escalation procedures
- Threat hunting and risk analysis

## Tools Used
- Splunk – SIEM platform for log ingestion and search
- Kali Linux – Security testing environment
- Google Docs, PDF – Incident report creation
- Excel Spreadsheet for filtered analysis

## Deliverables
- SOC Incident Reports (PDF)
- Splunk search queries and dashboard screenshots
- Log files from analysis sessions

## Incidents Found
- Multiple failed login attempts indicating brute force activity
- Unusual outbound traffic suggesting potential data exfiltration
- Suspicious admin login from foreign IP address

## Folder Map
```
SOC-Analysis-Incident-Reports/
├── README.md 
# Project overview
├── spl_queries.md 
# Documented SPL queries with explanations
├── reports/ 
# Written incident summaries per user
│ ├── bob_incident_report.md
│ ├── charlie_incident_report.md
│ ├── david_incident_report.md
│ ├── eve_incident_report.md
│ └── alice_incident_report.md
├── logs/ 
# Sample log files (redacted if needed)
│ └── SOC_Task2_Sample_Logs.txt
├── screenshots/ 
# Visuals from Splunk dashboards
│ ├── dashboard_view.png
│ ├── threat_by_ip.png
│ ├── event_severity_chart.png
│ └── spl_query_results.png
```
## Analysis Insights

- **High Severity Events**: Malware detected (ransomware, rootkit, trojan, worm)
- **Medium Severity**: Multiple login failures, connection attempts
- **Low Severity**: Routine file access and login success  
- **Red Flags**: Users with simultaneous activity across private and public IPs

## Dashboards & Visuals

Splunk dashboards were created to visualize:
- Event severity classification
- Top source IP addresses
- Most common threat types
- Recent high-priority alerts by user and time

## Final Outcome
The SOC analysis task demonstrated how effective log monitoring and event correlation can detect malicious activity before it escalates.

- Multiple high-severity incidents were detected uysing Splunk  
- Main attacker IP 203.0.113.77 had unauthorized attempts with many user logins
- Incident reporting and documentation for system isolation, IP blocking and full malware investigation

---

**Created by:** B.Brinson
