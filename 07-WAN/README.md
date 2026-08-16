# Case 08 — WAN
## Problem

The campus network requires connectivity to an edge router for future external network access.

## Solution

Connect the Core layer to EDGE-01 using Layer 3 point-to-point links.

### Implementation

* Layer 3 Routed Ports
* Point-to-Point Links
* Edge Router Connectivity

## IP Addressing

```text id="0mvpvs"
CORE-01    10.255.0.1/30
EDGE-01    10.255.0.2/30

CORE-02    10.255.0.5/30
EDGE-01    10.255.0.6/30
```


