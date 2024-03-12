<h1>Nessus Vulnerability Management Lab</h1>

<h2>Description</h2>
I setup Azure Sentinel (SIEM) and connected it to a live virtual machine acting as a honey pot. I observed live attacks (RDP Brute Force) from all around the world. I used a custom PowerShell script to look up the attackers Geolocation information and plot it on the Azure Sentinel Map!
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Azure</b>

<h2>Environments Used </h2>

- <b>Windows 10</b>

<h2>Program walkthrough:</h2>

<p align="center">
Create a virtual machine through Microsoft Azure with an open firewall <br/>
<img src="https://i.imgur.com/MLUCZP7.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
After creating the virtual machine, turn off all firewall settings and ping the machine, ensuring that echo requests are allowed  <br/>
<img src="https://i.imgur.com/5ZEd8wE.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
