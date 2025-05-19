# University LAN Network Design - Cisco Packet Tracer Project

## 📘 Project Overview

This project simulates a LAN network for a university using Cisco Packet Tracer. The network is designed to serve approximately 230 devices across multiple buildings, optimized for scalability, IP address management, and internal/external communication. It uses VLAN segmentation combined with subnetting and DHCP for dynamic IP allocation.

## 🎯 Objectives

- Support up to 230 end-user devices
- Provide internet and local intranet access
- Allow future scalability with available IP addresses
- Use 192.168.2.0/24 IP range with subnetting
- Enable communication across VLANs
- Ensure devices obtain IP dynamically using DHCP
- Provide wireless connectivity in large open areas

## 🏛️ Network Layout

The university network is divided into 4 major zones:

1. **Building A**
   - 3 Labs: P1 (20 PCs), P2 (20 PCs), P3 (22 PCs)
   - Total: 62 devices

2. **Building B**
   - 3 Labs: Lab1 (20 PCs), Lab2 (20 PCs), Lab3 (22 PCs)
   - Total: 62 devices

3. **Auditorium**
   - No fixed PCs
   - 1 Wireless Router (up to ~60 wireless clients)

4. **Library**
   - 46 PCs
   - 2 Switches for device aggregation

Each zone is connected through individual switches to a **central switch**, which then connects to a **Cisco Router 2621XM** for VLAN routing and internet access.

## 🧩 Network Topology

- **Topology model**: Extended Star Topology
- Each building connects to the central switch via its local switch
- Central switch handles VLAN segmentation and trunking
- Router connects to the central switch for inter-VLAN routing

## 📶 VLAN and Subnet Allocation

| Zone        | VLAN | Network          | IP Range              | Broadcast        |
|-------------|------|------------------|------------------------|------------------|
| Building A  | 10   | 192.168.2.0/26   | 192.168.2.1 - .62      | 192.168.2.63     |
| Building B  | 20   | 192.168.2.64/26  | 192.168.2.65 - .126    | 192.168.2.127    |
| Auditorium  | 30   | 192.168.2.128/26 | 192.168.2.129 - .190   | 192.168.2.191    |
| Library     | 40   | 192.168.2.192/26 | 192.168.2.193 - .254   | 192.168.2.255    |

## 🛠️ Equipment Used

### 🔌 Switches

- **12 x Cisco 2950-24 Switches**
  - 24 Ethernet ports, 10/100 Mbps
  - VLAN support, Layer 2 switching

### 🌐 Routers

- **1 x Cisco 2621XM Router**
  - 2 x 10/100 Mbps Ethernet ports
  - 1 x Serial port, 1 x ISDN BRI
  - Supports OSPF, DHCP, DNS, Telnet, SSH
  - DHCP server for dynamic IP assignment

### 📡 Wireless

- **1 x Linksys WRT300N Wireless Router**
  - 802.11n Wi-Fi (2.4 GHz)
  - Up to 300 Mbps
  - 4 Ethernet ports

## ⚙️ Configuration Highlights

- **DHCP Configuration**: On Cisco 2621XM router to provide IP addresses dynamically for all VLANs
- **VLAN Configuration**: Implemented on the central switch and trunk port to router
- **Router-on-a-Stick**: Configured subinterfaces on FastEthernet 0/0 to route between VLANs
- **Dynamic Routing**: Used OSPF for efficient and scalable routing
- **Internet Simulation**: Devices can access simulated external network via the router

## ✅ Testing & Validation

- All end devices successfully received dynamic IPs via DHCP
- Devices in the same and different VLANs can communicate via routing
- Internet connectivity validated using simulated ping across networks

## 🧪 Tools

- **Cisco Packet Tracer** (Project file: `Mini_project.pkt`)
- **Documentation**: Report available in `Report.docx`

## 📎 Author

- **Name**: Khương Đình Chiến
- **Email**: Chiendlb03@gmail.com

---

