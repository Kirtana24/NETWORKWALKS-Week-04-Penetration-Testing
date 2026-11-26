# NETWORKWALKS – WEEK 04
## Cybersecurity & Ethical Hacking Internship

---

## Internship Details

| Field | Details |
|---|---|
| **Name** | Kirtana Minoy |
| **Internship** | Cybersecurity & Ethical Hacking |
| **Organization** | Networkwalks |
| **Program/Batch** | B084D-Networkwalks |
| **Domain** | Cybersecurity |
| **Week** | 04 |
| **Modules** | M1, M2, M3 |

---

## 1. Introduction

Week 04 of the Networkwalks Cybersecurity & Ethical Hacking Internship focused on practical security assessment activities involving initial reconnaissance, PDF security analysis, and identifying potential information exposure.

The exercises were performed using Kali Linux in a controlled training environment. Various command-line utilities were used to gather technical information, examine document security, and investigate publicly disclosed web directories.

**Target Website:** `https://medirozahospital.com`

---

## 2. Objectives

- Perform initial reconnaissance and information gathering.
- Identify domain and DNS-related information.
- Examine PDF password protection and security.
- Understand PDF hash extraction and metadata analysis.
- Investigate publicly disclosed directories.
- Identify potential risks associated with exposed backup files.
- Document observations and recommend appropriate security measures.

---

## 3. Tools and Technologies Used

| Tool | Purpose |
|---|---|
| Kali Linux | Penetration testing environment |
| WHOIS | Domain registration information |
| cURL | HTTP requests and response analysis |
| Nslookup | Domain name resolution |
| Dig | DNS record investigation |
| Hash Calculator | Password auditing |
| QPDF | PDF decryption and processing |
| ExifTool | Document metadata examination |

---

# 4. Practical Implementation

## M1 – Initial Access and Reconnaissance
Target Website :
<img width="1897" height="865" alt="image" src="https://github.com/user-attachments/assets/fe44ef04-a41b-4a7c-9eca-22d3ddaf62f2" />

### 4.1 Objective

The objective of this module was to perform initial reconnaissance against the designated target website and gather publicly available technical information.

### 4.2 Environment Setup

The practical environment was prepared using Kali Linux running inside Oracle VirtualBox.

The system configuration, network connectivity, installed utilities, and Python version were checked before beginning the reconnaissance activities.

**Screenshot 1: Initial Environment Setup**

<img width="912" height="706" alt="image" src="https://github.com/user-attachments/assets/f6c90d7e-f8b4-4724-9680-d002530edac0" />
<img width="692" height="330" alt="image" src="https://github.com/user-attachments/assets/9fe80a9c-25d2-4352-a3d7-0090646a9f4b" />

### 4.3 Domain Information Gathering – WHOIS

The WHOIS utility was used to retrieve publicly available domain registration information, including registrar details, registration dates, and name servers.

**Command:**
`whois medirozahospital.com`

**Screenshot 2: WHOIS Lookup**

<img width="537" height="182" alt="image" src="https://github.com/user-attachments/assets/5251a561-530b-4bab-8e41-a9ddcd5aa009" />
<img width="922" height="765" alt="image" src="https://github.com/user-attachments/assets/59394888-309b-49e1-b4c1-dd54ad6a3c64" />


### 4.4 DNS Enumeration

DNS enumeration was performed using Nslookup and Dig to identify the domain's IP address and associated DNS records.

The following records were examined:

- A record
- NS record
- MX record
- TXT record

**Screenshot 3: Nslookup Results**

<img width="321" height="151" alt="image" src="https://github.com/user-attachments/assets/55e802d6-6401-4184-934f-48824b89f7ef" />

**Screenshot 4: DNS A Record**

<img width="600" height="332" alt="image" src="https://github.com/user-attachments/assets/ea91bc18-30eb-4355-803d-b9bff822e3e5" />

**Screenshot 5: DNS NS Record**

<img width="636" height="377" alt="05_DNS_NS_Records" src="https://github.com/user-attachments/assets/e54ec6cf-2d7d-4e75-b3bb-2571f5bbaca7" />

**Screenshot 6: DNS MX Record**

<img width="686" height="397" alt="image" src="https://github.com/user-attachments/assets/6a807d90-6c92-4575-9914-e06ed40f8d79" />

**Screenshot 7: DNS TXT Record**

<img width="937" height="380" alt="image" src="https://github.com/user-attachments/assets/cae24a93-2f30-4789-876d-ae6e0d701bd3" />

### 4.5 HTTP Header Analysis

cURL was used to examine the HTTP response headers returned by the target website.

This helped identify server information, response status, and other publicly available HTTP header details.

**Screenshot 8: HTTP Header Analysis**

<img width="427" height="181" alt="image" src="https://github.com/user-attachments/assets/802ecc32-1418-489b-8133-7b16fa624994" />

### 4.6 Website Technology Identification

WhatWeb was used to identify technologies and components associated with the target website.

This provided an overview of the publicly detectable web technologies.

**Screenshot 9: WhatWeb Scan**

<img width="937" height="97" alt="image" src="https://github.com/user-attachments/assets/f60672c7-6292-480b-902f-05e25425eaf5" />

