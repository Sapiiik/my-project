![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/4.3.8-Packet-Tracer-%E2%80%93-Configure-Layer-3-Switching-and-Inter-VLAN-Routing.jpg)

## Definition
Peralihan Lapisan 3 dalam bidang jaringan beroperasi pada lapisan jaringan model Open Systems Interconnection (OSI). Berbeda dengan Lapisan 2, yang menangani alamat MAC, Lapisan 3 menangani alamat Internet Protocol (IP), yang membuatnya bagian penting dari koneksi jaringan lokal. Salah satu manfaat utamanya adalah kemampuan untuk membuat keputusan tentang perutean dengan kecepatan kabel, meningkatkan efisiensi, dan mengurangi latensi.
# Configure Device
## MLS
    MLS>enable
    MLS#config t
    MLS(config)#ip routing
    MLS(config)#ipv6 unicast-routing
    MLS(config)#interface GigabitEthernet0/1
    MLS(config-if)#switchport trunk native vlan 999
    MLS(config-if)#switchport trunk encapsulation dot1q
    MLS(config-if)#switchport mode trunk
    MLS(config-if)#interface GigabitEthernet0/2
    MLS(config-if)#no switchport
    MLS(config-if)#ip address 209.165.200.225 255.255.255.252
    MLS(config-if)#ipv6 address 2001:DB8:ACAD:A::1/64
    MLS(config-if)#vlan 10
    MLS(config-vlan)#name Staff
    MLS(config-vlan)#vlan 20
    MLS(config-vlan)#name Student
    MLS(config-vlan)#vlan 30
    MLS(config-vlan)#name Faculty
    MLS(config-vlan)#interface Vlan10
    MLS(config-if)#ip address 192.168.10.254 255.255.255.0
    MLS(config-if)#ipv6 address 2001:DB8:ACAD:10::1/64
    MLS(config-if)#no shutdown
    MLS(config-if)#interface Vlan20
    MLS(config-if)#ip address 192.168.20.254 255.255.255.0 
    MLS(config-if)#ipv6 address 2001:DB8:ACAD:20::1/64
    MLS(config-if)#no shutdown
    MLS(config-if)#interface Vlan30
    MLS(config-if)#ip address 192.168.30.254 255.255.255.0
    MLS(config-if)#ipv6 address 2001:DB8:ACAD:30::1/64
    MLS(config-if)#no shutdown
    MLS(config-if)#interface Vlan99
    MLS(config-if)#ip address 192.168.99.254 255.255.255.0
    MLS(config-if)#no shutdown
    MLS(config-if)#end
## S1
    S1>enable
    S1#conf t
    S1(config)#int g0/1
    S1(config-if)#switchport mode trunk
    S1(config-if)#switchport trunk native vlan 99
    S1(config-if)#end