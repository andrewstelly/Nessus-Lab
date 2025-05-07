<h1 align="center">Nessus Vulnerability Management Lab</h1>

<h2>Description</h2>
<div>
  I installed and configured Nessus Essentials to perform credentialed vulnerability scans against Windows 10 Hosts.
</div>

---

<h2>Languages and Utilities Used</h2>

<div>
<ul>
  <li><b>Nessus</b></li>
  <li><b>VMware Workstation</b></li>
</ul>
</div>

<h2>Environments Used</h2>


<ul>
  <li><b>Windows 10</b></li>
</ul>


---

<h2 align="center">Program Walkthrough</h2>

<div align="center">

Create a virtual machine through VMware Workstation. For network adapter, select bridged. If you are not on ethernet, remove any bridging settings with ethernet  
<br/>
<img src="./images/Part1.png" width="80%" alt="Part 1"/>

<br/><br/>

Once running, shut off the firewall and ping it with your machine to ensure connectivity  
<br/>
<img src="./images/Part2.png" width="80%" alt="Part 2"/>

<br/><br/>

Create a new scan with Nessus and for the target, input the VM IP address  
<br/>
<img src="./images/Part3.png" width="80%" alt="Part 3"/>

<br/><br/>

The scan can be configured to your needs. I will be running a common port scan  
<br/>
<img src="./images/Part4.png" width="80%" alt="Part 4"/>

<br/><br/>

Save and run the scan  
<br/>
<img src="./images/Part5.png" width="80%" alt="Part 5"/>

<br/><br/>

Once complete, you can review the vulnerabilities tab  
<br/>
<img src="./images/Part6.png" width="80%" alt="Part 6"/>

<br/><br/>

When clicking on a vulnerability, you will see more details about it and what you can do to remediate it  
<br/>
<img src="./images/Part7.png" width="80%" alt="Part 7"/>

<br/><br/>

We will now do a credentialed scan. Go to services.msc and enable remote registry  
<br/>
<img src="./images/Part8.png" width="80%" alt="Part 8"/>

<br/><br/>

Make sure that file and printer sharing is on in Advanced sharing settings  
<br/>
<img src="./images/Part9.png" width="80%" alt="Part 9"/>

<br/><br/>

Disable User Account Control (This is not usually recommended, but we are not on the domain, so we have to disable it to complete the scan)  
<br/>
<img src="./images/Part10.png" width="80%" alt="Part 10"/>

<br/><br/>

Navigate to:  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`  
Add `LocalAccountTokenFilterPolicy` as a `DWORD (32-bit)` value, set to `1`, then restart the VM.  
<br/>
<img src="./images/Part11.png" width="80%" alt="Part 11"/>

<br/><br/>

Go back to Nessus. Configure your Windows 10 Host. Go to credentials and add the username and password for the VM. Restart the scan  
<br/>
<img src="./images/Part12.png" width="80%" alt="Part 12"/>

<br/><br/>

When the scan is complete, we can see the list of vulnerabilities and their severity level  
<br/>
<img src="./images/Part13.png" width="80%" alt="Part 13"/>

<br/><br/>

There is also a tab for remediations. (Automated patching can solve most of the errors)  
<br/>
<img src="./images/Part14.png" width="80%" alt="Part 14"/>

<br/><br/>

To further test the capabilities of Nessus, we will install an old version of Firefox and run a new scan  
<br/>
<img src="./images/Part15.png" width="80%" alt="Part 15"/>

<br/><br/>

We can see that Mozilla Firefox has many critical issues (177 vulnerabilities)  
<br/>
<img src="./images/Part16.png" width="80%" alt="Part 16"/>

<br/><br/>

To remediate some of our vulnerabilities, we can uninstall Firefox and update Windows. After running another scan, we can see that there are fewer vulnerabilities  
<br/>
<img src="./images/Part17.png" width="80%" alt="Part 17"/>

</div>
