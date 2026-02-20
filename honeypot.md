---
layout: default
title: Custom Multi-Service Honeypot (SSH & HTTP)
---

# Custom Multi-Service Honeypot (SSH & HTTP)

## Overview
This project involves the development of a lightweight Python-based honeypot designed to emulate SSH and HTTP services. The objective was to observe adversary interaction patterns and log malicious connection attempts in a controlled lab environment.

The honeypot simulates exposed network services to attract unauthorized access attempts while safely capturing behavioral data for analysis.

---

## Architecture
- Python-based socket server
- Multi-threaded service handling
- SSH service emulation (Port 22)
- HTTP service emulation (Port 80)
- Local log storage for captured data
- Isolated virtual lab environment

---

## Service Emulation Strategy
- Implemented socket-level TCP listeners
- Configured realistic SSH and HTTP protocol banners
- Accepted inbound connections
- Captured and logged:
  - Source IP addresses
  - Timestamps
  - Raw payload data

The system was intentionally designed to remain simple while demonstrating foundational service emulation and adversary interaction logging.

---

## Observations
- Identified connection attempts targeting default SSH service
- Observed automated scanning behavior
- Logged structured attacker interaction data
- Validated multi-threaded stability under concurrent connection attempts

---

## Key Takeaways
- Improved understanding of exposed attack surfaces
- Gained hands-on experience with socket programming
- Learned how service emulation influences adversary behavior
- Strengthened knowledge of basic threat intelligence collection concepts
