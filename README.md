<h1>Vulnerability Management</h1>
- [Credential Scan with  Nessus Homelab]

<h2>Description</h2>
In this lab we will cover vulnerability scanning and vulnerability remediation. These are two of the main steps in the Vulnerability Management Lifecycle. We will be using Nessus Essentials to scan local VMs hosted on Oracle virtual Box in order to run credentialed scans to discover vulnerabilities, remediate some of the vulnerabilities, then perform a rescan to verify remediation.
<br />


<h2>Tool Used</h2>

- <b>Nessus Essential</b> 

<h2>Environments Used </h2>

- <b>Oracle Virtual Box</b>
- <b>Windows 10</b> (21H2)

<h2>Lab walk-through:</h2>

<p align="center">
Windows10 and Nessus home page after successfully installed: <br/>
<img src="https://imgur.com/9De1u6V.png" height="80%" width="80%"/>
<br />
<br />
Ipconfig was used on command prompt to check IP address of the Windows10 Machine:  <br/>
<img src="https://imgur.com/PfJWmAY.png" height="80%" width="80%" />
<br />
<br />
My windows local machine was used to ping IP address of the windows10 host to determine its reachability for communication: Ping request timed out due to Firewall enabled on Windows10,blocking any communication <br/>
<img src="https://imgur.com/ffEAy1E.png" height="80%" width="80%" />
<br />
<br />
 Disabled Firewall to allow ping request <br/>
<img src="https://imgur.com/pTFg5As.png" height="80%" width="80%" />
<br />
<br />
Local machine successflly received reply from Windows10 host after disabling firewall <br/>
<img src="https://imgur.com/ZzimULX.png" height="80%" width="80%" />
<br />
<br />
Enabled Remote Registry:  <br/>
<img src="https://imgur.com/fey5FJi.png" height="80%" width="80%" />
<br />
<br />
I disbaled User Account Control Settings to "Never Notify:This is not a good practices but the windows is not a domain so it has to be done to be able to scan it: I got this documentations from nessus  <br/>
<img src="https://imgur.com/v6snDMP.png" height="80%" width="80%" />
<br />
<br />
Enabled Files and Printer Sharing:  <br/>
<img src="https://imgur.com/fjhQ4FG.png" height="80%" width="80%" />
<br />
<br />
Added LocalAccountTokenFilterPolicy key to the Registry: This is to further disable user account control for the remote account we are going to use to connect to the Windows 10 host during our scan <br/>
<img src="https://imgur.com/xO2A7oo.png" height="80%" width="80%" />
<br />
<br />
Set LocalAccountTokenFilterPolicy value to 1: Again,I got this documentation from Nessus on configure Windows host not a domain for credential scan <br/>
<img src="https://imgur.com/FhOBlXf.png" height="80%" width="80%" />
<br />
<br />
Clicked on Create a new scan on Nessus home page: Opens the scan template   <br/>
<img src="https://imgur.com/1Poa8uO.png" height="80%" width="80%" />
<br />
<br />
Clicked on Basic Network Scan: Opens a new scan page:<br/>
<img src="https://imgur.com/bQnsJqy.png" height="80%" width="80%" />
<br />
<br />
Configured the scan to perform a credential scan and saved the scan:  <br/>
<img src="https://imgur.com/bDhNch5.png" height="80%" width="80%" />
<br />
<br />
Launched Scan : Scan Running <br/>
<img src="https://imgur.com/VGNr6JT.png" height="80%" width="80%" />
<br />
<br />
Credential Scan Completed: Showing Scan Details :Color Coding severity of Vulnerability:  <br/>
<img src="https://imgur.com/GeYZKuW.png" height="80%" width="80%" />
<br />
<br />
Credential Scan Vulnerabilities Results :  <br/>
<img src="https://imgur.com/wrSyBdB.png" height="80%" width="80%" />
<br />
<br />
Mixed Result Details:Mixture of critical,High,and Info <br/>
<img src="https://imgur.com/2XQxNc9.png" height="80%" width="80%" />
<br />
<br />

<h2>Remediation</h2>
I disable remote registry, disabled SMB shares, Enabled user account control, deleted LocalAccountTokenFilterPolicy from the Registry, run Windows update and run the scan again. If most of the vulnerabilty requires you to run an update of a system or third-party application. it is best to automate a script to run these update instead of individually updating them.

Scan Completed: Showing Scan Details :Color Coding severity of Vulnerability:<br/>
<img src="https://imgur.com/zqYgTGP.png" height="80%" width="80%" />
<br />
<br />
Vulnerabilities Results:1 medium, the rest is info(Info means could not necessary be a vulnerability but something we should be aware: All critical and high vulnerability were remediated. <br/>
<img src="https://imgur.com/xY9htKp.png" height="80%" width="80%" />
<br />
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
