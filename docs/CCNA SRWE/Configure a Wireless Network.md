![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/02/13.1.10-Packet-Tracer-%E2%80%93-Configure-a-Wireless-Network.jpg)

## Definition
Perangkat dapat terhubung dan berkomunikasi melalui jaringan nirkabel tanpa menggunakan kabel fisik. Teknologi ini telah mengubah cara kita menggunakan internet, meningkatkan mobilitas dan fleksibilitas.

Perangkat dapat terhubung dan berkomunikasi melalui jaringan nirkabel tanpa menggunakan kabel fisik. Teknologi ini telah mengubah cara kita menggunakan internet, meningkatkan mobilitas dan fleksibilitas.

## PC Admin
### Bagian 1: Menghubungkan ke Router Nirkabel
#### Langkah 1: Hubungkan Admin ke WR.
a. Hubungkan Admin ke WR menggunakan kabel Ethernet langsung melalui port Ethernet. Pilih Connections, yang diwakili oleh tanda petir, dari sisi kiri bawah Packet Tracer. Klik Copper Straight-Through, yang diwakili oleh garis hitam solid.

b. Saat kursor berubah ke mode sambungan, klik Admin dan pilih FastEthernet0. Klik WR dan pilih port Ethernet yang tersedia untuk menyambungkan ujung kabel yang lain.

WR akan bertindak sebagai sakelar ke perangkat yang tersambung ke LAN dan sebagai router ke internet. Admin sekarang tersambung ke LAN (GigabitEthernet 1). Ketika Packet Tracer menampilkan segitiga hijau di kedua sisi sambungan antara Admin dan WR, lanjutkan ke langkah berikutnya.

!!! Note
    Jika tidak ada segitiga hijau yang ditampilkan, pastikan untuk mengaktifkan Tampilkan Lampu Tautan di bawah Opsi > Preferensi. Anda juga dapat mengklik Fast Forward Time tepat di atas kotak pilihan Connections pada bilah kuning.

#### Langkah 2: Konfigurasikan Admin untuk menggunakan DHCP.
Untuk mencapai halaman manajemen WR, Admin harus berkomunikasi di jaringan. Router nirkabel biasanya memiliki server DHCP, dan server DHCP biasanya diaktifkan secara default pada LAN. Admin akan menerima informasi alamat IP dari server DHCP pada WR.

a. Klik Admin, dan pilih tab Desktop.

b. Klik Konfigurasi IP, lalu pilih DHCP.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-11_233848.jpg)

c. Tutup jendela IP Configuration (Konfigurasi IP).

!!! Note
    Nilai dapat bervariasi dalam rentang jaringan karena operasi DHCP yang normal.

#### Langkah 3: Sambungkan ke Antarmuka Web WR.
a. Pada tab Desktop di Admin, pilih Web Browser.

b. Masukkan 192.168.0.1 pada kolom URL untuk membuka halaman konfigurasi web router nirkabel.

c. Gunakan admin untuk nama pengguna dan kata sandi.

d. Di bawah judul Network Setup (Pengaturan Jaringan) pada halaman Basic Setup (Pengaturan Dasar), perhatikan rentang alamat IP untuk server DHCP.

Apakah alamat IP untuk Admin berada dalam kisaran ini? Apakah sudah sesuai dengan yang diharapkan? Jelaskan jawaban Anda.

#### Langkah 4: Konfigurasikan Port Internet WR.
Pada langkah ini, WR dikonfigurasikan untuk merutekan paket dari klien nirkabel ke internet. Anda akan mengonfigurasi port Internet pada WR untuk menyambung ke internet.

a. Di bawah Pengaturan Internet di bagian atas halaman Pengaturan Dasar, ubah metode alamat IP Internet dari Konfigurasi Otomatis - DHCP ke IP Statis.

b. Ketik alamat IP yang akan ditetapkan ke antarmuka Internet sebagai berikut:

Alamat IP Internet: 209.165.200.225

Subnet Mask (Alamat Subnet): 255.255.255.252

Gateway Default: 209.165.200.226

Server DNS: 209.165.201.1

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-11_235239.jpg)

c. Gulir ke bawah halaman dan klik Simpan Pengaturan.

!!! Note
    Jika Anda mendapatkan pesan Request Timeout, tutup jendela Admin dan tunggu hingga lampu oranye berubah menjadi segitiga hijau. Klik tombol fast forward untuk mempercepatnya. Kemudian sambungkan kembali ke WR dari browser Admin menggunakan proses yang dijelaskan pada Langkah 3.

d. Untuk memverifikasi konektivitas, buka peramban web baru dan buka www.cisco.pka server.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-11_235549.jpg)

### Bagian 2: Mengonfigurasi Pengaturan Nirkabel
Dalam aktivitas ini, Anda hanya akan mengonfigurasi pengaturan nirkabel untuk 2,4 GHz.

#### Langkah 1: Konfigurasikan SSID WR.
a. Buka antarmuka GUI WR di 192.168.0.1 di browser web pada Admin.

b. Navigasikan ke Nirkabel > Pengaturan Nirkabel Dasar.

c. Ubah Nama Jaringan (SSID) menjadi aCompany hanya untuk 2,4 GHz. Perhatikan bahwa SSID peka terhadap huruf besar/kecil.

d. Ubah Saluran Standar ke 6 - 2,437GHz.

e. Untuk aktivitas ini, nonaktifkan kedua frekuensi 5 GHz. Biarkan pengaturan lainnya tidak berubah.

f. Gulir ke bagian bawah jendela dan klik Simpan Pengaturan.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-11_235939.jpg)

