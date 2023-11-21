![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/01/16.4.6-Packet-Tracer-Configure-Secure-Passwords-and-SSH.jpg)
## Definition
Kekuatan kata sandi Anda adalah dasar keamanan digital. Kata sandi yang aman memiliki kerumitan, unik, dan ketidakpastian. Gunakan kombinasi huruf besar dan kecil, angka, dan karakter unik untuk memperkuat pertahanan Anda. Menggunakan informasi yang mudah ditebak, seperti ulang tahun atau kata-kata umum, harus dihindari.
## Router RTA

    Router>enable
    Router#config terminal
    Router(config)#hostname RTA
    RTA(config)#interface g0/0
    RTA(config-if)#ip address 172.16.1.1 255.255.255.0
    RTA(config-if)#no shutdown
    RTA(config-if)#exit

    RTA(config)#service password-encryption 
    RTA(config)#security password min-length 10

    RTA(config)#enable secret itexamanswers
    RTA(config)#no ip domain-lookup
    RTA(config)#ip domain-name CCNA.com
    RTA(config)#username jony secret itexamanswers.net
    RTA(config)#crypto key generate rsa
    How many bits in the modulus [512]: 1024

    RTA(config)#login block-for 180 attempts 4 within 120

    RTA(config)#line vty 0 4
    RTA(config-line)#transport input ssh 
    RTA(config-line)#login local
    RTA(config-line)#exec-timeout 6
    RTA(config-line)#end

    RTA#copy running-config startup-config 

## Switch SW1

    Switch>enable
    Switch#config terminal
    Switch(config)#hostname SW1
    SW1(config)#

    SW1(config)#interface vlan 1
    SW1(config-if)#ip address 172.16.1.2 255.255.255.0
    SW1(config-if)#no shutdown
    SW1(config-if)#exit
    SW1(config)#ip default-gateway 172.16.1.1
    SW1(config)#interface range F0/2-24, G0/2
    SW1(config-if-range)#shutdown

    SW1(config-if-range)#exit
    SW1(config)#service password-encryption 
    SW1(config)#enable secret class
    SW1(config)#no ip domain-lookup
    SW1(config)#ip domain-name CCNA.com
    SW1(config)#crypto key generate rsa
    How many bits in the modulus [512]: 1024
    SW1(config)#username admin_switch secret p@ssword
    SW1(config)#line vty 0 15
    SW1(config-line)#transport input ssh 
    SW1(config-line)#login local
    SW1(config-line)#exec-timeout 6
    SW1(config-line)#end
    SW1#copy running-config startup-config

## PCA
![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/01/PAC-A.jpg)