# 🌐 Web Application Enumeration & HTTP Traffic Analysis Lab

## 📖 Project Overview

This project demonstrates fundamental web application security assessment techniques against **Acunetix's intentionally vulnerable web application** (`http://testasp.vulnweb.com`), a public training environment designed for cybersecurity education.

The lab focuses on network reconnaissance, web content enumeration, and HTTP traffic analysis using industry-standard security tools. It highlights how credentials transmitted over unencrypted HTTP can be intercepted and analyzed.

---

##  Objectives

* Identify open ports and running services on the target web application.
* Discover publicly accessible directories and files through directory enumeration.
* Capture and inspect HTTP login traffic using Wireshark.
* Demonstrate the security risks associated with transmitting credentials over HTTP.

---

##  Tools Used

* Kali Linux
* Nmap
* Gobuster
* Wireshark
* Mozilla Firefox

---

##  Target Environment

| Target                       | Description                                                    |
| ---------------------------- | -------------------------------------------------------------- |
| `http://testasp.vulnweb.com` | Intentionally vulnerable web application for security training |

---

# Task 1 – Network Reconnaissance

## Objective

The objective was to identify open ports and running services on the target host.

### Commands Used

```bash
ping testasp.vulnweb.com

nmap testasp.vulnweb.com

nmap -sV testasp.vulnweb.com

sudo nmap -A testasp.vulnweb.com
```

### Activities Performed

* Verified target availability.
* Performed a basic TCP port scan.
* Enumerated running services and versions.
* Conducted advanced service detection and host fingerprinting.

### Evidence

```
Evidence/
├── 01-ping-testasp.vulnweb.com.png
├── 02-nmap-basic.png
├── 03-nmap-service-scan.png
└── 04-nmap-advanced-scan.png
```

---

# Task 2 – Directory Enumeration

## Objective

The objective was to identify publicly accessible directories and files exposed by the web server.

### Commands Used

```bash
gobuster dir -u http://testasp.vulnweb.com -w /usr/share/wordlists/dirb/common.txt
```


```bash
gobuster dir -u http://testasp.vulnweb.com -w /usr/share/wordlists/dirb/common.txt -x asp,aspx

```

### Activities Performed

- Enumerated common directories.
- Identified accessible application resources.
- Documented discovered pages and folders.

### Evidence

```
Evidence/
│
├── 05-gobuster-scan.png
└── 06-discovered-directories.png
```

---

# Task 3 – HTTP Traffic Analysis

## Objective

Capture and analyze HTTP login traffic using Wireshark.

### Activities Performed

* Started packet capture on the active network interface.
* Accessed the target web application using Firefox.
* Submitted **test credentials** through the login page.
* Filtered captured traffic using the `http` display filter.
* Located the HTTP POST request.
* Followed the TCP stream to inspect transmitted form data.

### Note

The lab instruction required using my name as the username and password so that the credentials would appear in the captured Wireshark packets. The purpose was to demonstrate how HTTP transmits authentication data in plaintext. Although the login attempt was unsuccessful, Wireshark successfully captured the submitted credentials, highlighting the security risks of sending sensitive information over an unencrypted HTTP connection.


### Wireshark Filter

```text
http
```

### Evidence

```
Evidence/
│
├── 07-wireshark-capture.png
└── 08-http-post-request.png

```

---

# 📂 Project Structure

```
Web-Application-Enumeration-Lab/
│
├── README.md
│
├── Evidence/
│   ├── 01-ping-testasp.vulnweb.com.png
│   ├── 02-nmap-basic.png
│   ├── 03-nmap-service-scan.png
│   ├── 04-nmap-advanced-scan.png
│   ├── 05-gobuster-scan.png
│   ├── 06-discovered-directories.png
│   ├── 07-wireshark-capture.png
│   └── 08-http-post-request.png
│
└── Report/
    └── Web_Application_Enumeration_Report.pdf
```

---


# 🔍 Key Findings

* Successfully identified publicly accessible services running on the target.
* Enumerated exposed web directories using automated content discovery.
* Captured HTTP login traffic using Wireshark.
* Verified that credentials submitted over HTTP are transmitted in plaintext and can be observed in captured network traffic.
* Demonstrated the importance of encrypting authentication traffic with HTTPS.

---

# 📚 Skills Demonstrated

* Network Reconnaissance
* Service Enumeration
* Directory Enumeration
* Web Application Assessment
* Packet Capture and Analysis
* HTTP Protocol Analysis
* Wireshark Traffic Inspection
* Security Documentation
* Technical Reporting

---

# ⚠️ Disclaimer

This project was conducted against **Acunetix's intentionally vulnerable training application**, which is publicly provided for security education and penetration testing practice. All testing was performed within the scope of the authorized training environment.

---

## 👤 Author

**AWE AYODEJI OLUMIDE**

**Role:** IT & Cybersecurity Professional | Comptia Security+ Certified

**Project Type:** Web Application Security Lab
### ShadowFox Task
