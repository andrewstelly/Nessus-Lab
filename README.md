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

## Program Walkthrough

### Create VM and Configure Network
<p align="center">
  <img src="./images/Part1.png" width="80%" alt="Part 1"/>
</p>

### Verify Connectivity
<p align="center">
  <img src="./images/Part2.png" width="80%" alt="Part 2"/>
</p>

### Start Nessus Scan Setup
<p align="center">
  <img src="./images/Part3.png" width="80%" alt="Part 3"/>
</p>

### Configure Scan
<p align="center">
  <img src="./images/Part4.png" width="80%" alt="Part 4"/>
</p>

### Run the Scan
<p align="center">
  <img src="./images/Part5.png" width="80%" alt="Part 5"/>
</p>

### Review Vulnerability Tab
<p align="center">
  <img src="./images/Part6.png" width="80%" alt="Part 6"/>
</p>

### Investigate Vulnerabilities
<p align="center">
  <img src="./images/Part7.png" width="80%" alt="Part 7"/>
</p>

## Credentialed Scan Setup

### Enable Remote Registry
<p align="center">
  <img src="./images/Part8.png" width="80%" alt="Part 8"/>
</p>

### Enable File and Printer Sharing
<p align="center">
  <img src="./images/Part9.png" width="80%" alt="Part 9"/>
</p>

### Disable User Account Control (UAC)
<p align="center">
  <img src="./images/Part10.png" width="80%" alt="Part 10"/>
</p>

### Registry Tweak for Credentialed Scan  
Navigate to:  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`  
Add `LocalAccountTokenFilterPolicy` as a `DWORD (32-bit)` value, set to `1`, then restart the VM.  
<p align="center">
  <img src="./images/Part11.png" width="80%" alt="Part 11"/>
</p>

### Add Credentials in Nessus
<p align="center">
  <img src="./images/Part12.png" width="80%" alt="Part 12"/>
</p>

### Run Credentialed Scan
<p align="center">
  <img src="./images/Part13.png" width="80%" alt="Part 13"/>
</p>

### Vulnerability Results with Severity
<p align="center">
  <img src="./images/Part14.png" width="80%" alt="Part 14"/>
</p>

### Review Remediation Suggestions
<p align="center">
  <img src="./images/Part15.png" width="80%" alt="Part 15"/>
</p>

## Additional Testing

### Install Old Firefox
<p align="center">
  <img src="./images/Part16.png" width="80%" alt="Part 16"/>
</p>

### Observe Vulnerability Spike
<p align="center">
  <img src="./images/Part17.png" width="80%" alt="Part 17"/>
</p>

## Final Notes  
After uninstalling Firefox and updating Windows, a re-scan shows significantly fewer vulnerabilities, confirming successful remediation.
