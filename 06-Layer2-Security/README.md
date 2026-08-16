
# Case 06 — Layer 2 Security

## Problem

Layer 2 networks are vulnerable to unauthorized access, rogue devices, DHCP attacks, ARP spoofing, and switching attacks.

## Solution

Implement Layer 2 security controls to protect access ports and validate traffic within the campus network.

### Implementation

* Unused Port Shutdown
* Port Security
* PortFast + BPDU Guard
* DHCP Snooping
* Dynamic ARP Inspection (DAI)
* IP Source Guard

## Unused Ports

Unused switch ports were administratively disabled to prevent unauthorized devices from connecting to the network.

```cisco
interface range <unused-ports>
 shutdown
```

## Port Security

Port Security restricts access ports based on allowed MAC addresses and limits unauthorized devices.

```cisco
switchport port-security
```

## BPDU Guard

BPDU Guard protects edge ports from unauthorized switches participating in the Spanning Tree topology.

It is used together with PortFast on selected edge ports.

```cisco
spanning-tree portfast
spanning-tree bpduguard enable
```

## DHCP Snooping

DHCP Snooping protects the network against unauthorized DHCP servers and builds a trusted DHCP binding database.

```cisco
ip dhcp snooping
```

## Dynamic ARP Inspection

DAI validates ARP traffic using information learned through DHCP Snooping to help prevent ARP spoofing.

```cisco
ip arp inspection vlan <vlan-id>
```

## IP Source Guard

IP Source Guard restricts IP traffic on access ports using DHCP Snooping binding information.

```cisco
ip verify source
```

## Verification

```cisco
show port-security
show ip dhcp snooping
show ip dhcp snooping binding
show ip arp inspection
```
