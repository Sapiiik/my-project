![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/13.3.12-Packet-Tracer-%E2%80%93-Configure-a-WPA2-Enterprise-WLAN-on-the-WLC-768x593.jpg)

## Definition
Konfigurasi WLAN Enterprise WPA2 (Wireless Local Area Network) pada Pengontrol Jaringan Nirkabel Lokal (WLC) melibatkan penerapan protokol keamanan WPA2 Enterprise untuk menjaga jaringan nirkabel aman.

Jangan lupa bahwa prosedur dan opsi menu khusus dapat berbeda tergantung pada merek dan model WLC yang Anda gunakan. Untuk mendapatkan petunjuk yang akurat dan mendalam, selalu lihat instruksi yang disediakan oleh produsen WLC.

## Admin PC
### Bagian 1: Membuat WLAN baru
#### Langkah 1: Membuat antarmuka VLAN baru.
Setiap WLAN memerlukan antarmuka virtual pada WLC. Antarmuka ini dikenal sebagai antarmuka dinamis. Antarmuka virtual diberi ID VLAN dan lalu lintas yang menggunakan antarmuka akan ditandai sebagai lalu lintas VLAN. Inilah sebabnya mengapa koneksi antara AP, WLC, dan router melalui port trunk. Agar lalu lintas dari beberapa WLAN dapat diangkut melalui jaringan, lalu lintas untuk VLAN WLAN harus di-trunking.

a. Buka browser dari desktop PC Admin. Sambungkan ke alamat IP WLC melalui HTTPS. https://192.168.200.254

b. Login dengan nama pengguna admin dan kata sandi Cisco123.

c. Klik menu Controller dan kemudian klik Interfaces dari menu di sebelah kiri. Anda akan melihat antarmuka virtual default dan antarmuka manajemen yang terhubung dengan Anda.

d. Klik tombol New di sudut kanan atas halaman. Anda mungkin perlu menggulir halaman ke kanan untuk melihatnya.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_202654.jpg)

e. Masukkan nama antarmuka baru. Kita akan menyebutnya WLAN-5. Konfigurasikan ID VLAN sebagai 5. Ini adalah VLAN yang akan membawa lalu lintas untuk WLAN yang kita buat nanti. Klik Apply. Ini akan membawa Anda ke layar konfigurasi untuk antarmuka VLAN.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_202900.jpg)

f. Pertama, konfigurasikan antarmuka untuk menggunakan port fisik nomor 1. Beberapa antarmuka VLAN dapat menggunakan port fisik yang sama karena antarmuka fisik seperti port trunk khusus.

g. Alamat antarmuka sebagai berikut:

Alamat IP: 192.168.5.254
Netmask 255.255.255.0
Gateway: 192.168.5.1
Server DHCP utama: 192.168.5.1

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_203320.jpg)

Lalu lintas pengguna untuk WLAN yang menggunakan antarmuka VLAN ini akan berada di jaringan 192.168.5.0/24. Gateway default adalah alamat antarmuka pada router R-1. Sebuah DHCP pool telah dikonfigurasi pada router.
Alamat yang kita konfigurasikan di sini untuk DHCP memberitahu WLC untuk meneruskan semua permintaan DHCP yang diterimanya dari host di WLAN ke server DHCP di router.

h. Pastikan untuk mengklik Apply untuk memberlakukan perubahan Anda dan klik OK untuk merespons pesan peringatan. Klik Save Configuration agar konfigurasi Anda akan berlaku saat WLC dinyalakan ulang.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_203614.jpg)

#### Langkah 2: Konfigurasikan WLC untuk menggunakan server RADIUS.
WPA2-Enterprise menggunakan server RADIUS eksternal untuk mengautentikasi pengguna WLAN. Akun pengguna individual dengan nama pengguna dan kata sandi yang unik dapat dikonfigurasikan pada server RADIUS. Sebelum WLC dapat menggunakan layanan server RADIUS, WLC harus dikonfigurasikan dengan alamat server.

a. Klik menu Keamanan pada WLC.

b. Klik tombol New dan masukkan alamat IP server RADIUS pada bidang Alamat IP Server.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_203756.jpg)

c. Server RADIUS akan mengautentikasi WLC sebelum mengizinkan WLC mengakses informasi akun pengguna yang ada di server. Hal ini membutuhkan nilai rahasia bersama. Gunakan Cisco123. Konfirmasikan rahasia bersama dan klik Terapkan.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_203938-1.jpg)

#### Langkah 3: Buat WLAN baru.
Buat WLAN Baru. Gunakan antarmuka VLAN yang baru dibuat untuk WLAN baru.

