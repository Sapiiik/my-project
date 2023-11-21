![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/08/11.5.5-Packet-Tracer-Subnet-an-IPv4-Network-ILM.jpg )
## Definition
Subnetting membagi jaringan yang besar menjadi bagian yang lebih kecil dan lebih mudah dioperasikan. Proses ini membantu mengatur dan merampingkan aliran data, yang pada akhirnya menyebabkan jaringan bekerja lebih baik.

Subnetting adalah solusi untuk masalah alamat terbatas IPv4. Dengan memecah jaringan menjadi beberapa subnet, organisasi dapat mengatur alamat IP dengan lebih baik, yang meningkatkan manajemen sumber daya.
## CustomerRouter
    Router>enable
    Router#configure terminal
    Router(config)#hostname CustomerRouter
    CustomerRouter(config)#enable secret Class123
    CustomerRouter(config)#line con 0
    CustomerRouter(config-line)#password Cisco123
    CustomerRouter(config-line)#login
    CustomerRouter(config-line)#interface GigabitEthernet0/0
    CustomerRouter(config-if)#ip address 192.168.0.1 255.255.255.192
    CustomerRouter(config-if)#no shutdown
    CustomerRouter(config-if)#interface GigabitEthernet0/1
    CustomerRouter(config-if)#ip address 192.168.0.65 255.255.255.192
    CustomerRouter(config-if)#no shutdown
    CustomerRouter(config-if)#interface Serial0/1/0
    CustomerRouter(config-if)#ip address 209.165.201.2 255.255.255.252
    CustomerRouter(config-if)#no shutdown
    CustomerRouter(config-if)#end
## LAN-A
    Switch>enable
    Switch#configure terminal
    Switch(config)#interface Vlan1
    Switch(config-if)#ip address 192.168.0.2 255.255.255.192
    Switch(config-if)#no shutdown
    Switch(config-if)#ip default-gateway 192.168.0.1
    Switch(config)#end
## LAN-B
    Switch>enable
    Switch#configure terminal
    Switch(config)#interface Vlan1
    Switch(config-if)#ip address 192.168.0.66 255.255.255.192
    Switch(config-if)#no shutdown
    Switch(config-if)#ip default-gateway 192.168.0.65
    Switch(config)#end
## PC-A
    IP address: 192.168.0.62 /26
    Subnet Mask: 255.255.255.192
    Default gateway: 192.168.0.1
## PC-B
    IP address: 192.168.0.126 /26
    Subnet Mask: 255.255.255.192
    Default gateway: 192.168.0.65