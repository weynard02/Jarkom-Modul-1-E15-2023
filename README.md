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
  ![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/62aa3d1a-6646-4926-bc87-4ae725aa5eef)


 
- **Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?**
  
  Selanjutnya pada pertanyaan ini, pada bagian yang sama yaitu di REQUEST STOR dapat kita temukan nilai acknowledgment number (raw). Nilai acknowledgment number (raw) dari REQUEST STOR yaitu ```1044861039```
  ![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/37437ac6-e29e-4dbd-b274-8e8cd7e4a901)

 
- **Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?**

  Dalam pertanyaan ini, kami diminta untuk menemukan nilai sequence number (raw) dari RESPONSE STOR. Kita dapat mengakses nilai ini dengan mengamati bagian "Transmission       
  Control Protocol" dalam paket tersebut, dan nilai tersebut akan terdapat di dalamnya. Nilai sequence number (raw) dari RESPONSE STOR yaitu ```1044861039```.
  ![3](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/002935a6-f14a-4fda-b6ff-6ee2d79ac431)

  
- **Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?**

  Selanjutnya pada pertanyaan ini, pada bagian yang sama yaitu di RESPONSE STOR dapat kita temukan nilai acknowledgment number (raw). Nilai acknowledgment number (raw) dari RESPONSE STOR yaitu 
  ```258040696```
  ![4](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/866d0732-6388-4001-a706-a0d7cc19830e)


  ### Capture The Flag:
  ![5](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/7bad9ec3-5003-4a33-831f-e8bb06c4aaa7)


 
## 2. Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
Untuk mengetahui web server yang digunakan dalam portal praktikum Jaringan Komputer, kita dapat menggunakan filter ```ip.addr == 10.21.78.111``` dalam file soal2. Filter ini digunakan untuk mengambil atau menampilkan paket-paket yang memiliki alamat IP tujuan atau sumber yang sesuai dengan alamat IP yang diberikan, dalam hal ini 10.21.78.111 (alamat ip portal praktikum Jaringan Komputer). Setelah itu, langkah berikutnya adalah mengklik kanan pada paket tersebut, lalu memilih opsi "Follow" dan memilih "TCP Stream". Ini akan membuka tampilan yang menunjukkan request yang telah terjadi, seperti yang diilustrasikan di bawah ini. Di sini, kita dapat melihat rincian server yang digunakan. Web server yang digunakan yaitu ```gunicorn```.
![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/65f8f61e-6e33-4396-9ad1-f2aa5646d152)


![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/a8418443-9274-46f7-94b1-211262d46249)


### Capture The Flag:
![3](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/e4a9dcc7-b504-4714-ba65-c4e71ae4c329)


## 3. Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- **Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?**
- 
  Untuk dapat menemukan paket-paket tersebut, kita bisa menggunakan display filter
  
  ```ip.dst == 239.255.255.250 && (tcp.port == 3702 || udp.port == 3702)```
  
  Penjelasan:
  - `ip.dst == 239.255.255.250` destination ip ke 239.255.255.250
  - `&& (tcp.port == 3702 || udp.port == 3702)` dan port (tcp ataupun udp) merupakan 3702 
  - port dimiliki oleh tcp atau udp
  - Di sini lgsg menunjukan destination address 239.255.255.250 karena saat dicek source address `ip.src == 239.255.255.250` tidak ditemukan sebuah paket sehingga langsung menunjukkan `ip.dst` saja
    ![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/972f6143-5e64-434e-992e-10382645edad)


  Ditemukan hasil sebagai berikut:\
    ![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/3f1fe7d7-ccdd-49ea-8a0e-7eb2f1ed70f0)


  Sehingga untuk menjawab pertanyaan ini, ada **21** paket yang tercapture

