---
title: IP Subnetting
parent: Computer Networking
# has_children: true
nav_order: 2
---

# IP Subnetting

### Class

Class | Range     | Subnet Mask   | Subnet Mask
----- | --------- | ------------- | -----
A     | 001 - 127 | 255.0.0.0     | /8
B     | 128 - 191 | 255.255.0.0   | /16
C     | 192 - 223 | 255.255.255.0 | /24

### Example: 192.168.1.55/24

Class: C (Because 192 in range 192-223)

NetID: 24 bits

HostID: 8 bits

Number of usable hosts: 2^8 - 2 = 254

IP Address  | 192       | 168       | 1         | 55            | Result
----------- | --------- | --------- | --------- | ------------- | ---------
HostIP      | 1100 0000 | 1010 1000 | 0000 0001 | 0011 0111     | 192.168.1.55
Subnet Mask | 1111 1111 | 1111 1111 | 1111 1111 | 0000 0000     | 255.255.255.0
Net Address | 1100 0000 | 1010 1000 | 0000 0001 | ***0000 0000*** | 192.168.1.0
Broadcast   | 1100 0000 | 1010 1000 | 0000 0001 | ***1111 1111*** | 192.168.1.255

Host range: 192.168.1.1 - 192.168.1.254

## Subnetting

### Example: 192.168.1.0/24 -> 6 subnets

* Subnetting at Byte 4 (because /24)
* Minimum bits to used: **3** bits (because 2^3=8 > 6)
* 32 bits = 24 bits NetID + **3** bits Subnet + **5** bits HostID
* Jump: 2^**5** = 32
* Number of usable hosts: 30

Subnet | Subnet Mask | Broadcast | Host Range
- | - | - | -
192.168.1.**0**   | /27 | 192.168.1.**31** | 192.168.1.**1** - 192.168.1.**30**
192.168.1.**32**  | /27 | 192.168.1.**63** | 192.168.1.**33** - 192.168.1.**62**
192.168.1.**64**  | /27 | 192.168.1.**95** | 192.168.1.**65** - 192.168.1.**94**
192.168.1.**96**  | /27 | 192.168.1.**127** | 192.168.1.**97** - 192.168.1.**126**
192.168.1.**128** | /27 | 192.168.1.**159** | 192.168.1.**129** - 192.168.1.**158**
192.168.1.**160** | /27 | 192.168.1.**191** | 192.168.1.**161** - 192.168.1.**190**