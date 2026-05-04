1. Symmetric vs Asymmetric Encryption
 Symmetric Encryption
Uses one single key for both encryption & decryption
Fast and efficient

Examples: AES, DES

Working:

Plain Text → Encrypt (Key) → Cipher Text → Decrypt (Same Key) → Plain Text
 Asymmetric Encryption
Uses two keys:
Public Key (encryption)
Private Key (decryption)

Examples: RSA

Working:
Encrypt with Public Key → Decrypt with Private Key
 Difference
Feature	Symmetric	Asymmetric
Keys	One	Two
Speed	Fast	Slower
Security	Less secure key sharing	More secure
Example	AES	RSA 


2. Hashing (MD5, SHA-256)
 Definition

Hashing converts data into a fixed-length hash value

 One-way function (cannot be reversed)

 MD5
Produces 128-bit hash
Faster but not secure (collisions possible)
 SHA-256
Produces 256-bit hash
More secure, widely used
 Example
Input: hello
MD5 → 5d41402abc4b2a76b9719d911017c592
SHA-256 → 2cf24dba5fb0a...

3. Digital Certificates & SSL/TLS
 Digital Certificate
Electronic document used to verify identity
Issued by Certificate Authority (CA)

Contains:

Public key
Owner info
CA signature

 SSL/TLS
Protocols used for secure communication over internet

 Used in HTTPS

 Working (Simplified)
Client connects to server
Server sends certificate
Client verifies certificate
Secure connection established
 Key Point
 SSL is older, TLS is modern and secure