- **Protokol layer transport apa yang digunakan?**
  
  Jika dilihat dari hasil tersebut, semua paketnya menggunakan protokol **UDP**. Sehingga jawaban untuk pertanyaan ini adalah **UDP**

  ### Cara Alternatif
  Kita bisa memanfaatkan fitur Wireshark: Statistics -> IPv4 Statistics -> Destinations and Ports

  Di sana telah ketahuan berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702 beserta Protokol Layer Transport yang digunakan

  ![3](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/3a7ad6e1-45d4-49ca-8e44-61cf73733422)


  
  ### Capture Flag:
  ![4](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/5d30ac8c-363f-4308-8fee-f2872a59f734)



## 4. Berapa nilai checksum yang didapat dari header pada paket nomor 130?
Pada soal ini, kita perlu mencari paket ke-130 sesuai permintaan soal, lalu pada bagian “User Datagram Protocol” kita expand dan bisa kita dapatkan nilai checksumnya yaitu ```0x18e5```.
![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/c5594635-3520-4a8c-9b5b-fb9378220046)


### Capture The Flag:
![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/66a5612b-8c53-4744-8ac4-573604a23377)


## 5. Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
   Soal ini menyediakan juga zip file yang di mana perlu mencari passwordnya terlebih dahulu\
   ![Screenshot 2023-09-22 115442](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/3cbc4eda-bf8b-4d81-a1ec-361c717cbd45)

   ![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/83632a43-0c87-4951-84e8-25e0e261820c)


   Password dapat ditemukan melalui pcap sebagai berikut:

   Langkah pertama, kita dapat melakukan filter `SMTP` terlebih dahulu, kemudian karena setiap paket mengandung pesan, kita dapat membukanya melalui follow TCP Stream:
   ![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/97d47299-040c-4e4b-a63f-6d43c932536f)

   ![3](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/c56da9ea-e1ef-4e12-b517-fe88b09645a9)


   Di sana ada suatu paragraf yang menyatakan password untuk zip
   ```
   I send u a p45sword of a zip file, but you should decode it in Base64.

Here is the p45sword:

NWltcGxlUGFzNXdvcmQ=
   ```

  Akan tetapi, password itu perlu didecode terlebih dahulu (base64). Kita bisa memanfaatkan command Linux:
  ```
    echo NWltcGxlUGFzNXdvcmQ= | base64 --decode
  ```
   Sehingga didapatkan passwordnya `5implePas5word`\
   ![4](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/743c3615-85b3-4d94-91a1-65226775650f)


   Langkah berikutnya, kita dapat memasukkan password untuk zip itu dan menemukan file `connect.txt` yang berisi nc untuk menjawab pertanyaan-pertanyaan selanjutnya

   Isi file:\
![5](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/dcbb5063-5f82-47b1-8b7b-ceebcd2ad17c)


   
- Berapa banyak packet yang berhasil di capture dari file pcap tersebut?\
  Berdasarkan pcapnya, ada **60** packet.\
  ![6](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/8cbcf53a-235c-49d8-8707-a08be363100f)


- Port berapakah pada server yang digunakan untuk service SMTP?\
  Port ke **25** untuk SMTP
- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?\
  Satu-satunya public IP yang ditemukan dari pcap adalah `74.53.140.153`

  ### Capture Flag:
  ![7](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/dd9abe57-3651-4527-bf2d-9f6c7e5c53e3)



