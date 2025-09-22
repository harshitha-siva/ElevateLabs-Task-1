# ElevateLabs-Task-1
# Network Scanning with Nmap and Wireshark Analysis

## Overview
This repository demonstrates **network reconnaissance** using Nmap's SYN scan technique and **traffic analysis** with Wireshark.  
The example shows scanning of [scanme.nmap.org](https://scanme.nmap.org/), a legitimate test target provided by the Nmap project.

---

## Nmap SYN Scan (`-sS`)

### Command Used
```bash
sudo nmap -sS -T4 scanme.nmap.org -oN results.txt
```

## Parameters Explained

- `-sS`: SYN scan (stealth scan) — sends SYN packets without completing the TCP handshake  
- `-T4`: Aggressive timing template for faster scanning  
- `-oN`: Output results in normal format (`results.txt`)  

### Why SYN Scan?
- **Stealth:** Does not complete TCP connections, making it less detectable  
- **Speed:** Faster than full TCP connect scans  
- **Accuracy:** Reliable for determining open/closed ports  
- **Privileges:** Requires root/administrator privileges  

---

## Wireshark Traffic Analysis

### What Wireshark Shows
The capture demonstrates the SYN scan in action:  

- **SYN Packets:** Initial connection attempts to target ports  
- **Response Analysis:**  
  - SYN-ACK responses → open ports  
  - RST responses → closed ports  
  - No response → filtered ports  
- **HTTP Form Data:** Captured HTTP POST requests with form data (e.g., `uname=hacked`, `pass=hacked`)  

### Key Observations
- **TCP Keep-Alive:** Maintains persistent connections  
- **Form Submission:** Shows web application testing activity  
- **Multiple Connections:** Various TCP streams to different ports and services  

---
## Security Implications

### Legitimate Uses
- **Security Auditing:** Identifying open services on your own networks  
- **Network Troubleshooting:** Diagnosing connectivity issues  
- **Vulnerability Assessment:** Finding potential security gaps  

---

## Tools Used
- **Nmap 7.94SVN:** Network discovery and security auditing  
- **Wireshark:** Network protocol analyzer for traffic inspection  
- **Kali Linux:** Penetration testing distribution (used in terminal)

