# Pyramid of Pain – TryHackMe Walkthrough  
**Author:** Abdul Rahman Said  
**Platform:** TryHackMe  
**Room:** Pyramid of Pain  
**Objective:** Understand and apply the Pyramid of Pain framework to threat detection and adversary disruption.

---

## 📖 Introduction

The **Pyramid of Pain**, developed by David J. Bianco, is a framework used in **threat hunting** and **incident response**. It shows the difficulty level for attackers to modify different types of Indicators of Compromise (IOCs). The higher you go on the pyramid, the harder it becomes for adversaries to change their tactics, making those indicators more valuable to defenders.

This report documents my hands-on experience with the TryHackMe "Pyramid of Pain" room, including step-by-step explanations, analysis, detection techniques, and answers.

---

## 🔺 Pyramid Layers Overview

| Layer                                    | Difficulty for Attacker  | Description                                                                        |
|------------------------------------------|--------------------------|------------------------------------------------------------------------------------|
| Hash Values                              | Very Easy                | File fingerprints (e.g., SHA256). Easily changed by modifying one byte.            |
| IP Addresses                             | Easy                     | Attackers may rotate IPs or use proxies.                                           |
| Domain Names                             | Medium                   | Harder to obtain, register, and use. Can be obfuscated (Punycode, URL shorteners). |
| Host & Network Artifacts                 | Hard                     | Includes file paths, registry keys, user-agent strings, etc.                       |
| Tools                                    | Very Hard                | Malware frameworks like Cobalt Strike. Custom tools take time to create.           |
| TTPs (Tactics, Techniques, Procedures)   | Extremely Hard           | Behavioral patterns tied to attacker operations.                                   |

---

## ✅ Task-by-Task Breakdown

### 🧠 Task 1: Intro to Pyramid of Pain

- Read and understood the pyramid layers.
- No answer required.

---

### 🧪 Task 2: Hash Values

📌 **What I did:**
- Investigated a sample malware file using VirusTotal.
- Learned how appending a single character changes the hash.
- Realized that hashes alone are weak IOCs.

✅ **Answer:**  
- **File Name:** `Sales_invoice_receipt.xlsx`

---

### 🌍 Task 3: IP Addresses

📌 **What I did:**
- Reviewed a sandbox report of malware behavior.
- Identified IP address and domain it contacted.
- Noted that IPs can be rotated via Fast Flux techniques.

✅ **Answers:**  
- **First IP contacted (PID 1632):** `155.94.75.52`  
- **First Domain Contacted:** `craftinglegacy.com`

---

### 🌐 Task 4: Domain Names

📌 **What I did:**
- Explored how attackers obfuscate domains using Punycode or URL shorteners.
- Used the `+` trick in Bit.ly to preview shortened URLs.

✅ **Answers:**  
- **Suspicious URL:** `craftinglegacy.com`  
- **Term:** `Domain Name`  
- **Attack Type:** `Punycode Attack`  
- **Redirected URL (via shortener):** `https://tryhackme.com/room/pyramidofpain`

---

### 🖥️ Task 5: Host and Network Artifacts

📌 **What I did:**
- Inspected file and process behavior in a malware analysis report.
- Noted POST requests, dropped file, and user-agent string.

✅ **Answers:**  
- **IP Address (POST request on Port 88):** `5.182.210.85`  
- **Dropped Executable:** `Stealer.exe`  
- **Vendors Flagging it as Malicious:** `9`  
- **Browser from User-Agent:** `Google Chrome`  
- **Number of POST Requests:** `6`

---

### 🛠️ Task 6: Tools

📌 **What I did:**
- Learned about detection tools like YARA and Sigma.
- Reviewed fuzzy hashing (ssdeep) for malware similarity detection.

✅ **Answers:**  
- **Method to Compare Hashes:** `Fuzzy Hashing`  
- **Full Term for SSDP:** `Context Triggered Piecewise Hashes`

---

### 🔍 Task 7: TTPs

📌 **What I did:**
- Used MITRE ATT&CK to study real-world threat groups (APT).
- Found TTPs used by Chimera APT including their C2 tool.

✅ **Answers:**  
- **Exfiltration Techniques Count:** `6`  
- **C2 Tool Used by Chimera APT:** `Cobalt Strike`

---

### 🧩 Task 8: Static Site (Drag & Drop)

📌 **What I did:**
- Deployed a static page.
- Dragged each behavioral trait or IOC into the correct pyramid tier.

✅ **Flag:**  
`THM{PYRAMIDS_COMPLETE}`

---

### 🎯 Task 9–10: Reflection & Application

📌 **What I learned:**
- The higher on the pyramid your detection efforts target (Tools, TTPs), the more pain it causes the attacker.
- Real-world application: use behavioral analysis, EDR, threat intelligence, and detection rules to strengthen security.

---

## 📌 Key Lessons

- **Hash values are weak** IOCs; attackers change them effortlessly.
- **Network and Host Artifacts** are more reliable but require deeper monitoring.
- **Tools and TTPs are powerful indicators** that are hard for attackers to change.
- **Use community resources** like MITRE ATT&CK and VirusTotal to build stronger detection logic.

---

## 🏁 Final Thoughts

This lab wasn't just about answering questions. It provided a real-world view of **threat hunting**, **malware detection**, and how to **prioritize defenses**. As a future cybersecurity analyst, understanding the Pyramid of Pain helps me think like both a defender and an attacker.

---
