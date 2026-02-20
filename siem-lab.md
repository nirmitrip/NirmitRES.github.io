---
layout: default
title: SIEM Deployment & SOC Simulation Lab
---

# SIEM Deployment & SOC Simulation Lab

[← Back to Home](./)

## Overview
This lab was designed to simulate a real-world Security Operations Center (SOC) workflow using Wazuh SIEM. The objective was to deploy centralized log monitoring, execute controlled adversary simulations, and validate detection capabilities through rule-based alerting.

The environment was built to mirror enterprise detection architecture, focusing on log ingestion, rule correlation, and alert severity analysis.

![Wazuh Dashboard Overview](/assets/images/siem-overview.jpeg)

---

## Architecture
The lab environment consisted of:

- **Ubuntu Server** hosting Wazuh Manager, Indexer, and Dashboard  
- **Windows Endpoint (Agent)** configured for log forwarding  
- **Kali Linux Attacker Machine** used for adversary simulation  
- Centralized log ingestion and alert visualization via Wazuh Dashboard  

This setup enabled end-to-end visibility from attack execution to detection analysis.

---

## Attack Simulation
Adversary behavior was simulated using Atomic Red Team techniques targeting process discovery and PowerShell execution behaviors.

Techniques executed included:
- Process enumeration
- PowerShell command execution
- System information discovery
- Remote system discovery

These actions were performed intentionally to trigger predefined Wazuh detection rules and validate rule effectiveness.

![Atomic Red Team Execution](/assets/images/Atomic-RedTeam.jpeg)

---

## Detection & Alerts
Wazuh successfully generated alerts corresponding to the simulated adversary techniques. High-severity alerts (Rule Levels 12–14) were triggered based on suspicious PowerShell activity and process discovery behaviors.

Alert analysis included:
- Reviewing rule IDs and severity levels  
- Correlating timestamps with attack execution  
- Analyzing rule descriptions for detection logic validation  
- Verifying agent reporting and event indexing  

The dashboard confirmed proper ingestion, indexing, and visualization of security events.

![PowerShell Detection Alert - Rule Level 14](/assets/images/siem-events.jpeg)

---

## Key Takeaways
- Gained hands-on experience deploying and configuring a SIEM platform  
- Validated detection workflows through controlled adversary simulation  
- Improved understanding of alert severity classification and rule logic  
- Developed practical SOC-style investigation methodology  
- Strengthened knowledge of log-based threat detection in enterprise environments
