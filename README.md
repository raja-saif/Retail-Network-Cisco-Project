# Multi-Store Retail Chain Network (Cisco Packet Tracer)

A network simulated in Cisco Packet Tracer for a multi-store retail chain. Four districts and their shops connect to a central data router. Routing uses OSPF and RIP with redistribution, and a central DHCP server assigns addresses. This was the Computer Networks lab project (Fall 2024) at FAST-NUCES.

## 🌐 Features
- **Topology:**
  - 4 district routers, each with 2 end devices.
  - 3 shops per district, each with a router, a switch and 3 end devices.
  - All districts connect over serial links to a **central data router**, which links to the server.
- **OSPF:** used in Districts 1 and 2, which are split into OSPF **Area 0** and **Area 1**.
- **RIP:** used in Districts 3 and 4.
- **Route redistribution** on the central data router between OSPF and RIP, so all districts can reach each other.
- **Centralized DHCP:**
  - A server on `192.168.10.0/24` (DNS `192.168.10.3`) holds a pool for each subnet, for example `DR1`, `D2S1` and `D3R1`.
  - Each pool uses mask `255.255.255.0`, gateway `.1`, first address `.10` and up to 40 users.
- **Addressing:** each LAN and serial link has its own `192.168.x.0/24` subnet, from `192.168.10.0` through `192.168.45.0`.
- **Testing:** connectivity between subnets was verified (see the report).

## 🛠 Tech Stack / Tools
- Cisco Packet Tracer
- Cisco 2811 routers, 2960-24TT switches, Server-PT, PCs and laptops
- OSPF, RIP, route redistribution, DHCP

## 📁 Project Structure
```
Retail-Network-Cisco-Project/
├── i22-1353_F.pkt   # Packet Tracer topology and device configurations
└── i22-1353_F.pdf   # Project report: design, DHCP pools, routing tables, testing
```

## ▶️ How to Run
1. Install Cisco Packet Tracer.
2. Open `i22-1353_F.pkt` in Cisco Packet Tracer.
3. To check routing, run `show ip route` on the district and central routers. To check DHCP, ping between end devices in different districts or look at an end device's IP configuration.

The report, `i22-1353_F.pdf`, has screenshots of the topology, the DHCP pools and each router's routing table.

## 👤 Author
Raja Saif Ali — [GitHub](https://github.com/raja-saif) · [LinkedIn](https://www.linkedin.com/in/raja-saif-01702329a/)
