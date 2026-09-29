# Unauthenticated vs Authenticated Scans on Linux Ubuntu '24 Virtual Machine
Project showcasing unauthenticated and authenticated scans on a Linux (Ubuntu 24) VM, utilizing the Tenable platform




This project documents the vulnerability scanning of an **Ubuntu Linux Virtual Machine (VM)** deployed in Azure, using **Tenable.io** for both unauthenticated and authenticated scans. The project highlights the significant differences in vulnerability detection when using authenticated credentials for scanning.

---

## ⚙️ Technology Utilized
- **Microsoft Azure** – Deployment of Linux Ubuntu '24 VM.
- **Tenable.io (Nessus Scanner)** – Vulnerability scanning platform.
- **OpenSSH** – Secure login to the Ubuntu server.
- **Ubuntu 22.04.5 LTS** – Target operating system.

---

## 📁 Project Structure

---

## 📝 Phase 1: VM Creation and Environment Setup
✅ **Creating a Ubuntu VM in Azure:**  

<img width="1000" height="800" alt="Deploying VM" src="Linux VM/Linux VM Deployed.png"/> 

✅ **Connecting to the Linux VM via Bastion as user `drewbrees`:**  

<img width="1000" height="800" alt="Deploying VM" src="Linux VM/Connecting to Linux VM via Bastion.png"/> 

<img width="1000" height="800" alt="Connecting to VM" src="Linux VM/Connected to Linux VM.png"/> 

---

## 📝 Phase 2: Unauthenticated Scan
✅ **Created a Basic Network Scan in Tenable:**  

<img width="1000" height="800" alt="Setting up unauthenticated scan" src="VM Labs - Images/Creating Scan in Tenable.png"/> 

✅ **Configuring the Unauthenticated Scan and setting the private IP address as the only target:**  

<img width="1000" height="800" alt="Configuring unauthenticated scan" src="Linux VM/Creating Linux Scan.png"/> 


✅ **Editing Discovery tab settings for custom, and ensuring ping and fast network discovery are enabled:**  

<img width="1000" height="800" alt="Configuring Discovery settings for scan" src="Linux VM/Creating Linux Discovery Settings.png"/> 


✅ **Scan running:**  

<img width="1000" height="800" alt="Linux unauthenticated scan running" src="Linux VM/Linux scan running.png"/> 

✅ **Unauthenticated Scan Completion and Results:**  

<img width="1000" height="800" alt="Linux unauthenticated scan results" src="Linux VM/Linux scan results.png"/> 

✅ **Exported Results for better analysis:**

<img width="1000" height="800" alt="Linux unauthenticated scan executive summary results" src="Linux VM/Linux Exec Summary Results.png"/> 

---

## 📝 Phase 3: Enabling Root SSH for Authenticated Scanning
✅ **Resetting root password and executing command to enable remote login with SSH using the roots credentials:**  

<img width="1000" height="800" alt="Linux password reset" src="Linux VM/Linux password rest.png"/> 

<img width="1000" height="800" alt="Linux password reset" src="Linux VM/Linux password reset2.png"/> 

---

## 📝 Phase 4: Authenticated Scan
✅ **Editing the scan settings to create an Authenticated Scan by including SSH root credentials:**  

<img width="1000" height="800" alt="Linux credentials added to scan" src="Linux VM/Linux credentials added.png"/> 

✅ **Running the authenticated scan:**  

<img width="1000" height="800" alt="Authenticated scan running" src="Linux VM/Linux credentialed scan running.png"/> 

✅ **Authenticated Scan Completion and Results:**  

<img width="1000" height="800" alt="Linux authenticated scan results" src="Linux VM/Linux credentialed scan results.png"/> 

✅ **Exported Executive Summary results for better analysis:**  

<img width="1000" height="800" alt="Linux authenticated executive summary scan results" src="Linux VM/Linux credentialed scan exec summary results.png"/> 

---

## 🔍 Comparison of Results

| Metric                       | Unauthenticated Scan | Authenticated Scan |
|------------------------------|----------------------|--------------------|
| Critical Vulnerabilities     | 0                    | 0                  |
| High Vulnerabilities         | 0                    | 4                  |
| Medium Vulnerabilities       | 0                    | 5                  |
| Low Vulnerabilities          | 1                    | 2                  |
| Informational                | 12                   | 61                 |
| **Total Vulnerabilities**    | 13                   | 72                 |

Authenticated scans provide more precise and accurate vulnerability data by using privileged access to probe deeper within the system.

---

## 🚀 Final Takeaways
- Unauthenticated scans are helpful for external exposure but miss critical system-level vulnerabilities.  
- Authenticated scans reveal deeper issues, leveraging privileged access.  
- Always prioritize securing critical and high vulnerabilities first!
