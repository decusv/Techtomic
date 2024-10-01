---
title: Remote Procedure Call (RPC)
draft: false
tags:
  - protocol
---
**Remote Procedure Call (RPC)** is a way for a program (called the **client**) to request that a procedure (or function) runs on another computer (called the **server**), as if it were calling that procedure locally. It allows different systems to communicate and work together over a network, making it easier for developers to build distributed applications. Remote calls are usually slower and less reliable than local calls so it is helpful to distinguish RPC calls from local calls.

RPCs can be considered as internal APIs, even if they technically differ in their communication styles and transport mechanisms.

---

## RPC Frameworks

1. Protobuf
2. Thrit
3. Avro

---

## Disadvantages of RPCs

1. Clients using an RPC closely depend on how it has been implemented on the server i.e., they are tightly coupled which may mean that any updates to the server implementation of RPC may also require updates to the client implementation.

2. Each new use case will require a new API/RPC method to be defined.

3. Can be difficult to debug RPCs given client and server may be on different machines, you may have to consider network problems, or mismatched expectations between client and server implementations.
