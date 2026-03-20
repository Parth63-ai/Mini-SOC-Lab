# 🛡️ Mini SOC Lab – Network Reconnaissance Detection

## 📌 Overview

This project demonstrates a basic **Security Operations Center (SOC) workflow** by simulating and analyzing network reconnaissance activity.

The objective is to detect **port scanning attacks** using network traffic analysis.

---

## 🎯 Objectives

- Simulate network reconnaissance using Nmap  
- Capture network traffic using Wireshark  
- Identify SYN scan behavior  
- Analyze suspicious network activity  
- Create a SOC-style incident report  

---

## 🛠️ Tools Used

- Nmap  
- Wireshark  
- TCP/IP Networking  

---

## 🧪 Lab Setup

**Environment:** Local Network  

- Source (Attacker): 192.168.1.37  
- Target: Local system  

---

## ⚡ Attack Simulation

The following command was used:nmap -sS -A 192.168.1.37

---


This performs:

- SYN scan  
- Service detection  
- OS detection  

---

## 📊 Nmap Results

| Port | Service | Description |
|------|--------|------------|
| 135  | MSRPC  | Remote procedure call |
| 139  | NetBIOS| File sharing |
| 445  | SMB    | Windows sharing |
| 3306 | MySQL  | Database |

---

## 📡 Traffic Analysis (Wireshark)

Filter used:tcp.flags.syn == 1 && tcp.flags.ack == 0

---


### Observations

- Multiple SYN packets detected  
- Different ports targeted  
- No complete TCP handshake  

This indicates **port scanning activity**.

---

## 🚨 Indicators of Compromise (IOC)

| Indicator | Value |
|----------|------|
| Source IP | 192.168.1.37 |
| Activity | Port Scan |
| Tool | Nmap |
| Detection | Wireshark |

---

## 🧠 Incident Summary

The analysis showed that the source system generated multiple SYN packets targeting different ports.

This behavior matches a **TCP SYN scan**, which is commonly used during the reconnaissance phase of cyber attacks.

---

## 🖼️ Screenshots

<img width="735" height="496" alt="Screenshot 2026-03-15 103539" src="https://github.com/user-attachments/assets/27791b1b-a998-4423-81a8-6a4ae868fb64" />
<img width="1361" height="562" alt="Screenshot 2026-03-15 110751" src="https://github.com/user-attachments/assets/62137bb8-b425-4b12-a804-7b6c26c53ac2" />
<img width="1345" height="233" alt="Screenshot 2026-03-15 110552" src="https://github.com/user-attachments/assets/eea8e68c-f9fe-48fd-88ed-4e1320f9de2a" />
<img width="1363" height="270" alt="Screenshot 2026-03-15 110250" src="https://github.com/user-attachments/assets/d4f0ad4b-ecaf-4d93-95e3-6edfab8d8120" />
<img width="1297" height="304" alt="Screenshot 2026-03-15 110240" src="https://github.com/user-attachments/assets/65bd3ad3-46f5-4866-917c-8eeb54a15238" />

---

## 🚀 Future Improvements

- Add Zeek for log analysis  
- Add Suricata for IDS detection  
- Integrate SIEM tools  

---

## 💡 Skills Demonstrated

- Network traffic analysis  
- Packet inspection  
- Port scan detection  
- SOC investigation  

---

## 👨‍💻 Author

Kumar Partha  
Cybersecurity Enthusiast


