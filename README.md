# Secure File Sharing and Management System

## 1. Project Description

The project is a **Secure File Sharing and Management System Application** that ensures all data interactions comply with regulations while maintaining an audit trail for accountability. 

This system is designed for healthcare organizations and other industries that require secure handling of sensitive files.

Key highlights:
- Part of a suite of interworking applications that manage data securely with minimal dependencies.
- Enhances data security by ensuring that only authorized users can access, modify, and share classified files.

---

## 2. Individual Tasks

Below is a list of features and functions implemented in this system, along with associated security implementations.

| **Feature/Function**     | **Security Implementation**                                                                 |
|--------------------------|----------------------------------------------------------------------------------------------|
| **File Upload**          | - Scanning uploaded files for malware  <br> - Watermarking with hash values <br> - Logging of file with user ID, timestamps, and hash values to the database <br> - Handling duplicate files using hash values and filenames |
| **File Download**        | - Comparing hash values for verifying data integrity <br> - Watermark (“Owned by healthdefender”) shown on download |
| **File Sharing System**  | - HTTPS for protecting data in transit <br> - Secure tunneling using **Cloudflare** (proxy & DNS) <br> - Universal SSL certificate activated via Cloudflare <br> - Uses PEM file with private key, certificate, and Cloudflare tunnel token <br> - **CNAME:** `drive.healthdefenderportal.me` via port `5000` |
| **Chat System**          | - HTTPS for protecting data in transit <br> - Secure tunneling via Cloudflare <br> - Universal SSL certificate via Cloudflare <br> - AI profanity detection using **Streamchat** dashboard <br> - **CNAME:** `www.healthdefenderportal.me` via port `3000` |
| **AWS S3 File Storage**  | - Server-side encryption for protecting data at rest <br> - Data lifecycle set to **30 days** for users who resigned or accidentally deleted files |

---

> **Note:** All sensitive and official configurations are protected. This project emphasizes maintaining compliance and ensuring confidentiality, integrity, and availability of the data.

