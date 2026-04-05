# Four-Router Network Configuration

## Summary

This lab scales up to four Cisco routers (R1–R4) arranged in a ring topology, connected by four serial WAN links. Each router serves two local subnets through its Gigabit Ethernet interfaces, resulting in eight subnets and 16 PCs total. Static routes are configured on every router so that any PC can reach any other PC across the network.

This is a great exercise for understanding how static routing scales and how traffic flows through multiple hops in a more complex topology.

## What You'll Learn

- How to configure multiple Gigabit Ethernet and Serial interfaces on each router
- How to set the serial clock rate on DCE links
- How to write full static route tables for a multi-hop ring topology
- How traffic traverses multiple routers to reach distant subnets
- How to verify connectivity end-to-end with `ping`

## Topology

The four routers form a ring connected by serial links:

```
R1 —(11.0.0.x)— R2
|                 |
(14.0.0.x)   (12.0.0.x)
|                 |
R4 —(13.0.0.x)— R3
```

## Network Overview

| Router | LAN Subnet 1       | LAN Subnet 2       | Serial Links                          |
|--------|--------------------|--------------------|---------------------------------------|
| R1     | 192.168.10.0/24    | 192.168.11.0/24    | 11.0.0.1 (to R2), 14.0.0.2 (to R4)   |
| R2     | 10.1.1.0/24        | 10.1.2.0/24        | 11.0.0.2 (to R1), 12.0.0.1 (to R3)   |
| R3     | 172.16.22.0/24     | 172.16.23.0/24     | 12.0.0.2 (to R2), 13.0.0.1 (to R4)   |
| R4     | 192.0.41.0/24      | 192.0.42.0/24      | 13.0.0.2 (to R3), 14.0.0.1 (to R1)   |

**PC assignments** (2 PCs per subnet, 16 PCs total):

| PC    | IP Address    | Subnet Mask   | Default Gateway |
|-------|---------------|---------------|-----------------|
| PC1   | 192.168.10.2  | 255.255.255.0 | 192.168.10.1    |
| PC2   | 192.168.10.3  | 255.255.255.0 | 192.168.10.1    |
| PC3   | 192.168.11.2  | 255.255.255.0 | 192.168.11.1    |
| PC4   | 192.168.11.3  | 255.255.255.0 | 192.168.11.1    |
| PC5   | 10.1.1.2      | 255.255.255.0 | 10.1.1.1        |
| PC6   | 10.1.1.3      | 255.255.255.0 | 10.1.1.1        |
| PC7   | 10.1.2.2      | 255.255.255.0 | 10.1.2.1        |
| PC8   | 10.1.2.3      | 255.255.255.0 | 10.1.2.1        |
| PC9   | 172.16.22.2   | 255.255.255.0 | 172.16.22.1     |
| PC10  | 172.16.22.3   | 255.255.255.0 | 172.16.22.1     |
| PC11  | 172.16.23.2   | 255.255.255.0 | 172.16.23.1     |
| PC12  | 172.16.23.3   | 255.255.255.0 | 172.16.23.1     |
| PC13  | 192.0.41.2    | 255.255.255.0 | 192.0.41.1      |
| PC14  | 192.0.41.3    | 255.255.255.0 | 192.0.41.1      |
| PC15  | 192.0.42.2    | 255.255.255.0 | 192.0.42.1      |
| PC16  | 192.0.42.3    | 255.255.255.0 | 192.0.42.1      |

## Files

| File | Description |
|------|-------------|
| `Four-Router Network Configuration.pkt` | Packet Tracer project file |
| `Four-Router Network Configuration (Code Guide)` | CLI commands to configure the lab |
| `Four-Router Netwrok Configuration Summary Guide.pdf` | PDF walkthrough and reference |
