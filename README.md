# XDJR-HomeLab
# Personal Homelab

This repository documents my personal homelab and the projects I have built to gain hands-on experience with IT infrastructure, networking, virtualization, cybersecurity, monitoring, and automation.

*A lot of the finer details here were summarized with AI, but I also mixed in my own writing*

The lab gives me an environment where I can learn, build, and accidentally mess up without blowing up real systems. Gives me great ideas of what to do and what not to do in the real world. Also is practical (sometimes).

Here's the pic of the beast:

<img width="2078" height="1512" alt="image" src="https://github.com/user-attachments/assets/2a144d05-3915-4987-8c23-ecb8e8dc85dd" />

I know it's overkill, but I wanted experience with enterprise hardware. The switch in this picture has been upgraded.

## Lab Overview

My homelab currently includes several physical servers, network infrastructure, virtual machines, centralized logging, internal DNS, remote access, and custom automation.

### Hardware

* **HPE ProLiant DL120 Gen9**

  * 128 GB DDR4 RAM
  * Primary Proxmox virtualization host
  * Hosts several of my core services and virtual machines

* **Lenovo ThinkServer RS140**

  * 8 GB DDR3 RAM
  * Secondary Proxmox host
  * Used for lightweight services and experimentation

* **Cisco UCS C220 M3**

  * Approximately 64 GB RAM
  * Planned host for an isolated malware-analysis environment

* **Cisco Catalyst 2960S**

  * Managed switching
  * VLAN segmentation
  * Intended to support additional isolation for the malware-analysis environment

* **MikroTik Hex S Router**

  * Routing
  * Firewalling
  * DNS
  * WireGuard VPN
  * Network segmentation

---

## Virtualization

I use **Proxmox VE** as the primary virtualization platform in my homelab.

The environment allows me to create isolated Windows and Linux systems for testing infrastructure, security tools, services, and different network configurations.

My primary Proxmox host is the HPE DL120 Gen9, with the Lenovo RS140 serving as a smaller secondary host.


## Graylog SIEM

One of the largest projects in my homelab is a centralized logging and monitoring environment built with **Graylog**.

I know its not very practical since my homelab isn't public facing, and its really only me and one other person on there. But I really wanted to be able to understand the entire SIEM topology and be able to navigate them for future security roles.

I currently ingest logs from multiple systems, including:

* Windows 10
* Windows 11
* MikroTik RouterOS
* Proxmox

Windows systems send event logs through **Graylog Sidecar and Winlogbeat**.

I have built streams, searches, and alerts around Windows authentication activity, including successful and failed logon events.


---

## Networking

My MikroTik router serves as the primary router, firewall, and DNS server (besides the Caddy for reverse proxy) for the lab.

The Cisco Catalyst 2960S provides managed switching and will also play a larger role in my planned malware-analysis network.

---

## WireGuard VPN

I use **WireGuard** to remotely access my homelab.

I used WireGuard because of how easy it is to use, I've tried other services, and WireGuard is by far my favorite.

This allows me to securely connect to internal systems while away from the network and access services such as remote desktops, management interfaces, and internal web applications.

---

## Internal DNS and Reverse Proxy

Instead of accessing every internal service using an IP address and port number, I configured internal DNS and **Caddy** as a reverse proxy.

Internal services can use names under the `.home.arpa` namespace.

Example:

```text
https://service.home.arpa
```

Caddy handles HTTPS and forwards requests to the appropriate backend service.

---

## HPE iLO and Redfish Automation

I also built an Android application that communicates with the **HPE iLO 4 Redfish API** on my DL120 Gen9.

The application allows me to remotely control the server's power state from my phone.

The project includes functionality such as:

* Checking server status
* Powering the server on
* Forcing the server off
* Communicating with the Redfish REST API


This was mostly so that I can save power lol

---

## Planned Malware Analysis Environment

I really love malware analysis, so I decided to make a malware lab/sandbox.

The **Cisco C220 M3** is planned to serve as the virtualization host for malware-analysis VMs.

The goal is to create an environment where potentially malicious software can be analyzed without exposing trusted systems on my network.

The planned architecture includes:

* Dedicated malware-analysis VMs
* Cisco Catalyst 2960S network segmentation
* Dedicated VLANs
* MikroTik firewall restrictions
* Isolation from trusted systems
* Controlled network access when required
* Centralized logging and monitoring

This environment is currently **planned and not yet fully implemented**.


## So what skills have I learned? Here is a brief overview of skills I've developed

### Networking

* TCP/IP
* Routing
* VLANs
* Firewall policies
* DNS
* DHCP
* WireGuard
* Network segmentation
* Managed switching

### Security

* SIEM
* Centralized logging
* Windows Event Logs
* Detection engineering
* Alert tuning
* Network isolation
* Security monitoring

### Systems Administration

* Proxmox VE
* Linux
* Windows
* Server hardware
* HPE iLO
* Virtual machines
* Internal services

### Automation and Development

* REST APIs
* Redfish
* Android development
* Scripting
* Service automation
  

## Purpose

My goal with this lab is to gain hands-on experience outside of my classes and work, I also use it for practical uses. Being able to use Windows when I use mainly Linux as my daily driver is nice. I just spin up a VM and can RDP into it. 

Hopefully you enjoyed the summary! Keep looking to see fun pictures and more details on each smaller thing.

