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

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
First we will create two Virtual Machines on Azure. One machine will be a Linux machine and the other will be a Windows 10 machine. Both will have two cpus and they must be on the same VNET. Below is a shot of the Network Topology.
</p>

![image](https://user-images.githubusercontent.com/111653930/236491025-53d59445-7bfc-4863-87dc-3e0c18e3cbc6.png)

<br />

<br>
<p>
To begin we will login to VM-1 and download and install <a href="https://www.wireshark.org">WireShark</a>. Wireshark is a free and open-source packet analyzer. It is used for network troubleshooting, analysis, software and communications protocol development, and education. We can then run WireShark and filter traffic by ICMP. ICMP is a network layer protocol that relays messages concerning network connection issues. Ping uses this protocol - ping tests connectivity between hosts. When we filter wirehsark to only capture ICMP packets and ping the private IP address of our VM-2 linux machine we can visually see the packets on wireshark.
</p>

![image](https://user-images.githubusercontent.com/111653930/236505185-929b1b70-892c-4df8-951f-85176c8af952.png)


<br>
<p>
If you expand the "Internet Control Message Protocol" filter and hit "Data" you can see what was actually sent in each ping. 
</p>

![image](https://user-images.githubusercontent.com/111653930/236506627-f1e31060-4045-4f06-8362-dea0d61e91b6.png)
