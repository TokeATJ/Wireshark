# Wireshark

# 🌐 TCP/IP Protocol Analysis and Network Traffic Inspection

## 📖 Overview

## The IP andresses have been sanitized

This project demonstrates foundational network security concepts through hands-on analysis of TCP/IP communications, HTTP methods, packet captures, and encrypted communications using Kali Linux, Wireshark, Netcat, and OpenSSL. 

The objective was to understand how network communications occur, inspect protocol behavior, identify web server configurations, and analyze captured network traffic for investigative purposes.

---

## 🛠️ Tools Used

- Kali Linux
- Wireshark
- Netcat (nc)
- OpenSSL
- TCP/IP
- HTTP Protocol
- DNS

---

## 🎯 Skills Demonstrated

- Packet Analysis
- Protocol Inspection
- HTTP Method Enumeration
- TCP Three-Way Handshake Analysis
- DNS Analysis
- SSL/TLS Inspection
- Traffic Forensics
- Network Reconnaissance
- Security Assessment

---

# Part I: HTTP Protocol Analysis

## Objective

Investigate HTTP communications and analyze client-server interactions using Wireshark packet captures.

---

## HTTP Methods Examined

| Method | Purpose |
|----------|----------|
| HEAD | Retrieve headers without content |
| GET | Retrieve resources |
| OPTIONS | Discover supported methods |
| POST | Submit data |
| PUT | Update resources |
| DELETE | Remove resources |

### Security Relevance

HTTP methods can reveal application functionality and potential attack surfaces. During penetration testing, unsupported or insecure methods may indicate misconfigurations.

---

## Capturing HTTP Traffic

Network traffic was captured using Wireshark while manually interacting with web servers through Netcat.

### Connect to Google

```bash
nc www.example.edu 80
```
<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/4ff519d2-8f93-45a7-9d3c-4bb52ea319ff" />


### Send HEAD Request

```http
HEAD / HTTP/1.1
```

### Evidence

<img width="1537" height="1023" alt="image" src="https://github.com/user-attachments/assets/5a7a9f55-c395-43d4-b094-b03ed539df19" />


---

## TCP Three-Way Handshake Analysis

The packet capture demonstrated the establishment of a TCP connection through the standard three-way handshake process.

### Packet Sequence

1. SYN
2. SYN-ACK
3. ACK

### Security Relevance


Understanding the TCP handshake is essential for:

- Network troubleshooting
- Intrusion detection
- Packet analysis
- Penetration testing

### Evidence

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/9fb63574-60d7-4486-9ace-b82c31e9cc71" />

- The first three packet start with SYN message being sent from the client to the server. Once the initial SYN message is received it sends back the ACK/SYN message to the client to communicate it has acknowledged the original packet. Once they are received by the client, another ACK packet is sent to the server. This characterizes the three way handshake to create a connection. 
---

## Web Server Fingerprinting

A HEAD request was submitted to identify the underlying web server software.

### Target

www.example-target.com

### Result

```text
Apache/ (CentOS)
```

### Security Relevance

Web server fingerprinting helps identify:

- Software versions
- Potential vulnerabilities
- Patch management concerns
- Attack surface information

### Evidence

<img width="1392" height="1130" alt="image" src="https://github.com/user-attachments/assets/03342b50-f9fe-4a76-be6e-47593ffe7dca" />

---

## HTTP OPTIONS Enumeration

The OPTIONS method was used to determine supported HTTP methods on the target web server.

### Request

```http
OPTIONS / HTTP/1.1
Host: www.example-target.com
```

### Security Relevance

OPTIONS responses can expose functionality available on the server and reveal methods that may increase risk.

### Evidence

<img width="1825" height="862" alt="image" src="https://github.com/user-attachments/assets/e004069d-054c-44a4-9f58-485d13964e2b" />

---

## SSL/TLS Certificate Analysis

Encrypted communications were analyzed using OpenSSL.

### Command

```bash
openssl s_client -connect example-target.edu:443
```

### Findings

Certificate details and public key length were reviewed to assess encryption strength.

### Security Relevance

Certificate analysis helps determine:

- Encryption strength
- Key length
- Certificate validity
- Compliance readiness

### Evidence

<img width="1840" height="854" alt="image" src="https://github.com/user-attachments/assets/6717a642-33d0-4880-b746-787d8cb5f892" />

<img width="1403" height="1121" alt="image" src="https://github.com/user-attachments/assets/e143f5aa-1697-43c5-9b8b-8230fcf80f2e" />

- The HTTP OPTIONS method is important because it reveals which HTTP methods a web server supports. During penetration testing, this information helps identify the server's attack surface and can expose potentially dangerous methods such as PUT, DELETE, or TRACE that may be misconfigured. The length of the public key is important because it directly impacts the strength of the encryption used to protect communications. Larger key sizes generally require more computational effort to break, making encrypted communications more resistant to attacks. Reviewing key length helps determine whether a system meets current security best practices and compliance requirements.
---

# Part II: Network Capture Investigation

## Objective

Analyze a provided packet capture file and identify evidence related to network activity.

---

## Activities Performed

- Credential Analysis
- DNS Resolution Review
- Browser Identification
- Port Status Verification
- Domain Enumeration
- Host Identification
-

---

## Investigation Findings

| Investigation Item | Result |
|--------------------|---------|
| DNS Resolution | Identified target host mappings |
| Browser Analysis | Determined user-agent information |
| Port Verification | Confirmed service availability |
| Network Attribution | Mapped MAC addresses to hosts |
| Authentication Analysis | Reviewed credential transmission |
| Traffic Reconstruction | Reconstructed user activity |

---

## Security Relevance

Packet analysis enables security professionals to:

- Investigate incidents
- Trace attacker activity
- Recover cleartext credentials
- Validate network configurations
- Identify suspicious communications

### Evidence

![Packet Capture Analysis](screenshots/network-capture-analysis.png)

---

# 📚 Key Takeaways

- Captured and analyzed HTTP traffic
- Investigated TCP connection establishment
- Identified web server technologies
- Enumerated supported HTTP methods
- Performed SSL/TLS certificate inspection
- Conducted packet capture analysis using Wireshark
- Reconstructed network activity from packet captures

---

# 💡 Skills Gained

- Kali Linux
- Wireshark
- Netcat
- OpenSSL
- HTTP Analysis
- DNS Analysis
- TCP/IP Fundamentals
- Packet Inspection
- Network Forensics
- Security Assessment

---

# 🎓 Resume Alignment

> Performed TCP/IP protocol analysis, HTTP method enumeration, SSL/TLS inspection, and packet capture investigations using Kali Linux, Wireshark, Netcat, and OpenSSL to assess network communications and identify security-relevant information.
