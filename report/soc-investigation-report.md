# 🚨 SOC Investigation Report

**Project:** Network Traffic Analysis using Wireshark
**Analyst:** Basanth
**Role Simulation:** SOC Analyst (Level 1)

---

## 📌 Executive Summary

This investigation was conducted to analyze captured network traffic and identify any indicators of compromise (IOC), suspicious behavior, or malicious activity.

The analysis focused on:

* TCP connection behavior
* DNS resolution patterns
* Encrypted web traffic (HTTPS)
* Potential threat indicators

The findings indicate that the observed traffic is **benign and consistent with normal user activity**.

---

## 🎯 Scope of Analysis

* Packet capture using Wireshark
* Protocol analysis:

  * TCP
  * DNS
  * HTTP/HTTPS
* Threat detection:

  * SYN flood
  * Port scanning
  * DNS anomalies

---

## 🧪 Methodology

### Step 1: Traffic Capture

* Captured live traffic from active network interface
* Generated traffic via web browsing

---

### Step 2: TCP Analysis

* Used filters:

  * tcp.flags.syn == 1
* Observed standard TCP 3-way handshake

✔ Result: Normal connection establishment

---

### Step 3: DNS Analysis

* Filter used:

  * dns

✔ Observed:

* A, AAAA, and CNAME records
* Domains: Google, LinkedIn

✔ Result:

* No suspicious or malicious domains

---

### Step 4: HTTPS Analysis

* Observed traffic over port 443
* Identified TLS handshake:

  * Client Hello
  * SNI (Server Name Indication)

✔ Result:

* Encrypted and secure communication

---

### Step 5: Threat Detection

Filter used:

```bash
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

✔ Observed:

* SYN packets without ACK
* TCP retransmissions
* Incomplete connections

✔ Analysis:

* No high-volume traffic spikes
* No scanning patterns

✔ Result:

* Behavior consistent with normal network retries

---

## 🚨 Threat Assessment

| Threat Type           | Status         |
| --------------------- | -------------- |
| SYN Flood Attack      | ❌ Not Detected |
| Port Scanning         | ❌ Not Detected |
| DNS Tunneling         | ❌ Not Detected |
| Malware Communication | ❌ Not Detected |

---

## 📊 Key Findings

* Network traffic is predominantly HTTPS (secure)
* DNS queries are legitimate and expected
* TCP connections are properly established
* Minor retransmissions observed (normal)

---

## 🧠 Analyst Conclusion

The analyzed network traffic does not exhibit any indicators of malicious activity.
All observed patterns align with normal user behavior and standard network operations.

---

## 🚀 Recommendations

* Continue monitoring network traffic
* Use SIEM tools for real-time detection
* Implement alerting for abnormal SYN traffic spikes
* Integrate threat intelligence tools (e.g., VirusTotal)

---

## 📸 Evidence

Refer to screenshots:

* tcp-handshake.png
* dns-analysis.png
* threat-analysis.png

Located in:
`screenshots/`

---

## 👨‍💻 Analyst Note

This project demonstrates practical SOC-level skills including packet analysis, protocol inspection, and basic threat detection using Wireshark.
