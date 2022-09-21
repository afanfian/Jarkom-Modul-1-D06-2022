# Laporan Resmi Praktikum Modul 1 Kelompok D06 Jaringan Komputer D Tahun 2022/2023

Dokumen laporan resmi praktikum modul 1 kelompok D-06 Jaringan Komputer D Tahun 2022/2023

### Anggota Kelompok:
Nama Lengkap                | NRP
--------------------------- | -------------
Fian Awamiry Maulana        | 5025201035 
Rere Arga Dewanata          | 5025201078 
Muhamad Ridho Pratama       | 5025201186

## Soal 1   
   Sebutkan web server yang digunakan pada "monta.if.its.ac.id"! 
   
   **Jawaban Soal 1**          
   monta.if.its.ac.id meggunakan web server nginx/1.10.3  
       
## Soal 2  
   Ishaq sedang bingung mencari topik TA untuk semester ini, lalu ia datang ke website monta dan menemukan `detail topik` pada website “monta.if.its.ac.id”, judul TA apa yang dibuka oleh Ishaq?  
   
   **Jawaban Soal 2**    
   1. Pertama-tama, filter pada display filter dengan ```http.request.uri contains “detail”``` untuk mendapatkan keyword dari “detail topik” pada soal.
   2. Lalu didapatkan info ```/index.php/topik/detailTopik/194```.  
   3. Export objects, ambil file html-nya.  
       
   Dari file html “194”, judul TA-nya adalah “Evaluasi unjuk kerja User Space Filesystem FUSE” atau dengan judul “Evaluasi unjuk kerja User Space  Filesystem  (FUSE)” pada http://monta.if.its.ac.id/index.php/topik/detailTopik/194.  

## Soal 3  
   Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!      
   
   **Jawaban Soal 3**    
   Pada display filter, terapkan: `tcp.dstport == 80 || udp.dstport == 80`.  
   
## Soal 4   
   Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!  
   
   **Jawaban Soal 4**    
   Pada capture filter, terapkan: `src port 21`.  
  
## Soal 5 
   Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!  
   
   **Jawaban Soal 5**  
   Pada capture filter, terapkan: `src port 443`.  
   
## Soal 6  
   Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id!  
   
   **Jawaban Soal 6**  
   Pada display filter, terapkan: `ip.dst_host contains “lipi.go.id”`.  
   
## Soal 7  
   Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!  
   
   **Jawaban Soal 7**    
   Pada capture filter, terapkan: `src host <ip_kita>`, misal: `src host 192.168.18.13`.  
   
## Soal 8  
   Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.
   
   **Jawaban Soal 8**  
   Cara pertama -> Menggunakan display filter dengan syntax berikut: `tcp.stream eq 12`.
   Cara kedua -> Menggunakan display filter dengan syntax sebagai berikut: `(ip.src == 127.0.0.1 && tcp.flags.push == 1) || (ip.src == 127.0.1.1 && tcp.flags.push == 1)`.  
   
## Soal 9  
   Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format `[nama_kelompok].des3` dan simpan output file dengan nama `flag.txt`.  
   
   **Jawaban Soal 9**  
   1. Berdasarkan percakapan kedua orang diatas, dapat diketahui bahwa file salt dikirim menggunakan `port 9002`. Oleh karena itu, tampilkan file salt yang dikirim menggunakan `port 9002`.    
   2. Ubah file salt yang telah ditemukan menjadi `raw dan simpan dengan format `[nama_kelompok].des3`.  
   3. Berdasarkan percakapan kedua orang tersebut, dapat diketahui bahwa salt di-encrypt dengan openssl metode des3. Oleh karena itu, buka terminal dengan mengetikkan command ini `“openssl des3 -d -in D06.des3 -out flag.txt”` untuk melakukan decrypt. Input password sesuai hint dari percakapan `(password = nakano)`. 
   
## Soal 10 
   Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas! Note: Terkait soal nomor 9 dan 10, file yang didapatkan tidak perlu dikumpulkan, cukup tulis flag yang didapatkan ke dalam laporan kalian 🙏
   
   **Jawaban Soal 10**  
   Jika telah menginput password salt = ```“nakano”```, maka akan muncul sebuah file yang  flag.txt yang berisikan.  
   
## Kendala  
- 
