# Case 03 — Layer 2 Redundancy

## Problem

Redundant Layer 2 links can create switching loops and broadcast storms.

## Solution

Implement Layer 2 redundancy with loop prevention and link failover.

### Implementation

* Rapid STP
* Root and Secondary Root
* PortFast
* EtherChannel (LACP)
* Redundant Uplinks

## Rapid STP

Rapid PVST+ was implemented across the switching infrastructure.

CORE-01 → Root Primary
CORE-02 → Root Secondary

```cisco
spanning-tree mode rapid-pvst
```

## PortFast

PortFast was enabled on selected edge ports connected to servers, printers, and the wireless access point.

## EtherChannel

LACP was used to aggregate redundant physical links between the Core and Distribution layers.

```cisco
channel-group <id> mode active
```

## Redundant Uplinks

Redundant uplinks provide alternate paths between the Access, Distribution, and Core layers.

RSTP prevents Layer 2 loops and provides path failover.

## Verification

```cisco
show spanning-tree
show etherchannel summary
show interfaces trunk
```


