# HTB-Writeups-scaning
A collection of my technical write-ups, enumeration notes, and exploitation steps for cybersecurity labs and HackTheBox machines.


# Comprehensive Service Enumeration and Exploitation Report: Target 10.129.62.65

This repository contains my professional write-up and methodology for identifying and exploiting vulnerabilities on the target machine `10.129.62.65`.

## Table of Contents
1. [Reconnaissance](#1-reconnaissance)
2. [Deep Service Enumeration](#2-deep-service-enumeration)
3. [FTP Exploitation](#3-ftp-exploitation)
4. [Credential Analysis](#4-credential-analysis)
5. [SMB Enumeration & Flag Retrieval](#5-smb-enumeration--flag-retrieval)
6. [Conclusion](#6-conclusion)

---

## 1. Reconnaissance
**Command:** `nmap 10.129.62.65`
**Description:** Initial network scan to identify the attack surface.
![Nmap Scan](image1.png)

## 2. Deep Service Enumeration
**Command:** `nmap -sV -sC -p- 10.129.62.65`
**Description:** Full port scan and version detection.
![Full Scan](image2.png)

## 3. FTP Exploitation
**Command:** `ftp -p 10.129.62.65`
**Description:** Exploiting anonymous FTP access to retrieve login credentials.
![FTP Access](image3.png)

## 4. Credential Analysis
**Command:** `cat login.txt`
**Description:** Extracting plaintext credentials from the retrieved file.
![Credentials](image4.png)

## 5. SMB Enumeration & Flag Retrieval
**Command:** `smbclient -U bob //10.129.62.65/users`
**Description:** Using credentials to access SMB shares and retrieve the final flag.
![SMB Login](image5.png)
![Flag Retrieval](image6.png)

## 6. Manual Verification
**Command:** `nc -nv 10.129.62.65 21`
**Description:** Final service verification via banner grabbing.
![Netcat](image7.png)

---
**Final Flag:** `dceece590f3284c3866305eb2473d099`

*Documented by: Chamika Prabashwara*
