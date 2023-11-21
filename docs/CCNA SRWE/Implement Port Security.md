![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/11.1.10-Packet-Tracer-%E2%80%93-Implement-Port-Security.jpg)

## Definition
Dalam konteks jaringan komputer dan teknologi informasi, "keamanan port" adalah istilah yang mengacu pada prosedur dan prosedur yang digunakan untuk menjaga port jaringan aman. Protokol lapisan transport seperti Protokol Pengendalian Transmisi TCP dan Protokol Datagram Pengguna UDP menggunakan port sebagai titik akhir komunikasi dalam jaringan. Nilai numerik diberikan kepada port untuk membedakan berbagai proses atau layanan yang berjalan pada satu perangkat.
## Switch S1
    S1>enable
    S1#configure t
    S1(config)# interface range f0/1 – 2
    S1(config-if-range)# switchport port-security
    S1(config-if-range)# switchport port-security maximum 1
    S1(config-if-range)# switchport port-security mac-address sticky
    S1(config-if-range)# switchport port-security violation restrict
    S1(config-if-range)# interface range f0/3 - 24 , g0/1 - 2
    S1(config-if-range)# shutdown