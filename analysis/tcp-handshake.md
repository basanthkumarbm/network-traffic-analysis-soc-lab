# 🔍 TCP Handshake Analysis

## Filter Used

```id="tcp1"
tcp.flags.syn == 1
```

## Observation

* SYN packets initiating connections
* Followed by SYN-ACK and ACK packets

## Example

* Client → SYN
* Server → SYN-ACK
* Client → ACK

## SOC Insight

* Indicates normal connection establishment
* No SYN flood detected

## Conclusion

Traffic is normal.