## 6. Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
Pada paragraf, huruf-huruf yang dikapital membentuk suatu kata **“SUBSTITUSI”**, lalu terdapat pula **"a1 e5 u21"**, yang menunjukkan bahwa tiap huruf dapat disubstitusi dengan angka sesuai urutan abjad. Maksud dari a1 e5 u21 yaitu a merupakan huruf ke-1, e merupakan huruf ke-5, dan u merupakan huruf ke-21. Lalu, pada pesan error terdapat **“SOURCE 7812”**, itu artinya file pcap paket ke-7812. Sekarang kita berfokus pada kata yang lain yaitu **"SOURCE ADDRESS"**, dimana kita dapat melihat ip source yang ada pada paket ke-7812. Kemudian, kita menghubungkan dari semua clue dan informasi yang kita dapat di atas. Selanjutnya dari ip source tersebut yaitu **“104 18 14 101”**, jika disubstitusi dari angka menjadi huruf sesuai urutan abjad dapat menjadi **"JDRNJA"**` (10 4 18 14 10 1).

Jadi, solusi kode error tersebut yaitu ```JDRNJA```.

![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/c2eb184c-eb23-40d0-be6f-4c8197a6fa44)


### Capture The Flag:
![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/81927e42-a342-4deb-85d1-5cc75aefbf97)


## 7. Berapa jumlah packet yang menuju IP 184.87.193.88?
Untuk soal ini, kita bisa mencari paket-paket destinationnya dengan display filter 
```
ip.dst == 184.87.193.88
```
Penjelasan: destination ip ke 184.87.193.88

atau langsung menggunakan fitur Statistics 

sehingga didapatkan **6** paket
![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/cac7e352-89be-4959-9bed-becf26afabd8)


### Capture Flag:
![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/9fe17db7-e194-42af-8efa-d0f0c323a35b)



## 8. Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
Ada lebih dari satu port yaitu tcp.port dan udp.port sehingga kita bisa mencari keduanya dengan filter:
```
tcp.dstport == 80 || udp.dstport == 80
```
Penjelasan: 
- `dstport` = menuju port (destination)
- `||` merupakan "atau" karena kita mencari dari 2 jenis port == 80 yang ada
![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/7773becc-e8c5-455d-b96b-09941988f580)


### Capture Flag:
![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/a772bb21-19ed-4425-874e-b2ea3bb174ec)



## 9. Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
Agar wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34, kita dapat menggunakan query filter yaitu 
```ip.src == 10.51.40.1 && ip.dst != 10.39.55.34```.

#### Penjelasan :

- ```ip.src == 10.51.40.1```: Ini akan mengambil semua paket yang memiliki alamat IP sumber (source IP address) 10.51.40.1.

- ```&&```: Ini adalah operator logika "dan", yang digunakan untuk menggabungkan dua kondisi.

- ```ip.dst != 10.39.55.34```: Ini akan memastikan bahwa alamat IP tujuan (destination IP address) bukan 10.39.55.34. Jadi, paket-paket yang memiliki alamat IP tujuan 10.39.55.34 akan diabaikan.

Dengan menggunakan query ini, kita akan melihat hanya paket-paket yang berasal dari alamat 10.51.40.1 dan tidak menuju ke alamat 10.39.55.34.

### Capture The Flag:
![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/5f3bf4fc-70e7-4472-97e3-830b79e62157)


## 10. Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
Pertama, kita bisa melakukan filter `telnet` pada pcap
![1](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/6beb163b-ccec-4811-a4e7-ce31d729608b)


Kemudian ditemukan jawaban [username]:[password]. Untuk lebih jelasnya, dapat difollow TCP Stream
![2](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/7bb0f7ba-be3e-4b01-882a-2fd57b1cc53d)


Untuk meyakinkan bahwa kredensial ini yang digunakan untuk login, bisa dengan filter `telnet contains "Login"` dapat ditemukan TCP Stream berikut\
![3](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/693bf40c-90be-4beb-a844-a14384bd382b)

Jawaban: **dhafin:kesayangannyak0k0**

### Capture Flag:
![4](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/ef4f9cdd-f061-473f-b690-ce2a1951efc2)


## Kendala:
- Untuk soal 5, membutuhkan waktu lama untuk kepikiran bahwa password untuk zip berada di file pcap itu sendiri (bukan jawaban soal).
- Untuk soal 6, kesulitan dan membutuhkan waktu lama untuk menemukan clue dan informasi yang dibutuhkan untuk memecahkan solusi soal tersebut (minimnya clue pada soal).
- Untuk soal 10, sempat bingung karena ada banyak kombinasi [username]:[password] yang kemungkinan bisa menjadi jawaban sehingga perlu mencari mana yang benar. Yang benar adalah kredensial itu berada di pesan "Login...".
