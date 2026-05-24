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
### 2. Comprehensive Port & Service Enumeration
Executed a detailed TCP SYN Stealth Scan (`-sS`) against discovered targets to identify top open communication ports and aggressive service version fingerprints (`-sV`).
```bash
nmap -sS -sV -O 192.168.1.50
### 3. Vulnerability Script Scanning
Utilized the built-in Nmap Scripting Engine (NSE) vulnerability scanning scripts (`--script vuln`) to cross-reference exposed network ports against known CVE vulnerabilities.
```bash
nmap --script vuln 192.168.1.50
```
## 📈 Key Discovery & Security Findings
* **Port 22/TCP (SSH):** Open. Detected OpenSSH version 8.2p1. Recommended implementation of public-key-only authentication to prevent brute-force exposures.
* **Port 80/TCP (HTTP):** Open. Detected legacy web server framework. Flagged for lack of SSL/TLS encryption (HTTP vs HTTPS configuration).
* **Port 443/TCP (HTTPS):** Open. Verified functional TLS certificate chain.

## 🛡️ Remediation Protocols
1. Close all unneeded or non-essential communication ports at the hardware firewall level.
2. Enforce explicit patch schedules for identified web server frameworks to eliminate public CVE exploits.
3. Migrate all plain-text communication protocols to securely encrypted alternatives (e.g., forcing HTTPS over HTTP).
