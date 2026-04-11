# 🌐 DNS Traffic Analysis

## 📌 Objective

To analyze DNS queries and responses in order to identify domain resolution behavior and detect any suspicious or malicious activity.

---

## 🧪 Filter Used

```bash
dns
```

---

## 📊 Observations

* Multiple DNS queries and responses were observed between the client and DNS server.

* Queries include both IPv4 and IPv6 resolutions:

  * **A records** (IPv4)
  * **AAAA records** (IPv6)

* Example domains observed:

  * `accounts.google.com`
  * `linkedin.com`

---

## 🔍 DNS Resolution Behavior

### ✔ A Record (IPv4)

* Example:

  * `accounts.google.com → 192.178.211.84`

### ✔ AAAA Record (IPv6)

* IPv6 addresses observed for modern services

### ✔ CNAME Resolution

* Observed chained resolution:

  * `linkedin.com → cctld.linkedin.com`

👉 Indicates use of CDN (Content Delivery Network)

---

## 🔐 Advanced Observation (HTTPS DNS Query)

* Observed DNS query type:

```text
Type: HTTPS
```

### SOC Insight:

* Indicates modern secure service discovery
* Used in HTTP/3 and encrypted communication
* Shows real-world modern network behavior

---

## 🧠 SOC Analyst Insight

* DNS queries are consistent with normal user browsing activity

* No suspicious/random domains detected

* No signs of:

  * DNS tunneling
  * Domain generation algorithms (DGA)
  * Malware beaconing

* Presence of well-known domains (Google, LinkedIn) indicates legitimate traffic

---

## 📸 Evidence

Screenshot reference:
`screenshots/dns-analysis.png`

The screenshot shows:

* Standard DNS queries and responses
* Domain resolution process
* Record types (A, AAAA, CNAME)

---

## 🚨 Threat Analysis

### Checked for:

* High frequency DNS requests
* Random/unusual domains
* Suspicious external communication

### Result:

* No abnormal DNS behavior detected
* Traffic appears clean and legitimate

---

## ✅ Conclusion

The DNS traffic analysis confirms normal domain resolution behavior with no indicators of compromise.
All observed domains and query patterns align with standard user activity.
