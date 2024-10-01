---
title: TCP
draft: false
tags:
  - protocol
---
**Transmission Control Protocol (TCP)** establishes and terminates connections using a handshake (usually a three-way handshake). All packets sent are guaranteed to reach the destination in the original order without data corruption. Due to the guarantees, TCP may be slower compared to protocols like [[UDP]].

## Reliability mechanisms

1. Sequence numbers to ensure order.
2. Checksum fields to ensure data isn't corrupted.
3. Acknowledgement packets and automatic retransmission in case a packet with a specific sequence number has been lost.
5. Timeouts lead to retransmission. After multiple timeouts, connection is dropped.

TCP dynamically adjusts the flow of data and controls congestion to avoid overwhelming the network or causing delays, allowing it to make efficient use of the network's capacity to transmit data.

---

## Disadvantages of TCP

1. Can be resource intensive if a large number of TCP connections have to be open. Connection pooling (maintaining a pool of open connections and using them when needed) may be a useful alternative.

