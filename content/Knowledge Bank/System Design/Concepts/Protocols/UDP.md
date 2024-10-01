---
title: UDP
draft: false
tags:
  - protocol
---
**UDP is a connectionless protocol** that transmits data in units called **datagrams** (similar to packets). Unlike [[TCP]], which provides guarantees for data delivery, UDP offers reliability only at the datagram level. This means datagrams may arrive out of order, be lost entirely, or reach their destination without confirmation. Additionally, UDP does not implement congestion control, making it generally more efficient for certain applications.

One of the key features of UDP is its ability to **broadcast** datagrams to all devices on a subnet. This capability is particularly useful in scenarios like [[DHCP]], where the client has not yet received an IP address, thereby preventing the establishment of a [[TCP]] stream without an assigned address.

While UDP is less reliable than [[TCP]], it excels in real-time applications such as **VoIP** video chats (e.g., Zoom/Skype), streaming (Twitch), and real-time multiplayer games due to its lower latency.

## Use UDP over [[TCP]] when:

- You need the lowest latency.
- Late data is worse than loss of data
- You want to implement your own error correction