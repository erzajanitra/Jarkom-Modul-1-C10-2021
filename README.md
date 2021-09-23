# Soal dan Pembahasan Modul 1 

## No 1
### Soal 
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
## No 2
### Soal 
Temukan paket dari web-web yang menggunakan basic authentication method!
## No 3
### Soal 
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
## No 4
### Soal 
Temukan paket mysql yang mengandung perintah query select!
## No 5
### Soal 
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
## No 6
### Soal 
Cari username dan password ketika melakukan login ke FTP Server!
## No 7
### Soal 
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
## No 8
### Soal 
Cari paket yang menunjukan pengambilan file dari FTP tersebut!
## No 9
### Soal 
Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
## No 10
### Soal 
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
## No 11
### Soal 
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
* Menggunakan capture filter dengan command **src port 80** untuk menangkap paket yang berasal dari port 80. Port 80 digunakan untuk mengakses web HTTP. <br>
![image](https://user-images.githubusercontent.com/75319371/134529649-64a49d7e-1ca4-4a7f-92d4-1199a247e20e.png)
## No 12
### Soal 
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
* Menggunakan capture filter dengan command **port 21** untuk menangkap paket yang mengandung port 21. Paket yang mengandung port 21 adalah paket yang berasal dari port 21 dan memiliki tujuan ke port 21. Port 21 digunakan untuk mengakses filezilla server<br>
![image](https://user-images.githubusercontent.com/75319371/134529353-708b7c35-1786-4839-b76c-ac2b25fdf43e.png)
## No 13
### Soal 
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
* Menggunakan capture filter dengan command **dst port 443** untuk menangkap paket yang tujuannya ke port 443.<br>
![image](https://user-images.githubusercontent.com/75319371/134527896-040a6d42-0908-4c81-81ca-5632d1429268.png)
## No 14
### Soal 
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
* Menggunakan capture filter dengan command **dst host kemenag.go.id** untuk menangkap paket yang tujuannya ke kemenag.go.id. Paket-paket tersebut didapatkan ketika mengakses web kemenag.go.id.<br>
![image](https://user-images.githubusercontent.com/75319371/134527646-39a6aa5f-3ec8-4381-bd2e-4ae32882e21e.png)
## No 15
### Soal 
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
* Untuk menangkap paket yang berasal dari ip host menggunakan command **src host [ip address]** dengan IP Address yang digunakan ketika praktikum adalah 192.168.43.67 <br>
![image](https://user-images.githubusercontent.com/75319371/134527538-c5491dc8-5275-4590-b80b-0ab15a33ed25.png)
