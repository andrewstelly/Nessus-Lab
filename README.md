<h1>Nessus Vulnerability Management Lab</h1>

<h2>Description</h2>
I installed and configured Nessus Essentials to perform credentialed vulnerability scans against Windows 10 Hosts 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Nessus</b>
- <b>VMware Workstation</b> 


<h2>Environments Used </h2>

- <b>Windows 10</b>

<h2>Program walkthrough:</h2>

<p align="center">
Create a virtual machine through VMware Workstation. For network adapter, select bridged. If you are not on ethernet, remove any bridging settings with ethernet <br/>
<img src="https://i.imgur.com/IJk5pPM.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
Once running, shut off the firewall and ping it with your machine to ensure connectivity  <br/>
<img src="https://i.imgur.com/1BDJBpd.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />

<br />
<p align="center">
Ceate a new scan with Nessus and for the target, input the VM ip address <br/>
<img src="https://i.imgur.com/MByZQr6.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
The scan can be configured to your needs. I will be running a common port scan <br/>
<img src="https://i.imgur.com/pZUl0AA.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
Save and run the scan. <br/>
<img src="https://i.imgur.com/0yDk97j.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
Once complete, you can review the vulnerabilties tab <br/>
<img src="https://i.imgur.com/Dam1PrW.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
When clicking on a vulnerability, you will see more details about it and what you can do to remediate it<br/>
<img src="https://i.imgur.com/f2ucCJj.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
We will now do a credential can. Go to services.msc and enable remote registry <br/>
<img src="https://i.imgur.com/z2lshT2.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
Make sure that file and printer sharing is on in Advanced sharing settings <br/>
<img src="https://i.imgur.com/GdeqTON.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
Disable User Account Control (This is not usually recommended, but we are not on the domain, so we have to disable it to complete the scan) <br/>
<img src="https://i.imgur.com/IUrpb1z.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
Go to registry editor, browse to Local Machine → Software → Microsoft → Windows → Current Version → Policies → System. Create a dword value named LocalAccountTokenFilterPolicy. Set the value to 1, then restart the VM <br/>
<img src="https://i.imgur.com/LFzR2cH.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
Go back to Nessus. Configure your Windows 10 Host, go to credentials. Add the username and password for the VM. Restart the scan <br/>
<img src="https://i.imgur.com/l5fGc5b.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
When the scan is complete, we can see the list of vulnerabilities and their severity level <br/>
<img src="https://i.imgur.com/eSxTRL9.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
There is also a tab for remediations (Automated Patching can solve most of the errors)  <br/>
<img src="https://i.imgur.com/OVX3IpO.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
To further test the capabilities of Nessus, we will install an old version of firefox and run a new scan <br/>
<img src="https://i.imgur.com/PX6XnRN.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
We can see that Mozilla Firefox has many critical issues (177 vulnerabilities) <br/>
<img src="https://i.imgur.com/k7QAwgt.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
  
<br />
<p align="center">
To remediate some of our vulnerabilities, we can uninstall firefox and update windows. After running another scan, we can see that there are less vulnerabilities <br/>
<img src="https://i.imgur.com/LGcKTW4.png" height="80%" width="80%" alt="Nessus Steps"/>
<br />
