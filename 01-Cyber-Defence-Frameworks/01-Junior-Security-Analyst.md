# Room: Junior Security Analyst Intro

## 🎯 Objective
Understand the role, responsibilities, and environment of a Junior Security Analyst in a Security Operations Center (SOC), and simulate real-world scenarios including alert triage, investigation, and escalation.

---

## ✅ Task 1: Introduction to the Role

### 🔹 Role Title
**Triage Specialist** – A Junior Security Analyst primarily reviews alerts and determines whether they are false positives or actual threats requiring escalation.

---

## ✅ Task 2: What is a SOC?

A Security Operations Center (SOC) is responsible for:
- Monitoring and protecting organizational assets (e.g., data, systems, IP)
- Preventing, detecting, and responding to cyber threats 24/7
- Using tools like SIEM, IDS, IPS, EDR, and threat intelligence feeds
- Following structured workflows across Preparation, Detection, and Response

### 🔍 SOC Responsibilities Breakdown:
- **Preparation & Prevention**: Updating firewalls, signatures, patching, gathering intel
- **Monitoring & Investigation**: Using SIEM/EDR, prioritizing alerts (Critical → Low)
- **Response**: Isolate infected hosts, kill malicious processes, delete artifacts

No flag was required for this task.

---

## ✅ Task 3: Simulated SOC Workflow

### 🔍 Scenario:
An SSH brute-force attack occurred and succeeded.

| Timestamp              | Event Description                                                   |
|------------------------|----------------------------------------------------------------------|
| 2024-04-16 05:25:28    | 🚨 Unauthorized SSH attempt from `221.181.185.159`                  |
| 2024-04-16 05:27:00    | ✅ Successful SSH login from the same IP                             |

---

### 🧠 Investigation Results

- **IP**: `221.181.185.159`
- **Country**: China
- **ISP**: China Mobile Communications Corporation
- **Threat Confidence**: 100% malicious (source: ip-scanner.thm)

---

### 🧾 Actions Taken

- Escalated to: **Will Griffin (SOC Team Lead)**
- IP Blocked via Firewall Tool
- Malicious actor left the message: THM{UNTIL-WE-MEET-AGAIN}

  
---

## ✅ Flags Collected

| Flag Description              | Value                          |
|-------------------------------|--------------------------------|
| Role Confirmation             | `Triage Specialist`            |
| Malicious IP Address          | `221.181.185.159`              |
| Escalation Contact            | `Will Griffin`                 |
| Firewall Block Response       | `THM{UNTIL-WE-MEET-AGAIN}`     |

---

## 📝 Notes

- This hands-on exercise reinforced key Tier 1 SOC analyst tasks: triage, investigation, IP reputation lookup, and proper escalation.
- Practicing with real-world logs and dashboards gives valuable context for threat detection and response workflows.