### 4.7 M1 Observations

The reconnaissance activities provided an overview of the target domain, DNS configuration, HTTP response information, and website technologies.

These observations established a foundation for the subsequent security assessment activities.

---

## M2 – PDF Security Analysis and Data Extraction

### 4.8 Objective

The objective of this module was to understand PDF password protection, perform password auditing on the provided training documents, and examine document metadata.

### 4.9 Hash Extraction

PDF password hashes were extracted for use in the password auditing process.

The extracted hash represents the information required by compatible auditing tools to test password candidates. It is not the original password itself.

**Screenshot 1: PDF Hash Extraction**

<img width="1896" height="867" alt="image" src="https://github.com/user-attachments/assets/9a32079c-c928-4bfd-a71e-b8867d128b43" />
<img width="1901" height="870" alt="image" src="https://github.com/user-attachments/assets/109951e1-8bea-4032-b873-62564c3f0ed2" />

**Screenshot 2: Password Audit :**
patient record 1 password cracked

<img width="1896" height="862" alt="image" src="https://github.com/user-attachments/assets/ce5baf43-13c2-4eda-a8f2-c86c3725ef4f" />

patient record 2 password cracked

<img width="905" height="557" alt="image" src="https://github.com/user-attachments/assets/3b979be8-bdc9-43de-888e-85caa6054b78" />

patient record 3 password cracked

<img width="985" height="472" alt="image" src="https://github.com/user-attachments/assets/ecb66706-12c9-4b72-ac42-24fd08d33a85" />

### 4.10 PDF Decryption Using QPDF

After completing the authorized password audit, QPDF was used to decrypt the designated training PDF document.

The decrypted output was saved separately for further examination.

**Screenshot 4: PDF Decryption Using QPDF**

<img width="937" height="727" alt="image" src="https://github.com/user-attachments/assets/44f023ce-2d0a-4778-acd5-ca667198b3b4" />

### 4.11 PDF Metadata Examination

ExifTool was used to examine the metadata of the PDF document.

Metadata analysis helps identify document properties and potentially sensitive information embedded within files.

**Screenshot 5: PDF Metadata Analysis

<img width="907" height="370" alt="image" src="https://github.com/user-attachments/assets/f8e5a24a-386c-4386-a596-512582747f3f" />

### 4.12 M2 Observations

This module demonstrated how password-protected documents can be assessed using password auditing utilities. It also highlighted the importance of strong passwords and careful management of document metadata.

---

## M3 – Critical Data Exposure

### 4.13 Objective

The objective of this module was to investigate potential information disclosure through publicly accessible website resources and identify the security implications of exposed directories and backup files.

### 4.14 Robots.txt Analysis

The website's `robots.txt` file was examined using cURL.

The file contained directory paths that search engine crawlers were instructed not to access.

The following paths were identified:

- `/patient/`
- `/staff/`
- `/old/`

The presence of these entries indicates disclosed directory names but does not independently confirm that the directories are publicly accessible.

**Screenshot 1: Robots.txt Analysis**

<img width="696" height="375" alt="image" src="https://github.com/user-attachments/assets/fc78d362-4beb-43fd-a7f1-0bf664e5d641" />

### 4.15 Directory Listing Assessment

The `/old/` directory was investigated to determine whether the web server exposed its directory contents.

Directory listing can reveal filenames and resources that should not be publicly accessible.

**Screenshot 2: Old Directory Listing**

<img width="1897" height="297" alt="image" src="https://github.com/user-attachments/assets/5b3bb7a0-3af4-44c8-9a81-aaa3f53ecaeb" />

**Screenshot 3: Exposed Directory Listing**

<img width="1897" height="622" alt="image" src="https://github.com/user-attachments/assets/d2c8987c-183f-4651-a444-fdd3e0ae3604" />

### 4.16 Database Backup Exposure

A database backup resource was identified during the directory exposure assessment.

Public exposure of database backups can create significant security risks because such files may contain confidential organizational information, account details, or other sensitive records.

The assessment focused on documenting the exposure without downloading or disclosing confidential records.

**Screenshot 3: Database Backup
<img width="1882" height="552" alt="image" src="https://github.com/user-attachments/assets/0125ab55-e747-470f-875e-9718b921fc73" />
<img width="1881" height="750" alt="image" src="https://github.com/user-attachments/assets/9d5f074b-deaa-4773-abca-174a06115f2a" />
<img width="1882" height="337" alt="image" src="https://github.com/user-attachments/assets/d9aaf9d3-c526-4d0a-ad16-b520f4d9f465" />

5. Key Learning Outcomes

Understood the initial reconnaissance process.

Practiced PDF password security assessment.

Learned to examine PDF metadata.

Identified how publicly disclosed directory paths can reveal potential exposure.

Understood the security risks associated with publicly accessible backup files.

Improved technical documentation and vulnerability reporting skills.

6. Conclusion

Week 04 provided practical exposure to reconnaissance, document security assessment, information disclosure analysis, and penetration testing documentation. These exercises strengthened my understanding of identifying potential security weaknesses and communicating findings responsibly.
