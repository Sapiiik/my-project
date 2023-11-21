![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/01/16.5.1-Packet-Tracer-Secure-Network-Devices.jpg)
## Definition
Untuk memastikan bahwa jaringan beroperasi dengan efisien dan aman, konfigurasi dasar perangkat sangat penting, dan Cisco menggunakan langkah-langkah ini untuk mengoptimalkan perangkat mereka. Mari kita lihat lebih lanjut tentang bagaimana konfigurasi dasar perangkat memengaruhi keberhasilan jaringan.
## RTR-A
    Router>enable
    Router#conf t
    Router(config)#service password-encryption
    Router(config)#security passwords min-length 10
    Router(config)#hostname RTR-A
    RTR-A(config)#login block-for 45 attempts 3 within 100
    RTR-A(config)#enable secret @Cons1234!
    RTR-A(config)#username NETadmin secret LogAdmin!9
    RTR-A(config)#no ip domain-lookup
    RTR-A(config)#ip domain-name security.com
    RTR-A(config)#banner motd #Unauthorized access prohibited.#
    RTR-A(config)#line con 0
    RTR-A(config-line)#exec-timeout 7 0
    RTR-A(config-line)#password @Cons1234!
    RTR-A(config-line)#login
    RTR-A(config-line)#line aux 0
    RTR-A(config-line)#line vty 0 4
    RTR-A(config-line)#exec-timeout 7 0
    RTR-A(config-line)#login local
    RTR-A(config-line)#transport input ssh
    RTR-A(config-line)#line vty 5 15
    RTR-A(config-line)#no login
    RTR-A(config-line)#crypto key generate rsa
    How many bits in the modulus [512]: 1024
    RTR-A(config)#end
## SW-1
    Switch>enable
    Switch#conf t
    Switch(config)#hostname SW-1
    SW-1(config)#ip domain-name security.com
    SW-1(config)#enable secret @Cons1234!
    SW-1(config)#username NETadmin secret LogAdmin!9
    SW-1(config)#interface range fastEthernet0/1, fastEthernet0/3-9, fastEthernet0/11-24, GigabitEthernet0/2
    SW-1(config-if-range)#shutdown
    SW-1(config-if-range)#interface Vlan1
    SW-1(config-if)#ip address 192.168.1.254 255.255.255.0
    SW-1(config-if)#no shutdown
    SW-1(config-if)#ip default-gateway 192.168.1.1
    SW-1(config)#line vty 0 4
    SW-1(config-line)#login local
    SW-1(config-line)#transport input ssh
    SW-1(config-line)#crypto key generate rsa
    How many bits in the modulus [512]: 1024
    SW-1(config)#end