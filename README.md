
# 🌐 Cisco CCNA Mega Lab – Summary

> A full-scale enterprise network built in Cisco Packet Tracer covering every major CCNA topic in one unified topology.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Topology](#topology)
- [What I Built](#what-i-built)
- [Technologies Used](#technologies-used)
- [Key Highlights](#key-highlights)
- [Credits](#credits)

---

## Overview

This lab simulates a real enterprise network with two offices, a hierarchical 3-tier design (Core → Distribution → Access), WAN redundancy, and a wireless infrastructure — all configured from scratch across 13 devices.

| Stat | Detail |
|---|---|
| Total devices | 13 (1 router, 2 core, 4 distribution, 6 access) |
| Lab parts completed | 9 |
| Simulator | Cisco Packet Tracer |
| Difficulty | CCNA / Entry-level Enterprise |

---

## Topology

```
              Internet (Dual ISP)
                     |
                    R1
               /         \
           CSW1  ═══════  CSW2          ← Core Layer
          / | \ \       / / | \
     DSW-A1 DSW-A2   DSW-B1 DSW-B2     ← Distribution (HSRP)
       |  \  / |       |  \  / |
  ASW-A1 ASW-A2 ASW-A3  ASW-B1 ASW-B2 ASW-B3  ← Access Layer
```

---

## What I Built

| Part | Topic | Key Config |
|---|---|---|
| 1 | Initial Setup | Hostnames, enable secret (type 9), local user auth, console security |
| 2 | VLANs & L2 EtherChannel | VTP v2, trunking, PAgP & LACP EtherChannel |
| 3 | IPs, L3 EtherChannel & HSRP | /30 point-to-point links, HSRPv2 Active/Standby |
| 4 | Rapid Spanning Tree | Rapid PVST+, STP/HSRP alignment, PortFast, BPDU Guard |
| 5 | Static & Dynamic Routing | OSPFv2 Area 0, ASBR, floating static default routes |
| 6 | Network Services | DHCP, DNS, NTP (authenticated), SNMP, Syslog, SSH, NAT/PAT |
| 7 | Security | Extended ACLs, Port Security, DHCP Snooping, DAI |
| 8 | IPv6 | EUI-64 addressing, static & floating default routes |
| 9 | Wireless | WLC GUI, dynamic interface, WPA2/AES WLAN, LWAP association |

---

## Technologies Used

| Category | Technology |
|---|---|
| Routing | OSPFv2, Static & Floating Static Routes |
| Switching | VLANs, VTP v2, 802.1Q Trunking, Rapid PVST+ |
| EtherChannel | PAgP (L2 & L3), LACP (L2) |
| Redundancy | HSRPv2 |
| IP Services | DHCP, DNS, NTP, SNMP, Syslog, FTP, NAT/PAT |
| Security | SSHv2, ACLs, Port Security, DHCP Snooping, DAI |
| IPv6 | EUI-64, Static Routes |
| Wireless | WLC, Lightweight APs, WPA2/AES |
| Discovery | LLDP (CDP disabled) |

---

## Key Highlights

- **Dual WAN** on R1 with primary/floating static default routes and OSPF redistribution
- **HSRPv2** load-balanced across Distribution switches — Active/Standby intentionally split per VLAN
- **OSPF point-to-point** on all physical L3 links to eliminate DR/BDR elections
- **Full L2 security stack** — Port Security, DHCP Snooping, and DAI on all Access switches
- **NTP authentication** using MD5 key across all 13 devices
- **Static NAT + pool-based PAT** with Internet failover verification

---

## Credits

- Lab design: [Jeremy's IT Lab](https://www.youtube.com/@JeremysITLab) – CCNA Mega Lab series
- Simulator: [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer)

---
