# Case 02 — VLAN Segmentation

## Problem

The flat Layer 2 network does not provide isolation between departments.

## Solution

The network was segmented using IEEE 802.1Q VLANs to separate departments and infrastructure services.

### Implementation

- Access Ports
- 802.1Q Trunks
- Native VLAN
- Voice VLAN
- VTP

## VLAN Design

VLAN 10  EXECUTIVE  
VLAN 20  SALES  
VLAN 30  MARKETING  
VLAN 40  HR  
VLAN 50  OPERATIONS  
VLAN 60  ACCOUNTING  
VLAN 70  SERVERS  
VLAN 80  PRINTERS  
VLAN 90  WIRELESS  
VLAN 99  MANAGEMENT  
VLAN 100 VOICE  
VLAN 999 NATIVE  

## Access Layer

Access ports were assigned to their corresponding departmental VLANs.

IP phone interfaces use VLAN 100 for voice traffic while maintaining the appropriate data VLAN for connected workstations.

VLAN 99 is reserved for network management.

## Trunking

802.1Q trunks were configured between the Access, Distribution, and Core layers.

VLAN 999 is used as the native VLAN.

Only required VLANs are allowed across each trunk.

## VTP

VTPv2 is used between the Core and Distribution layers for centralized VLAN management.

CORE-01 → VTP Server  
CORE-02 → VTP Client  
DIST-01 → VTP Client  
DIST-02 → VTP Client  

Domain: VERTEX  
Version: 2

The Access layer is configured manually and does not rely on VTP.

## Verification

`show vlan brief`  
`show interfaces trunk`  
`show interfaces switchport`  
`show vtp status`

