![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/11.6.1-Packet-Tracer-%E2%80%93-Switch-Security-Configuration.jpg)

## Definition
Keamanan port adalah istilah yang mengacu pada tindakan dan praktik yang digunakan untuk mengamankan port jaringan; khususnya, "Konfigurasi Keamanan Sakelar" mengacu pada serangkaian tindakan dan pengaturan yang diterapkan pada sakelar jaringan untuk meningkatkan keamanan dan melindungi integritas, kerahasiaan, dan ketersediaan sumber daya jaringan. Sakelar jaringan adalah perangkat jaringan penting yang menghubungkan beberapa perangkat dalam jaringan area lokal (LAN), memungkinkan mereka berkomunikasi satu sama lain secara efisien, terutama dalam bidang jaringan komputer dan teknologi informasi. Protokol lapisan transportasi seperti TCP dan UDP menggunakan port dalam jaringan sebagai titik akhir komunikasi. Nilai numerik diberikan kepada port untuk membedakan berbagai proses atau layanan yang berjalan pada satu perangkat.

## SW-1 Configurations
    SW-1>enable
    SW-1#configure terminal
    Enter configuration commands, one per line.  End with CNTL/Z.
    SW-1(config)#spanning-tree portfast default
    SW-1(config)#interface FastEthernet0/1
    SW-1(config-if)#ip dhcp snooping limit rate 5
    SW-1(config-if)#switchport mode access
    SW-1(config-if)#switchport port-security
    SW-1(config-if)#switchport port-security maximum 4
    SW-1(config-if)#switchport port-security mac-address sticky
    SW-1(config-if)#switchport port-security violation restrict
    SW-1(config-if)#switchport port-security mac-address 0010.11E8.3CBB
    SW-1(config-if)#spanning-tree portfast
    SW-1(config-if)#spanning-tree bpduguard enable

    SW-1(config-if)#interface range FastEthernet0/2, FastEthernet0/10,FastEthernet0/24
    SW-1(config-if-range)#ip dhcp snooping limit rate 5
    SW-1(config-if-range)#switchport mode access
    SW-1(config-if-range)#switchport port-security
    SW-1(config-if-range)#switchport port-security maximum 4
    SW-1(config-if-range)#switchport port-security mac-address sticky
    SW-1(config-if-range)#switchport port-security violation restrict
    SW-1(config-if-range)#spanning-tree portfast
    SW-1(config-if-range)#spanning-tree bpduguard enable

    SW-1(config-if-range)#interface range FastEthernet0/3-9, FastEthernet0/11-23
    SW-1(config-if-range)#switchport access vlan 999
    SW-1(config-if-range)#shutdown

    SW-1(config-if-range)#interface range GigabitEthernet0/1-2
    SW-1(config-if-range)#switchport trunk native vlan 100
    SW-1(config-if-range)#ip dhcp snooping trust
    SW-1(config-if-range)#switchport mode trunk
    SW-1(config-if-range)#switchport nonegotiate
    SW-1(config-if-range)#vlan 100
    SW-1(config-vlan)#name Native
    SW-1(config-vlan)#vlan 999
    SW-1(config-vlan)#name BlackHole
## SW-2 Configuration
    SW-2>enable
    SW-2#configure terminal
    Enter configuration commands, one per line.  End with CNTL/Z.
    SW-2(config)#ip dhcp snooping
    SW-2(config)#ip dhcp snooping vlan 10,20,99
    SW-2(config)#spanning-tree portfast default
    SW-2(config)#interface GigabitEthernet0/1
    SW-2(config-if)#switchport trunk native vlan 100
    SW-2(config-if)#switchport mode trunk
    SW-2(config-if)#switchport nonegotiate

    SW-2(config-if)#interface GigabitEthernet0/2
    SW-2(config-if)#switchport trunk native vlan 100
    SW-2(config-if)#switchport mode trunk
    SW-2(config-if)#switchport nonegotiate

    SW-2(config-if)#vlan 100
    SW-2(config-vlan)#name Native