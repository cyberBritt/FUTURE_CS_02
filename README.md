# FUTURE_CS_02 
<b>SOC Analysis Incident Report</b>

This repository contains my analysis and reporting for Task 2 of my cybersecurity internship, where I performed log analysis using Splunk to identify suspicious activity and generate incident reports.

---

## 🔧 Tools Used

- **Splunk Cloud** – For log ingestion, search, and dashboard creation  
- **SPL (Search Processing Language)** – To query and classify event severity  
- **Excel** – To organize suspicious events before analysis  
- **GitHub** – To document and present the incident workflow professionally 

---

## 📌 Project Objective

The goal of this project was to simulate the responsibilities of a SOC analyst by:

- Investigating user activity logs for anomalies  
- Detecting malware, suspicious logins, and access attempts  
- Classifying events based on severity (High, Medium, Low)  
- Creating a dashboard to visualize threats by IP, action, and severity  
- Writing incident summaries per user

---

## 📁 Folder Structure
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
---

## 🔍 Sample Analysis Insights

- **High Severity Events**: Malware detected (ransomware, rootkit, trojan, worm)
- **Medium Severity**: Multiple login failures, connection attempts
- **Low Severity**: Routine file access and login success  
- **Red Flags**: Users with simultaneous activity across private and public IPs

---

## 📈 Dashboards & Visuals

Splunk dashboards were created to visualize:
- Event severity classification
- Top source IP addresses
- Most common threat types
- Recent high-priority alerts by user and time

---

## ✅ Outcome

This project demonstrates practical experience in:
- SOC monitoring workflows  
- Writing SPL queries to detect security events  
- Incident reporting and documentation  
- Threat visualization using dashboards  

---

**Created by:** B.Brinson
