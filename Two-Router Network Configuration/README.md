# Two-Router Network Configuration

## Summary

This lab demonstrates how to connect two Cisco routers (R1 and R2) over a serial WAN link and enable communication between PCs on four separate subnets using static routing in Cisco Packet Tracer.

R1 serves two local subnets (`192.168.10.x` and `192.168.11.x`) and R2 serves two more (`10.1.1.x` and `10.1.2.x`). The routers are connected via a point-to-point serial link (`209.165.200.224/30`). Static routes are added to each router so that all 12 PCs can reach each other across the WAN.

## What You'll Learn

- How to configure Gigabit Ethernet and Serial interfaces on a Cisco router
- How to set up a point-to-point serial WAN link between two routers
- How to add static routes to enable inter-router communication
- How to secure routers with console passwords, enable secrets, and encrypted passwords
- How to verify end-to-end connectivity with `ping`

## Network Overview

**R1 side** — Serial link IP: `209.165.200.225`

| Device | IP Address      | Subnet Mask   | Default Gateway  |
|--------|-----------------|---------------|------------------|
| PC1    | 192.168.10.10   | 255.255.255.0 | 192.168.10.1     |
| PC2    | 192.168.10.11   | 255.255.255.0 | 192.168.10.1     |
| PC3    | 192.168.10.12   | 255.255.255.0 | 192.168.10.1     |
| PC4    | 192.168.11.10   | 255.255.255.0 | 192.168.11.1     |
| PC5    | 192.168.11.11   | 255.255.255.0 | 192.168.11.1     |
| PC6    | 192.168.11.12   | 255.255.255.0 | 192.168.11.1     |

**R2 side** — Serial link IP: `209.165.200.226`

| Device | IP Address  | Subnet Mask   | Default Gateway |
|--------|-------------|---------------|-----------------|
| PC7    | 10.1.1.10   | 255.255.255.0 | 10.1.1.1        |
| PC8    | 10.1.1.11   | 255.255.255.0 | 10.1.1.1        |
| PC9    | 10.1.1.12   | 255.255.255.0 | 10.1.1.1        |
| PC10   | 10.1.2.10   | 255.255.255.0 | 10.1.2.1        |
| PC11   | 10.1.2.11   | 255.255.255.0 | 10.1.2.1        |
| PC12   | 10.1.2.12   | 255.255.255.0 | 10.1.2.1        |

## Files

| File | Description |
|------|-------------|
| `Two-Router Network Configuration.pkt` | Packet Tracer project file |
| `Two-Router Network Configuration (Code Guide)` | CLI commands to configure the lab |
| `Two-Router Network Configuration Summary Guide.pdf` | PDF walkthrough and reference |
