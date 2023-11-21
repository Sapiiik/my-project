![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/15.6.1-Packet-Tracer-%E2%80%93-Configure-IPv4-and-IPv6-Static-and-Default-Routes-1024x574.jpg)

## Definition
Proses pengaturan dan penetapan informasi perutean untuk jaringan IPv4 dan IPv6 disebut sebagai "Konfigurasi Rute Statis dan Default IPv4 dan IPv6."

## Router Edge_Router
    Edge_Router>enable
    Edge_Router#config terminal
    Edge_Router(config)#ip route 0.0.0.0 0.0.0.0 10.10.10.1
    Edge_Router(config)#ip route 0.0.0.0 0.0.0.0 10.10.10.5 5
    Edge_Router(config)#ipv6 route ::/0 2001:db8:a:1::1
    Edge_Router(config)#ipv6 route ::/0 2001:db8:a:2::1 5
    Edge_Router(config)#ip route 198.0.0.10 255.255.255.255 serial0/0/0
    Edge_Router(config)#ip route 198.0.0.10 255.255.255.255 serial0/0/1 5
    Edge_Router(config)#ipv6 route 2001:db8:f:f::10/128 2001:db8:a:1::1
    Edge_Router(config)#ipv6 route 2001:db8:f:f::10/128 2001:db8:a:2::1 5


## Router ISP1
    ISP1>enable
    ISP1#config terminal
    ISP1(config)#ip route 192.168.10.16 255.255.255.240 10.10.10.2
    ISP1(config)#ip route 192.168.11.32 255.255.255.224 10.10.10.2
    ISP1(config)#ip route 192.168.10.16 255.255.255.240 g0/0 5
    ISP1(config)#ip route 192.168.11.32 255.255.255.224 g0/0 5
    ISP1(config)#ipv6 route 2001:db8:1:10::/64 2001:db8:a:1::2
    ISP1(config)#ipv6 route 2001:db8:1:11::/64 2001:db8:a:1::2
    ISP1(config)#ipv6 route 2001:db8:1:10::/64 2001:db8:f:f::2 5
    ISP1(config)#ipv6 route 2001:db8:1:11::/64 2001:db8:f:f::2 5
