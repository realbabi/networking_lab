<h1>Using Arp and Mac Tables</h1>

<h2>Description</h2>
This lab shows how to use ARP and MAC tables to find the device's location and the port to which it is connected. Will focus on finding out where  MAC adress 3C43 is connected.
<br />


<h2>Utilities Used</h2>

- <b>PowerShell</b> - <b>Putty Terminal</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b> - <b>GNS3</b> - <b>VMware Workstation</b> - <b>Packet Tracer</b> 

<h2>Program walk-through:</h2>

<p align="center">
Setup switches and clients in a daisy chain: <br/>
<img src="https://i.imgur.com/oGuyi8i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 
 <p align="center">
Ping all devices from a single PC to build a complete APR table and use "arp -a" to display it. Locate the necessary MAC adress, we are focusing on finding 3C43: <br/>  
<br/>
<img src="https://i.imgur.com/VXrRcMD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Access the MAC adress table in the first switch with "show mac-address-table." Locate the required MAC, it is on interface G0/1, connected to Switch2. Will verify that with "show cdp neighbor":  <br/>
<img src="https://i.imgur.com/2R9XhjA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Do the same as above on Switch2 to find where MAC 3C43 is located. It is connected to G0/2 this time:  <br/>
<img src="https://i.imgur.com/n2qyZB1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On Switch3 we find MAC 3C43 connected to interfface FastEthernet F0/2:  <br/>
<img src="https://i.imgur.com/UwPXW3l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
RECAP: We used the ARP table to find the MAC adress of the computer with IP adress 10.0.0.19. We used the MAC-adress-table on each switch to find out which interface MAC 3C43 is connected to until we found the our MAC adress as the only adress on the interface.  <br/>
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
