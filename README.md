# Soal dan Pembahasan Modul 1

## No 1

### Soal

Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!

- Untuk mencari webservernya, kita bisa menggunakan display filter `http.host == ichimarumaru.tech`
  ![1a](screenshots/1a.png)

- Setelah itu, lakukan follow pada HTTP streamnya
  ![1b](screenshots/1b.png)

- Lalu, muncullah web server dari host yang dicari
  ![1c](screenshots/1c.png)

## No 2

### Soal

Temukan paket dari web-web yang menggunakan basic authentication method!

- Untuk mencari web yang menggunakan basic authentication method, dapat digunakan display filter `http.authbasic`
  ![2](screenshots/2a.png)

## No 3

### Soal

Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

- Lakukan display filter menggunakan `http.authbasic` dan cari credetials di dalam bagian authentication, bagian kiri sebelum ':' adalah username dan bagian lainnya adalah password
  ![3a](screenshots/3a.png)

- Setelah dimasukkan ke dalam basic.ichimarumaru.tech, website menampilkan soal mengenai pengkabelan T568A.
  ![3b](screenshots/3b.png)

## No 4

### Soal

Temukan paket mysql yang mengandung perintah query select!

- Untuk mencari paket mysql mengandung query select, dapat digunakan display filter `mysql.query matches select`
  ![4](screenshots/4a.png)

## No 5

### Soal

Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

- Untuk mencari query insert, dapat menggunakan display filter seperti pada no 4 yaitu `mysql.query matches insert`, setelah itu bisa kita lihat pada bagian statement dari sqlnya terdapat username dan password.
  ![5a](screenshots/5a.png)
  
- Setelah login terdapat soal mengenai pengkabelan T658B
  ![5b](screenshots/5b.png)

## No 6

### Soal

Cari username dan password ketika melakukan login ke FTP Server!

- Menggunakan display filter dengan command **ftp contains “USER” || ftp contains “PASS”** untuk melakukan filter agar hanya USER (username) dan PASS (password) yang muncul. <br>
  ![image](screenshots/6a.png)

## No 7

### Soal

Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

- Menggunakan display filter dengan command **frame contains Real.pdf** untuk melakukan filter agar yang muncul hanya yang mempunyai **Real.pdf**.<br>
  ![image](screenshots/7a.png)
- Untuk mendownload filenya kita lakukan **Right Click -> Follow -> TCP Stream**. <br>
  ![image](screenshots/7b.png)
- Lalu lakukan **Show Data as Raw** lalu download file tersebut. Isi file sebagai berikut: <br>
  ![image](screenshots/7c.png)

## No 8

### Soal

Cari paket yang menunjukan pengambilan file dari FTP tersebut!

- Menggunakan display filter **ftp.request.command == RETR** untuk menunjukkan paket yang menunjukkan pengambilan file dari ftp. <br>
  ![image](screenshots/8a.png)

## No 9

### Soal

Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

- Menggunakan display filter **ftp-data.command contains secret.zip** untuk mencari file yang mengandung kata **secret.zip**. <br>
  ![image](screenshots/9a.png)
- Lalu untuk mendownload filenya dilakukan **Right Click -> Follow -> TCP Stream**. <br>
  ![image](screenshots/9b.png)
- Setelah itu lakukan **Show Data as Raw** dan download file tersebut. Saat File zip tersebut sudah didownload dan dibuka, maka akan muncul kolom untuk menambahkan password. <br>
  ![image](screenshots/9c.png)
- Password didapatkan dari soal No 10, dan setelah dimasukkan passwordnya akan muncul gambar berikut: <br>
  ![image](screenshots/9d.png)

## No 10

### Soal

Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

- Menggunakan display filter **ftp-data.command contains history.txt** untuk menyaring file yang hanya mengandung kata **history.txt**. <br>
  ![image](screenshots/10a.png)
- Lalu untuk membuka filenya dilakukan **Right Click -> Follow -> TCP Stream**. <br>
  ![image](screenshots/10b.png)
- Isi file mengandung command bash yang menyatakan bahwa password berada di dalam file **bukanapaapa.txt**. <br>
  ![image](screenshots/10c.png)
- Setelah itu digunakan display filter **ftp-data.command contains bukanapaapa.txt** untuk menyaring file yang hanya mengandung kata **bukanapaapa.txt**. <br>
  ![image](screenshots/10d.png)
- Sama seperti tadi, untuk membuka filenya dilakukan **Right Click -> Follow -> TCP Stream**. <br>
  ![image](screenshots/10e.png)
- Di dalam file tersebut berisi password yang dibutuhkan untuk soal No 9. <br>
  ![image](screenshots/10f.png)

## No 11

### Soal

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

- Menggunakan capture filter dengan command **src port 80** untuk menangkap paket yang berasal dari port 80. Port 80 digunakan untuk mengakses web HTTP. <br>
- Pada gambar dibawah ini tidak terdapat paket yang ditangkap karena tidak sedang mengakses web HTTP<br>
  ![image](https://user-images.githubusercontent.com/75319371/134529649-64a49d7e-1ca4-4a7f-92d4-1199a247e20e.png)

## No 12

### Soal

Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

- Menggunakan capture filter dengan command **port 21** untuk menangkap paket yang mengandung port 21. Paket yang mengandung port 21 adalah paket yang berasal dari port 21 dan memiliki tujuan ke port 21. Port 21 digunakan untuk mengakses filezilla server<br>
- Pada gambar dibawah ini tidak terdapat paket yang ditangkap karena tidak sedang mengakses filezilla server<br>
  ![image](https://user-images.githubusercontent.com/75319371/134529353-708b7c35-1786-4839-b76c-ac2b25fdf43e.png)

## No 13

### Soal

Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

- Menggunakan capture filter dengan command **dst port 443** untuk menangkap paket yang tujuannya ke port 443.<br>
  ![image](https://user-images.githubusercontent.com/75319371/134527896-040a6d42-0908-4c81-81ca-5632d1429268.png)

## No 14

### Soal

Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

- Menggunakan capture filter dengan command **dst host kemenag.go.id** untuk menangkap paket yang tujuannya ke kemenag.go.id. Paket-paket tersebut didapatkan ketika mengakses web kemenag.go.id.<br>
  ![image](https://user-images.githubusercontent.com/75319371/134527646-39a6aa5f-3ec8-4381-bd2e-4ae32882e21e.png)

## No 15

### Soal

Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

- Untuk menangkap paket yang berasal dari ip host menggunakan command **src host [ip address]** dengan IP Address yang digunakan ketika praktikum adalah 192.168.43.67 <br>
  ![image](https://user-images.githubusercontent.com/75319371/134527538-c5491dc8-5275-4590-b80b-0ab15a33ed25.png)
