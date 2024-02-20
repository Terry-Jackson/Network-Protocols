<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<br>

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

- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>

<p>

![F](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/94df29ac-c72c-4bcd-9f4f-8e5bf54f189a)


</p>
<p>
First we will setup our VM within our Resource Group. Once that has been established with windows 10 OS. We will then create our second VM with Ubuntu Server 20.04. Making sure this is all under the same Resource Group.
</p>
<br />

<p>

  ![N](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/96a39fee-46ab-485d-a66b-80c7580173f8)

</p>
<p>
Now that we have both Virtual Machines running.We will remote into first "VM" by pasting Public IP into address for Remote Desktop.

</p>
<br />

<p>

  ![o](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/c67282f7-a9d0-48a5-9a49-259a229bc705)
</p>
<p>
Logging into Virtual Machine one now to download Wireshark in order to observe ICMP Traffic flow.
</p>
<br />
<br>

![tempsnip](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/ea33432c-b2ce-4e49-b334-6e49ab23c6d4)
<br>
Now we will proceed and go through the setup wizard to install.
<br>
<br>
![tempsni2](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/23f77eaa-b39a-4f12-88ec-fdfcfdeb8af9)
<br>
Click on the shark button top left corner in order to view live traffic and to capture packets.
<br>
<br>

![tempsnip3](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/6c1f453f-bbb5-4475-a812-f07a50463f8f)
<br>
Now we are observing ICMP traffic flow.
<br>
<br>

![tempsnip4](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/1117e1de-7232-4ff8-8b03-306c214efe31)
<br>
Opening up command prompt and pinging VM 2 private IP address. Once we have pinged the address we can see that there where four packets sent and recieved with 
zero packets lost.



