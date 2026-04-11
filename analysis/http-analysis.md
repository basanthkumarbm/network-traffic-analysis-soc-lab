# 🌍 HTTP/HTTPS Analysis

## 📌 Objective

To analyze web traffic and identify any unencrypted data transmission or sensitive information exposure.

---

## 🧪 Filter Used

```bash
http
```

---

## 📊 Observations

* No significant HTTP traffic observed in the capture.
* Majority of traffic was over **port 443 (HTTPS)**.

---

## 🔐 Analysis

* Modern web applications use HTTPS for secure communication.
* Traffic is encrypted using TLS, making payload inspection difficult.

---

## 🧠 SOC Analyst Insight

* Absence of HTTP traffic indicates secure browsing practices.
* Encrypted HTTPS traffic protects data confidentiality.
* However, metadata such as:

  * IP addresses
  * TLS handshake (SNI)

  can still be analyzed for investigation.

---

## 📸 Evidence

No HTTP packets observed due to encrypted traffic.

---

## ✅ Conclusion

The network traffic primarily uses HTTPS, ensuring secure communication.
No unencrypted HTTP traffic or sensitive data exposure was detected.
