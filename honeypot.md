---
layout: default
title: Custom Multi-Service Honeypot (SSH & HTTP)
---

# Custom Multi-Service Honeypot (SSH & HTTP)

[← Back to Home](./)

## Overview
This project involved designing and implementing a lightweight multi-service honeypot to emulate exposed SSH and HTTP services. The objective was to observe adversary interaction patterns, log connection attempts, and analyze behavioral characteristics of unsolicited inbound traffic within a controlled lab environment.

The honeypot was intentionally developed from scratch using Python to better understand service emulation, socket-level communication, and attacker reconnaissance behavior.

---

## Architecture
The honeypot environment consisted of:

- Python-based TCP socket listeners  
- Multi-threaded handling for concurrent connections  
- SSH service emulation on Port 22  
- HTTP service emulation on Port 80  
- Structured local logging mechanism  
- Execution within isolated virtual lab environment  

This setup allowed safe observation of inbound traffic without exposing production systems.

---

## Service Emulation & Logging
The honeypot was engineered to mimic legitimate service banners to increase interaction likelihood:

- SSH banner emulating OpenSSH version string  
- HTTP response simulating Apache server header  
- Timestamped logging of:
  - Source IP addresses  
  - Connection attempts  
  - Raw payload data  

Multi-threading ensured the honeypot could handle multiple simultaneous inbound requests without blocking execution.

![Honeypot Log Output](assets/images/honeypot-log.png)

---

## Observations
During testing, the honeypot captured:

- Automated scanning attempts targeting default SSH ports  
- Repeated connection attempts from the same IP ranges  
- Suspicious payload data consistent with reconnaissance behavior  

These observations reinforced the importance of monitoring exposed services and understanding adversary probing techniques.

---

## Key Takeaways
- Gained hands-on experience with socket-level network programming  
- Developed understanding of service fingerprinting and banner emulation  
- Learned how attackers interact with exposed services  
- Strengthened practical knowledge of threat intelligence data collection  
- Improved understanding of network-layer attack surface exposure
