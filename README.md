# 🛡️ Nmap Network Reconnaissance & Port Scanning Lab

## 📋 Objective
The purpose of this lab was to conduct active network reconnaissance and infrastructure mapping against a secure target environment to identify active hosts, open ports, operational services, and underlying operating systems while analyzing potential network vulnerabilities.

## 🛠️ Environment & Tools Used
* **Operating System:** Linux Kali / Windows 11 environment
* **Scanner Framework:** Nmap (Network Mapper) v7.9x
* **Target Environment:** Local sandboxed network / Authorized scanning targets

## 🔍 Execution & Methodology

### 1. Active Host Discovery (Ping Sweep)
Conducted a target subnet sweep to identify live hosts on the network infrastructure without triggering deep intrusion alerts.
```bash
nmap -sn 192.168.1.0/24
```