#### Langkah 2: Konfigurasikan pengaturan keamanan nirkabel.
Pada langkah ini, Anda mengkonfigurasi pengaturan keamanan nirkabel menggunakan mode keamanan WPA2 dengan enkripsi dan kata sandi.

a. Navigasikan ke Nirkabel > Keamanan Nirkabel.

b. Di bawah judul 2,4 GHz, pilih WPA2 Personal untuk Mode Keamanan.

c. Untuk bidang Enkripsi, pertahankan pengaturan AES default.

d. Pada bidang Kata Sandi, masukkan Cisco123! sebagai kata sandi.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_000226.jpg)

e. Klik Simpan Pengaturan.

f. Verifikasi bahwa pengaturan di halaman Pengaturan Nirkabel Dasar dan Keamanan Nirkabel sudah benar dan disimpan.

#### Langkah 3: Hubungkan Klien Nirkabel.
a. Buka Laptop1. Pilih tab Desktop. Klik PC Wireless (Nirkabel PC).

b. Pilih tab Connect (Sambungkan). Klik Refresh bila perlu. Pilih Nama Jaringan Nirkabel aPerusahaan.

c. Masukkan kata sandi yang telah dikonfigurasi pada langkah sebelumnya. Masukkan Cisco123! di bidang kunci yang telah dibagi sebelumnya, lalu klik Connect. Tutup jendela PC Wireless (Nirkabel PC).

d. Buka browser web dan verifikasi bahwa Anda dapat menavigasi ke www.cisco.pka server.

e. Ulangi langkah di atas untuk menyambungkan Laptop2 ke jaringan nirkabel.

### Bagian 3: Menghubungkan Klien Nirkabel ke Jalur Akses
Titik akses (AP) adalah perangkat yang memperluas jaringan area lokal nirkabel. Titik akses terhubung ke router berkabel menggunakan kabel Ethernet untuk memproyeksikan sinyal ke lokasi yang diinginkan.

#### Langkah 1: Konfigurasikan Titik Akses.
a. Sambungkan Port 0 AP ke port Ethernet yang tersedia pada WR menggunakan kabel Ethernet langsung.

b. Klik AP. Pilih tab Config.

c. Di bawah judul INTERFACE, pilih Port 1.

d. Pada bidang SSID, masukkan aCompany.

e. Pilih WPA2-PSK. Masukkan kata sandi Cisco123! di bidang Pass Phrase.

f. Pertahankan AES sebagai Jenis Enkripsi default.

#### Langkah 2: Hubungkan Klien Nirkabel.
a. Buka Laptop3. Pilih tab Desktop. Klik Nirkabel PC.

b. Pilih tab Connect (Sambungkan). Klik Refresh bila perlu. Pilih Nama Jaringan Nirkabel aPerusahaan dengan sinyal yang lebih kuat (Saluran 1), lalu klik Connect.

c. Buka browser web dan verifikasi bahwa Anda dapat menavigasi ke www.cisco.pka server.

### Bagian 4: Tugas Administratif Lainnya
#### Langkah 1: Ubah Kata Sandi Akses WR.
a. Pada Admin, navigasikan ke antarmuka GUI WR di 192.168.0.1.

b. Navigasikan ke Administrasi > Manajemen dan ubah Kata Sandi Router saat ini menjadi cisco.

c. Gulir ke bagian bawah jendela dan klik Simpan Pengaturan.

d. Gunakan nama pengguna admin dan kata sandi baru cisco ketika diminta untuk masuk ke router nirkabel.

Klik OK untuk melanjutkan.

e. Klik Continue dan lanjutkan ke langkah berikutnya.

#### Langkah 2: Ubah rentang alamat DHCP di WR.
Pada langkah ini, Anda akan mengubah alamat jaringan internal dari 192.168.0.0/24 menjadi 192.168.50.0/24. Bila alamat jaringan LAN berubah, alamat IP pada perangkat di LAN dan WLAN harus diperbarui untuk menerima alamat IP baru sebelum masa sewanya habis.

a. Navigasikan ke Setup (Pengaturan) > Basic Setup (Pengaturan Dasar).

b. Gulir ke bawah halaman ke Network Setup (Pengaturan Jaringan).

c. Alamat IP yang ditetapkan untuk IP Router adalah 192.168.0.1. Ubah menjadi 192.168.50.1. Verifikasi bahwa alamat IP masih dimulai dengan .100, dan ada 50 alamat IP yang tersedia di DHCP pool.

d. Tambahkan 209.165.201.1 sebagai server DNS dengan pengaturan DHCP.

![alt](https://a5m9a8c3.rocketcdn.me/wp-content/uploads/2020/09/2020-09-12_001331.jpg)

e. Gulir ke bagian bawah jendela dan klik Simpan Pengaturan.

f. Perhatikan bahwa rentang alamat DHCP telah diperbarui secara otomatis untuk mencerminkan perubahan alamat IP antarmuka. Browser Web akan menampilkan Batas Waktu Permintaan setelah beberapa saat.

g. Tutup browser web Admin.

h. Pada tab Admin Desktop, klik Command Prompt.

i. Ketik ipconfig /renew untuk memaksa Admin mendapatkan kembali informasi IP melalui DHCP.

j. Pastikan bahwa Anda masih dapat menavigasi ke server www.cisco.pka.

k. Perbarui alamat IP di laptop lain untuk memverifikasi bahwa Anda masih dapat menavigasi ke server www.cisco.pka.

l. Perhatikan bahwa Laptop1 tersambung ke AP, bukan ke WR.