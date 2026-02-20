---
layout: default
title: Endpoint Telemetry & Behavioral Monitoring Tool
---

# Endpoint Telemetry & Behavioral Monitoring Tool

[← Back to Home](./)

## Overview
This project focused on developing a host-level monitoring utility to study system input capture and behavioral logging within an isolated virtual machine environment.

The objective was to better understand endpoint visibility mechanisms, structured logging practices, and how host-level activity may be monitored for security analysis.

---

## Architecture
The monitoring tool consisted of:

- Python-based system event listener  
- Keyboard input capture mechanism  
- Structured log file output  
- Execution in isolated Windows test environment  

The tool was designed strictly for controlled experimentation and research within a sandboxed lab setup.

---

## Monitoring Implementation
The tool utilized a system-level event listener library to capture input events and normalize data into structured log entries.

Key implementation details:

- Filtering of special key inputs  
- Normalization of captured keystrokes  
- Append-based structured log writing  
- Controlled execution within virtual test environment  

This allowed study of how host-level activity can be logged and analyzed.

![Endpoint Monitoring Output](assets/images/endpoint-log.png)

---

## Observations
Through controlled testing, the project provided insight into:

- How input-level telemetry can be captured  
- How behavioral logging mechanisms operate  
- The visibility of endpoint-level activity within monitoring systems  
- Differences between raw event capture and structured logging  

---

## Key Takeaways
- Strengthened understanding of endpoint telemetry concepts  
- Explored host-level behavioral monitoring mechanisms  
- Gained practical experience in structured logging design  
- Improved knowledge of endpoint visibility in security contexts  
- Developed awareness of defensive monitoring implications
