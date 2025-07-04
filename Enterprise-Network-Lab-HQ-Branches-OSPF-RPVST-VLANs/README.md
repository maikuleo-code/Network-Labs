Enterprise Network Lab Report

Title: Enterprise Network Lab: HQ + Branches with OSPF, VLANs, DHCP, and Rapid PVST+

Author: Michael Leo Salamanca

Role: Aspiring Network Security Engineer

Date: 4/07/2025

1. Project Overview
This lab simulates a scalable, enterprise-grade hierarchical network architecture composed of a Headquarters (HQ) and two Branch Offices. It serves as a foundational hands-on project that demonstrates advanced routing, switching, redundancy, and service provisioning techniques using Cisco technologies.
Key Features:
- Multi-site VLAN segmentation
- Layer 3 inter-VLAN routing via Core switches
- Dynamic routing using OSPFv2
- Rapid PVST+ for Layer 2 loop prevention
- Centralized DHCP/DNS server hosted at HQ
- Root bridge priority management for STP optimization
  
2. Technologies and Design
Layer	Technology
Layer 2	VLANs, Rapid PVST+, PortFast, BPDU Guard
Layer 3	Inter-VLAN Routing, OSPFv2, DHCP Relay
Protocols	OSPFv2, STP, DHCP
Design Model	3-Tier Hierarchical: Core, Distribution, Access
Simulation	Cisco Packet Tracer

3. VLAN Structure
Site	VLANs	Description
HQ	10–80	User, IT, Voice, Admin, etc.
Branch 1	90–110	Departmental VLANs for local use
Branch 2	120–140	VLANs for remote site departments
Global VLAN	50	Shared DHCP/DNS Server

4. Routing and DHCP Design
- All routers and Layer 3 switches operate within OSPF Area 0
- Inter-VLAN gateway interfaces configured via SVIs on the Core switch
- OSPF adjacencies formed between the HQ, Branch 1, Branch 2, and Core devices
- DHCP relay (ip helper-address) configured on VLAN interfaces at branches to forward to HQ DHCP server
  
5. Spanning Tree Protocol Setup
- STP Mode: Rapid PVST+
- Core Switch Priority: 4096 (Root Bridge)
- Distribution Switch Priority: 8192 (Secondary Root)
- Access Ports: Configured with portfast and bpduguard
- Trunk Ports: Configured as point-to-point links
  
6. Verification Checklist
✅ VLAN communication is operational via inter-VLAN routing
✅ OSPF routing tables are synchronized and adjacencies formed
✅ Central DHCP server successfully leases IPs to clients in all sites
✅ Spanning Tree root bridge roles are stable and manually controlled
✅ No broadcast storms or loops due to proper STP and trunk configuration
✅ Documentation is complete and submitted

7. Included Files
- enterprise-network-documentation.docx – Full project documentation
- topology.png – Visual network layout
- device-configs/ – Cisco CLI startup configurations
- notes.md – Manual testing logs and configuration notes
  
8. Future Enhancements
- Transition from single-area to multi-area OSPF
- Enforce Access Control Lists (ACLs) for VLAN segmentation and security
- Enable NAT, DHCP Snooping, and Port Security features
- Export configuration files for deployment on physical Cisco devices
- Replicate and enhance the project using GNS3 or EVE-NG
  
9. About the Author
Michael Leo Salamanca
Aspiring Network Security Engineer
Focused on enterprise infrastructure, vendor certifications (Fortinet, Cisco), and real-world lab implementations to pursue mastery in network security and architecture.
