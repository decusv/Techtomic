---
title: Hypervisor
draft: false
tags:
  - definition
  - system-design
---
## Definition

Hypervisor is a piece of firmware ([[#Type 1 Hypervisor (Bare-metal Hypervisor)|type 1]]) or software ([[#Type 2 (Hosted Hypervisor)|type 2]]) that allows a physical computer (also referred to as the **host**) to create and manage multiple [[Virtual Machine (VM)|virtual machines]] on the same hardware i.e., physical resources. Use of the hypervisor allows for better utilization of hardware sources by diving them across multiple [[Virtual Machine (VM)|virtual machines]].

## Analogy

Imagine your computer as a house with many rooms. A hypervisor is like a landlord who manages those rooms, making sure each room has what it needs (like electricity, water, etc.). Each room represents a virtual machine, and even though they all share the same house (the computer’s hardware), they each function independently as if they were separate houses.

---

# Hypervisor types

### Type 1  (Bare-metal Hypervisor)

Hypervisor that is built in directly into the firmware of the hardware. This means they run directly on the physical hardware without needing the underlying operating system. These are are often found in enterprise environments, where servers are designed to run multiple [[Virtual Machine (VM)|virtual machines]], e.g., a company hosting multiple [[Virtual Private Server (VPS)|Virtual Private Servers]] on the same hardware.

### Type 2 (Hosted Hypervisor)

Hypervisor that is running on top of an existing operating system just like any other software application e.g., VMWare, or VirtualBox. The host operating system interacts with the underlying hardware.