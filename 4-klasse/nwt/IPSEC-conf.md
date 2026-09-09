---
tags:
  - 4te_Klasse
  - nwt
date: 2026-02-20T11:55:00
---
Mitschrift in der stunde von der PT aufgabe auf moodle 

```cisco
crypto isakmp policy 1
encryption aes
authentication pre-share
group 5
exit

crypto isakmp key
htl22VPN address 90.65.20.10
```

ka was das is
```cisco
crypto ipsec transform-set HTL22_ipsec esp-aes esp-sha-hmac
```
verknüpfen
```csico
crypto map HTL22-map 1 ipsec-isakmp
set peer 90.65.20.10 !nicht für auth sondern tunnel
set transform-set HTL22_ipsec
```

acces list verknüpfen

```cisco
access-list extended IPSEC-VPN
permit ip 192.168.1.0 0.0.0.0 192.168.2.0 0.0.0.0
exit
crypto map HTL22_map 1 ipsec-isakmp

show crypto isakmp policy
show crypto map

show crypto isakmp sa !security association
!zeigt nix an

verschl. für isp traffic pro schnittstelle
int s0/0/0 
crypto map HTL22_map
!sagt dann ist on

show crypto isakmp sa 
!zeigt jz was an
```
meow

ip route 90.56.20.10 255.255.255.255 s0/0/0
!andere seite
ip route 209.265.7.34 255.255.255.255 s0/0/0