a. Klik entri WLAN di bar menu. Cari kotak pilihan di sudut kanan atas layar WLAN. Kotak tersebut akan bertuliskan Create New. Klik Go untuk membuat WLAN baru.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_204423.jpg)

b. Masukkan Nama Profil WLAN baru. Gunakan nama profil Karyawan Lantai 2. Tetapkan SSID SSID-5 ke WLAN. Ubah drop down ID menjadi 5. Host harus menggunakan SSID ini untuk bergabung dengan jaringan.
Setelah selesai, klik Apply untuk menerima pengaturan Anda.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_204555.jpg)

c. Klik Terapkan agar pengaturan diterapkan.

d. Setelah WLAN dibuat, Anda dapat mengkonfigurasi fitur-fitur jaringan. Klik Enabled untuk membuat WLAN berfungsi. Merupakan kesalahan umum jika tidak sengaja melewatkan langkah ini.

e. Pilih antarmuka VLAN yang akan digunakan untuk WLAN baru. WLC akan menggunakan antarmuka ini untuk lalu lintas pengguna di jaringan. Klik kotak drop-down untuk Interface/Interface Group (G). Pilih antarmuka yang telah dibuat pada Langkah 1.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_204836.jpg)

f. Buka tab Advanced (Lanjutan). Gulir ke bagian FlexConnect pada antarmuka.

g. Klik untuk mengaktifkan FlexConnect Local Switching dan FlexConnect Local Auth.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_205107.jpg)

h. Klik Apply (Terapkan) untuk mengaktifkan WLAN baru. Jika Anda lupa melakukan hal ini, WLAN tidak akan beroperasi.

#### Langkah 4: Konfigurasikan keamanan WLAN.
Sebagai ganti WPA2-PSK, kita akan mengkonfigurasi WLAN baru untuk menggunakan WPA2-Enterprise.

a. Klik ID WLAN dari WLAN yang baru dibuat untuk melanjutkan konfigurasi, jika perlu.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_205318.jpg)

b. Klik tab Keamanan. Di bawah tab Layer 2, pilih WPA + WPA2 dari kotak tarik-turun.

c. Di bawah Parameter WPA + WPA2, aktifkan Kebijakan WPA2. Klik 802.1X di bawah Manajemen Kunci Otentikasi. Hal ini akan memerintahkan WLC untuk menggunakan protokol 802.1X untuk mengautentikasi pengguna secara eksternal.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_205550.jpg)

d. Klik tab Server AAA. Buka menu tarik-turun di samping Server 1 pada kolom Server Otentikasi dan pilih server yang telah dikonfigurasi pada Langkah 2.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_205754.jpg)

e. Klik Apply untuk menerapkan konfigurasi ini. Anda sekarang telah mengkonfigurasi WLC untuk menggunakan RADIUS sever untuk mengautentikasi pengguna yang mencoba menyambung ke WLAN.

### Bagian 2: Mengkonfigurasi Cakupan DHCP dan SNMP
#### Langkah 1: Konfigurasi Cakupan DHCP.
WLC menawarkan server DHCP internalnya sendiri. Cisco merekomendasikan agar server DHCP WLAN tidak digunakan untuk layanan DHCP bervolume tinggi, seperti yang diperlukan oleh WLAN pengguna yang lebih besar. Namun, dalam jaringan yang lebih kecil, server DHCP dapat digunakan untuk memberikan alamat IP ke LAP yang tersambung ke jaringan manajemen berkabel. Pada langkah ini, kita akan mengonfigurasi cakupan DHCP pada WLC dan menggunakannya untuk mengalamatkan LAP-1.

a. Harus terhubung ke GUI WLC dari PC Admin.

b. Klik menu Controller lalu klik Interfaces.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_210007.jpg)

c. Klik Antarmuka manajemen. Catat informasi pengalamatannya di sini.

d. Kami ingin WLC menggunakan DHCP sever-nya sendiri untuk memberikan pengalamatan ke perangkat pada jaringan manajemen nirkabel, seperti AP ringan. Untuk alasan ini, masukkan alamat IP antarmuka manajemen WLC sebagai alamat server DHCP utama. Klik Apply (Terapkan). Klik OK untuk mengetahui pesan peringatan yang muncul.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_210448.jpg)

e. Pada menu sebelah kiri, perluas bagian Server DHCP Internal. Klik Cakupan DHCP.

f. Untuk membuat cakupan DHCP, klik tombol New....

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_210651.jpg)

g. Beri nama cakupan Wired Management (Manajemen Berkabel). Anda akan mengkonfigurasi lingkup DHCP ini untuk memberikan alamat ke jaringan infrastruktur berkabel yang menghubungkan PC Admin, WLC-1, dan LAP-1.

