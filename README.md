Enterprise Network with Security & VLANs
📋 Project Overview
Objective: Design and implement a complete enterprise network with multiple departments, security policies, NAT, ACLs, VLANs, and internet connectivity.
Difficulty: Advanced
Completion Date: January 2025
🎯 Technologies Implemented

✅ VLANs - Network segmentation (VLAN 10, 20, 30, 100)
✅ Subnetting - VLSM for efficient IP address allocation
✅ Inter-VLAN Routing - Router-on-a-stick configuration
✅ NAT (Network Address Translation) - Private to public IP translation
✅ ACLs (Access Control Lists) - Security policies between departments
✅ STP - Spanning Tree Protocol with PortFast and BPDU Guard
✅ DMZ - Demilitarized zone for public servers
✅ Internet Routing - Default gateway and ISP connectivity

🏗️ Network Topology

Network Architecture
Three-Tier Design:

Connectivity Tests
Test 1: Inter-VLAN Communication
HR PC1 (10.0.0.2) → Finance PC1 (10.0.0.66): ✅ SUCCESS
Finance PC1 → HR PC1: ❌ BLOCKED by ACL
IT PC1 (10.0.0.34) → All departments: ✅ SUCCESS
Test 2: DMZ Access
All departments → Web Server (192.168.100.2): ✅ SUCCESS
All departments → Mail Server (192.168.100.3): ✅ SUCCESS
Test 3: Internet Connectivity (NAT)
HR PC1 → Internet (via NAT): ✅ SUCCESS
Finance PC1 → Internet (via NAT): ✅ SUCCESS
IT PC1 → Internet (via NAT): ✅ SUCCESS

! Verify NAT translation
Router1# show ip nat translations
Test 4: STP PortFast
! PC connections should come up immediately (no 30-second delay)
Switch# show spanning-tree interface fa0/1 portfast
Portfast: enabled
Test 5: BPDU Guard
! Connect rogue switch to access port
! Port should go into err-disabled state
Switch# show interfaces status err-disabled

Complete Topology - Full network diagram
VLAN Configuration - show vlan brief output
NAT Translations - show ip nat translations
ACL Rules - show access-lists
Ping Tests - Successful and blocked pings
Routing Table - show ip route with default route
STP Status - show spanning-tree with PortFast

Skills Demonstrated

✅ VLSM Subnetting - Efficient IP address allocation
✅ VLAN Design - Department segmentation
✅ Inter-VLAN Routing - Router-on-a-stick (802.1Q)
✅ NAT/PAT - Address translation for internet access
✅ ACLs - Security policy implementation
✅ STP - Loop prevention with PortFast and BPDU Guard
✅ DMZ Architecture - Public server isolation
✅ Default Routing - Internet connectivity
✅ Network Security - Multiple security layers

🔐 Security Features Implemented

Network Segmentation - VLANs isolate departments
Access Control - ACLs restrict inter-department traffic
DMZ - Public servers in separate zone
NAT - Hides internal addressing
STP Security - BPDU Guard prevents rogue switches
PortFast - Only on verified access ports

📚 Lessons Learned

VLSM Planning - Proper subnetting saves IP addresses
ACL Order Matters - Most specific rules first
NAT Inside/Outside - Critical to define correctly
PortFast Caution - Only enable on access ports to end devices
Testing is Critical - Verify each feature before moving on

Possible Enhancements

 Add DHCP server for automatic IP assignment
 Implement HSRP for router redundancy
 Add VPN for remote access
 Configure QoS for voice/video traffic
 Add wireless access points
 Implement 802.1X port authentication
 Add syslog server for monitoring

📁 Repository Files
CCNA Exam Topics Covered

✅ 2.0 Network Access (VLANs, Trunking)
✅ 3.0 IP Connectivity (Routing, Default Route)
✅ 4.0 IP Services (NAT, ACLs)
✅ 5.0 Security Fundamentals (ACLs, Port Security)
✅ STP, PortFast, BPDU Guard
