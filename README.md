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

![5](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/9a035cab-3b51-435a-b51c-e3b57e71b44b)
<br>
Opening up Powershell and pinging VM 2 private IP address. Once we have pinged the address we can see that there where four packets sent and recieved with 
zero packets lost.
<br>
<br>

![6](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/56de7a96-8e01-428f-9019-846dc20687c9)
<br>
Within Powershell we are going to perpetual ping on using VM 2 private IP address 10.0.0.5 -t 
<br>
<br>

![7](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/7e9a5092-e0b0-4057-892a-6559aa393d7a)
<br>
We are now going to proceed and open up the Network Security Group for VM2. From here we are going to create an inbound rule that will 
deny all inbound ICMP traffic. Once this rule is added the traffic will be blocked.
<br>
<br>

![8](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/cfb62f7b-3323-4b8e-a7f1-c621bfda9089)
<br>
Now we are able to see that the request has timed out.
<br>
<br>

![9](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/c4ec10f0-6577-4060-8256-34f49ddfeb2e)
<br>
Our VM is now replying to us again now that we have deleted the inbound rule.
<br>
<br>

![10](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/e9abfbcf-914c-4083-972f-d5f46c46d4d3)
<br>
Now we are filtering for SSH traffic and we will input Yes to continue. Notice the traffic in wireshark. 
<br>
<br>

![11](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/12d1104c-21d3-4741-8234-5962c1951942)
<br>
At this point we will input the password for VM2 remembering that we will not be able to see the input.
<br>
<br>

![12](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/fc9fd588-0c0a-4280-9f0b-2ec87a681935)
<br>
We can tell that we are logged into VM2 now. Our user profile has popped up.
<br>
<br>

![13](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/1af775db-dd97-4c24-8258-6ecc56c5fb49)
<br>
We are now using different commands on the linux command line and observing the traffic. Once we are done we will exit. Then ipconfig to make sure we are back on VM 1.
<br>
<br>

![14](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/0f651385-2400-49a0-acab-68ac822502bd)
<br>
Observing DHCP traffic now. We can see the new address being shown.
<br>
<br>

![15](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/f4e4cf8d-72b3-4757-b9c8-b59fd339826e)
<br>
Now we are filtering for DNS Traffic.
<br>
<br>

![16](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/0d66dcea-be3c-4d8f-a324-fcbe874879ca)
<br>
We can ask our DNS server whats the ip address for any site. As we can see we looked up www.msn.com and it shows the ip address for msn.
<br>
<br>
![17](https://github.com/Terry-Jackson/Network-Protocols/assets/155121596/ebd0ee48-11b3-446b-9269-49d896eb4ee3)
<br> 
Viewing the RDP traffic using tcp.port==3389.







