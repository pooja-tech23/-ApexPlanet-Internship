OSI Model (7 Layers & Functions)
Definition
The OSI (Open Systems Interconnection) Model is a conceptual framework used to understand how data is transmitted over a network.

 Layers (Top → Bottom)
1.	Application Layer 
	Provides services to users 
	Examples: HTTP, FTP, SMTP 
2.	Presentation Layer 
	Data encryption, compression, formatting 
3.	Session Layer 
	Establishes, manages, terminates sessions 
4.	Transport Layer 
	End-to-end communication 
  Protocols: TCP, UDP 
5.	Network Layer 
	Routing & IP addressing 
  Protocol: IP 
6.	Data Link Layer 
	Frame transmission, MAC addressing 
7.	Physical Layer 
	Transmission of raw bits (cables, signals) 

 Key Point:
 Each layer performs a specific function and communicates with adjacent layers 

 2. TCP/IP Protocol Suite
Definition
A practical model used for real-world internet communication.

 Layers (4 Layers)
1.	Application Layer 
	Combines OSI top 3 layers 
	Protocols: HTTP, DNS, FTP 
2.	Transport Layer 
	Data delivery 
	Protocols: TCP (reliable), UDP (fast) 
3.	Internet Layer 
	Routing and IP addressing 
4.	Network Access Layer 
	Physical transmission (Ethernet, Wi-Fi) 
 TCP vs UDP
•	TCP → Reliable, connection-oriented 
•	UDP → Fast, connectionless 


3. DNS & HTTP/HTTPS

 DNS (Domain Name System)
Definition:
DNS converts domain names into IP addresses
Working:
1.	User enters URL 
2.	DNS query sent 
3.	IP address received 
4.	Connection established 

 HTTP
•	Stands for HyperText Transfer Protocol 
•	Used for web communication 
•	Not secure 

 HTTPS
•	Secure version of HTTP 
•	Uses SSL/TLS encryption 

 Difference
HTTP	HTTPS
Not secure	Secure
No encryption	Encrypted
Port 80	Port 443

4. IP Addressing
 Definition
An IP address is a unique identifier for devices on a network.

 Types
•	IPv4 → 32-bit (e.g., 192.168.1.1) 
•	IPv6 → 128-bit (e.g., 2001:db8::1) 


5. Subnetting
 Definition
Subnetting divides a large network into smaller sub-networks.

 Advantages
•	Improves network performance 
•	Enhances security 
•	Efficient IP usage 

 Example
•	Network: 192.168.1.0/24 
•	Subnet mask: 255.255.255.0  

6. NAT (Network Address Translation)
Definition
NAT converts private IP addresses into public IP addresses

 Types
•	Static NAT 
•	Dynamic NAT 
•	PAT (Port Address Translation) 

 Advantage
•	Saves IP addresses 
•	Provides security


