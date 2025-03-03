<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Resource Group and Virtual Machines
- Create resources new Vnet and Subnet
- Remote Desktop Connect using Virtual Machines
- Use Command prompt to ping activity
- Open WireShark to filter the pinged traffic

<h2>Actions and Observations</h2>
</p>
</p>
</p>

<p>
1. Create a Resource Group</p>  
-  Create a Windows 10 Virtual Machine (VM)</p>
-  Create a Linux (Ubuntu) VM</p>
-  Select the created Resource Group and Vnet will appear (use same information for both VMs)</p>
-  Ensure there are different Private IP Addresses</p>
</p>
</p>


<p>
<img src="https://i.imgur.com/HbxAqXB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/fqc6nON.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/sy9VuGp.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/IsOwDCF.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> 
</p>
</p>
<br />
<br />


<p>
2. Use Windows 10 Virtual Machine via Remote Desktop access</p>
-  Download and access WireShark</p>
-  Using WireShark, filter for ICMP traffic only</p>
-  Get your Private IP address from Azure platform</p>
-  Ping the private address using Command Prompt</p>
-  Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM</p>
-  Open Network Security Group using Azure </p>
-  Disable incoming ICMP traffic (ICMPv4), observe ICMP traffic in WireShark and Command line</p>
-  Re-enable ICMP traffic, observe ICMP traffic in WireShark and Command line </p>
</p>
</p>
</p>
</p>
<br />
<br />
<br />


<p>
<img src="https://i.imgur.com/W763fq1.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/Rr9VL2p.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p>  <img src="https://i.imgur.com/y2IwQbd.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p>  <img src="https://i.imgur.com/sS2alrf.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/JfwGMyK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/JHJcxqK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p>  <img src="https://i.imgur.com/fhI5p1q.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p>
</p>
</p>
</p>
</p>
<br />
<br />
<br />
 

</p>
<p>
3. In Wireshark, filter for SSH traffic only</p>
-  From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)</p>
-  Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark</p>
-  Exit the SSH connection by typing ‘exit’ and pressing [Enter]</p>
</p>
</p>
</p>
</p>
<br />
<br />
<br />

<p>
<img src="https://i.imgur.com/puY47lu.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/USXWPJT.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> 
</p>
</p>
</p>
<br />
<br />
<br />


4. Observe DHCP Traffic</p>
-  In Wireshark, filter for DHCP traffic only</p>
-  From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)</p>
-  Observe the DHCP traffic appearing in WireShark</p>
</p>
</p>
</p>
</p>
<br />
<br />
<br />

<p>
<img src="https://i.imgur.com/27YcH1P.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> 
</p>
</p>
</p>
</p>
<br />
<br />
<br />


5. Observe DNS Traffic</p>
-  Back in Wireshark, filter for DNS traffic only</p>
-  From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are</p>
-  Observe the DNS traffic being show in WireShark</p>
</p>
</p>
</p>
</p>
<br />
<br />
<br />

<p>
<img src="https://i.imgur.com/ztKcYiq.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> <img src="https://i.imgur.com/3r1oGpY.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> 
</p>
</p>
</p>
</p>
<br />
<br />
<br />


6. Observe RDP Traffic</p>
-  Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)</p>
-  Observe the immediate non-stop spam of traffic</p>


-  Note:  The reason Why there is non-stop spamming is because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefore traffic is always being transmitted.</p>
</p>
</p>
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/XEcIdCO.png" height="40%" width="40%" alt="Disk Sanitization Steps"/></p> 
</p>
</p>
</p>
</p>
<br />
<br />
<br />

