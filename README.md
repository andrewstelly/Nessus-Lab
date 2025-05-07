# Nessus Vulnerability Management Lab

## Description  
Installed and configured **Nessus Essentials** to perform credentialed vulnerability scans against Windows 10 hosts.

---

## Languages and Utilities Used  
- **Nessus**  
- **VMware Workstation**

## Environments Used  
- **Windows 10**

---
<div align="center">

## Program Walkthrough

### Create VM and Configure Network  
<img src="./images/Part1.png" width="80%" alt="Part 1"/>

### Verify Connectivity  
<img src="./images/Part2.png" width="80%" alt="Part 2"/>

### Start Nessus Scan Setup  
<img src="./images/Part3.png" width="80%" alt="Part 3"/>

### Configure Scan  
<img src="./images/Part4.png" width="80%" alt="Part 4"/>

### Run the Scan  
<img src="./images/Part5.png" width="80%" alt="Part 5"/>

### Review Vulnerability Tab  
<img src="./images/Part6.png" width="80%" alt="Part 6"/>

### Investigate Vulnerabilities  
<img src="./images/Part7.png" width="80%" alt="Part 7"/>

---

## Credentialed Scan Setup

### Enable Remote Registry  
<img src="./images/Part8.png" width="80%" alt="Part 8"/>

### Enable File and Printer Sharing  
<img src="./images/Part9.png" width="80%" alt="Part 9"/>

### Disable User Account Control (UAC)  
<img src="./images/Part10.png" width="80%" alt="Part 10"/>

### Registry Tweak for Credentialed Scan  
Navigate to:  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`  
Add `LocalAccountTokenFilterPolicy` as a `DWORD (32-bit)` value, set to `1`, then restart the VM.  
<img src="./images/Part11.png" width="80%" alt="Part 11"/>

### Add Credentials in Nessus  
<img src="./images/Part12.png" width="80%" alt="Part 12"/>

### Run Credentialed Scan  
<img src="./images/Part13.png" width="80%" alt="Part 13"/>

### Vulnerability Results with Severity  
<img src="./images/Part14.png" width="80%" alt="Part 14"/>

### Review Remediation Suggestions  
<img src="./images/Part15.png" width="80%" alt="Part 15"/>

---

## Additional Testing

### Install Old Firefox  
<img src="./images/Part16.png" width="80%" alt="Part 16"/>

### Observe Vulnerability Spike  
<img src="./images/Part17.png" width="80%" alt="Part 17"/>

---

## Final Notes  
After uninstalling Firefox and updating Windows, a re-scan shows significantly fewer vulnerabilities, confirming successful remediation.

</div>
