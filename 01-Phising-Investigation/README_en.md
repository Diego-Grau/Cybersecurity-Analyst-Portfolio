# Phishing Investigation – SOC Simulator

## Overview

This project documents the investigation of multiple security alerts related to phishing activity within a simulated SOC environment provided by TryHackMe.

The analysis focuses on identifying phishing attempts, assessing potential impact, and determining appropriate response actions based on available log data (email, firewall, and web traffic).

---

## Objectives

- Identify phishing attempts and distinguish them from legitimate emails  
- Analyze indicators such as sender domains, URLs, and IP addresses  
- Assess whether user interaction or system compromise occurred  
- Determine escalation requirements  
- Recommend remediation actions  

---

## Environment Context

The investigation was conducted in a simulated SOC environment with limited log visibility, including:

- Email logs  
- Firewall logs  
- Web traffic data  

Note: Some indicators may not produce results in real-world threat intelligence tools due to the simulated environment.

---

## Incident Summary

| Alert ID | Type                         | Description                                  | Escalation |
| -------- | ---------------------------- | ------------------------------------------- | ---------- |
| 8814     | False Positive               | Legitimate onboarding email                 | No         |
| 8815     | Phishing                     | Malicious email (Amazon spoofing)           | No         |
| 8816     | Malicious Connection Attempt | Blocked outbound connection to phishing URL | Yes        |
| 8817     | Phishing Campaign            | Typosquatting domain (Microsoft spoofing)   | Yes        |

---

## Key Findings

### 1. Phishing Techniques Identified

- Domain spoofing (amazon.biz)  
- Typosquatting (m1crosoftsupport.co)  
- Use of URL shorteners (bit.ly)  
- Social engineering tactics  

---

### 2. Infrastructure Reuse

- Repeated use of the same malicious URL (bit.ly)  
- Indicates coordinated phishing activity  

---

### 3. New Malicious Infrastructure

- Detection of a new typosquatting domain  
- Suggests a potential phishing campaign targeting users  

---

### 4. Network Activity

- One alert showed an outbound connection attempt  
- Firewall successfully blocked the connection  
- No successful communication established  

---

## Impact Assessment

- User interaction: Not observed  
- Outbound traffic: Blocked or not detected  
- System compromise: No evidence identified  

All attacks were contained at early stages, with no confirmed compromise.

---

## Escalation Logic

- **Not Escalated:** Alerts with no user interaction or impact  
- **Escalated:**  
  - Evidence of connection attempts  
  - Detection of new malicious infrastructure  
  - Potential for broader campaign  

---

## Response Actions

- Block malicious domains and IP addresses  
- Remove phishing emails from user inboxes  
- Monitor for similar indicators  
- Investigate affected hosts when connection attempts occur  
- Improve email filtering rules  
- Promote user awareness training  

---

## Indicators of Compromise (IOCs)

**Domains:**  
- amazon.biz  
- m1crosoftsupport.co  
- bit.ly/3sHkX3da12340  

**IP Addresses:**  
- 67.199.248.11  
- 102.89.222.143  

**Emails:**  
- urgents[@]amazon[.]biz  
- no-reply[@]m1crosoftsupport[.]co  

---

## Lessons Learned

- Detection alone is not sufficient; impact assessment is critical  
- Absence of logs is a valid investigative finding  
- Not all phishing alerts require escalation  
- Identifying patterns across alerts helps detect campaigns  
- Proper documentation is essential for SOC operations  

---

## Skills Demonstrated

- Phishing analysis  
- Log investigation  
- Incident triage (True Positive / False Positive)  
- Impact assessment  
- Escalation decision-making  
- IOC identification and correlation  

---


---

## Tools Used

- SIEM SPLUNK (simulated environment)  
- Internal threat intelligence tools  

---

## Conclusion

This investigation demonstrates how multiple seemingly independent alerts can reveal broader phishing activity when analyzed collectively.

By correlating indicators, assessing impact, and making informed escalation decisions, it is possible to effectively detect and respond to threats even in environments with limited visibility.
