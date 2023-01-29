<h1>Vulnerability Management</h1>
- [Credential Scan with  Nessus Homelab]

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

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
Both Windows10 and Nessus home after successfully installed: <br/>
<img src="https://imgur.com/9De1u6V.png" height="80%" width="80%"/>
<br />
<br />
Used ipconfig on command prompt to check IP address of the Windows10 Machine:  <br/>
<img src="https://imgur.com/0VbezUL.png" height="80%" width="80%" />
<br />
<br />
Used the local machine to ping IP address of the windows10 host to determine its reachability for communication: Ping request timed out due to Firewall enabled on Windows10 and blocking any ping request <br/>
<img src="https://imgur.com/OOfT9tZ.png" height="80%" width="80%" />
<br />
<br />
 Disabled Firewall to allow ping request <br/>
<img src="https://imgur.com/pTFg5As.png" height="80%" width="80%" />
<br />
<br />
Local machine successflly received reply from Windows10 host after disabling firewall <br/>
<img src="https://imgur.com/ujHp4bI.png" height="80%" width="80%" />
<br />
<br />
Clicked on Create a new scan on Nessus home page: Opens the scan template   <br/>
<img src="https://imgur.com/IMCTsBC.png" height="80%" width="80%" />
<br />
<br />
Clicked on Basic Network Scan: Opens a new scan page: Input name of scan: Input target Ip address(Windows10 host):Saved scan<br/>
<img src="https://imgur.com/YImsxPd.png" height="80%" width="80%" />
<br />
<br />
Launched Scan : Scan Running <br/>
<img src="https://imgur.com/VGNr6JT.png" height="80%" width="80%" />
<br />
<br />
Scan Completed: Showing Scan Details :Color Coding severity of Vulnerability:<br/>
<img src="https://imgur.com/CFXrIow.png" height="80%" width="80%" />
<br />
<br />
Vulnerabilities Results:  <br/>
<img src="https://imgur.com/xY9htKp.png" height="80%" width="80%" />
<br />
<br />
SMB Vulnerability:  <br/>
<img src="https://imgur.com/qFQYWWy.png" height="80%" width="80%" />
<br />
<br />
Enabled Remote Registry:  <br/>
<img src="https://imgur.com/fey5FJi.png" height="80%" width="80%" />
<br />
<br />
Change User Account Control Settings to "Never Notify:  <br/>
<img src="https://imgur.com/v6snDMP.png" height="80%" width="80%" />
<br />
<br />
Enabled Files and Printer Sharing:  <br/>
<img src="https://imgur.com/fjhQ4FG.png" height="80%" width="80%" />
<br />
<br />
Added LocalAccountTokenFilterPolicy to Registry:  <br/>
<img src="https://imgur.com/xO2A7oo.png" height="80%" width="80%" />
<br />
<br />
Set LocalAccountTokenFilterPolicy value to 1:  <br/>
<img src="https://imgur.com/FhOBlXf.png" height="80%" width="80%" />
<br />
<br />
Reconfigured my scan to perform a credential scan:  <br/>
<img src="https://imgur.com/GxsX0Ze.png" height="80%" width="80%" />
<br />
<br />
Input the credential and saved the scan:  <br/>
<img src="https://imgur.com/bDhNch5.png" height="80%" width="80%" />



Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
