# Static Routing with 3 Routers – Cisco Packet Tracer Project

This project demonstrates **static routing** between three routers in **Cisco Packet Tracer**, where each router is connected to its own PC. The goal is to configure routing manually (without dynamic protocols) so that all PCs can communicate with each other across different networks.

---

## 🛠️ Network Topology


---

## 🌐 IP Addressing Scheme

| Device         | Interface      | IP Address       | Subnet Mask         | Gateway         |
|----------------|----------------|------------------|----------------------|------------------|
| **PC0**        | -              | 192.168.1.2      | 255.255.255.248      | 192.168.1.1      |
| **Router0**    | G0/0           | 192.168.1.1      | 255.255.255.248      | -                |
|                | G0/1           | 192.168.1.18     | 255.255.255.248      | -                |
| **Router1**    | G0/0           | 192.168.1.9      | 255.255.255.248      | -                |
|                | G0/1           | 192.168.1.19     | 255.255.255.248      | -                |
|                | G0/2           | 192.168.1.33     | 255.255.255.248      | -                |
| **PC1**        | -              | 192.168.1.10     | 255.255.255.248      | 192.168.1.9      |
| **Router2**    | G0/0           | 192.168.1.24     | 255.255.255.248      | -                |
|                | G0/2           | 192.168.1.34     | 255.255.255.248      | -                |
| **PC2**        | -              | 192.168.1.26     | 255.255.255.248      | 192.168.1.24     |

---

## ⚙️ Static Routing Configuration

### 🔸 Router 0

```bash
enable
configure terminal
ip route 192.168.1.8 255.255.255.248 192.168.1.18
ip route 192.168.1.24 255.255.255.248 192.168.1.18
ip route 192.168.1.32 255.255.255.248 192.168.1.18
exit

enable
configure terminal
ip route 192.168.1.0 255.255.255.248 192.168.1.18
ip route 192.168.1.24 255.255.255.248 192.168.1.34
exit

enable
configure terminal
ip route 192.168.1.0 255.255.255.248 192.168.1.33
ip route 192.168.1.8 255.255.255.248 192.168.1.33
exit
