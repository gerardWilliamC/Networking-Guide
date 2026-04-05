# Basic Switch-to-Switch Connectivity and VLAN

## Summary

This lab covers the foundational steps to set up a small switched network using three Cisco switches (S1, S2, S3) and four end-user PCs in Cisco Packet Tracer.

Each switch is assigned a management IP address on VLAN 1, and all PCs are placed on the `192.168.20.0/24` subnet. The goal is to verify that all devices can communicate with each other across the switches using basic Layer 2 connectivity.

## What You'll Learn

- How to configure hostnames, console passwords, enable passwords, and banners on a Cisco switch
- How to assign an IP address to a switch's VLAN 1 interface for in-band management
- How to assign static IP addresses to PCs and verify connectivity with `ping`

## Network Overview

| Device | IP Address      | Subnet Mask     |
|--------|-----------------|-----------------|
| S1     | 192.168.20.11   | 255.255.255.0   |
| S2     | 192.168.20.12   | 255.255.255.0   |
| S3     | 192.168.20.13   | 255.255.255.0   |
| PC1    | 192.168.20.21   | 255.255.255.0   |
| PC2    | 192.168.20.31   | 255.255.255.0   |
| PC3    | 192.168.20.41   | 255.255.255.0   |
| PC4    | 192.168.20.51   | 255.255.255.0   |

## Files

| File | Description |
|------|-------------|
| `Basic Switch to Switch Connectivity and VLAN.pkt` | Packet Tracer project file |
| `Basic Switch-to-Switch Connectivity and VLAN (Code Guide)` | CLI commands to configure the lab |
| `Basic Switch-to-Switch Connectivity and VLAN Summary Guide.pdf` | PDF walkthrough and reference |
