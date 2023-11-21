![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2019/12/10.4.3-Packet-Tracer-Basic-Device-Configuration.jpg)
## Definition
Sebelum memulai proses, sangat penting untuk memahami seluk-beluk konfigurasi perangkat. Bagian ini akan menjelajahi berbagai komponen yang terlibat, menekankan betapa pentingnya pengaturan konfigurasi untuk fungsionalitas perangkat.
## College Router
    Router>enable
    Router#config terminal
    Router(config)#hostname College

    College(config)#enable secret class
    College(config)#line console 0
    College(config-line)#password cisco
    College(config-line)#login
    College(config-line)#line vty 0 15
    College(config-line)#password cisco
    College(config-line)#login
    College(config-line)#exit
    College(config)#service password-encryption

    College(config)#banner motd #Unauthorized access to this device is prohibited!#

    College(config)#interface g0/0
    College(config-if)#ip address 128.107.20.1 255.255.255.0
    College(config-if)#ipv6 address 2001:db8:a::1/64
    College(config-if)#ipv6 address FE80::1 link-local
    College(config-if)#description Link to Class-A
    College(config-if)#no shutdown

    College(config-if)#interface g0/1
    College(config-if)#ip address 128.107.30.1 255.255.255.0
    College(config-if)#ipv6 address 2001:db8:b::1/64
    College(config-if)#ipv6 address FE80::1 link-local
    College(config-if)#description Link to Class-B
    College(config-if)#no shutdown
    College(config-if)#exit

    College(config)#ipv6 unicast-routing
    College(config)#end
    College#copy running-config startup-config

## Class-B Switch

    Switch>enable
    Switch#configure terminal
    Switch(config)#hostname Class-B
    Class-B(config)#banner motd #Unauthorized access to this device is prohibited!#

    Class-B(config)#enable secret class
    Class-B(config)#line console 0
    Class-B(config-line)#password cisco
    Class-B(config-line)#login
    Class-B(config-line)#line vty 0 4
    Class-B(config-line)#password cisco
    Class-B(config-line)#login
    Class-B(config-line)#exit
    Class-B(config)#service password-encryption

    Class-B(config)#interface vlan 1
    Class-B(config-if)#description Vlan 1
    Class-B(config-if)#ip address 128.107.30.15 255.255.255.0
    Class-B(config-if)#no shutdown
    Class-B(config-if)#end

    Class-B#copy running-config startup-config

## PCs host

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2019/12/Student-1.jpg)

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2019/12/Student-2.jpg)

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2019/12/Student-3.jpg)

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2019/12/Student-4.jpg)