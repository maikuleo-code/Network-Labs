 Cisco-MultiVLAN-Network-Lab
📘 Overview
This lab project is designed to simulate a real-world enterprise network using Cisco Packet Tracer, implementing a multi-VLAN architecture with a hierarchical network design (Core, Aggregated, and Access Layers). It serves as part of my self-paced study and skills enhancement in preparation for a career in network security and enterprise networking.

🎯 Objectives
Design and configure a 3-tier network topology

Create and manage multiple VLANs (10–60)

Implement inter-VLAN routing using SVIs on the core switch

Configure DHCP and DNS servers

Use ip helper-address for DHCP relay

Enable trunk links between switches

Practice spanning-tree modes for redundancy and loop prevention

Document configurations clearly and consistently

🧩 Lab Topology Summary
Layer	Devices	Description
Core Layer	1 Layer 3 Switch	Inter-VLAN routing via SVIs
Distribution	2 Aggregated Switches	VLAN distribution via trunk links
Access Layer	4 Access Switches	End device connectivity
Servers	DHCP/DNS Server (VLAN 99)	IP address management & name resolution

VLANs:

VLAN 10 – Admin

VLAN 20 – HR

VLAN 30 – Engineering

VLAN 40 – Architecture

VLAN 50 – Guest

VLAN 60 – Costumer

VLAN 99 – Infrastructure Services (DHCP/DNS/Webserver)
