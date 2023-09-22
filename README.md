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
- Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
- Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

## 2. Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

## 3. Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- **Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?**
  Untuk dapat menemukan paket-paket tersebut, kita bisa menggunakan display filter
  ```ip.dst == 239.255.255.250 && (tcp.port == 3702 || udp.port == 3702)```
  
  Note:
  - port dimiliki oleh tcp atau udp
  - Di sini lgsg menunjukan destination address 239.255.255.250 karena saat dicek source address `ip.src == 239.255.255.250` tidak ditemukan sebuah paket sehingga langsung menunjukkan `ip.dst` saja
    ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/0e036c0a-7bbc-4e5d-bfed-17d2f95b5779)

  Ditemukan hasil sebagai berikut:\
    ![Screenshot 2023-09-18 193722](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/b4ec4860-5296-46c3-8eb1-ed444abe4ae1)

  Sehingga untuk menjawab pertanyaan ini, ada **21** paket yang tercapture

- Protokol layer transport apa yang digunakan?
  Jika dilihat dari hasil tersebut, semua paketnya menggunakan protokol **UDP**. Sehingga jawaban untuk pertanyaan ini adalah **UDP**

  ### Cara Alternatif
  Kita bisa memanfaatkan fitur Wireshark: Statistics -> IPv4 Statistics -> Destinations and Ports

  Di sana telah ketahuan berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702 beserta Protokol Layer Transport yang digunakan

  ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/bd1ced08-2bc1-4349-a8dd-49463b391127)

  
  ### Capture Flag:
  ![Screenshot 2023-09-18 194032](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/df5e8d8c-8bcb-490e-a2c1-f636a05efa86)


## 4. Berapa nilai checksum yang didapat dari header pada paket nomor 130?

## 5. Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
   Soal ini menyediakan juga zip file yang di mana perlu mencari passwordnya terlebih dahulu\
   ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/269788d2-38d1-4b67-9d2b-128d28df2812)
   ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/b0b37ea7-a7e1-4532-bb2a-bae45812a32d)

   Password dapat ditemukan melalui pcap sebagai berikut:

   Langkah pertama, kita dapat melakukan filter `SMTP` terlebih dahulu, kemudian karena setiap paket mengandung pesan, kita dapat membukanya melalui follow TCP Stream:
   ![Screenshot 2023-09-18 211426](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/a1bfed7e-d435-4f68-8554-606e77a83677)
    ![Screenshot 2023-09-18 211438](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/d1537e26-40d0-4fdf-bfed-dc49ed2cd04b)

   Di sana ada suatu paragraf yang menyatakan password untuk zip
   ```
   I send u a p45sword of a zip file, but you should decode it in Base64.

Here is the p45sword:

NWltcGxlUGFzNXdvcmQ=
   ```

  Akan tetapi, password itu perlu didecode terlebih dahulu (base64). Kita bisa memanfaatkan command Linux:
  ```
    echo NWltcGxlUGFzNXdvcmQ= | bas64 --decode
  ```
   Sehingga didapatkan passwordnya `5implePas5word`\
   ![Screenshot 2023-09-18 211244](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/b29d5fec-c5f5-404c-8e54-bb560d191e82)

   Langkah berikutnya, kita dapat memasukkan password untuk zip itu dan menemukan file `connect.txt` yang berisi nc untuk menjawab pertanyaan-pertanyaan selanjutnya

   Isi file:\
![Screenshot 2023-09-18 211508](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/f9c6bb4a-d7de-4af1-b36d-87005925f4fa)

   
- Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
  Berdasarkan pcapnya, ada 60 packet.\
  ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/1a69ea6a-e782-4fcf-b96b-d909321c9e8f)

- Port berapakah pada server yang digunakan untuk service SMTP?
  Port ke 25 untuk SMTP
- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
  Public IPnya adalah `74.53.140.153`

  ### Capture Flag:
  ![Screenshot 2023-09-18 211451](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/efcf2755-40ba-4e8a-a454-4566c2c3e765)


## 6. Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

## 7. Berapa jumlah packet yang menuju IP 184.87.193.88?
Kita bisa mencari paket-paket destinationnya dengan display filter 
```
ip.dst == 184.87.193.88
```
atau langsung menggunakan fitur Statistics sehingga didapatkan **6** paket
![Screenshot 2023-09-18 190733](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/407164e3-1cd4-4077-9331-71096b3cf8b7)

### Capture Flag:
![Screenshot 2023-09-18 194158](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/43e8b074-58e3-4b7d-85a0-bff9dcab1d66)


## 8. Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
Ada lebih dari satu port yaitu tcp.port dan udp.port sehingga kita bisa mencari keduanya dengan filter:
```
tcp.dstport == 80 || udp.dstport == 80
```
Note: `dstport` = menuju port (destination)
![Screenshot 2023-09-18 192740](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/78afc764-a946-4f90-ae9c-dd37d389d674)

### Capture Flag:
![Screenshot 2023-09-18 194052](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/37c50fdc-398e-4893-91c2-29113badfce4)


## 9. Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

## 10. Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
Kita bisa melakukan filter `telnet` pada pcap
![Screenshot 2023-09-18 195758](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/8566e715-aec0-414e-933a-c482e335edf2)

Kemudian ditemukan jawaban [username]:[password] yang berada di paket 81. Untuk lebih jelasnya, dapat difollow TCP Stream
![Screenshot 2023-09-18 215611](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/46fb7a48-f3cd-464f-ae24-5bb136e92c20)

Jawaban: **dhafin:kesayangannyak0k0**

### Capture Flag:
![Screenshot 2023-09-18 195712](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/b0cfe3b3-eb1b-457f-9176-5afb3372ebcd)

## Kendala:
- Untuk soal 5, membutuhkan waktu lama untuk kepikiran bahwa password untuk zip berada di file pcap itu sendiri (bukan jawaban soal)
- Untuk soal 10, ada banyak kombinasi yang kemungkinan bisa menjadi jawaban sehingga perlu mencari mana yang benar.
  
  ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/a26003a0-8f90-4160-884a-9529ae5a6e6a)

  ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/25d062a0-21e3-4055-9c8f-cd280faeedc4)

  ![image](https://github.com/weynard02/Jarkom-Modul-1-E15-2023/assets/90879937/1ece2824-607e-4420-9b3f-82ab54e3814c)

  dan lain sebagainya.


