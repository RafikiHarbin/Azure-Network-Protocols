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
- Linux (Ubuntu) Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Create a Resource Group.

- Step 2: Create a Windows 10 Virtual Machine (VM1).

         a.While creating the VM1, select the previously created Resource Group.

         b.While creating the VM1, allow it to create a new Virtual Network (Vnet) and Subnet.

- Step 3: Create a Linux (Ubuntu) Virtual Machine (VM2).

         a.While creating the VM2, select the previously created Resource Group and Vnet.

- Step 4:  Observe Your Virtual Network within Network Watcher.  

<h2>Actions and Observations</h2>

CREATING A RESOURCE GROUP

![Screenshot 2024-06-22 141422](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/687e7dfd-96b8-447a-b149-48dba54e72ea)





![RG-Lab-01 Completed](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/6a0101f5-6bf7-46e7-bacd-b4f9e7a4199c)

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________

CREATING VIRTUAL MACHINE 1 (VM1)


![Creating VM1](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/07fee03b-717f-478b-bc30-a626542a981a)


![VM1 Completed](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/49e88671-28d6-4d2e-a133-65ecdabf4455)

RESOURCES CREATED AUTOMATICALLY WHEN CREATING A VIRTUAL MACHINE (VM1)


![Resources automatically created from creating VM1](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/ec4fd057-7108-4561-8fda-7d34387bcb8a)

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________

CREATING A VIRTUAL NETWORK & SUBNET


![Creating Virtual Network   Subnet](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/c49a7b77-b5a1-48e1-9510-fc787af7d9bd)
___________________________________________________________________________________________________________________________

CREATING VIRTUAL MACHINE 2 (VM2)


![Creating VM2](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/ccea5b01-608f-43c6-b536-3d4082251f4a)


![VM1   VM2 together](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/b661b11e-0f64-4f41-b0a6-d62168205df0)

RESOURCES CREATED AUTOMATICALLY FROM CREATING A VIRTUAL MACHINE (VM1) & (VM2)


![Resources automatically created from creating VM1   VM2](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/4d6704cd-34aa-4cdd-9c44-0daec4d4d642)



![Resources automatically created from creating VM1   VM2 (2)](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/1905afb4-2d28-4120-86a4-37ffcbfbb40b)


___________________________________________________________________________________________________________________________
CONNECTING TO VIRTUAL MACHINE 1 (VM1) IN WINDOWS 

     ● Copy Public IP address from within VM1
     ● From the start menu, open the Remote Desktop Connection & paste the Public IP address
    
![Copy IP address from within VM1](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/2efed8c4-15c8-4287-b516-320d9cdb72d9)
        


![Paste IP address to Remote Desktop Connection](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/975b98f8-b475-457b-983a-c541fb0625db)


![Connected to VM1](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/d236c7f8-a66c-4112-8c87-c57c104a1d8c)
___________________________________________________________________________________________________________________________

INSTALLING WIRESHARK TO INSPECT TRAFFIC AS I INTERACT WITH VIRTUAL MACHINE 2 (VM2)


     ● Download Wireshark from VM1 
     ● Capture packets & see live traffic on VM1




![Downloading Wireshare from VM1](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/e7b87ea3-e6ac-4336-bd3d-e374479a6d76)


https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/de3cc429-85f8-4225-9af9-d6a4664986de






___________________________________________________________________________________________________________________________

LIVE TRAFFIC ON VIRTUAL MACHINE (VM-1) FILTERED FOR INTERNET CONTROL MESSAGING PROTOCOL (ICMP) TRAFFIC ONLY, USING WIRESHARK
![Type in ICMP](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/db5b6208-bcd9-4035-8311-253ed1cce4f5)





![ICMP filtered traffic](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/5ebe1694-35fa-42f7-a93d-d2ab7ec3564e)





______________________________________________________________________________________________________________________

VIRTUAL MACHINE (VM1) PING VIRTUAL MACHINE (VM2) FROM PRIVATE IP ADDRESS, USING POWERSHELL
           
  ● Copy private IP address for VM2
          
  ● Go to VM1 Remote Desktop Connection & type in Powershell from start menu
          
  ● Type in ping & paste VM2 private IP address


![VM2 private IP address](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/423e45bb-2ef9-47a0-ae0f-eff8ca6a5179)



![Powershell from start menu](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/b89837d4-ea01-4e76-984c-b852c592526d)



![Screenshot 2024-05-21 144818](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/53a2ebaa-b9b4-4f9e-8331-954890e60bae)



Virtual Machine (VM-2) responded to Virtual Machine (VM-1) ping 4 times. Sent 4 request, recieved 4 replies.


![Observe ping requests and replies within WireShark](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/d8945c6f-f2cc-45fc-91df-5ae002b9e88a)



![Ping VM2 from private IP address](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/d3b538e1-029e-4004-ac14-2eb34bebd6cd)


______________________________________________________________________________________________________________________


FILTERED FOR DOMAIN HOST CONFIGURATION PROTOCOL (DHCP) TRAFFIC ONLY, USING WIRESHARK

![DHCP IP address reissued](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/383349ef-9c09-48c7-acfa-a90e34f97297)

 ● DHCP is used to automatically assign an IP address
          
 ● ipconfig/ renew from the command line in Powershell forces the renewal of an IP address




_____________________________________________________________________________________________________________________________________________________________________________________________________________________________
FILTERED FOR SECURE SHELL (SSH) TRAFFIC ONLY, USING WIRESHARK



![SSH](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/379b5d26-5d2f-4331-9402-742a4342b92a)


_____________________________________________________________________________________________________________________________________________________________________________________________________________________________
FILTERED FOR DOMAIN NAME SYSTEM (DNS) TRAFFIC ONLY, USING WIRESHARK





![DNS](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/c68b640e-dd6e-42ff-9e9a-17dbe644ff01)

 ● From Virtual Machine (VM1) within the command line of Powershell, use nslookup to see what is google.com IP address





