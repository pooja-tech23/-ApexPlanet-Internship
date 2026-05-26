Firewall Configuration using iptables

Linux firewall rules were configured using iptables to control incoming network traffic and improve system security. The firewall was used to allow and deny access to specific ports and demonstrate basic protection against unauthorized scanning activity.

Objective

The objective of this task was to:

Configure simple firewall rules using iptables
Allow access to required services
Block unwanted ports
Demonstrate blocking a port scan attempt
Understand basic firewall security concepts
Tool Used
Linux iptables
Why Firewall Rules Are Important

Firewall rules help in:

Restricting unauthorized access
Protecting network services
Blocking suspicious traffic
Reducing attack surface
Monitoring incoming connections
Viewing Existing Firewall Rules

The following command was used to view current firewall rules:

sudo iptables -L
Observation

The command displayed:

INPUT chain rules
OUTPUT chain rules
Allowed and blocked traffic policies
Allowing Specific Ports
Allow SSH Port 22

The following rule was added to allow SSH access:

sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
Observation

This rule allowed incoming TCP traffic on port 22 for secure remote login access.

Denying Specific Ports
Block HTTP Port 80

The following rule was added to block HTTP traffic:

sudo iptables -A INPUT -p tcp --dport 80 -j DROP
Observation

The firewall denied incoming connections targeting port 80.

Blocking a Port Scan Attempt

Basic scan mitigation was demonstrated using iptables rules to limit excessive SYN requests.

Rule Used
sudo iptables -A INPUT -p tcp --syn -m limit --limit 1/s -j ACCEPT
sudo iptables -A INPUT -p tcp --syn -j DROP
Explanation
Option	Purpose
--syn	Matches SYN packets
-m limit	Limits packet rate
--limit 1/s	Allows only 1 SYN packet per second
DROP	Blocks excessive packets
Port Scan Test

A port scan was performed using Nmap.

Command Used
nmap <target-ip>
Observation

After applying firewall rules:

Some ports appeared filtered
Excessive SYN packets were blocked
Scan responses were reduced

This demonstrated how firewall configurations can limit scanning attempts and reduce exposure of network services.

Saving Firewall Rules

To save firewall rules permanently:

sudo apt install iptables-persistent
sudo netfilter-persistent save
Findings
Firewall rules successfully controlled incoming traffic
SSH access was allowed on port 22
HTTP access on port 80 was blocked
Port scan attempts were partially mitigated using SYN packet filtering
iptables provided basic network protection against unauthorized access
Conclusion

Firewall configuration using iptables provided practical understanding of network access control and basic intrusion prevention techniques. Allowing and denying ports helped manage service accessibility, while SYN filtering demonstrated simple protection against port scanning activity.

Understanding firewall rules and traffic filtering is essential for securing systems and protecting network services from unauthorized access and reconnaissance attempts.
