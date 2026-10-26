# Computer Networks Laboratory Programs

This repository contains Cisco Packet Tracer network simulation models (`.pkt`) created for the **Computer Networks Laboratory** course. The experiments encompass fundamental networking principles including LAN switching and hub behavior, router interface configuration and connectivity testing, dynamic host configuration protocol (DHCP) with relay agents across subnets, and static/default IP routing.

---

## 👨‍🎓 Student Details

| Field | Details |
| :--- | :--- |
| **Name** | Sarthak Thrishuleshwar |
| **USN** | 1BM24CS260 |
| **Section** | J |
| **Email** | [sarthak.cs24@bmsce.ac.in](mailto:sarthak.cs24@bmsce.ac.in) |
| **Institution** | B.M.S. College of Engineering (BMSCE) |

---

## 🧪 Lab Experiments Overview

| Lab # | Simulation File | Experiment Title | Objective & Expected Observations |
| :---: | :--- | :--- | :--- |
| **Lab 1** | [`1BM24CS260-1.pkt`](1BM24CS260-1.pkt) | **Communication using Switch and Hub** | Evaluate and compare unicast packet forwarding in a switch-based LAN vs. frame broadcasting in a hub-based LAN using ICMP ping packets. Verify isolation between distinct broadcast domains. |
| **Lab 2** | [`1BM24CS260-2.pkt`](1BM24CS260-2.pkt) | **Router Interfaces and Connectivity Testing** | Configure IPv4 addressing and subnet masks on router fast/gigabit ethernet interfaces. Test reachability between subnets and analyze ICMP outcomes (successful replies, request timed out, and destination host unreachable). |
| **Lab 3** | [`1BM24CS260-3.pkt`](1BM24CS260-3.pkt) | **DHCP & IP Address Assignment across Subnets** | Set up a central DHCP server providing IP pools for multiple local and remote LAN segments. Configure router IP helper addresses (`ip helper-address`) to relay broadcast DHCP discover messages across routers. |
| **Lab 4** | [`1BM24CS260-4.pkt`](1BM24CS260-4.pkt) | **Static and Default Route Configuration** | Implement static routes on the core router (`ip route <dest-network> <mask> <next-hop>`) and default routes (`0.0.0.0 0.0.0.0`) on perimeter/edge routers. Verify routing tables and end-to-end multi-hop connectivity. |

---

## 🛠️ Requirements & Tools

- **Software**: [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (Version 8.0 or newer recommended)
- **Protocols Covered**: ICMP, ARP, IPv4, DHCP, RIP / Static Routing

---

## 🚀 Execution & Verification Guide

1. **Launch Simulation**: Open the corresponding `.pkt` file inside Cisco Packet Tracer.
2. **Link Stabilization**: Wait a few moments until all link state indicators transition from amber/orange to green (indicating Spanning Tree Protocol convergence).
3. **End-to-End Connectivity (Labs 1–3)**:
   - Click on an end-user PC / laptop device.
   - Navigate to **Desktop → Command Prompt**.
   - Issue standard ping commands:
     ```bash
     ping <target-ip-address>
     ```
4. **DHCP Verification (Lab 3)**:
   - On the client PC, open **Desktop → IP Configuration**.
   - Toggle radio button from **Static** to **DHCP** and ensure IP address, subnet mask, and default gateway are assigned successfully.
5. **Routing Table Inspection (Lab 4)**:
   - Click on the designated router and navigate to the **CLI** tab.
   - Enter privileged EXEC mode:
     ```ios
     Router> enable
     Router# show ip route
     ```
   - Check for entries flagged with `S` (Static) or `S*` (Candidate Default).
   - Verify end-to-end ping across opposing edge LAN terminals.

---

## 🎯 Key Learning Outcomes

- Differentiating Layer 2 collision domains and broadcast domains across switches and hubs.
- Applying basic IPv4 subnet schemes and assigning gateway addresses to router interfaces.
- Understanding DHCP DORA exchanges and configuring DHCP relay agents across broadcast boundaries.
- Inspecting and managing IP routing tables with static and default routing paradigms.
