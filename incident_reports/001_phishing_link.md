# Incident Report 001 – Black  Listed External URL blocked by Firewall

# Incident Report – Alert 8816

## Time of Activity
2025-10-14 02:26:16 AEST

## List of Affected Entities
- Source IP: 10.20.2.17
- Destination IP: 67.199.248.11
- Destination Port: 80
- Application: web-browsing
- Protocol: TCP
- URL: http://bit.ly/3sHkX3da12340

## Reason for Classifying as True Positive
- URL matched threat intelligence feeds and firewall blacklist.
- Splunk logs confirmed outbound request.
- Sandbox analysis returned 404, indicating prior malicious use.
- User behavior suggests phishing exposure.

## Reason for Escalating the Alert
- User clicked a shortened malicious link during business-related research.
- Potential phishing compromise and social engineering risk.
- Endpoint integrity and lateral movement need assessment.

## Recommended Remediation Actions
- Notify user and review endpoint.
- Block destination IP across perimeter.
- Add URL to internal threat feeds.
- Conduct phishing awareness training.
- Monitor for similar outbound attempts.

## Screenshots

### 🔔 Alert Summary
![Alert Summary](screenshots/alert_summary.png)

### 📊 Splunk Event
![Splunk Event](screenshots/splunk_event.png)

### 🧑‍💻 User Activity in Splunk
![User Activity](screenshots/splunk_user_activity.png)

### 🌐 VM Browser History
![Browser History](screenshots/vm_browser_history.png)

### 📧 VM Email Evidence
![Email Evidence](screenshots/vm_email_bitly_link.png)

### 🖥️ VM Task Manager
![Task Manager](screenshots/vm_taskmanager_suspicious.png)

### 📁 VM Downloads Folder
![Downloads Folder](screenshots/vm_downloads_folder.png)
- Report documented and linked to dashboard repo
