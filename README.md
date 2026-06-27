# Enterprise Hospital Network Infrastructure 🏥💻

## Project Overview
This repository contains the comprehensive design and configuration of an enterprise-grade hospital network. The architecture ensures secure, highly available, and efficient communication between critical hospital departments, including Doctors, Nurses, HR, Finance, and central services. 
- The simulation and configuration were developed using Cisco Packet Tracer.

**Team Asjed**
Prepared by: Tasneem Adel Khamis Soliman & Fatema Ahmed Khalil Ibrahim

---

## Key Features & Technologies Implemented

* **Network Segmentation (VLANs & ROAS):** Separated departmental traffic (Doctors VLAN 20, Nurses VLAN 30, HR VLAN 10, Finance VLAN 40) to enforce security and optimize performance, utilizing Router-on-a-Stick (ROAS) for Inter-VLAN routing.
* **Dynamic Routing (OSPF):** Configured Single-Area OSPF to enable automated, loop-free route discovery and efficient communication across the core, staff, and administration network segments.
* **High Availability (HSRP):** Implemented Hot Standby Router Protocol (HSRP) to provide seamless gateway redundancy and failover protection for the Staff Network.
* **Link Aggregation (EtherChannel):** Deployed LACP (active-active mode) to bundle physical links between switches, maximizing bandwidth and providing Layer 2 redundancy.
* **Secure Device Access (AAA & SSH):** Centralized device login authentication using a RADIUS server with a local database fallback, alongside secure remote access configuration via SSH.
* **IP Management (DHCP & Relay):** Centralized IPv4 address distribution using a dedicated DHCP server and configured IP helper-addresses (DHCP Relay) on routers to serve isolated VLANs.
* **Network Address Translation (Static NAT):** Configured Static NAT to map private inside local IPs to inside global IPs, securely exposing internal standalone servers (Web, AAA, DHCP, FTP).
* **Configuration Backups (FTP):** Utilized an FTP server to securely store and manage configuration backups for network switches and routers.

---

## Topology Structure

The network is logically divided into several functional zones:
1.  **Central Core:** The heart of the topology routing traffic between all major blocks.
2.  **Staff Network:** Hosts the Doctors and Nurses departments, utilizing HSRP for gateway redundancy and EtherChannel for switch-to-router link aggregation.
3.  **Administration Network:** Hosts the Human Resources (HR) and Finance departments.
4.  **Server Farm:** Contains the centralized AAA RADIUS, DHCP, FTP, and Web servers, securely accessible via NAT.

---

## How to Run
1. Clone this repository.
2. Open the `.pkt` topology file using **Cisco Packet Tracer**.
3. All devices are pre-configured. You can access the device CLIs using the management credentials configured via the AAA RADIUS server.

## Management Credentials
* Authentication is handled via the central RADIUS server.
* *Note: Ensure the AAA server is reachable for network access, otherwise devices will fall back to local authentication.*

---

## 📁 Project Documentation
📄 **[View Full Project PDF](./HospitalNetwork.pdf)**
