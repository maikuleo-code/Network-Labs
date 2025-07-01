\# 🏢 **Enterprise Network Lab: HQ + Branches with OSPF, VLANs, DHCP, and Rapid PVST+**



\## 👨‍💻 Engineer

\*\*Michael Leo Salamanca\*\*

Aspiring Network Security Engineer | Lab-Based Learner | Cisco \& Fortinet Focused



---



\## 🧠 Project Overview



This lab simulates an \*\*enterprise-grade hierarchical network\*\* that includes:



\- A \*\*Headquarters (HQ)\*\* and \*\*two Branch sites\*\*

\- Fully segmented \*\*VLAN architecture\*\*

\- \*\*Inter-VLAN routing\*\* via Layer 3 Core switches

\- \*\*OSPF\*\* dynamic routing between sites

\- \*\*Rapid PVST+\*\* for Layer 2 redundancy

\- \*\*Centralized DHCP/DNS server\*\* from HQ

\- Spanning Tree \*\*Root Bridge Control (Core: 4096, Distribution: 8192)\*\*



---



\## 🗂️ Technologies Used



| Layer | Technology |

|-------|------------|

| Layer 2 | VLANs, Rapid PVST+, PortFast, BPDU Guard |

| Layer 3 | Inter-VLAN Routing, OSPF, DHCP Relay |

| Protocols | OSPFv2, STP, DHCP |

| Design | 3-Tier (Core, Distribution, Access) |

| Tool | Cisco Packet Tracer |



---



\## 🧱 VLAN Design



| Site       | VLANs        | Description            |

|------------|--------------|------------------------|

| HQ         | 10–80        | User, IT, VoIP, etc.   |

| Branch 1   | 90–110       | Local site VLANs       |

| Branch 2   | 120–140      | Local site VLANs       |

| Global     | 50           | DHCP/DNS (shared)      |



---



\## 🔀 Routing Overview



\- \*\*OSPF Area 0\*\* for all routers (future plan: multi-area)

\- L3 Core handles \*\*SVIs\*\* for VLAN gatewaying

\- Routers form OSPF adjacencies with Core and each other

\- \*\*DHCP Helper\*\* used to relay requests from branches to HQ server



---



\## 🌲 Spanning Tree Setup



\- \*\*Mode:\*\* Rapid PVST+

\- \*\*Core Switches:\*\* Root bridge with `priority 4096`

\- \*\*Distribution Switches:\*\* Secondary root with `priority 8192`

\- \*\*Access Ports:\*\* `portfast` + `bpduguard`

\- \*\*Trunk Ports:\*\* `link-type point-to-point`



---



\## ✅ Verification Checklist



\- \[x] VLANs communicate via inter-VLAN routing

\- \[x] OSPF adjacencies formed between routers and core

\- \[x] DHCP server assigns IPs across all sites

\- \[x] STP prevents loops; root bridges manually controlled

\- \[x] Fully documented in `.docx`



---



\## 📘 Files Included



\- `enterprise-network-documentation.docx` – Full project report

\- `topology.png` – Network diagram

\- `device-configs/` – Per-device startup configs

\- `notes.md` – Manual notes and testing results



---



\## 🧭 Future Improvements



\- Convert OSPF to \*\*multi-area\*\*

\- Implement \*\*ACLs\*\* for VLAN access control

\- Add \*\*NAT\*\*, \*\*DHCP Snooping\*\*, and \*\*Port Security\*\*

\- Export configurations and scripts for real Cisco hardware

\- Replicate lab using \*\*GNS3\*\* or \*\*EVE-NG\*\*



---

