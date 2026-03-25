# 🔐 End-to-End SOC Detection & Incident Response Lab

## 📌 Objective

The objective of this project is to simulate a real-world brute-force attack and detect it using a SIEM solution. This lab demonstrates how a Security Operations Center (SOC) analyst monitors, detects, and analyzes suspicious activity.

---

## 🧱 Lab Architecture

* **Attacker Machine:** Kali Linux
* **Target Machine:** Windows 10
* **SIEM Server:** Ubuntu (Splunk Enterprise)

---

## 🛠️ Tools & Technologies Used

* Kali Linux
* Windows 10
* Ubuntu Linux
* Splunk Enterprise
* Splunk Universal Forwarder
* Hydra (Brute-force tool)

---

## ⚔️ Attack Simulation

* A brute-force attack was simulated using Hydra targeting the RDP service.
* The attack attempted multiple login attempts on a test user.

Example command used:
hydra -t 1 -W 3 -l test -P /usr/share/wordlists/rockyou.txt rdp://192.168.56.xxx

---

## 📊 Log Collection & Forwarding

* Installed Splunk Universal Forwarder on Windows machine
* Configured forwarder to send logs to Splunk server
* Enabled monitoring of Windows Security logs

---

## 🔍 Detection & Analysis

* Logs were analyzed in Splunk using the following query:

index=* EventCode=4625

* Event ID **4625** indicates failed login attempts
* Logs showed:

  * Target user: test
  * Source IP: Kali machine
  * Multiple failed authentication attempts

---

## 🚨 Key Findings

* Detected multiple failed login attempts indicating brute-force activity
* Identified attacker source IP
* Verified logs captured in real-time in SIEM

---

## 📸 Screenshots

Included in `/Screenshots` folder:

* Hydra attack execution
* Windows Event Viewer logs (Event ID 4625)
* Splunk log ingestion
* Detection query results

---

## 🧠 Conclusion

This project successfully demonstrates:

* End-to-end SOC workflow
* Attack simulation and detection
* Log ingestion and analysis using Splunk

This lab reflects real-world SOC Level 1 responsibilities including monitoring, detection, and initial investigation.

---

## 🚀 Future Improvements

* Create Splunk alerts for brute-force detection
* Build dashboards for visualization
* Integrate Sysmon for enhanced logging

---
