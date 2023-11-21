![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/7.2.10-Packet-Tracer-Configure-DHCPv4.jpg)
## Defintion
Salah satu komponen penting dari jaringan modern, DHCPv4 memastikan bahwa perangkat yang tersambung ke jaringan menerima konfigurasi yang diperlukan tanpa perlu melakukannya secara manual. Mari kita pelajari seluk-beluk konfigurasi DHCPv4 untuk mengoptimalkan kinerja jaringan Anda.

Sebelum memasuki detail konfigurasi, sangat penting untuk memahami protokol konfigurasi host dinamis, juga dikenal sebagai DHCP. Protokol ini mengotomatiskan proses pemberian alamat IP dalam jaringan.

## Router R1
    R1>enable
    R1#config t
    R1(config)#interface g0/0
    R1(config-if)#ip helper-address 10.1.1.2
## Router R2
    R2>enable
    R2#config t
    R2(config)#ip dhcp excluded-address 192.168.10.1 192.168.10.10
    R2(config)#ip dhcp excluded-address 192.168.30.1 192.168.30.10
    R2(config)#ip dhcp pool R1-LAN
    R2(dhcp-config)#network 192.168.10.0 255.255.255.0
    R2(dhcp-config)#default-router 192.168.10.1
    R2(dhcp-config)#dns-server 192.168.20.254
    R2(dhcp-config)#ip dhcp pool R3-LAN
    R2(dhcp-config)#network 192.168.30.0 255.255.255.0
    R2(dhcp-config)#default-router 192.168.30.1
    R2(dhcp-config)#dns-server 192.168.20.254
    R2(dhcp-config)#interface g0/1
    R2(config-if)#ip address dhcp
    R2(config-if)#no shutdown

## Router R3
    R3>enable
    R3#config t
    R3(config)#interface g0/0
    R3(config-if)#ip helper-address 10.2.2.2