---
layout: default
title: Endpoint Telemetry & Behavioral Monitoring Tool
---

# Endpoint Telemetry & Behavioral Monitoring Tool

[← Back to Home](./)

## Overview
This project focused on developing a host-level telemetry utility to study system input capture and structured behavioral logging within an isolated virtual machine environment.

The objective was to understand endpoint visibility mechanisms, event normalization techniques, and how host-level activity may be captured and analyzed during controlled security research.

---

## Architecture
The monitoring tool consisted of:

- Python-based system event listener  
- Keyboard input capture mechanism  
- Event normalization layer  
- Timestamped structured log output  
- Execution within isolated Windows test environment  

The tool was developed strictly for controlled experimentation within a sandboxed lab setup.

---

## Implementation Approach
The utility utilizes a system-level event listener to capture input events, normalize special keys, and write timestamped entries into a structured log file.

Below is a simplified implementation snippet:

```python
import datetime

def on_press(key):
    normalized = normalize_key(key)
    if normalized:
        log_event(normalized)

def log_event(formatted_key):
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    with open("endpoint_telemetry.log", "a") as f:
        f.write(f"{timestamp} | {formatted_key}\n")
```
---

This structure ensures consistent formatting and enables easier behavioral analysis during lab testing.

Example Telemetry Output
2026-02-18 15:02:11 | h
2026-02-18 15:02:12 | e
2026-02-18 15:02:13 | l
2026-02-18 15:02:14 | l
2026-02-18 15:02:15 | o
2026-02-18 15:02:16 | [ENTER]
2026-02-18 15:02:18 | [BACKSPACE]
2026-02-18 15:02:20 | s
2026-02-18 15:02:21 | e
2026-02-18 15:02:22 | c

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
