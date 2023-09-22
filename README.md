# Jarkom-Modul-1-E15-2023

<table>
    <tr>
        <th colspan=2> Kelompok E05 </th>
    </tr>
    <tr>
        <th>NRP</th>
        <th>Nama Anggota</th>
    </tr>
    <tr>
        <td>5025211014</td>
        <td>Alexander Weynard Samsico</td>
    </tr>
  <tr>
        <td>5025211121</td>
        <td>Frederick Yonatan Susanto</td>
    </tr>
</table>

## 1. User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
Dalam konteks ini, kita dapat mengidentifikasi aktivitas pengguna dengan melihat petunjuk yang diberikan, yaitu "mengunggah suatu file." Tindakan mengunggah file ini dapat dikaitkan dengan operasi         STORE pada komputer, oleh karena itu, kita dapat mencari paket dengan info STOR menggunakan perintah ```tcp contains "STOR"``` dan didapatkan request dan response yang relevan dengan request tersebut yaitu pada paket nomor 147 dan 149.
  
- **Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?**
  
  Dalam pertanyaan ini, kami diminta untuk menemukan nilai sequence number (raw) dari REQUEST STOR. Kita dapat mengakses nilai ini dengan mengamati bagian "Transmission       
  Control Protocol" dalam paket tersebut, dan nilai tersebut akan terdapat di dalamnya. Nilai sequence number (raw) dari REQUEST STOR yaitu ```258040667```.
  ![Screenshot (4365)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/79dfc137-797a-445b-8f25-5bca339055f6)

 
- **Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?**
  
  Selanjutnya pada pertanyaan ini, pada bagian yang sama yaitu di REQUEST STOR dapat kita temukan nilai acknowledgment number (raw). Nilai acknowledgment number (raw) dari REQUEST STOR yaitu ```1044861039```
  ![Screenshot (4365)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/79dfc137-797a-445b-8f25-5bca339055f6)
 
- **Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?**

  Dalam pertanyaan ini, kami diminta untuk menemukan nilai sequence number (raw) dari RESPONSE STOR. Kita dapat mengakses nilai ini dengan mengamati bagian "Transmission       
  Control Protocol" dalam paket tersebut, dan nilai tersebut akan terdapat di dalamnya. Nilai sequence number (raw) dari RESPONSE STOR yaitu ```1044861039```.
  ![Screenshot (4406)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/87ef0234-f7f5-4a5e-97bd-e99b03b05e78)
  
- **Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?**

  Selanjutnya pada pertanyaan ini, pada bagian yang sama yaitu di RESPONSE STOR dapat kita temukan nilai acknowledgment number (raw). Nilai acknowledgment number (raw) dari RESPONSE STOR yaitu 
  ```258040696```
  ![Screenshot (4406)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/87ef0234-f7f5-4a5e-97bd-e99b03b05e78)

  ### Capture The Flag
  ![Screenshot (4366)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/e77be3fe-cbff-4d42-8e69-8597b89db57f)

 
## 2. Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
Untuk mengetahui web server yang digunakan dalam portal praktikum Jaringan Komputer, kita dapat menggunakan filter ```ip.addr == 10.21.78.111``` dalam file soal2. Filter ini digunakan untuk mengambil atau menampilkan paket-paket yang memiliki alamat IP tujuan atau sumber yang sesuai dengan alamat IP yang diberikan, dalam hal ini 10.21.78.111 (alamat ip portal praktikum Jaringan Komputer). Setelah itu, langkah berikutnya adalah mengklik kanan pada paket tersebut, lalu memilih opsi "Follow" dan memilih "TCP Stream". Ini akan membuka tampilan yang menunjukkan request yang telah terjadi, seperti yang diilustrasikan di bawah ini. Di sini, kita dapat melihat rincian server yang digunakan. Web server yang digunakan yaitu ```gunicorn```.
![Screenshot (4362)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/8d50d900-5059-492f-ad5b-7dff271f07c1)

![Screenshot (4363)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/e199420f-1073-42b9-8cda-a154f8b77761)

### Capture The Flag
![Screenshot (4364)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/beec2d65-0190-4026-b350-f917199764bd)

## 3. Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
- Protokol layer transport apa yang digunakan?

## 4. Berapa nilai checksum yang didapat dari header pada paket nomor 130?
Pada soal ini, kita perlu mencari paket ke-130 sesuai permintaan soal, lalu pada bagian “User Datagram Protocol” kita expand dan bisa kita dapatkan nilai checksumnya yaitu ```0x18e5```.
![Screenshot (4368)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/50041560-433d-4c84-9d22-00807c8d93dd)

### Capture The Flag
![Screenshot (4369)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/8cc17932-dc86-4e66-ad9f-f3f38ce9e157)

## 5. Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
- Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
- Port berapakah pada server yang digunakan untuk service SMTP?
- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

## 6. Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
Pada paragraf, huruf-huruf yang dikapital membentuk suatu kata **“SUBSTITUSI”**, lalu terdapat pula **"a1 e5 u21"**, yang menunjukkan bahwa tiap huruf dapat disubstitusi dengan angka sesuai urutan abjad. Maksud dari a1 e5 u21 yaitu a merupakan huruf ke-1, e merupakan huruf ke-5, dan u merupakan huruf ke-21. Lalu, pada pesan error terdapat **“SOURCE 7812”**, itu artinya file pcap paket ke-7812. Sekarang kita berfokus pada kata yang lain yaitu **"SOURCE ADDRESS"**, dimana kita dapat melihat ip source yang ada pada paket ke-7812. Kemudian, kita menghubungkan dari semua clue dan informasi yang kita dapat di atas. Selanjutnya dari ip source tersebut yaitu **“104 18 14 101”**, jika disubstitusi dari angka menjadi huruf sesuai urutan abjad dapat menjadi **"JDRNJA"**` (10 4 18 14 10 1).

Jadi, solusi kode error tersebut yaitu ```JDRNJA```.

![Screenshot (4403)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/54e72106-175d-463e-84ef-1a0665c06188)

### Capture The Flag
![Screenshot (4404)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/be305441-7c89-4470-b442-9099af43d317)

## 7. Berapa jumlah packet yang menuju IP 184.87.193.88?

## 8. Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

## 9. Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
Agar wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34, kita dapat menggunakan query filter yaitu 
```ip.src == 10.51.40.1 && ip.dst != 10.39.55.34```.

#### Penjelasan :

- ```ip.src == 10.51.40.1```: Ini akan mengambil semua paket yang memiliki alamat IP sumber (source IP address) 10.51.40.1.

- ```&&```: Ini adalah operator logika "dan", yang digunakan untuk menggabungkan dua kondisi.

- ```ip.dst != 10.39.55.34```: Ini akan memastikan bahwa alamat IP tujuan (destination IP address) bukan 10.39.55.34. Jadi, paket-paket yang memiliki alamat IP tujuan 10.39.55.34 akan diabaikan.

Dengan menggunakan query ini, kita akan melihat hanya paket-paket yang berasal dari alamat 10.51.40.1 dan tidak menuju ke alamat 10.39.55.34.

### Capture The Flag
![Screenshot (4371)](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/106955551/67c3b2a9-c186-4950-ab1b-201e555e322a)

## 10. Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet



