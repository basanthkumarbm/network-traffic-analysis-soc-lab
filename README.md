# network-traffic-analysis-soc-lab
# 🚨 Network Traffic Analysis & Threat Detection (SOC Lab)

## 📌 Project Overview

This project demonstrates hands-on **network traffic analysis** using Wireshark, simulating real-world responsibilities of a **SOC (Security Operations Center) Analyst**.

The goal is to capture live network traffic, analyze protocols, and identify potential security threats such as suspicious connections, abnormal traffic patterns, and protocol misuse.

---

## 🎯 Objectives

* Capture live network packets
* Analyze TCP 3-way handshake
* Investigate DNS queries
* Inspect HTTP/HTTPS traffic
* Detect anomalies (retransmissions, scanning behavior)
* Build a SOC-style analysis report

---

## 🛠️ Tools Used

* Wireshark
* Windows OS
* Browser (for generating traffic)

---

## 🌐 Network Traffic Capture

Traffic was captured using Wireshark by monitoring the active network interface while performing:

* Web browsing
* DNS queries
* Background system communication

Capture file format: `.pcapng`

---

## 🔍 Analysis Performed

### 1. TCP Analysis

Filter used:

```
tcp.flags.syn == 1
```

#### Findings:

* Observed multiple TCP 3-way handshakes:

  * SYN → SYN-ACK → ACK
* Connections primarily made to port 443 (HTTPS)
* Indicates normal secure web communication

#### SOC Insight:

* No SYN flood behavior detected
* No incomplete handshake patterns observed

---

### 2. DNS Analysis

Filter used:

```
dns
```

#### Findings:

* Domain name resolution requests observed
* Example: google.com → resolved to IP addresses

#### SOC Insight:

* No suspicious or random domain patterns detected
* No DNS tunneling behavior identified

---

### 3. HTTP/HTTPS Analysis

Filter used:

```
http
```

#### Findings:

* Limited HTTP traffic (due to HTTPS encryption)
* Majority traffic over port 443

#### SOC Insight:

* Encrypted communication prevents payload inspection
* Normal modern browsing behavior

---

### 4. TCP Retransmission Analysis

Observed:

* TCP retransmissions in traffic

#### SOC Insight:

* Indicates minor packet loss or network delay
* No abnormal volume → considered normal

---

### 5. Threat Detection

#### Checked for:

* SYN Flood Attack
* Port Scanning
* Suspicious IP behavior
* Data exfiltration patterns

#### Result:

* No malicious activity detected
* Traffic consistent with normal user behavior

---

## 📊 Conclusion

The network traffic analysis revealed normal system and user activity, primarily involving secure HTTPS communication. No indicators of compromise (IOCs) or malicious patterns were detected.

---

## 🧠 Skills Demonstrated

* Packet analysis using Wireshark
* Protocol analysis (TCP, DNS, HTTP)
* Traffic filtering techniques
* Basic threat detection methodology
* SOC investigation workflow

---

## 🚀 Future Improvements

* Integrate SIEM tool (Splunk)
* Simulate attacks using Kali Linux
* Automate detection using scripts
* Threat intelligence integration (VirusTotal)

---

## 👨‍💻 Author

Basanth

Aspiring SOC Analyst | Cybersecurity Enthusiast

