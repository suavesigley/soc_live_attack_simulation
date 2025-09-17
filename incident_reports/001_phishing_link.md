# 🧪 Incident Report 001 – Phishing Link Simulation

**Analyst**: Joshua Sigley  
**Date**: [Insert Date]  
**Lab Environment**: Kali Linux (attacker) → Windows VM (victim)  
**Attack Type**: Phishing Email with Malicious Link  
**Objective**: Simulate a phishing campaign and observe system behavior and detection

---

## 1️⃣ Attack Summary

- **Method**: Spoofed email sent from Kali using `swaks` or `sendemail`
- **Payload**: Link to fake login page or PowerShell command hosted on Kali
- **Victim Action**: Link clicked on Windows VM (liberta), triggering payload
- **Expected Behavior**: Execution of PowerShell command, possible outbound traffic

---

## 2️⃣ Execution Details

| Component | Action |
|----------|--------|
| **Email Tool** | `swaks --to victim@lab.local --from admin@corp.com --server 192.168.x.x --data phishing.txt`  
| **Payload** | `Invoke-WebRequest` to download and execute script  
| **Hosting** | Apache or Python HTTP server on Kali  
| **Victim Response** | PowerShell execution logged via Sysmon or Wazuh

---

## 3️⃣ Detection & Logging

| Tool Used | Detection |
|-----------|-----------|
| **Sysmon** | Logged PowerShell execution (Event ID 1)  
| **Wazuh** | Alert triggered for suspicious command-line activity  
| **Zeek** *(optional)* | Detected HTTP request to Kali server  

---

## 4️⃣ MITRE ATT&CK Mapping

| Tactic           | Technique       | Description                        |
|------------------|-----------------|------------------------------------|
| Initial Access   | T1566.001       | Phishing via email  
| Execution        | T1059.001       | PowerShell execution  
| Credential Access| T1111           | Fake login page *(if used)*  
| Command & Control| T1071.001       | Web-based C2 traffic *(if observed)*  

---

## 5️⃣ Screenshots

- Email preview  
- Payload execution  
- Sysmon/Wazuh alert  
- Network traffic (if captured)

> 📁 Save these in `/Screenshots/` as:
> - `001-email-preview.png`
> - `001-payload-execution.png`
> - `001-sysmon-alert.png`

---

## 6️⃣ Analyst Notes

- This simulation confirms visibility of phishing and execution behavior  
- Future iterations will include credential harvesting and lateral movement  
- MITRE mapping updated in `MITRE-Mapping/001.md`  
- Incident status tracked in `incident-tracker.csv`

---

## ✅ Actions Taken

- IOC added to threat feed  
- Alert rule tuned in Wazuh  
- Report documented and linked to dashboard repo
