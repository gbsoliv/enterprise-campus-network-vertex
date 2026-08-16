# Vertex Solutions Enterprise Network

Vertex Solutions is a fictitious mid-sized technology company that requires a scalable and redundant campus network to support its daily operations.

The network was designed and implemented in Cisco Packet Tracer using a three-tier enterprise campus architecture.

## Business Requirements

- Support approximately 100 corporate users
- Segment departments and network services
- Provide network redundancy and high availability
- Provide centralized network services
- Secure the Layer 2 infrastructure

## Network Architecture

The network follows a three-tier campus design:

- Core Layer
- Distribution Layer
- Access Layer
- Edge Router

<img width="1035" height="643" alt="vertex-diagram" src="https://github.com/user-attachments/assets/45caadee-ea9f-4c2a-a599-1edbce3d9ad1" />


## Implementation

### Case 01 — Network Foundation

- Three-tier campus topology
- Management VLAN
- Management addressing

### Case 02 — VLAN Segmentation

- Access Ports
- Trunk Ports
- Native VLAN
- Voice VLAN
- VTP

### Case 03 — Layer 2 Redundancy

- Rapid PVST+
- Root Bridge
- Secondary Root
- EtherChannel (LACP)
- Redundant Uplinks

### Case 04 — Inter-VLAN Routing

- Layer 3 Switching
- SVIs
- Inter-VLAN Routing
- HSRP
- Gateway Failover

### Case 05 — DHCP

- Centralized DHCP Server
- DHCP Pools
- DHCP Relay
- Dynamic IP Assignment

### Case 06 — Layer 2 Security

- Unused Port Shutdown
- Port Security
- PortFast + BPDU Guard
- DHCP Snooping

### Case 08 — Edge Connectivity

- Layer 3 Routed Ports
- Point-to-Point Links
- Edge Router Connectivity

