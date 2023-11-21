![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/4.2.7-Packet-Tracer-%E2%80%93-Configure-Router-on-a-Stick-Inter-VLAN-Routing.jpg)
## Definition
VLAN meningkatkan keamanan dan lalu lintas jaringan dengan membagi jaringan menjadi subkelompok logis.

VLAN meningkatkan manajemen jaringan, keamanan, dan pemanfaatan bandwidth.

## Switch S1
    S1(config)#vlan 10
    S1(config-vlan)#vlan 30
    S1(config)#interface f0/11
    S1(config-if)#switchport mode access
    S1(config-if)#switchport access vlan 10
    S1(config-if)#interface f0/6
    S1(config-if)#switchport mode access
    S1(config-if)#switchport access vlan 30
    S1(config)#int g0/1
    S1(config-if)#switchport mode trunk

## Router R1
    R1(config)# int g0/0.10
    R1(config-subif)# encapsulation dot1Q 10
    R1(config-subif)# ip address 172.17.10.1 255.255.255.0
    R1(config-subif)#int g0/0.30
    R1(config-subif)#encapsulation dot1Q 30
    R1(config-subif)#ip address 172.17.30.1 255.255.255.0
    R1(config)#interface g0/0
    R1(config-if)#no shutdown