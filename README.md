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

![Screenshot 2024-07-22 171726](https://github.com/user-attachments/assets/d2624d36-98e3-4b3f-9955-28b0e0d8a83a)




![Screenshot 2024-07-22 164153](https://github.com/user-attachments/assets/e0381722-1b42-4749-93b2-22c4512d22ea)


_____________________________________________________________________________________________________________________________________________________________________________________________________________________________

CREATING VIRTUAL MACHINE 1 (VM1)

![Screenshot 2024-07-22 175330](https://github.com/user-attachments/assets/1eda909b-0320-485b-86cd-fbb202c56a67)





![Screenshot 2024-07-22 180633](https://github.com/user-attachments/assets/bfd69d11-1c50-4bca-b734-911e45bb1f47)

________________________________________________________________________________________________________________________________________________________________________________________________________________________________

RESOURCES CREATED AUTOMATICALLY WHEN CREATING A VIRTUAL MACHINE (VM1)




![Screenshot 2024-07-22 182046](https://github.com/user-attachments/assets/b686056b-7201-4306-a9b8-1e74cb66c8e4)


_____________________________________________________________________________________________________________________________________________________________________________________________________________________________

VIRTUAL NETWORK & SUBNET CREATED AUTOMATICALLY WHEN CREATING A VIRTUAL MACHINE 




![Subnet](https://github.com/user-attachments/assets/4c9d9fa6-f46f-4066-9e13-2f8ec8063be6)


___________________________________________________________________________________________________________________________

CREATING VIRTUAL MACHINE 2 (VM2)


![VM2](https://github.com/user-attachments/assets/d5bf4fbf-191e-476e-8e3b-ae6f557e5d53)



![VM 1 2](https://github.com/user-attachments/assets/a4f37c2e-df82-42c9-83dd-a8ad5b10c7a0)

________________________________________________________________________________________________________________________________________________________________________________________________________________________________
RESOURCES CREATED AUTOMATICALLY FROM CREATING VIRTUAL MACHINE 1 & 2 (VM1) & (VM2)



![VM 1 2 RESOURCES](https://github.com/user-attachments/assets/ed5f224e-09d1-4964-a526-f337a17e7b17)

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

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________


