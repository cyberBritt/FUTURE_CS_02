# SPL Queries for Monitoring and Response
These are the SPL queries I used for analyzing the security logs in Splunk.
<br><br>

## Action type with user
```
index=* sourcetype="SOC T2 IP Logs" user="bob"
| stats count by action
| sort - count
```

## Top IPs used by user
```
index=* sourcetype="SOC T2 IP Logs" user="eve"
| stats count by ip
| sort - count
```

## Login access by user
```
index=* sourcetype="SOC T2 IP Logs" user="alice" action="login success" OR action="login failed"
| stats count by action
```

 ## Threats by user
```
index=* sourcetype="SOC T2 IP Logs" user="david" action="malware detected"
| stats count by threat ip
| sort - count
```
