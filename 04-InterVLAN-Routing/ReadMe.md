# Case 04 — Inter-VLAN Routing

## Problem

VLANs create separate broadcast domains and cannot communicate with each other without Layer 3 routing.

## Solution

Implement Inter-VLAN Routing using Layer 3 switching and provide gateway redundancy with HSRP.

### Implementation

* Layer 3 Switching
* SVIs
* Inter-VLAN Routing
* HSRP
* Virtual Gateways
* Gateway Failover

## SVI Addressing

CORE-01 and CORE-02 provide Layer 3 connectivity for each VLAN.

```text
              CORE-01       CORE-02

VLAN 10       10.10.10.2    10.10.10.3
VLAN 20       10.10.20.2    10.10.20.3
VLAN 30       10.10.30.2    10.10.30.3
VLAN 40       10.10.40.2    10.10.40.3
VLAN 50       10.10.50.2    10.10.50.3
VLAN 60       10.10.60.2    10.10.60.3
VLAN 70       10.10.70.2    10.10.70.3
VLAN 80       10.10.80.2    10.10.80.3
VLAN 90       10.10.90.2    10.10.90.3
VLAN 99       10.10.99.2    10.10.99.3
VLAN 100      10.10.100.2   10.10.100.3
```

## HSRP

HSRP provides a redundant default gateway for each VLAN.

CORE-01 → Active
CORE-02 → Standby

The `.1` address of each subnet is used as the virtual default gateway.

```text
VLAN 10       10.10.10.1
VLAN 20       10.10.20.1
VLAN 30       10.10.30.1
VLAN 40       10.10.40.1
VLAN 50       10.10.50.1
VLAN 60       10.10.60.1
VLAN 70       10.10.70.1
VLAN 80       10.10.80.1
VLAN 90       10.10.90.1
VLAN 99       10.10.99.1
VLAN 100      10.10.100.1
```

### Addressing Convention

```text
.1 → HSRP Virtual Gateway
.2 → CORE-01 SVI
.3 → CORE-02 SVI
```

## Failover

Gateway failover was tested by disabling the active SVI on CORE-01.

CORE-02 successfully transitioned from Standby to Active while maintaining connectivity through the virtual gateway.

## Verification

```cisco
show ip interface brief
show ip route
show standby brief
```
