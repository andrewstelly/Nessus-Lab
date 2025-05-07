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
Create a VM in VMware Workstation. Select bridged network adapter. If you're on Wi-Fi, remove any Ethernet bridging.
![Part 1](./images/Part1.png)

### Verify Connectivity
Shut off the VM firewall and ping it from your host to confirm network connectivity.
![Part 2](./images/Part2.png)

### Start Nessus Scan Setup
Create a new scan in Nessus. Set the target to the VM's IP address.
![Part 3](./images/Part3.png)

### Configure Scan
Set scan type (e.g., common ports).
![Part 4](./images/Part4.png)

### Run the Scan
Save and run the scan.
![Part 5](./images/Part5.png)

### Review Vulnerability Tab
After the scan completes, review the **Vulnerabilities** tab.
![Part 6](./images/Part6.png)

### Investigate Vulnerabilities
Click a vulnerability to view details and remediation steps.
![Part 7](./images/Part7.png)

---

## Credentialed Scan Setup

### Enable Remote Registry
Open `services.msc` on the VM and enable **Remote Registry**.
![Part 8](./images/Part8.png)

### Enable File and Printer Sharing
Ensure it's turned on in Advanced Sharing Settings.
![Part 9](./images/Part9.png)

### Disable User Account Control (UAC)
Temporarily disable UAC for proper scanning (not ideal for domain machines).
![Part 10](./images/Part10.png)

### Registry Tweak for Credentialed Scan
In `regedit`:  
Navigate to:  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`  
Add `LocalAccountTokenFilterPolicy` as a `DWORD (32-bit)` value, set to `1`, then restart the VM.
![Part 11](./images/Part11.png)

### Add Credentials in Nessus
Go to the Credentials tab in the scan configuration, and enter the VM’s username/password.
![Part 12](./images/Part12.png)

### Run Credentialed Scan
Start the scan again.
![Part 13](./images/Part13.png)

### Vulnerability Results with Severity
Review vulnerabilities categorized by severity.
![Part 14](./images/Part14.png)

### Review Remediation Suggestions
Check the **Remediations** tab — many issues can be resolved with patching.
![Part 15](./images/Part15.png)

---

## Additional Testing

### Install Old Firefox
Install an outdated version of Firefox to test Nessus detection capability.
![Part 16](./images/Part16.png)

### Observe Vulnerability Spike
See 177 vulnerabilities reported for old Firefox version.
![Part 17](./images/Part17.png)

---

## Final Notes  
After uninstalling Firefox and updating Windows, a re-scan shows significantly fewer vulnerabilities, confirming successful remediation.