h. Klik Apply (Terapkan) untuk membuat cakupan DHCP baru.

i. Klik cakupan baru pada tabel DHCP Scopes untuk mengkonfigurasi informasi pengalamatan untuk cakupan tersebut. Masukkan informasi berikut ini.

Pool Start Address: 192.168.200.240
Pool End Address: 192.168.200.249
Status: Diaktifkan

Berikan nilai untuk Network, Netmask, dan Default Routers dari informasi yang Anda kumpulkan di Langkah 1c.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_211032.jpg)

j. Klik Apply (Terapkan) untuk mengaktifkan konfigurasi. Klik Save Configuration (Simpan Konfigurasi) di sudut kanan atas antarmuka WLC untuk menyimpan pekerjaan Anda agar tersedia saat WLC dinyalakan ulang.

Server DHCP internal sekarang akan memberikan alamat ke LAP-1 setelah penundaan singkat. Ketika LAP-1 mendapatkan alamat IP, terowongan CAPWAP akan dibuat dan LAP-1 akan dapat menyediakan akses ke WLAN Karyawan Lantai 2 (SSID-5). Jika Anda menggerakkan mouse ke atas LAP-1 dalam topologi, Anda akan melihat alamat IP-nya, status terowongan CAPWAP, dan WLAN yang menyediakan akses ke LAP-1.

#### Langkah 2: Konfigurasi SNMP
a. Klik menu Manajemen di GUI WLC dan perluas entri untuk SNMP di menu sebelah kiri.

b. Klik Trap Receivers lalu New...

c. Masukkan string komunitas sebagai WLAN_SNMP dan alamat IP server di 172.31.1.254.

d. Klik Apply untuk menyelesaikan konfigurasi.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_211302.jpg)

### Bagian 3: Menghubungkan Host ke Jaringan
#### Langkah 1: Konfigurasikan host untuk menyambung ke jaringan perusahaan.
Dalam aplikasi klien Nirkabel PC Packet Tracer, Anda harus mengkonfigurasi Profil WLAN untuk menyambungkan ke WLAN WPA2-Enterprise.

a. Klik Wireless Host (Host Nirkabel) dan buka aplikasi PC Wireless (Nirkabel PC).

b. Klik tab Profiles (Profil), lalu klik New (Baru) untuk membuat profil baru. Beri nama profil WLC NET.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_211549.jpg)

c. Sorot Nama Jaringan Nirkabel untuk WLAN yang telah dibuat sebelumnya dan klik Advanced Setup.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_211659.jpg)

d. Verifikasi bahwa SSID untuk LAN nirkabel ada, lalu klik Next. Host Nirkabel seharusnya melihat SSID-5. Jika tidak, gerakkan mouse ke atas LAP-1 untuk memverifikasi bahwa ia berkomunikasi dengan WLC. Kotak popup seharusnya menunjukkan bahwa LAP-1 mengetahui SSID-5. Jika tidak, periksa konfigurasi WLC. Anda juga dapat memasukkan SSID secara manual.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_211806.jpg)

e. Verifikasi bahwa pengaturan jaringan DHCP telah dipilih, lalu klik Next (Berikutnya).

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_211918.jpg)

f. Pada kotak drop-down Keamanan, pilih WPA2-Enterprise. Klik Berikutnya.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_212006.jpg)

g. Masukkan nama login user1 dan kata sandi User1Pass, lalu klik Berikutnya.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_212110.jpg)

h. Verifikasi Pengaturan Profil dan klik Simpan.

i. Pilih profil WLC NET dan klik tombol Hubungkan ke Jaringan. Setelah penundaan singkat, Anda akan melihat Host Nirkabel tersambung ke LAP-1. Anda dapat mengklik tombol Fast Forward Time untuk mempercepat proses jika tampaknya terlalu lama.

j. Konfirmasikan bahwa Host Nirkabel telah tersambung ke WLAN. Host Nirkabel harus menerima alamat IP dari server DHCP yang dikonfigurasi untuk host pada R1. Alamat tersebut akan berada di jaringan 192.168.5.0/24. Anda mungkin perlu mengklik tombol Fast Forward Time untuk mempercepat proses.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_212307.jpg)

#### Langkah 2: Uji Konektivitas.
a. Tutup aplikasi PC Wireless.

b. Buka prompt perintah dan konfirmasikan bahwa laptop Wireless Host telah memperoleh alamat IP dari jaringan WLAN.

c. Lakukan ping ke gateway default, SW1, dan server RADIUS. Keberhasilan menunjukkan konektivitas penuh dalam topologi ini.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_212511.jpg)