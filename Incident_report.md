# 🚨 Incident Report – Network Reconnaissance Detection

## 📌 Incident Overview

* **Incident Title:** Network Port Scan Detection
* **Date:** 15 March 2026
* **Environment:** Controlled Lab Network
* **Tools Used:** Nmap, Wireshark

This incident report documents the detection and analysis of a **network reconnaissance activity** performed within a lab environment.

---

## ⚡ Incident Description

During network monitoring, suspicious activity was observed originating from a host within the local network. The system initiated multiple connection attempts targeting different ports on a machine.

This behavior is characteristic of a **port scanning attack**, typically used in the **reconnaissance phase** of cyber attacks.

---

## 🧪 Attack Simulation

The following command was used to simulate the attack:

```
nmap -sS -A 192.168.1.37
```

### 🔍 Purpose of the Scan

* Perform a **SYN (stealth) scan**
* Identify **open ports and services**
* Detect **operating system details**

---

## 📊 Nmap Scan Findings

The scan revealed the following open ports:

| Port | Service | Description                     |
| ---- | ------- | ------------------------------- |
| 135  | MSRPC   | Microsoft Remote Procedure Call |
| 139  | NetBIOS | File sharing communication      |
| 445  | SMB     | Windows file sharing            |
| 3306 | MySQL   | Database service                |

These services indicate that the target system is likely running **Windows-based services** with an exposed database service.

---

## 📡 Network Traffic Analysis (Wireshark)

Network traffic was captured using **Wireshark** during the scanning activity.

### 🔎 Filter Used

```
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

### 📌 Observations

* Multiple **TCP SYN packets** were observed
* Packets targeted **multiple ports**
* No complete TCP handshake occurred

This pattern is consistent with a **TCP SYN scan**.

---

## 🚨 Indicators of Compromise (IOC)

| Indicator        | Value                    |
| ---------------- | ------------------------ |
| Source IP        | 192.168.1.37             |
| Activity         | Port Scanning            |
| Tool Used        | Nmap                     |
| Detection Method | Packet Analysis          |
| Evidence         | SYN packets in Wireshark |

---

## ⚠️ Risk Assessment

The activity is classified as **network reconnaissance**, which is often the **first step in a cyber attack**.

### Potential Risks:

* Identification of vulnerable services
* Exposure of sensitive ports
* Preparation for further exploitation

---

## 🛡️ Mitigation & Recommendations

* Restrict access to unnecessary open ports
* Implement firewall rules to block suspicious traffic
* Monitor network activity regularly
* Use Intrusion Detection Systems (IDS) for real-time alerts
* Disable unused services

---

## 🧠 Conclusion

The investigation successfully identified **port scanning activity** using Nmap and confirmed it through **packet-level analysis in Wireshark**.

This lab demonstrates how reconnaissance attacks can be detected using basic network monitoring techniques and highlights the importance of **SOC investigation workflows**.

---

## 📎 Evidence

* Nmap scan results
* Wireshark packet capture (.pcap)
* SYN packet analysis screenshots

---

## 👨‍💻 Author
Kumar Partha
Cybersecurity Enthusiast 🚀
