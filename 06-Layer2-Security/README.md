# Case 06 — Layer 2 Security

## Problem

Access-layer switches are directly exposed to end devices, creating potential Layer 2 security risks and unauthorized network access.

## Solution

Implement basic Layer 2 security controls to protect access ports and DHCP traffic.

### Implementation

* Unused Port Shutdown
* Port Security
* PortFast + BPDU Guard
* DHCP Snooping

## Unused Ports

Unused switch ports were administratively disabled to prevent unauthorized devices from connecting to the network.

```cisco
interface range <unused-ports>
 shutdown
```

## Port Security

Port Security was configured on access ports using sticky MAC learning.

Single-device ports allow one MAC address, while ports shared by an IP Phone and PC allow two.

```cisco
switchport port-security
switchport port-security maximum <1-2>
switchport port-security mac-address sticky
switchport port-security violation shutdown
```

## PortFast and BPDU Guard

PortFast and BPDU Guard were enabled on edge ports.

PortFast provides faster connectivity for end devices, while BPDU Guard protects edge ports from unexpected STP BPDUs.

```cisco
spanning-tree portfast
spanning-tree bpduguard enable
```

## DHCP Snooping

DHCP Snooping was enabled on client VLANs to prevent unauthorized DHCP servers from providing network configuration to clients.

```cisco
ip dhcp snooping
ip dhcp snooping vlan 10,20,30,40,50,60,90
```

Uplinks toward the Distribution layer were configured as trusted interfaces.

```cisco
interface <uplink>
 ip dhcp snooping trust
```

The interface connected to the legitimate DHCP server was also configured as trusted.

## Verification

```cisco
show interfaces status
show port-security
show port-security address
show ip dhcp snooping
show ip dhcp snooping binding
```

DHCP Snooping bindings were verified on the Access switches, confirming that client IP and MAC information was learned correctly.
