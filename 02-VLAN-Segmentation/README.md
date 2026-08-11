\# Case 02 — VLAN Segmentation



\## Problem:



The flat Layer 2 network don't provide isolation between departments.



\## Solution:



To improve security, the network will be segmented using IEEE 802.1Q VLANs.



\### Implementation



* VLAN Creation
* Access Ports
* Trunk Ports
* Native VLAN
* Voice VLAN



\## VLAN Design



&#x20;VLAN 10   EXECUTIVE

&#x20;VLAN 20   SALES

&#x20;VLAN 30   MARKETING

&#x20;VLAN 40   HR

&#x20;VLAN 50   OPERATIONS

&#x20;VLAN 60   ACCOUNTING

&#x20;VLAN 70   SERVERS

&#x20;VLAN 80   PRINTERS

&#x20;VLAN 90   WIRELESS

&#x20;VLAN 99   MANAGEMENT

&#x20;VLAN 100  VOICE

&#x20;VLAN 999  NATIVE





\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



\### ACC-01



VLAN 99  MANAGEMENT

Fa0/1 ───── VLAN 10  EXECUTIVE

Fa1/1 ───── VLAN 10  EXECUTIVE + VLAN 100 VOICE

Fa2/1 ───── VLAN 20  SALES + VLAN 100 VOICE

Fa3/1 ───── VLAN 20  SALES      

Fa6/1 ───── TRUNK                      



\### ACC-02



VLAN 99  MANAGEMENT

Fa0/1 ───── VLAN 30  MARKETING

Fa0/2 ───── VLAN 30  MARKETING

Fa0/3 ───── VLAN 40  HR

Fa6/1 ───── TRUNK



\### ACC-03



VLAN 99  MANAGEMENT

Fa0/1 ───── VLAN 50  OPERATIONS + VLAN 100 VOICE

Fa0/2 ───── VLAN 60  ACCOUNTING

VLAN 99  MANAGEMENT

Fa6/1 ───── TRUNK



\### ACC-04



VLAN 99  MANAGEMENT

Fa0/1 ───── VLAN 80  PRINTERS

Fa0/2 ───── VLAN 80  PRINTERS

Fa0/3 ───── VLAN 90  WIRELESS

Fa0/4 ───── VLAN 70  SERVERS

Fa0/5 ───── VLAN 70  SERVERS

Fa6/1 ───── TRUNK



