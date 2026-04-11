# 📊 Final Network Traffic Analysis Report

## 📌 Objective

To analyze captured network traffic and identify any potential security threats.

---

## 🔍 Summary of Analysis

### TCP Traffic

* Normal TCP 3-way handshake observed
* Majority traffic over port 443 (HTTPS)

### DNS Traffic

* Legitimate domain queries (Google, LinkedIn)
* No suspicious domains detected

### HTTP/HTTPS

* Traffic primarily encrypted (HTTPS)
* TLS handshake observed (Client Hello, SNI)

### Threat Detection

* SYN-only packets observed
* Minor TCP retransmissions
* No abnormal traffic patterns

---

## 🚨 Threat Assessment

| Threat Type       | Status         |
| ----------------- | -------------- |
| SYN Flood Attack  | ❌ Not Detected |
| Port Scanning     | ❌ Not Detected |
| DNS Tunneling     | ❌ Not Detected |
| Data Exfiltration | ❌ Not Detected |

---

## ✅ Final Conclusion

The analyzed network traffic is **benign and consistent with normal user activity**.
No indicators of compromise (IOC) or malicious behavior were identified.

---

## 🧠 Analyst Note

This analysis demonstrates fundamental SOC skills including packet inspection, protocol analysis, and basic threat detection using Wireshark.
