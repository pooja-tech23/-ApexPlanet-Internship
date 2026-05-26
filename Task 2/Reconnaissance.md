Reconnaissance
Objective

The objective of this phase was to gather information about the target system using passive and active reconnaissance techniques. Passive reconnaissance was used to collect publicly available information without directly interacting with the target, while active reconnaissance was used to identify live systems and network services.

1. Passive Reconnaissance

Passive reconnaissance was performed using WHOIS and NSLOOKUP to gather domain and DNS-related information.

A. WHOIS Lookup
Aim

To collect domain registration and ownership information of the target domain.

Tool Used
WHOIS
Command Used
whois example.com
Information Gathered

The WHOIS lookup provided:

Domain registration details
Registrar information
Domain creation and expiry dates
Name server details
Administrative and technical information
Observation

WHOIS lookup helps in identifying ownership and infrastructure details related to a domain. It is useful for understanding the background information of a target system.

B. NSLOOKUP
Aim

To retrieve DNS records and resolve domain names into IP addresses.

Tool Used
NSLOOKUP utility
Commands Used
nslookup google.com

Reverse lookup:

nslookup 8.8.8.8
Information Gathered

The NSLOOKUP command provided:

IP address information
DNS server details
Reverse DNS records
Observation

DNS enumeration helps identify network infrastructure and associated systems connected to the target domain.

2. Active Reconnaissance

Active reconnaissance was performed using Nmap to identify live hosts and gather information about running services.

A. Ping Sweep
Aim

To identify active hosts available on the network.

Tool Used
Nmap
Command Used
nmap -sn 192.168.1.0/24
Information Gathered

The ping sweep identified:

Live hosts on the network
Reachable IP addresses
Active systems
Observation

Ping sweep scanning helps discover systems currently connected and responding within the network range.

B. Nmap Scanning
Aim

To identify open ports and services running on the target system.

Tool Used
Nmap
Commands Used

TCP SYN Scan:

sudo nmap -sS 192.168.1.5

Service Version Detection:

sudo nmap -sV 192.168.1.5

OS Detection:

sudo nmap -O 192.168.1.5
Information Gathered

The Nmap scan identified:

Open ports
Running services
Service versions
Operating system details
Observation

Nmap scanning helps identify exposed services and possible entry points within the target system.

Key Findings
WHOIS successfully retrieved domain ownership and registration information.
NSLOOKUP resolved domain names and DNS records.
Nmap ping sweep identified active hosts on the network.
Nmap scans detected open ports and running services on the target machine.
Conclusion

Reconnaissance techniques provided important information about the target system and network. Passive reconnaissance helped gather DNS and domain-related information, while active reconnaissance identified live hosts, open ports, and running services using Nmap.
