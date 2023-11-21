![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/9.3.3-Packet-Tracer-%E2%80%93-HSRP-Configuration-Guide-768x403.jpg)

## Definition
Protokol redundansi Hot Standby Router (HSRP), yang dibuat oleh Cisco untuk menyediakan ketersediaan jaringan yang tinggi, sering digunakan dalam jaringan perusahaan untuk memastikan operasi yang berkelanjutan dengan memungkinkan peralihan router otomatis jika terjadi kegagalan. Dengan protokol ini, beberapa router dapat bekerja sama untuk menyampaikan alamat IP virtual dan alamat MAC virtual ke host jaringan.

## Router R1
    R1>enable
    R1#config t
    R1(config)# interface g0/1
    R1(config-if)# standby version 2
    R1(config-if)# standby 1 ip 192.168.1.254
    R1(config-if)# standby 1 priority 150
    R1(config-if)# standby 1 preempt
## Router R3
    R3>enable
    R3#config t
    R3(config)#int g0/0
    R3(config-if)#standby version 2
    R3(config-if)#standby 1 ip 192.168.1.254
## Switch S1
    S1>enable
    S1#config t
    S1(config)#ip default-gateway 192.168.1.254
## Switch S3
    S3>enable
    S3#config t
    S3(config)#ip default-gateway 192.168.1.254
## PC-A and PC-B
![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/2020-09-11_175337.jpg)

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/2020-09-11_181140.jpg)