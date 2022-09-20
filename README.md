# Jarkom-Modul-1-D06-2022  
## Praktikum Modul 1  
## “Crimping dan Wireshark”  
### Anggota Kelompok:  
### Fian Awamiry Maulana - 5025201035  
### Rere Arga Dewanata- 5025201078  
### Muhamad Ridho Pratama - 5025201186 

#### 1. Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!  
#### Jawab:  
##### “monta.if.its.ac.id” menggunakan web server nginx ```“nginx/1.10.3\r\n”```.  
#### 2.Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan ```detail topik``` pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?  
#### Jawab:  
##### 1. Pertama, filter pada display filter dengan ```http.request.uri contains “detail”``` untuk mendapatkan keyword dari “detail topik” pada soal.
##### 2. Lalu didapatkan info ```/index.php/topik/detailTopik/194```.  
##### 3. Export objects, ambil file html-nya
##### Dari file html “194”, judul TA-nya adalah ```“Evaluasi unjuk kerja User Space Filesystem FUSE”``` atau dengan judul ```“Evaluasi unjuk kerja User Space Filesystem (FUSE)”``` pada http://monta.if.its.ac.id/index.php/topik/detailTopik/194.  
#### 3. Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!  
#### Jawab:
##### Pada display filter, terapkan: ```tcp.dstport == 80 || udp.dstport == 80```.  
#### 4. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!  
#### Jawab:
##### Pada capture filter, terapkan: ```src port 21```.  
#### 5. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!  
#### Jawab:
##### Pada capture filter, terapkan: ```src port 443```.  
#### 6. Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id!  
#### Jawab:
##### Pada display filter, terapkan: ```ip.dst_host contains “lipi.go.id”```.  
#### 7. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!  
#### Jawab:
##### Pada capture filter, terapkan: ```src host <ip_kita>```, misal: ```src host 192.168.18.13```.  
#### 8. Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.
#### Jawab:
##### Cara pertama -> Menggunakan display filter dengan syntax berikut: ```tcp.stream eq 12```.
##### Cara kedua -> Menggunakan display filter dengan syntax sebagai berikut: ```(ip.src == 127.0.0.1 && tcp.flags.push == 1) || (ip.src == 127.0.1.1 && tcp.flags.push == 1)```.  
#### 9. Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format ```[nama_kelompok].des3``` dan simpan output file dengan nama ```“flag.txt”```.
#### Jawab:
##### A. Berdasarkan percakapan kedua orang diatas, dapat diketahui bahwa file salt dikirim menggunakan ```port 9002```. Oleh karena itu, tampilkan file salt yang dikirim menggunakan ```port 9002```.  
##### B. Ubah file salt yang telah ditemukan menjadi ```“raw”``` dan simpan dengan format```[nama_kelompok].des3```.  
##### C. Berdasarkan percakapan kedua orang tersebut, dapat diketahui bahwa salt di-encrypt dengan openssl metode des3. Oleh karena itu, buka terminal dengan mengetikkan command ini ```“openssl des3 -d -in D06.des3 -out flag.txt”``` untuk melakukan decrypt. Input password sesuai hint dari percakapan ```(password = nakano)```.  
#### 10. Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas! Note: Terkait soal nomor 9 dan 10, file yang didapatkan tidak perlu dikumpulkan, cukup tulis flag yang didapatkan ke dalam laporan kalian 🙏
#### Jawab:
##### Jika telah menginput password salt = ```“nakano”```, maka akan muncul sebuah file yang  flag.txt yang berisikan.  
