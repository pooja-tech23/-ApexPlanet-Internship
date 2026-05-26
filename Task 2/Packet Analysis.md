Packet Analysis with Wireshark

Wireshark is a powerful network packet analyzer used to capture, inspect, and analyze network traffic in real time. It enables security analysts and network administrators to monitor packet-level communication and identify network activities, suspicious traffic, and protocol behavior.

Packet analysis plays an important role in cybersecurity, network monitoring, troubleshooting, and forensic investigations.

Why Packet Analysis Is Important
Detects unencrypted credentials transmitted over insecure protocols
Identifies suspicious or malicious network activity
Helps analyze network attacks and abnormal traffic patterns
Assists in troubleshooting connectivity issues
Supports digital forensic investigations
Traffic Types Analyzed

The following network protocols were analyzed during packet capture:

ICMP
HTTP
FTP
DNS
TCP Handshake

Each protocol provides specific information related to communication between systems on a network.

Capture Process

The packet capture process was performed using the following steps:

Select the active network interface
Start packet capture in Wireshark
Generate network traffic
Stop packet capture
Analyze captured packets using filters

This process allows accurate inspection and monitoring of network communication.

HTTP Traffic Analysis

HTTP traffic was captured to analyze web communication between client and server systems.

Filter Used
http
Observation

The capture displayed:

HTTP GET requests
HTTP responses
Status codes
Host information
Request headers

HTTP analysis helps understand web communication and identify insecure web traffic.

DNS Traffic Analysis

DNS packets were analyzed to observe domain name resolution requests and responses.

Filter Used
dns
Commands Used
ping google.com

OR

nslookup google.com
Observation

The DNS capture displayed:

DNS query packets
Resolved IP addresses
DNS response records

DNS analysis helps monitor domain resolution activity within a network.

FTP Traffic Analysis

FTP traffic was captured to analyze insecure file transfer communication.

Filter Used
ftp
FTP Login Command
ftp <target-ip>
Observation

The capture revealed:

FTP username packets
FTP password packets
FTP server responses

The analysis showed that FTP transmits credentials in plaintext, making it an insecure protocol for sensitive communication.

Filtering FTP Credentials

The following Wireshark filters were used to identify FTP login credentials.

Username Filter
ftp.request.command == "USER"
Password Filter
ftp.request.command == "PASS"
Observation

Using these filters, FTP usernames and passwords were visible directly inside packet contents because the protocol does not encrypt authentication data.

TCP Handshake Analysis

TCP handshake packets were analyzed to observe connection establishment between systems.

Filter Used
tcp.flags.syn == 1
Observation

The analysis displayed:

SYN packets
SYN-ACK responses
ACK packets

This demonstrated the standard TCP three-way handshake process used to establish reliable communication.

SYN Flood Attack Simulation

A SYN flood attack was simulated in a controlled lab environment using hping3.

Command Used
sudo hping3 -S --flood -p 80 <target-ip>
Attack Analysis Filter
tcp.flags.syn == 1 && tcp.flags.ack == 0
Observation

During the simulation:

A large number of SYN packets were generated
Continuous connection requests targeted port 80
Wireshark displayed abnormal traffic volume

This demonstrated how SYN flood attacks can overwhelm a target system and potentially lead to denial-of-service conditions.

Example Commands
Capture ICMP Packets
tcpdump -i eth0 icmp

Captures ICMP packets such as ping requests and replies.

Capture DNS Traffic
tshark -i eth0 -f "port 53"

Captures DNS traffic on the network interface.

Filter HTTP Requests from PCAP File
tshark -r traffic.pcap -Y "http.request"

Displays HTTP requests from a saved packet capture file.

Common Wireshark Filters
icmp
http
dns
ftp

Filters help isolate specific protocols and simplify packet analysis.

Findings
HTTP packets revealed web request and response communication
DNS analysis displayed domain resolution activity
FTP traffic exposed plaintext credentials
TCP handshake packets demonstrated connection establishment
SYN flood traffic showed abnormal packet generation patterns

Packet analysis provided deep visibility into network behavior and protocol communication.

Conclusion

Packet analysis using Wireshark provided practical understanding of network communication, protocol behavior, and security risks associated with insecure protocols such as FTP. The analysis also demonstrated how abnormal traffic patterns generated during network attacks can be identified and investigated using packet inspection techniques.

Understanding packet-level communication is an essential skill in cybersecurity, network analysis, and digital forensics.
