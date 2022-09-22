# Laporan Resmi Praktikum Modul 1 Kelompok D06 Jaringan Komputer D Tahun 2022/2023

Dokumen laporan resmi praktikum modul 1 kelompok D-06 Jaringan Komputer D Tahun 2022/2023

### Anggota Kelompok:
Nama Lengkap                | NRP
--------------------------- | -------------
Fian Awamiry Maulana        | 5025201035 
Rere Arga Dewanata          | 5025201078 
Muhamad Ridho Pratama       | 5025201186  

## Daftar Isi  
- [Soal1](#soal-1)
- [Soal2](#soal-2)
- [Soal3](#soal-3)
- [Soal4](#soal-4)
- [Soal5](#soal-5)
- [Soal6](#soal-6)
- [Soal7](#soal-7)
- [Soal8](#soal-8)
- [Soal9](#soal-9)
- [Soal10](#soal-10)
- [Kendala](#kendala)


## Soal 1   
   Sebutkan web server yang digunakan pada "monta.if.its.ac.id"! 
   
   **Jawaban Soal 1**          
   monta.if.its.ac.id meggunakan web server nginx/1.10.3  
   
   ![Soal1](https://user-images.githubusercontent.com/70679432/191622150-3c0a4590-6369-47de-81c3-eca2f663bd74.png)
     
## Soal 2  
   Ishaq sedang bingung mencari topik TA untuk semester ini, lalu ia datang ke website monta dan menemukan `detail topik` pada website “monta.if.its.ac.id”, judul TA apa yang dibuka oleh Ishaq?  
   
   **Jawaban Soal 2**    
   1. Pertama-tama, filter pada display filter dengan ```http.request.uri contains “detail”``` untuk mendapatkan keyword dari “detail topik” pada soal.
   2. Lalu didapatkan info ```/index.php/topik/detailTopik/194```.  
      ![Soal2_i](https://user-images.githubusercontent.com/70679432/191622394-4e04974b-4a12-4dfd-b2b3-16cf82c6c7d7.png)
   3. Export objects, ambil file html-nya.  
       
   Dari file html “194”, judul TA-nya adalah “Evaluasi unjuk kerja User Space Filesystem FUSE” atau dengan judul “Evaluasi unjuk kerja User Space  Filesystem  (FUSE)” pada http://monta.if.its.ac.id/index.php/topik/detailTopik/194.  
   ![Soal2_ii](https://user-images.githubusercontent.com/70679432/191622401-45ca1bed-6f29-4b73-844a-b51af0b6778d.png)

## Soal 3  
   Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!      
   
   **Jawaban Soal 3**    
   Pada display filter, terapkan: `tcp.dstport == 80 || udp.dstport == 80`. 
   
   ![Soal3](https://user-images.githubusercontent.com/70679432/191622668-79130569-bd09-4ee4-97ad-fbd17ede58f9.png)
   
## Soal 4   
   Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!  
   
   **Jawaban Soal 4**    
   Pada capture filter, terapkan: `src port 21`.  
   
   ![Soal4](https://user-images.githubusercontent.com/70679432/191623221-18c174d0-eaef-4733-a148-140d5401decd.png)
  
## Soal 5 
   Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!  
   
   **Jawaban Soal 5**  
   Pada capture filter, terapkan: `src port 443`.  
   
   ![Soal5_i](https://user-images.githubusercontent.com/70679432/191623319-3e5c284c-4815-42f7-8448-a8626756c543.png)
   ![Soal5_ii](https://user-images.githubusercontent.com/70679432/191623326-7dcb5103-bf46-4dad-bb3c-6ec7d0b06ac7.png)
   
## Soal 6  
   Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id!  
   
   **Jawaban Soal 6**  
   Pada display filter, terapkan: `ip.dst_host contains “lipi.go.id”`.  
   
   ![Soal6](https://user-images.githubusercontent.com/70679432/191623498-5e05fa48-c3e8-49f5-bee0-8092145cef1f.png)
   
## Soal 7  
   Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!  
   
   **Jawaban Soal 7**    
   Pada capture filter, terapkan: `src host <ip_kita>`, misal: `src host 192.168.18.13`.  
   
   ![Soal7_i](https://user-images.githubusercontent.com/70679432/191623804-730a04b1-5222-4847-a1c4-67cfd57bbb13.png)
   ![Soal7_ii](https://user-images.githubusercontent.com/70679432/191623824-d9e18086-518a-44ed-bf08-c0e317f168c8.png)
   
## Soal 8  
   Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.
   
   **Jawaban Soal 8**  
   Cara pertama -> Menggunakan display filter dengan syntax berikut: `tcp.stream eq 12`.
   
   ![Soal8](https://user-images.githubusercontent.com/70679432/191623934-89df905f-50ec-4d0c-a095-7d78179b3ffd.png)
   
   Cara kedua -> Menggunakan display filter dengan syntax sebagai berikut: `(ip.src == 127.0.0.1 && tcp.flags.push == 1) || (ip.src == 127.0.1.1 && tcp.flags.push == 1)`.  
   
   [Gambar-Gambar Soal 8 Cara Kedua](https://drive.google.com/drive/folders/170caLhlqn-XE6bIaBbGWoj2d1IY-Dlv8?usp=sharing)
   
## Soal 9  
   Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format `[nama_kelompok].des3` dan simpan output file dengan nama `flag.txt`.  
   
   **Jawaban Soal 9**  
   1. Berdasarkan percakapan kedua orang diatas, dapat diketahui bahwa file salt dikirim menggunakan `port 9002`. Oleh karena itu, tampilkan file salt yang dikirim menggunakan `port 9002`.  
   
      ![Soal9_i](https://user-images.githubusercontent.com/70679432/191624307-c4bac331-d34a-4f4a-84cd-36e0ae94e2f8.png)
   
   2. Ubah file salt yang telah ditemukan menjadi `raw dan simpan dengan format `[nama_kelompok].des3`.  
   
      ![Soal9_ii](https://user-images.githubusercontent.com/70679432/191624360-cc6d1747-e580-4c9f-a98c-721ad061e973.png)
   
   3. Berdasarkan percakapan kedua orang tersebut, dapat diketahui bahwa salt di-encrypt dengan openssl metode des3. Oleh karena itu, buka terminal dengan mengetikkan command ini `“openssl des3 -d -in D06.des3 -out flag.txt”` untuk melakukan decrypt. Input password sesuai hint dari percakapan `(password = nakano)`. 
   
      ![Soal9_iii](https://user-images.githubusercontent.com/70679432/191624391-d75e117e-73cf-4d73-bfb8-0a31449d372b.png)
   
## Soal 10 
   Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas! Note: Terkait soal nomor 9 dan 10, file yang didapatkan tidak perlu dikumpulkan, cukup tulis flag yang didapatkan ke dalam laporan kalian 🙏
   
   **Jawaban Soal 10**  
   Jika telah menginput password salt = `“nakano”`, maka akan muncul sebuah file flag.txt yang berisikan.  
   
   ![Soal10](https://user-images.githubusercontent.com/70679432/191624474-6349ef33-9631-4251-8552-d7fd8658f40b.png)
   
## Kendala  
- Tidak mengetahui bahwa file salt harus diubah dulu menjadi bertipe raw baru bisa dilakukan decrypt menggunakan openssl des3. Sehingga, harus mencoba-coba semua format yang ada.
- Sempat kebingungan dalam implementasi capture filter, karena sudah mencoba menyalakan FTP Server, FTP Client dan mengirimkan file tetapi data record di Wireshark tidak kedeteksi atau kosong
