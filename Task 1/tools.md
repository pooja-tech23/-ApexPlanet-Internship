1. Wireshark (Packet Capture Tool)
 Definition
Wireshark is a network protocol analyzer used to capture and analyze network traffic in real time.

 Features
Captures live packets
Deep packet inspection
Supports many protocols (HTTP, TCP, DNS)

 Uses
Network troubleshooting
Security analysis
Packet filtering

 Basic Steps
Open Wireshark
Select network interface (Wi-Fi/Ethernet)
Click Start Capture
Apply filters

 Common Filters
http
ip.addr == 192.168.1.1
tcp.port == 80 


2. Nmap (Network Scanner)
 Definition
Nmap is used to discover hosts and services on a network.

 Uses
Port scanning
OS detection
Vulnerability scanning

 Basic Commands
nmap 192.168.1.1          # scan single IP
nmap -sS target           # SYN scan
nmap -A target            # aggressive scan
nmap -p 80 target         # scan specific port

3. Burp Suite (Web Proxy Tool)
 Definition
Burp Suite is a tool used for testing web application security.

 Features
Intercepts HTTP/HTTPS traffic
Modify requests/responses
Vulnerability scanning

 Key Components
Proxy
Repeater
Intruder

 Working
Set browser proxy to Burp
Intercept requests
Analyze or modify

4. Netcat (Networking Tool)
 Definition
Netcat is a command-line tool used for reading and writing data over network connections.

 Uses
Debugging network issues
Port listening
File transfer
Backdoor testing

 Basic Commands
🔹 Listen on a port
nc -lvp 1234
🔹 Connect to a port
nc 192.168.1.1 1234
🔹 File Transfer Example

Sender:
nc -lvp 1234 < file.txt

Receiver:
nc sender_ip 1234 > file.txt
