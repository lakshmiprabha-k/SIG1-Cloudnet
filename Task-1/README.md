Single-Host Static IPv4 Addressing & Local Loopback Verification

Lab Overview
This lab demonstrates how to configure a single workstation with a static IPv4 address and connect it to a Layer 2 switch using Cisco Packet Tracer.
The configured IP address is verified using a ping test.

Objectives
- Configure a static IPv4 address on PC0.
- Connect PC0 to a 2960 Layer 2 switch.
- Configure the subnet mask, default gateway, and DNS server.
- Verify the configured IP address.
- Test connectivity using ping.

Tools Used
- Cisco Packet Tracer
- Generic PC
- Cisco 2960-24TT Switch
- Copper Straight-Through Cable
- IPv4 Networking
- Command Prompt

Network Configuration
Device| Interface| IPv4 Address| Subnet Mask| Default Gateway
PC0| FastEthernet0| 192.168.10.25| 255.255.255.0| 192.168.10.1
DNS Server: 8.8.8.8

Connection
- PC0 FastEthernet0 → Switch0 FastEthernet0/1

Configuration Steps
1. Add Devices
Place the following devices in Cisco Packet Tracer:
- PC0
- 2960-24TT Switch0
2. Connect the Devices
Use a Copper Straight-Through cable.
Connect:
"PC0 FastEthernet0 → Switch0 FastEthernet0/1"
Wait for the link to turn green.
3. Configure PC0
Go to:
PC0 → Desktop → IP Configuration → Static
Enter:
IPv4 Address:    192.168.10.25
Subnet Mask:     255.255.255.0
Default Gateway: 192.168.10.1
DNS Server:      8.8.8.8
4. Verify the Configuration
Open:
PC0 → Desktop → Command Prompt
Run:
ping 192.168.10.25
A successful reply confirms that PC0 responds to its configured IPv4 address.

Verification Results
Test| Expected Result| Status
PC0–Switch0 Connection| Link is active| Passed
Static IPv4 Configuration| Correct IP parameters| Passed
Ping Test| Successful replies| Passed

Screenshots
- "topology.png" – PC0 connected to Switch0
- "ip-config.png" – PC0 static IP configuration
- "ping.png" – Successful ping verification

Project Files
- "README.md"
- "Single-Host-Static-IPv4-Verification.pkt"
- "topology.png"
- "ip-config.png"
- "ping.png"

Key Learning
- Learned how to configure a static IPv4 address.
- Learned how to connect a PC to a Layer 2 switch.
- Learned how to configure network parameters.
- Learned how to verify connectivity using ping.

Conclusion
PC0 was successfully configured with a static IPv4 address and connected to a 2960 Layer 2 switch. The network configuration and connectivity were successfully verified using ping.
