# 🚨 Threat Detection Analysis

## 📌 Objective

To identify potential malicious activity such as SYN flood attacks, port scanning, or abnormal connection behavior using network traffic analysis.

---

## 🧪 Filter Used

```bash
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

---

## 📊 Observations

* Multiple TCP SYN packets observed without corresponding ACK responses.

* Connections initiated to multiple external IP addresses:

  * `3.253.183.169`
  * `15.216.182.97`
  * `52.215.107.167`

* Some packets marked as:

  * **TCP Retransmissions**

* Certain TCP streams show:

  * **Incomplete connections**

---

## 🔍 Analysis

### ✔ SYN Behavior

* SYN packets indicate connection initiation attempts
* Lack of ACK response suggests:

  * Server did not respond OR
  * Packet loss / delay

---

### ✔ TCP Retransmissions

* Indicates network retry mechanism
* Common in unstable or delayed connections

---

### ✔ Incomplete TCP Streams

* Connections not fully established
* Could indicate:

  * Network issues
  * Dropped packets

---

## 🧠 SOC Analyst Insight

* While SYN-only traffic can indicate **SYN flood attacks or port scanning**, the observed traffic does not show:

  * High volume spikes
  * Rapid port probing patterns
  * Repeated aggressive attempts

* Behavior is consistent with:

  * Normal network retries
  * Temporary connection failures

---

## 📸 Evidence

Screenshot reference:
`screenshots/threat-analysis.png`

The screenshot highlights:

* SYN packets without ACK
* TCP retransmissions
* Incomplete TCP connections

---

## 🚨 Threat Assessment

| Check                  | Result                     |
| ---------------------- | -------------------------- |
| SYN Flood Attack       | ❌ Not Detected             |
| Port Scanning          | ❌ Not Detected             |
| Suspicious IP Behavior | ❌ Not Detected             |
| Network Anomalies      | ⚠️ Minor (Retransmissions) |

---

## ✅ Conclusion

Although SYN-only packets and retransmissions were observed, the traffic does not indicate malicious activity.
The behavior is consistent with normal network conditions such as packet loss or connection retries.

No security threats were identified in the captured traffic.
