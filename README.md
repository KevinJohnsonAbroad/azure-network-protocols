<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Resources
- Observe ICMP Traffic
- Observe SSH Traffic)
- Observe DHCP Traffic
- Observe DNS Traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/R21OQ1i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 A resource group and 2 virtual machines (Microsoft 10 and Linux) were created.
</p>
<br />

<p>
<img src="https://i.imgur.com/doywL1t.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within Windows 10 Virtual Machine - Install Wireshark
-In Wireshark ICMP traffic was flitered. <br>
-The private IP address was retrieved of the Ubuntu VM and pinged from within the Windows 10 VM.<br>
-Observe ping requests and replies within WireShark.<br>
-From the Windows 10 ,  open PowerShell was and ping (www.google.com)<br>
-A perpetual/non-stop ping was initiated from Windows 10 VM Ubuntu VM.<br>
-Open Network Security Group on Ubuntu VM.<br>
-Disable Incoming (inbound) ICMP traffic was disabled.<br>
-In Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity.<br>
-Enable again ICMP traffic for Network Security Group on the Ubuntu VM.<br>
-In Windows 10 VM, the ICMP traffic can be seen again in WireShark.<br>

</p>
<br />

<p>
<img src="https://i.imgur.com/qCTHzgS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
-In Wireshark, "SSH traffic only" was filtered.<br>
-From Windows 10 VM, “SSH into” Ubuntu Virtual Machine (via its private IP address)<br>
-Using commands such as ls, pwd, etc, type into the linux SSH was used to connect.<br>
-SSH traffic is observed spamming in WireShark.<br>
-Exit SSH connection by typing ‘exit’ and pressing [Enter].<br>


</p>
<br />

<p>
<img src="https://i.imgur.com/s0wzQ1y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
-Via Wireshark, filter "DHCP traffic only"<br>
-From Windows 10 VM, a new IP address was issued from the command line (ipconfig /renew)<br>
-DHCP traffic can be observed in WireShark.<br>


</p>
<br />

<p>
<img src="https://i.imgur.com/6Ysh565.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
-In Wireshark, DNS traffic "only" was filtered.<br>
-Windows 10 command line, type nslookup to see what google.com and disney.com’s IP addresses are.<br>
-The DNS traffic was then observed in WireShark.<br>





</p>
<br />
