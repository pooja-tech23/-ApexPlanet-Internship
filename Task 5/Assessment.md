# Vulnerability Assessment of Test Network

## Overview
This project was completed as part of the Cybersecurity & Ethical Hacking Internship.

The objective was to perform a vulnerability assessment on a controlled lab environment using Kali Linux and Metasploitable2.

## Tools Used
- Kali Linux
- Metasploitable2
- Nmap
- Nikto

## Network Setup

Kali Linux (192.168.56.101)
|
| Host-Only Network
|
Metasploitable2 (192.168.56.102)

## Methodology

1. Network Discovery
2. Port Scanning
3. Service Enumeration
4. Vulnerability Assessment
5. Risk Analysis
6. Mitigation Recommendations

## Commands Used

### Ping Test
ping -c 4 192.168.56.102

### Basic Port Scan
sudo nmap -Pn -n 192.168.56.102 

### Service Enumeration
sudo nmap -Pn -n -sV 192.168.56.102

### Vulnerability Scan 
sudo nmap -Pn -n --script vuln 192.168.56.102

 ### Web Assessment
 nikto -h http://192.168.56.102 

### Key Findings
VSFTPD 2.3.4 Backdoor (Critical)
Java RMI Remote Code Execution (Critical)
Telnet Service Enabled (Critical)
SMB Exposure (High)
Weak SSL/TLS Configuration (High)
HTTP TRACE Enabled (Medium)

### Recommendations
Disable Telnet
Upgrade vulnerable services
Restrict SMB access
Remove unnecessary services
Apply security patches regularly 


Author
Pooja Yadav
Cybersecurity & Ethical Hacking Intern
