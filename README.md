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

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Create a Resource Group.

- Step 2: Create a Windows 10 Virtual Machine (VM).

         a.While creating the VM, select the previously created Resource Group.

         b.While creating the VM, allow it to create a new Virtual Network (Vnet) and Subnet.

- Step 3: Create a Linux (Ubuntu) VM.

         a.While creating the VM, select the previously created Resource Group and Vnet.

- Step 4:  Observe Your Virtual Network within Network Watcher.  

<h2>Actions and Observations</h2>


![Screenshot 2024-05-21 144818](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/a3d5bf46-804e-48df-b5e6-d3507fd4d3cf)



Live traffic on Virtual Machine (VM-1) filtered for Internet Control Messaging Protocol (ICMP) traffic only using Wireshark.
______________________________________________________________________________________________________________________

![Screenshot 2024-05-21 144818](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/fc653446-952b-4dc7-9757-460d6226421f)


Virtual Machine (VM-1) Ping Virtual Machine (VM-2) from private IP address using Powershell.

![Observe ping requests and replies within WireShark](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/d8945c6f-f2cc-45fc-91df-5ae002b9e88a)



![Ping VM2 from private IP address](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/d3b538e1-029e-4004-ac14-2eb34bebd6cd)

Virtual Machine (VM-2) responded to Virtual Machine (VM-1) ping 4 times. Sent 4 request, recieved 4 replies.
______________________________________________________________________________________________________________________



<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
