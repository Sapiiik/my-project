![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/3.6.1-Packet-Tracer-Implement-VLANs-and-Trunking.jpg)

## Defintion
Dengan menggunakan VLAN, yang merupakan segmentasi virtual dari jaringan fisik, Anda dapat membuat grup terisolasi yang lebih aman dan efisien. Di sisi lain, trunking adalah cara untuk membawa beberapa VLAN ke dalam satu tautan jaringan.

Implementasi VLAN dan trunking sangat penting untuk meningkatkan keamanan data, mengoptimalkan kinerja jaringan, dan merampingkan operasi jaringan.
# Configure Device
## Switch SWA
    SWA>enable
    SWA#conf t
    SWA(config)#vlan 10
    SWA(config-vlan)#name Admin
    SWA(config-vlan)#vlan 20
    SWA(config-vlan)#name Accounts
    SWA(config-vlan)#vlan 30
    SWA(config-vlan)#name HR
    SWA(config-vlan)#vlan 40
    SWA(config-vlan)#name Voice
    SWA(config-vlan)#vlan 99
    SWA(config-vlan)#name Management
    SWA(config-vlan)#vlan 100
    SWA(config-vlan)#name Native
    SWA(config-vlan)#interface GigabitEthernet0/1
    SWA(config-if)#switchport trunk native vlan 100
    SWA(config-if)#switchport mode trunk
    SWA(config-if)#switchport nonegotiate
    SWA(config-if)#interface GigabitEthernet0/2
    SWA(config-if)#switchport trunk native vlan 100
    SWA(config-if)#switchport mode dynamic desirable
    SWA(config-if)#interface Vlan1
    SWA(config-if)#no ip address
    SWA(config-if)#shutdown
    SWA(config-if)#interface Vlan99
    SWA(config-if)#ip address 192.168.99.252 255.255.255.0
    SWA(config-if)#end

## Switch SWB
    SWB>enable
    SWB#conf t
    SWB(config)#vlan 10
    SWB(config-vlan)#name Admin
    SWB(config-vlan)#vlan 20
    SWB(config-vlan)#name Accounts
    SWB(config-vlan)#vlan 30
    SWB(config-vlan)#name HR
    SWB(config-vlan)#vlan 40
    SWB(config-vlan)#name Voice
    SWB(config-vlan)#vlan 99
    SWB(config-vlan)#name Management
    SWB(config-vlan)#vlan 100
    SWB(config-vlan)#name Native
    SWB(config-vlan)#interface FastEthernet0/1
    SWB(config-if)#switchport access vlan 10
    SWB(config-if)#switchport mode access
    SWB(config-if)#interface FastEthernet0/2
    SWB(config-if)#switchport access vlan 20
    SWB(config-if)#switchport mode access
    SWB(config-if)#interface FastEthernet0/3
    SWB(config-if)#switchport access vlan 30
    SWB(config-if)#switchport mode access
    SWB(config-if)#interface GigabitEthernet0/1
    SWB(config-if)#switchport trunk native vlan 100
    SWB(config-if)#switchport mode trunk
    SWB(config-if)#switchport nonegotiate
    SWB(config-if)#interface Vlan99
    SWB(config-if)#ip address 192.168.99.253 255.255.255.0
    SWB(config-if)#end

## Switch SWC
    SWC>enable
    SWC#conf t
    SWC(config)#vlan 10
    SWC(config-vlan)#name Admin
    SWC(config-vlan)#vlan 20
    SWC(config-vlan)#name Accounts
    SWC(config-vlan)#vlan 30
    SWC(config-vlan)#name HR
    SWC(config-vlan)#vlan 40
    SWC(config-vlan)#name Voice
    SWC(config-vlan)#vlan 99
    SWC(config-vlan)#name Management
    SWC(config-vlan)#vlan 100
    SWC(config-vlan)#name Native
    SWC(config-vlan)#interface FastEthernet0/1
    SWC(config-if)#switchport access vlan 10
    SWC(config-if)#switchport mode access
    SWC(config-if)#interface FastEthernet0/2
    SWC(config-if)#switchport access vlan 20
    SWC(config-if)#switchport mode access
    SWC(config-if)#interface FastEthernet0/3
    SWC(config-if)#switchport access vlan 30
    SWC(config-if)#switchport mode access
    SWC(config-if)#interface FastEthernet0/4
    SWC(config-if)#switchport access vlan 10
    SWC(config-if)#switchport mode access
    SWC(config-if)#switchport voice vlan 40
    SWC(config-if)#mls qos trust cos
    SWC(config-if)#interface GigabitEthernet0/2
    SWC(config-if)#switchport trunk native vlan 100
    SWC(config-if)#switchport mode trunk
    SWC(config-if)#interface Vlan99
    SWC(config-if)#ip address 192.168.99.254 255.255.255.0
    SWC(config-if)#end