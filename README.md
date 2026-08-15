# Network-Lab---Short-Config---Troubleshoot

# Enterprise / Small Business (SOHO) Network Lab

**Aaron Smith**  
**July 3, 2026**

---

## 📋 Project Objective

The primary goal of this lab was to design, implement, and troubleshoot a realistic **Small Office / Home Office (SOHO)** network using **Cisco Packet Tracer**.

Key learning objectives included:
- Building a multi-switch star topology with a central router
- Configuring IP addressing, routing, and basic device connectivity
- Intentionally introducing configuration errors to practice systematic troubleshooting
- Demonstrating the difference between Layer 2 switching and Layer 3 routing
- Understanding the real-world risks of poor configurations (e.g., duplicate IPs in VLAN environments)

---

## 🖧 Physical Topology

**Devices Deployed:**
- **1 Router (R1)** – Equipped with NM-2FE2W module for additional Ethernet ports
- **4 Switches** (SW1, SW2, SW3, SW4)
- **1 Server**
- **6 End-User PCs**

**Connectivity:**
- Central router acting as the core of a star topology
- Straight-through Ethernet cables used throughout
- Designed to reflect real-world structured cabling practices (dedicated IT rooms and patch panels)

*(See detailed Packet Tracer screenshots on pages 3 and 7 of the full lab report)*

---

## 🌐 Logical Topology & IP Addressing Scheme

A clean, segmented subnet design was implemented:

| Subnet            | Purpose                    | Devices                  |
|-------------------|----------------------------|--------------------------|
| 192.168.1.0/24    | Management / Server        | Server (SW2)             |
| 192.168.2.0/24    | User Segment 1             | Devices on SW1           |
| 192.168.3.0/24    | User Segment 2             | Devices on SW3           |
| 192.168.4.0/24    | User Segment 3             | Devices on SW4           |

- Router serves as the default gateway for all subnets (`192.168.1.1`, etc.)
- Server configured at `192.168.1.100`

**Injected Error:** Duplicate IP address intentionally added to demonstrate troubleshooting challenges and the dangers of misconfiguration in production environments.

---

## ⚙️ Configuration & Implementation

**Router (R1):**
- Hostname configuration
- Interface IP addressing (FastEthernet and Ethernet ports)
- CLI commands: `hostname`, `interface`, `ip address`, `no shutdown`

**Switches:**
- Basic management configuration
- Port assignments optimized for performance

**Key Learning:**
- FastEthernet (100 Mbps) used for router-to-switch links
- Standard Ethernet (10 Mbps) sufficient for low-traffic end devices but highlights potential bottlenecks

---

## 🔍 Testing, Troubleshooting & Verification

**Phase 1 – Initial Testing:**
- Intra-switch communication worked (Layer 2 switching functional)
- Inter-segment connectivity revealed injected issues

**Troubleshooting Process:**
1. Identified symptoms using ping tests
2. Verified physical connectivity and interface status
3. Located duplicate IP conflict
4. Resolved configuration errors
5. Confirmed full network reachability

**Critical Insight:**
Even with a duplicate IP, local Layer 2 communication remained possible. However, this would cause major problems in a VLAN environment — reinforcing why proper IP management and documentation are essential in enterprise networks.

**Final Verification:**
- Successful end-to-end pings across all subnets
- Router routing table validated
- Server and client connectivity confirmed

*(Full CLI outputs and Packet Tracer screenshots available in the lab document)*

---

## 📚 Key Takeaways & Skills Demonstrated

- Strong understanding of OSI model (especially Layers 2 & 3)
- Practical troubleshooting methodology
- Importance of accurate IP planning and avoiding common configuration pitfalls
- Real-world implications of design decisions in SOHO and enterprise environments

This lab strengthened my foundational networking knowledge and troubleshooting abilities — directly applicable to CompTIA Network+, CCNA, and real IT support roles.

---

## 📎 Files & Resources

- **[Full Lab Report (PDF)]([(https://github.com/apacheclient/Network-Lab-Short-Config-and-Troubleshoot/blob/main/network-lab/Enterprise%20%20Small%20Business%20(SOHO)%20Network.pdf)])**
- Packet Tracer Project File (`.pkt`) – Available upon request/or if not already in file

---

**Aaron Smith**  
IT Professional | Network & Systems Enthusiast  
July 3, 2026

---

*This lab was completed as part of ongoing self-directed IT skill development.*
