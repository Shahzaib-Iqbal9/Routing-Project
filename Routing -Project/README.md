
# Static Routing with 3 Routers - Cisco Packet Tracer Project

This project demonstrates static routing configuration across three routers using Cisco Packet Tracer. Each router connects to a local PC and is configured with unique subnets and static routes to enable full network communication.

## 🛠️ Network Topology

```
[PC0]---[Router0]---[Router1]---[Router2]---[PC2]
             |         |
            PC1       PC2
```

## 🌐 IP Scheme

| Device         | Interface      | IP Address       | Subnet Mask       | Gateway         |
|----------------|----------------|------------------|-------------------|------------------|
| PC0            | -              | 192.168.1.2      | 255.255.255.248   | 192.168.1.1      |
| Router0        | G0/0           | 192.168.1.1      | 255.255.255.248   | -                |
| Router0        | G0/1           | 192.168.1.18     | 255.255.255.248   | -                |
| Router1        | G0/1           | 192.168.1.19     | 255.255.255.248   | -                |
| Router1        | G0/2           | 192.168.1.33     | 255.255.255.248   | -                |
| Router2        | G0/2           | 192.168.1.34     | 255.255.255.248   | -                |
| PC1            | -              | 192.168.1.10     | 255.255.255.248   | 192.168.1.9      |
| Router1        | G0/0           | 192.168.1.9      | 255.255.255.248   | -                |
| PC2            | -              | 192.168.1.26     | 255.255.255.248   | 192.168.1.24     |
| Router2        | G0/0           | 192.168.1.24     | 255.255.255.248   | -                |

## 📌 Static Routing Commands

### Router 0

```
enable
configure terminal
ip route 192.168.1.8 255.255.255.248 192.168.1.18
ip route 192.168.1.24 255.255.255.248 192.168.1.18
ip route 192.168.1.32 255.255.255.248 192.168.1.18
exit
```

### Router 1

```
enable
configure terminal
ip route 192.168.1.0 255.255.255.248 192.168.1.18
ip route 192.168.1.24 255.255.255.248 192.168.1.34
exit
```

### Router 2

```
enable
configure terminal
ip route 192.168.1.0 255.255.255.248 192.168.1.33
ip route 192.168.1.8 255.255.255.248 192.168.1.33
exit
```

## ✅ Result

All three PCs (connected to Router 0, Router 1, and Router 2 respectively) can successfully communicate with each other using static routing.

## 📁 Files

- `.pkt` file (Cisco Packet Tracer topology)
- `README.md` (project documentation)

---

**Author:** Shahzaib Iqbal  
**Last Updated:** 2025-08-20
