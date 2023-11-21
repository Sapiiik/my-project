![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/13.2.7-Packet-Tracer-%E2%80%93-Configure-a-Basic-WLAN-on-the-WLC.jpg)

## Definition
Di bidang jaringan, WLAN telah merevolusi cara kita menghubungkan perangkat. Kemudahan mobilitas yang mereka tawarkan tidak tertandingi, menjadikannya komponen penting dalam lanskap digital saat ini. Mengonfigurasi WLAN Dasar pada WLC menambahkan lapisan kontrol dan keamanan ekstra, memastikan kinerja yang optimal.

Wireless LAN Controller (WLC) bertindak sebagai otak pusat jaringan nirkabel. WLC mengelola dan mengontrol beberapa titik akses, menyederhanakan proses manajemen dan menyediakan hub terpusat untuk konfigurasi jaringan.

## PC Admin
### Bagian 1: Memantau WLC
Tunggu hingga STP menyatu pada jaringan. Anda dapat mengklik tombol Packet Tracer Fast Forward Time (Waktu Maju Cepat) untuk mempercepat proses. Lanjutkan bila semua lampu tautan menyala hijau.

a. Buka desktop PC Admin dan buka browser. Masukkan alamat IP manajemen WLC-1 dari tabel pengalamatan ke dalam bilah alamat. Anda harus menentukan protokol HTTPS.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_003315.jpg)

b. Klik Login dan masukkan kredensial ini: Nama Pengguna: admin, Kata Sandi: Cisco123. Setelah beberapa saat, Anda akan melihat layar Ringkasan Monitor WLC.

!!! Note
    Packet Tracer tidak mendukung dasbor awal yang telah didemonstrasikan dalam modul ini.

c. Gulir melalui layar Ringkasan Monitor.

d. Klik Detail di samping entri Semua AP di bagian Ringkasan Titik Akses pada halaman.

### Bagian 2: Membuat LAN Nirkabel
Sekarang Anda akan membuat LAN nirkabel baru pada WLC. Anda akan mengonfigurasi pengaturan yang diperlukan agar host dapat bergabung dengan WLAN.

#### Langkah 1: Buat dan aktifkan WLAN.
a. Klik WLAN di bar menu WLC. Cari kotak tarik-turun di sudut kanan atas layar WLAN. Kotak tersebut akan bertuliskan Create New. Klik Go untuk membuat WLAN baru.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_150423.jpg)

b. Masukkan Nama Profil WLAN baru. Gunakan nama profil Karyawan Lantai 2. Tetapkan SSID SSID-5 ke WLAN. Host harus menggunakan SSID ini untuk bergabung dengan jaringan.

c. Pilih ID untuk WLAN. Nilai ini merupakan label yang akan digunakan untuk mengidentifikasi WLAN pada tampilan lain. Pilih nilai 5 agar konsisten dengan nomor VLAN dan SSID. Ini bukan persyaratan tetapi membantu dalam memahami topologi.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_150546.jpg)

d. Klik Terapkan agar pengaturan diterapkan.

e. Setelah WLAN dibuat, Anda dapat mengkonfigurasi fitur-fitur jaringan. Klik Enabled (Diaktifkan) untuk membuat WLAN berfungsi. Merupakan kesalahan umum jika tidak sengaja melewatkan langkah ini.

f. Pilih antarmuka VLAN yang akan digunakan untuk WLAN. WLC akan menggunakan antarmuka ini untuk lalu lintas pengguna di jaringan. Klik kotak drop-down untuk Interface/Interface Group (G). Pilih antarmuka WLAN-5. Antarmuka ini sebelumnya dikonfigurasi pada WLC untuk aktivitas ini.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_152334.jpg)

g. Klik tab Lanjutan.

h. Gulir ke bawah ke bagian FlexConnect pada halaman. Klik untuk mengaktifkan FlexConnect Local Switching dan FlexConnect Local Auth.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_155417.jpg)

i. Klik Apply (Terapkan) untuk mengaktifkan WLAN baru. Jika Anda lupa melakukan hal ini, WLAN tidak akan beroperasi.

#### Langkah 2: Mengamankan WLAN.
WLAN baru saat ini belum memiliki keamanan. WLAN ini pada awalnya akan menggunakan keamanan WPA2-PSK. Pada aktivitas lain, Anda akan mengkonfigurasi WLAN untuk menggunakan WPA2-Enterprise, solusi yang jauh lebih baik untuk jaringan nirkabel yang lebih besar.

a. Pada layar Edit WLAN untuk WLAN Karyawan Lantai 2, klik tab Security. Di bawah tab Layer 2, pilih WPA+WPA2 dari kotak pilihan Layer 2 Security. Ini akan menampilkan parameter WPA.

b. Klik kotak centang di samping Kebijakan WPA2. Ini akan menampilkan pengaturan keamanan tambahan. Di bawah Manajemen Kunci Otentikasi, aktifkan PSK.

c. Sekarang Anda dapat memasukkan kunci yang telah dibagi sebelumnya yang akan digunakan oleh host untuk bergabung dengan WLAN. Gunakan Cisco123 sebagai kata sandi.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_195926.jpg)

d. Klik Terapkan untuk menyimpan pengaturan ini.

!!! Note
    Bukan praktik yang baik untuk menggunakan ulang kata sandi saat mengonfigurasi keamanan. Kami telah menggunakan ulang kata sandi dalam aktivitas ini untuk menyederhanakan konfigurasi.

Langkah 3: Verifikasi Pengaturan
a. Setelah Menerapkan konfigurasi, klik Kembali. Ini akan membawa Anda kembali ke layar WLAN.

b. Jika Anda mengeklik ID WLAN, Anda akan dibawa ke layar Edit WLAN. Gunakan ini untuk memverifikasi dan mengubah rincian pengaturan.

### Bagian 3: Menyambungkan Host ke WLAN
#### Langkah 1: Sambungkan ke jaringan dan verifikasi konektivitas.
a. Buka desktop Host Nirkabel dan klik ubin Nirkabel PC.

b. Klik tab Connect (Sambungkan). Setelah jeda beberapa saat, Anda akan melihat SSID untuk WLAN muncul di tabel nama jaringan nirkabel. Pilih jaringan SSID-5 dan klik tombol Connect (Sambungkan).

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_200451.jpg)

c. Masukkan kunci pra-berbagi yang telah dikonfigurasikan untuk WLAN, lalu klik Connect.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_200701.jpg)

d. Klik tab Link Information. Anda akan melihat pesan yang mengonfirmasi bahwa Anda telah berhasil tersambung ke titik akses. Anda juga akan melihat gelombang nirkabel pada topologi yang menunjukkan sambungan ke LAP-1.

e. Klik tombol More Information untuk melihat detail tentang sambungan.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_201003-1.jpg)

f. Tutup aplikasi PC Wireless dan buka aplikasi IP Configuration (Konfigurasi IP). Verifikasi bahwa Host Nirkabel telah menerima alamat IP non-APIPA melalui DHCP. Jika tidak, klik tombol Fast Forward Time (Waktu Maju Cepat) beberapa kali.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_201446.jpg)

g. Dari Wireless Host, lakukan ping ke gateway default WLAN dan Server untuk memverifikasi bahwa laptop memiliki konektivitas penuh.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_201348.jpg)