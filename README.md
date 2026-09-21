# Enterprise Secure & High-Availability Network Infrastructure

A Cisco Packet Tracer enterprise network project implementing VLAN segmentation, Inter-VLAN routing, DHCP, HSRP, OSPF, ACL-based security, and switch port security.

## 📌 Project Overview

This project demonstrates a redundant and secure enterprise network infrastructure designed using **Cisco Packet Tracer**.

The network includes dual multilayer core switches, access switches, an edge router, centralized DHCP, dynamic routing, gateway redundancy, and basic network security controls.

## 🏗️ Network Topology

**Devices:**

* 1 × Cisco 2911 Edge Router
* 2 × Cisco 3560 Multilayer Switches
* 2 × Cisco 2960 Access Switches
* 1 × DHCP Server
* 8 × End-user PCs

### VLANs

| VLAN | Department | Network       |
| ---- | ---------- | ------------- |
| 10   | HR         | 10.10.10.0/24 |
| 20   | Finance    | 10.10.20.0/24 |
| 30   | IT         | 10.10.30.0/24 |
| 40   | Guest      | 10.10.40.0/24 |
| 50   | Server     | 10.10.50.0/24 |
| 99   | Management | 10.10.99.0/24 |

## ⚙️ Technologies & Features

* **VLAN & 802.1Q Trunking** – Network segmentation
* **Inter-VLAN Routing** – Communication between VLANs
* **DHCP & DHCP Relay** – Centralized IP address allocation
* **HSRP** – Default gateway redundancy and failover
* **OSPF** – Dynamic routing with redundant paths
* **Extended ACL** – Guest VLAN traffic restrictions
* **Port Security** – Sticky MAC-based access control

## 🔄 HSRP Design

HSRP provides redundant default gateways using:

```text
VLAN 10 → 10.10.10.1
VLAN 20 → 10.10.20.1
VLAN 30 → 10.10.30.1
VLAN 40 → 10.10.40.1
VLAN 50 → 10.10.50.1
VLAN 99 → 10.10.99.1
```

CORE1 is active for VLANs 10, 20, 30, while CORE2 is active for VLANs 40, 50, 99.

HSRP failover was also tested successfully.

## 🌐 OSPF

OSPF Area 0 is configured between the core and edge devices.

```text
CORE1 → Router ID 1.1.1.1
CORE2 → Router ID 2.2.2.2
EDGE-R1 → Router ID 3.3.3.3
```

OSPF neighbor relationships and routing tables were verified using Cisco IOS commands.

## 🔐 Security

### Guest VLAN ACL

The Guest VLAN is restricted from accessing internal HR, Finance, IT, and Server networks.

### Port Security

Access ports use:

```text
Maximum MAC addresses: 1
MAC learning: Sticky
Violation mode: Restrict
```

## 🧪 Verification

Network functionality was validated using:

```text
show vlan brief
show interfaces trunk
show ip interface brief
show standby brief
show ip ospf neighbor
show ip route
show access-lists
show port-security
ping
tracert
```

## 📁 Project Files

```text
Enterprise-Secure-High-Availability-Network.pkt
screenshots/
```

The `.pkt` file can be opened directly in **Cisco Packet Tracer**.

## 🖼️ Screenshots

Project screenshots covering the topology and major configurations are available in the `screenshots` folder.

## 👨‍💻 Author

**Prathmesh Dalavi**

B.E. Electronics & Telecommunication Engineering

Networking | Cisco | Network Security | Infrastructure

---

**Project Status:** Completed

**Tool:** Cisco Packet Tracer
