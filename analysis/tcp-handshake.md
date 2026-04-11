# 🔍 TCP Handshake Analysis

## 📌 Objective

To analyze TCP connection establishment behavior and identify any abnormal patterns such as SYN flood attacks or incomplete handshakes.

---

## 🧪 Filter Used

```
tcp.flags.syn == 1
```

---

## 📊 Observations

* Multiple TCP connection initiations were observed.

* Standard **3-way handshake** pattern identified:

  * Client → Server: SYN
  * Server → Client: SYN, ACK
  * Client → Server: ACK

* Majority of connections were made to **port 443 (HTTPS)**.

* TCP sessions completed successfully without interruption.

---

## 🌐 Example Flow

Client (192.168.x.x) → Server → SYN
Server → Client → SYN, ACK
Client → Server → ACK

---

## 🔐 Additional Observation (TLS Traffic)

* TLSv1.3 handshake detected in the captured traffic.
* Observed **Client Hello** packets containing:

  * Server Name Indication (SNI)
  * Example domain: `assets.msn.com`

### SOC Insight:

* Indicates encrypted HTTPS communication
* Even though payload is encrypted, SNI reveals destination domain
* Useful for threat intelligence and monitoring

---

## 🚨 Threat Analysis

### Checked for:

* SYN flood attack
* Incomplete TCP handshakes
* Abnormal connection spikes

### Result:

* No excessive SYN packets detected
* No half-open connections observed
* No indication of SYN flood attack

---

## 🧠 SOC Analyst Insight

* Traffic reflects normal user activity (web browsing)
* Proper TCP session establishment confirms healthy communication
* No suspicious patterns or anomalies identified

---

## ✅ Conclusion

The TCP traffic analysis shows **normal and legitimate network behavior**, with no evidence of malicious activity or attack patterns.
