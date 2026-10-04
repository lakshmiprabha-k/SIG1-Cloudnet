Peer-to-Peer Local Area Network Verification

Lab Overview
This lab demonstrates a simple Peer-to-Peer Local Area Network using two computers connected through a Layer 2 switch. Static IPv4 addresses are configured and connectivity is verified using ping and ARP commands.

Objective
- Connect two PCs using a 2960 Layer 2 switch.
- Configure static IPv4 addresses.
- Verify connectivity between the PCs.
- Check the ARP table.

Tools Used
- Cisco Packet Tracer
- 2 PCs
- Cisco 2960-24TT Switch
- Copper Straight-Through Cable
- IPv4

Network Configuration
Device| IPv4 Address| Subnet Mask| Default Gateway
PC0| 192.168.10.25| 255.255.255.0| 192.168.10.1
PC1| 192.168.10.26| 255.255.255.0| 192.168.10.1

Connections
- PC0 FastEthernet0 → Switch0 FastEthernet0/1
- PC1 FastEthernet0 → Switch0 FastEthernet0/2

Configuration Steps
1. Added PC0, PC1 and a 2960-24TT switch.
2. Connected both PCs to the switch using Copper Straight-Through cables.
3. Configured PC0 with IP address "192.168.10.25".
4. Configured PC1 with IP address "192.168.10.26".
5. Used the same subnet mask "255.255.255.0".
6. Tested connectivity using the "ping" command.
7. Checked the ARP table using "arp -a".

Verification
The connection was successfully verified using:
ipconfig
ping 192.168.10.26
arp -a
The ping test was successful, confirming connectivity between PC0 and PC1.

Screenshots
The following screenshots are included:
- Network topology
- PC1 IP configuration
- Successful ping result

Project File
- "Peer-to-Peer-LAN-Verification.pkt"

Key Learning
This lab helped in understanding basic LAN connectivity, static IPv4 addressing, switch connections, ping testing, and ARP.
Conclusion

The Peer-to-Peer LAN was successfully configured and tested using Cisco Packet Tracer. Both PCs were connected through the switch and communication between them was verified successfully.
