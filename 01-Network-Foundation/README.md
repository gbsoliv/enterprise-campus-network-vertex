# Case 01 — Network Foundation

## Problem

Vertex Solutions requires an enterprise campus infrastructure capable of supporting approximately 100 users and future network services.

## Solution

Build a three-tier campus network using Core, Distribution, and Access layers with dedicated management addressing.

### Implementation

* Three-Tier Campus Topology
* Management VLAN
* Management IP Addressing
* Default Gateway
* MOTD Banner
* Cabling and Endpoint Placement
* Management VLAN

> vlan 99 name MANAGEMENT

> interface vlan 99
 ip address <ip-address> 255.255.255.0
Management Addressing

> Subnet: 10.10.99.0/24
> Gateway: 10.10.99.1

> CORE-01: 10.10.99.11
> CORE-02: 10.10.99.12

> DIST-01: 10.10.99.21
> DIST-02: 10.10.99.22

> ACC-01: 10.10.99.31
> ACC-02: 10.10.99.32
> ACC-03: 10.10.99.33
> ACC-04: 10.10.99.34

## Topology 

<img width="1235" height="686" alt="case01-Diagram " src="https://github.com/user-attachments/assets/6ea7455e-a309-449f-a917-26bf6fbc2995" />
