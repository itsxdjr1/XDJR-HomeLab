# Networking

## Overview

My MikroTik router is the main network device in my homelab. It handles routing,
firewalling, DNS, VPN access, and communication between different parts of the lab.

## Hardware

- MikroTik Hex S 
- Cisco Catalyst 2960S
- HPE ProLiant DL120 Gen9
- Lenovo ThinkServer RS140
- Cisco C220 M3

## What I Implemented

- LAN routing
- Firewall rules
- DNS
- DHCP
- WireGuard VPN
- VLAN support
- Internal service access
- Network segmentation
- Managed switching

## Network Design

The MikroTik acts as the gateway for the lab and controls traffic between systems.

The Cisco Catalyst 2960S provides managed switching and is used for network segmentation, specifically just segmented off my malware VMs (still in progress). Wanted to use a big enterprise grade Cisco Switch as I am studying the CCNA, and it's good practice.

I want to place things in different subnets based on use for ease of remembering stuff, but my number of devices isn't really big enough. Really only segment off the malware stuff right now.

## WireGuard Remote Access

I configured WireGuard so I can securely connect back to my homelab while away
from home (which is all the time).

This allows me to reach:

- Proxmox
- Graylog
- Windows systems
- Internal web services
- Server management interfaces

I also configured DNS so internal `.home.arpa` hostnames can be used while
connected through the VPN. I really was annoyed of typing in and remembering IPs, so this helped a bunch with easily remembering.

## What I Learned

- Routing between networks
- Firewall rule design
- DNS troubleshooting
- VPN routing
- Network segmentation
- Managed switching
- Layer 3 troubleshooting
- Testing connectivity step-by-step
