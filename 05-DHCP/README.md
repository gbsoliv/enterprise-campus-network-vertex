# Case 05 — DHCP

## Problem

Manually assigning IP addresses to end devices is inefficient and difficult to manage as the network grows.

## Solution

Implement a centralized DHCP service to automatically provide network configuration to client devices across multiple VLANs.

### Implementation

* Centralized DHCP Server
* DHCP Pools
* DHCP Relay
* Dynamic IP Assignment

## DHCP Server

A centralized DHCP server was configured in VLAN 70.

```text
IP Address       10.10.70.10
Subnet Mask      255.255.255.0
Default Gateway  10.10.70.1
```

Servers, printers, and network infrastructure remain statically addressed.

## DHCP Pools

Separate DHCP pools were created for each client VLAN.

```text
Pool         Network          Gateway        Start IP

EXECUTIVE    10.10.10.0/24    10.10.10.1     10.10.10.10
SALES        10.10.20.0/24    10.10.20.1     10.10.20.10
MARKETING    10.10.30.0/24    10.10.30.1     10.10.30.10
HR           10.10.40.0/24    10.10.40.1     10.10.40.10
OPERATIONS   10.10.50.0/24    10.10.50.1     10.10.50.10
ACCOUNTING   10.10.60.0/24    10.10.60.1     10.10.60.10
WIRELESS     10.10.90.0/24    10.10.90.1     10.10.90.10
```

## DHCP Relay

Because the DHCP server is located in a different VLAN, DHCP Relay was configured on the Layer 3 SVIs.

```cisco
interface vlan <id>
 ip helper-address 10.10.70.10
```

The helper address was configured on both Core switches to maintain DHCP availability with the redundant gateway design.

## Verification

Client devices successfully received:

* IP address from the correct VLAN pool
* `/24` subnet mask
* HSRP virtual gateway

DHCP connectivity was verified across all configured client VLANs.

