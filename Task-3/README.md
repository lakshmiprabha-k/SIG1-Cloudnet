Ping Troubleshooting and Network Connectivity Verification

Lab Overview
This lab demonstrates a systematic method for troubleshooting ping failures in Cisco Packet Tracer.
The network is checked from the physical connection to IP configuration, ping connectivity, and ARP resolution.

Objectives
- Check the physical network connection.
- Verify IPv4 configuration on both PCs.
- Identify common causes of ping failure.
- Test local and remote connectivity using ping.
- Verify ARP entries using "arp -a".
- Understand basic Layer 1, Layer 2, and Layer 3 troubleshooting.

Tools Used
- Cisco Packet Tracer
- Generic PCs
- Cisco 2960-24TT Switch
- Copper Straight-Through Cable
- Command Prompt
- IPv4 Networking

Network Configuration
Device| Interface| IPv4 Address| Subnet Mask| Default Gateway
PC0| FastEthernet0| 192.168.10.25| 255.255.255.0| 192.168.10.1
PC1| FastEthernet0| 192.168.10.26| 255.255.255.0| 192.168.10.1

Connection
- PC0 FastEthernet0 → Switch0 FastEthernet0/1
- PC1 FastEthernet0 → Switch0 FastEthernet0/2

Troubleshooting Steps
1. Check the Physical Connection
Check the link lights between the PCs and Switch0.
A green link indicates that the connection is active.
If the link is amber, wait for the switch to complete its startup process or use Fast Forward Time.
2. Verify PC0 Configuration
Open:
PC0 → Desktop → Command Prompt
Run:
ipconfig /all
Check that PC0 has the correct IPv4 address, subnet mask, and default gateway.
3. Verify PC1 Configuration
Open:
PC1 → Desktop → Command Prompt
Run:
ipconfig /all
Check that PC1 has the correct IPv4 address, subnet mask, and default gateway.
4. Test the Local TCP/IP Stack
On PC0, run:
ping 127.0.0.1
A successful reply confirms that the local TCP/IP stack is working.
5. Test the Assigned IP Address
On PC0, run:
ping 192.168.10.25
A successful response confirms that PC0 responds to its own configured IPv4 address.
6. Test PC0 to PC1 Connectivity
On PC0, run:
ping 192.168.10.26
Successful replies confirm connectivity between PC0 and PC1.
The first ping may sometimes fail because ARP needs to resolve the destination MAC address.
7. Check the ARP Table
On PC0, run:
arp -a
The ARP table should contain an entry for:
192.168.10.26
with the MAC address of PC1.

Common Troubleshooting Checks
Problem| Possible Cause| Action
Request timed out| Wrong IP configuration| Check "ipconfig /all"
Destination host unreachable| Different subnet or incorrect configuration| Check IP addresses and subnet masks
Red link| Cable or interface problem| Check the cable and connections
Amber link| Switch startup/STP convergence| Wait or use Fast Forward Time
First ping fails| ARP resolution| Run ping again and check "arp -a"
Duplicate IP| Same IP assigned to two devices| Check the IP configuration

Verification Results
Test| Expected Result| Status
Physical Link| Green connection| Passed
PC0 IP Configuration| Correct IPv4 parameters| Passed
PC1 IP Configuration| Correct IPv4 parameters| Passed
Ping PC0 to PC1| Successful replies| Passed
ARP Verification| PC1 IP/MAC entry displayed| Passed

Screenshots
The following screenshots were captured during the lab:
1. "topology.png" – PC0 and PC1 connected to Switch0
2. "pc0-ipconfig.png" – PC0 IP configuration
3. "pc1-ipconfig.png" – PC1 IP configuration
4. "ping.png" – Successful ping from PC0 to PC1
5. "arp.png" – ARP table showing PC1 entry

Project Files
- "README.md"
- "Ping-Troubleshooting.pkt"
- "topology.png"
- "pc0-ipconfig.png"
- "pc1-ipconfig.png"
- "ping.png"
- "arp.png"

Key Learning
- Learned how to troubleshoot network connectivity step by step.
- Understood basic Layer 1, Layer 2, and Layer 3 problems.
- Learned how to verify IP configuration using "ipconfig /all".
- Learned how to test connectivity using ping.
- Learned how ARP maps an IPv4 address to a MAC address.

Conclusion
The network was systematically checked from the physical connection to IP configuration and ARP resolution. Successful ping and ARP verification confirmed connectivity between PC0 and PC1.
