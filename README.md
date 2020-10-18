# Lapres Praktikum Jarkom Modul 1

## 1

### Soal
Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

### Jawaban
- Gunakan display filter: **http.host == “testing.mekanis.me”**
- Follow HTTP Stream dari paket yang telah diperoleh
- Carilah string **server** untuk memperoleh webserver dari website tersebut

![Gambar 1-1](1-1.png)

![Gambar 1-2](1-2.png)

## 2

### Soal
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"

### Jawaban
- Buka File > Export Objects > HTTP
- Kemudian di Text Filter masukkan nama file.
- Save file dengan extensi .jpg

![Gambar 2-1](2-1.png)

![Gambar 2-1](2-2.png)

## 3

### Soal
Cari username dan password ketika login di "ppid.dpr.go.id"!

### Jawaban
- Gunakan display filter: **http.request.method  == “POST” && http.host == “ppid.dpr.go.id”**
- Follow HTTP Stream dari paket yang telah diperoleh
- Carilah string **username** atau **password** untuk memperoleh username dan password ketika login di website tersebut

![Gambar 3-1](3-1.png)

![Gambar 3-2](3-2.png)

## 4

### Soal
Temukan paket dari web-web yang menggunakan basic authentication method!

### Jawaban
- Masukkan **http.authorization contains Basic** ke Display Filter

![Gambar 4](4.png)

## 5

### Soal
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

### Jawaban
Pada website tersebut, kita diminta untuk melakukan proses login. Untuk menemukan login credentials, maka kita perlu mencari username dan password
di file .pcapng yang telah diberikan.

- Gunakan display filter: **http.host == “aku.pengen.pw”**
- Follow HTTP Stream dari paket yang telah diperoleh
- Carilah string **authorization** untuk memperoleh kode base64 dari login credentials
- Konversikan kode base64 ke teks (Bisa melalui third party website) untuk memperoleh login credentials
- Login dan kerjakan soal pada web tersebut

![Gambar 5-1](5-1.png)

![Gambar 5-2](5-2.png)

![Gambar 5-3](5-3.png)

![Gambar 5-4](5-4.png)
## 6

### Soal
Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

### Jawaban
- Masukkan **ftp-data.command contains zipkey.txt** ke Display Filter
- Klik kanan pada paket, kemudian Follow > TCP Stream, diubah jadi RAW dan disimpan dengan ekstensi .txt
- Buka file .txt untuk mendapatkan password.
- Kemudian masukkan **ftp-data.command contains Answer.zip** ke Display Filter
- Klik kanan pada salah satu paket, kemudian Follow > TCP Stream, diubah jadi RAW dan disimpan dengan ekstensi .zip
- Ekstrak file .zip dan masukkan password untuk mendapatkan isi .zip.

![Gambar 6-1](6-1.png)

![Gambar 6-2](6-2.png)

![Gambar 6-3](6-3.png)

![Gambar 6-4](6-4.png)

## 7

### Soal
Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.

### Jawaban
Melalui hint, kita mengetahui bahwa file yang harus kita cari bernama **Yes.pdf**

- Gunakan display filter: **frame contains “Yes.pdf”**
- Follow TCP Stream paket tersebut
- Simpan file yang didapat dengan format **RAW** dan berekstensi **zip**
- Buka file .zip tersebut dan extract file .pdf yang ada di dalam archive tersebut

![Gambar 7-1](7-1.png)

![Gambar 7-2](7-2.png)

![Gambar 7-3](7-3.png)

![Gambar 7-4](7-4.png)

## 8

### Soal
Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

### Jawaban
- Masukkan **frame contains "Microsoft FTP"** ke dalam Display Filter untuk mencari IP dari Microsoft FTP Service.
- Masukkan **ftp.request.command contains RETR && ip.dst == 198.246.117.106** ke dalam Display Filter untuk mencari objek yang didownload.

![Gambar 8-1](8-1.png)

![Gambar 8-2](8-2.png)

## 9

### Soal
Cari username dan password ketika login FTP pada localhost!

### Jawaban
- Gunakan display filter: **ftp.request.command == “USER” || ftp.request.command == “PASS”**
- Akan terlihat Username dan Password yang telah digunakan saat login FTP client

![Gambar 9-1](9-1.png)

## 10

### Soal
Cari file .pdf di wireshark lalu download dan buka file tersebut!

### Jawaban
- Buka menu find (CTRL + F) lalu masukkan Hex Code 25 50 44 46.
- Klik kanan pada paket yang di highlight, kemudian Follow > TCP Stream, diubah jadi RAW dan disimpan dengan ekstensi .pdf

![Gambar 10-1](10-1.png)

![Gambar 10-2](10-2.png)

## 11

### Soal
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

### Jawaban
- Gunakan capture filter: **port 21** (Merupakan port untuk FTP)

![Gambar 11-1](11-1.png)

![Gambar 11-1](11-2.png)

## 12

### Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

### Jawaban
- Masukkan **src port 80** di Capture Filter.

![Gambar 12](12.png)

## 13

### Soal
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

### Jawaban
- Gunakan capture filter: **dst port 443** (Merupakan port untuk https)

![Gambar 13-1](13-1.png)

![Gambar 13-2](13-2.png)

## 14

### Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

### Jawaban
- Buka Comman Prompt, masukkan perintah ipconfig untuk mendapat alamat IP sendiri (192.168.1.16 untuk hasilnya)
- Masukkan **src port 192.168.1.16** di Capture Filter.

![Gambar 14-1](14-1.png)

![Gambar 14-2](14-2.png)

## 15

### Soal
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!

### Jawaban
- Gunakan capture filter: **dst host monta.if.its.ac.id**

![Gambar 15-1](15-1.png)

![Gambar 15-2](15-2.png)
