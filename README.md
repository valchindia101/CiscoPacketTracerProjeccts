# Enterprise Network — VLAN Switching Lab

A Cisco Packet Tracer project demonstrating core enterprise switching concepts: VLAN segmentation, 802.1Q trunking, Spanning Tree Protocol, and EtherChannel link aggregation on a small multi-switch topology.

## Overview

This project simulates a small enterprise LAN where traffic is segmented into multiple VLANs across two or more switches, with redundant trunk links protected by STP and bundled via EtherChannel for increased throughput and resiliency.

## Topology

- **Devices:** 2–4 (switches and end hosts)
- **File:** [`ENTERPRISE_NETWORK.pkt`](./ENTERPRISE_NETWORK.pkt) — open with [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer)

*(Add a topology screenshot here, e.g. `![Topology](./topology.png)`)*

## Features Implemented

- **VLANs & 802.1Q Trunking** — End hosts segmented into separate broadcast domains, with trunk links carrying tagged traffic between switches.
- **Spanning Tree Protocol (STP)** — Loop prevention on redundant switch links, ensuring a single active forwarding path while blocking backup links.
- **EtherChannel** — Multiple physical links bundled into a single logical link for increased bandwidth and link redundancy between switches.

## Key Configuration Concepts

```text
# VLAN creation
vlan <id>
 name <VLAN_NAME>

# Trunk port configuration
interface <interface>
 switchport mode trunk
 switchport trunk allowed vlan <list>

# Access port assignment
interface <interface>
 switchport mode access
 switchport access vlan <id>

# EtherChannel (LACP/PAgP)
interface range <interfaces>
 channel-group <n> mode active
```

## How to Open

1. Install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free with a Cisco Networking Academy / NetAcad account).
2. Open `ENTERPRISE_NETWORK.pkt`.
3. Use Simulation mode to trace VLAN-tagged frames across trunk links, or `show` commands in each switch CLI to verify VLAN, STP, and EtherChannel state.

## Verification Commands

```text
show vlan brief
show interfaces trunk
show spanning-tree
show etherchannel summary
```

## Author

**Valderhaug Chindia**
Final-year BBIT (Networking), Strathmore University
[GitHub](https://github.com/valchindia101/PersonalProjects) · [TryHackMe](https://tryhackme.com/p/vlchindia)

## License

This project is for educational purposes as part of a networking portfolio.
