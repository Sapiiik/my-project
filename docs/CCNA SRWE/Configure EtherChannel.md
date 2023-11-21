![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/6.2.4-Packet-Tracer-Configure-EtherChannel.jpg)

## Definition
Konfigurasi EtherChannel adalah proses mengatur atau mengubah parameter EtherChannel. Teknologi ini digunakan dalam jaringan untuk menggabungkan banyak sambungan Ethernet fisik ke dalam satu sambungan logis, yang memungkinkan peningkatan bandwidth dan toleransi kesalahan.

## Switch S1
    Switch>enable
    Switch#config terminal
    Switch(config)#hostname S1
    S1(config)#interface range f0/21 - 22
    S1(config-if-range)# switchport mode trunk
    S1(config-if-range)# shutdown
    S1(config-if-range)# channel-group 1 mode desirable
    S1(config-if-range)# no shutdown
    S1(config-if-range)#
    S1(config-if-range)#interface port-channel 1
    S1(config-if)# switchport mode trunk
    S1(config-if)#interface range g0/1 - 2
    S1(config-if-range)# switchport mode trunk
    S1(config-if-range)# shutdown
    S1(config-if-range)# channel-group 2 mode active
    S1(config-if-range)# no shutdown
    S1(config-if-range)#interface port-channel 2
    S1(config-if)# switchport mode trunk
    S1(config-if)#spanning-tree vlan 1 root primary
    S1(config)#end

## Switch S2
    Switch>enable
    Switch#config terminal
    Switch(config)#hostname S2
    S2(config)#interface range g0/1 - 2
    S2(config-if-range)# switchport mode trunk
    S2(config-if-range)# shutdown
    S2(config-if-range)# channel-group 2 mode active
    S2(config-if-range)# no shutdown
    S2(config-if-range)#interface port-channel 2
    S2(config-if)# switchport mode trunk
    S2(config-if)#interface range f0/23 - 24
    S2(config-if-range)# switchport mode trunk
    S2(config-if-range)# no shutdown
    S2(config-if-range)#interface port-channel 3
    S2(config-if)# switchport mode trunk
    S2(config-if)# end

## Switch S3
    Switch>enable
    Switch#config terminal
    Switch(config)#hostname S3
    S3(config)#interface range f0/21 - 22
    S3(config-if-range)# switchport mode trunk
    S3(config-if-range)# shutdown
    S3(config-if-range)# channel-group 1 mode desirable
    S3(config-if-range)# no shutdown
    S3(config-if-range)#interface port-channel 1
    S3(config-if)# switchport mode trunk
    S3(config-if)#interface range f0/23 - 24
    S3(config-if-range)# switchport mode trunk
    S3(config-if-range)# shutdown
    S3(config-if-range)# channel-group 3 mode active
    S3(config-if-range)# no shutdown
    S3(config-if-range)#interface port-channel 3
    S3(config-if)# switchport mode trunk
    S3(config-if)#end