---
title: DHCP
draft: false
tags:
  - protocol
---
Dynamic Host Configuration Protocol (DHCP) is used by devices to automatically receive an IP address, which is needed for them to communicate over a network. 

When a new device connects to a network, it doesn’t have an IP address yet. It needs to ask for one from a DHCP server. The device uses UDP to send a broadcast message akin to “Is there a DHCP server that can give me an IP address?”. This is needed because the device (e.g., smartphone) doesn't have an IP address, it can’t use [[TCP]], which requires a connection. Instead, it sends out a datagram that all devices on the subnet can see.