Subnet Mismatch and ARP Resolution Failure

Lab Overview
This lab demonstrates how a subnet mismatch can cause network communication to fail between two directly connected hosts.
PC0 and PC1 are configured on different subnets to observe ARP resolution failure using Cisco Packet Tracer Simulation Mode. The configuration is then corrected and connectivity is verified.

Objectives
- Configure two PCs with IPv4 addresses.
- Create a deliberate subnet mismatch.
- Observe ARP resolution using Simulation Mode.
- Identify the packet drop caused by the mismatch.
- Correct the IP configuration.
- Verify successful connectivity after fixing the problem.

Tools Used
- Cisco Packet Tracer
- Generic PCs
- Cisco 2960-24TT Switch
- Copper Straight-Through Cable
- Command Prompt
- IPv4 Networking
- Simulation Mode

Initial Network Configuration
Device| Interface| IPv4 Address| Subnet Mask
PC0| FastEthernet0| 192.168.10.10| 255.255.255.0
PC1| FastEthernet0| 192.168.20.20| 255.255.255.0

Connection
- PC0 FastEthernet0 → Switch0 FastEthernet0/1
- PC1 FastEthernet0 → Switch0 FastEthernet0/2

Configuration Steps
1. Create the Network
Place PC0, PC1, and a 2960-24TT switch in Cisco Packet Tracer.
Connect both PCs to the switch using Copper Straight-Through cables.
2. Configure PC0
Navigate to:
PC0 → Desktop → IP Configuration → Static
Enter:
IPv4 Address: 192.168.10.10
Subnet Mask: 255.255.255.0
3. Configure PC1
Navigate to:
PC1 → Desktop → IP Configuration → Static
Enter:
IPv4 Address: 192.168.20.20
Subnet Mask: 255.255.255.0
PC0 and PC1 are now intentionally placed on different subnets.
4. Open Simulation Mode
Switch from Realtime to Simulation Mode.
Open Edit Filters and enable only:
- ARP
- ICMP
5. Test the Mismatched Network
On PC0, open:
Desktop → Command Prompt
Run:
ping 192.168.20.20
The communication does not succeed because PC0 and PC1 are configured on different subnets.
6. Demonstrate ARP Failure
To observe the ARP request, temporarily change PC0's subnet mask to:
255.255.0.0
Keep PC1 as:
IP Address: 192.168.20.20
Subnet Mask: 255.255.255.0
Run the ping again:
ping 192.168.20.20
Use Capture/Forward in Simulation Mode.
The ARP request is sent toward PC1 but no valid ARP reply is received, resulting in a packet drop.
7. Fix the Configuration
Return to Realtime Mode.
Change PC0's subnet mask back to:
255.255.255.0
Change PC1 to the same subnet:
IPv4 Address: 192.168.10.11
Subnet Mask: 255.255.255.0
8. Verify Connectivity
On PC0, run:
ping 192.168.10.11
Successful replies confirm that the subnet mismatch has been corrected.

Verification Results
Test| Expected Result| Status
Initial IP Configuration| Different subnets configured| Passed
Ping with Subnet Mismatch| Communication fails| Observed
ARP Simulation| Packet drop observed| Observed
Corrected IP Configuration| Same subnet| Passed
Final Ping| Successful replies| Passed

Screenshots
The following screenshots were captured during the lab:
1. "topology.png" – PC0, Switch0, and PC1 topology
2. "pc0-config.png" – PC0 initial IP configuration
3. "pc1-mismatch.png" – PC1 different-subnet configuration
4. "simulation.png" – Simulation Mode with ARP/ICMP packets
5. "arp-drop.png" – ARP packet drop with red X
6. "successful-ping.png" – Successful ping after fixing the configuration

Project Files
- "README.md"
- "Day-4-Subnet-Mismatch.pkt"
- "topology.png"
- "pc0-config.png"
- "pc1-mismatch.png"
- "simulation.png"
- "arp-drop.png"
- "successful-ping.png"

Key Learning
- Learned how subnet mismatches affect network communication.
- Understood the role of ARP in local network communication.
- Learned how to use Simulation Mode to observe packets.
- Learned how to identify a packet drop.
- Learned how to correct an incorrect subnet configuration.

Conclusion
A subnet mismatch was intentionally created between PC0 and PC1 to observe ARP resolution failure in Cisco Packet Tracer. After correcting the IP configuration and placing both PCs on the same subnet, successful communication was verified using ping.
