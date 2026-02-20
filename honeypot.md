---
layout: default
title: Custom Multi-Service Honeypot (SSH & HTTP)
---

# Custom Multi-Service Honeypot (SSH & HTTP)

[← Back to Home](./)

## Overview
This project involved designing and implementing a lightweight multi-service honeypot to emulate exposed SSH and HTTP services. The objective was to observe adversary interaction patterns, log connection attempts, and analyze behavioral characteristics of unsolicited inbound traffic within a controlled lab environment.

The honeypot was developed from scratch using Python to better understand service emulation, socket-level communication, concurrent connection handling, and attacker reconnaissance behavior.

---

## Architecture
The honeypot environment consisted of:

- Python-based TCP socket listeners  
- Multi-threaded handling for concurrent connections  
- SSH service emulation on Port 22  
- HTTP service emulation on Port 80  
- Structured local logging mechanism  
- Execution within isolated virtual lab environment  

This setup enabled safe observation of inbound traffic without exposing production systems.

---

## Service Emulation & Logging
The honeypot was engineered to mimic legitimate service banners in order to increase interaction likelihood:

- SSH banner emulating OpenSSH version string  
- HTTP response simulating Apache server header  
- Timestamped logging of:
  - Source IP addresses  
  - Connection attempts  
  - Captured payload data  

Below is a simplified implementation snippet used for structured logging:

```python
def log_event(filename, ip, data):
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    with open(filename, "a") as f:
        f.write(f"{timestamp} | {ip} | {data}\n")
```

This function ensures consistent formatting and simplifies later behavioral analysis.

---

## Example Log Output

```
2026-02-18 14:23:11 | 192.168.1.45 | SSH-2.0-OpenSSH_8.2p1
2026-02-18 14:23:15 | 192.168.1.45 | root login attempt
2026-02-18 14:24:02 | 10.0.2.7 | GET / HTTP/1.1
2026-02-18 14:24:05 | 10.0.2.7 | User-Agent: curl/7.81.0
```

---

## Observations

During controlled lab testing, the honeypot captured multiple connection attempts consistent with automated reconnaissance behavior. Observed patterns included:

- Repeated probing of default SSH port (22)  
- Automated HTTP requests targeting root directories  
- Identical payload structures across multiple connection attempts  
- User-Agent strings indicative of scripted tools (e.g., curl, automated scanners)  
- Rapid sequential connection attempts from the same source IP  

These findings demonstrate how exposed services are continuously scanned and probed, even in isolated environments. The experiment reinforced the importance of monitoring public-facing services and analyzing inbound connection behavior for early threat intelligence indicators.
