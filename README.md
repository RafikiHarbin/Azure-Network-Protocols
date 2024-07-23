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
    

        
![Screenshot 2024-07-22 193536](https://github.com/user-attachments/assets/bb164691-054f-4fc3-9a3a-863178fcaab0)



![Screenshot 2024-07-22 194713](https://github.com/user-attachments/assets/9f64410b-4df7-4999-bd7c-98a9c8305900)

___________________________________________________________________________________________________________________________

INSTALLING WIRESHARK ON (VM1) TO INSPECT THE TRAFFIC INTERACTING WITH (VM2)


     ● Download Wireshark from VM1 
     ● Capture packets & see live traffic on VM1

![Wireshark](https://github.com/user-attachments/assets/ccf78a6c-3782-43fd-9d37-8aef31bb791e)





https://github.com/user-attachments/assets/d44c106f-dfa9-4d86-8a2f-33ee50c48371


___________________________________________________________________________________________________________________________

LIVE TRAFFIC ON VIRTUAL MACHINE (VM-1) FILTERED FOR INTERNET CONTROL MESSAGING PROTOCOL (ICMP) TRAFFIC ONLY, USING WIRESHARK
![ICMP Only](https://github.com/user-attachments/assets/4f658ae9-cae5-44b6-8445-62e975d605d4)





______________________________________________________________________________________________________________________

VIRTUAL MACHINE (VM1) PING VIRTUAL MACHINE (VM2) FROM PRIVATE IP ADDRESS, USING POWERSHELL
           
  ● Private IP address for VM2: 10.0.0.5
 
  ● Private IP address for VM1: 10.0.0.4       




![ping 10 0 0 5](https://github.com/user-attachments/assets/da08f4a8-6d67-4db4-b418-d47b87b4a64e)



Virtual Machine (VM-2) responded to Virtual Machine (VM-1) ping 4 times. Sent 4 request, recieved 4 replies.


![Communicating](https://github.com/user-attachments/assets/dd8d0772-7870-44f3-911e-4122419f6d83)

![Packets](https://github.com/user-attachments/assets/3f84e4cc-30ce-49c3-b257-72163b63cc99)

______________________________________________________________________________________________________________________

CREATE A NEW SECURITY RULE THAT WILL DENY INBOUND ICMP (PING) TRAFFIC




![Creating Rule](https://github.com/user-attachments/assets/d7c410ef-b199-4fc1-a95e-696a2368bf37)




![Deny ICMP](https://github.com/user-attachments/assets/e0e17150-c017-4e2a-8589-574987875563)




![No Response](https://github.com/user-attachments/assets/69a7ca14-624d-412e-9be5-0eb4dedacf19)

_______________________________________________________________________________________________________________________________________________________


FILTERED FOR DOMAIN HOST CONFIGURATION PROTOCOL (DHCP) TRAFFIC ONLY, USING WIRESHARK

![DHCP](https://github.com/user-attachments/assets/4b919c7d-d958-4951-8868-3e40c5012180)


 ● DHCP is used to automatically assign an IP address
          
 ● ipconfig/ renew from the command line in Powershell forces the renewal of an IP address




_____________________________________________________________________________________________________________________________________________________________________________________________________________________________
FILTERED FOR SECURE SHELL (SSH) TRAFFIC ONLY, USING WIRESHARK



![SSH](https://github.com/RafikiHarbin/Azure-Network-Protocols/assets/170275827/379b5d26-5d2f-4331-9402-742a4342b92a)


_____________________________________________________________________________________________________________________________________________________________________________________________________________________________
FILTERED FOR DOMAIN NAME SYSTEM (DNS) TRAFFIC ONLY, USING WIRESHARK





![DNS only](https://github.com/user-attachments/assets/4bf61e52-33b1-4487-8c4c-15ef1c509e6a)


 ● From Virtual Machine (VM1) within the command line of Powershell, use nslookup to see what is google.com IP address

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________


