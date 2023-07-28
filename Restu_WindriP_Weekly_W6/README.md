# Membuat Node.js app

## Install Docker

![alt text](asset/1d.png)

### Pada tahap ini, Docker meminta saya untuk update wsl

![alt text](asset/2d.png)

### Ini bukti bahwa docker telah terinstal

![alt text](asset/3d.png)

![alt text](asset/19d.png)

### Download source code Node.js dan menyimpannya dengan nama main.js

![alt text](asset/cd20.png)

### Membuat image menggunakan Dockerfile tanpa instalasi Node.js

![alt text](asset/4d.png)

![alt text](asset/5d.png)

![alt text](asset/6d.png)

### Menjalakan Container dengan melakukan setting pada bagian port yang akan dapat mengakses port source code(-p), di sini saya memilih port 8081 untuk bisa mengakses port source code di 3001. Lalu memberi perintah untuk menjalankan Container di bagian belakang dan tampilkan ID Container tsb (-d)

![alt text](asset/7d.png)

### Melakukan cek apakah Container tersebut sudah berhasil dijalankan(ps)

![alt text](asset/8d.png)

### Saya mencoba akses sesuai port yang sudah disetting sebelumnya

![alt text](asset/9d.png)


## 1. Membuat Direktori Baru
### Tempat semua file akan disimpan. Di direktori ini buat file package.json yang mendeskripsikan aplikasi  dan dependensinya:

![alt text](asset/10d.png)

### Dengan file package.json baru, jalankan npm install. Jika menggunakan npm versi 5 atau lebih baru, ini akan menghasilkan file package-lock.json yang akan disalin ke image Docker Anda.

## 2. Buat file main.js

### Ini menunjukan bahwa aplikasi web dibangun menggunakan bahasa JavaScript

![alt text](asset/11d.png)


## 3. Membuat Dockerfile 

### Buat file kosong bernama Dockerfile di teks editor yang anda suka, di sini saya menggunakan VSCode

![alt text](asset/12d.png)

### Hal pertama yang perlu kita lakukan adalah menentukan dari images apa kita ingin membuilding. Di sini saya menggunakan versi terbaru LTS (long term support) 20-alpine3.17 dari node yang tersedia di Docker Hub

![alt text](asset/13d.png)

### Selanjutnya kita membuat direktori untuk menyimpan kode aplikasi di dalam images, ini akan menjadi direktori eksekusi untuk aplikasi saya

![alt text](asset/14d.png)

### Images ini dilengkapi Node.js dan NPM yang sudah diinstal sehingga hal selanjutnya adalah menginstal dependensi aplikasi menggunakan npm. Harap perhatikan bahwa jika Anda menggunakan npmversi 4 atau sebelumnya, package-lock.json file tidak akan dibuat.

![alt text](asset/15d.png)

### Daripada menyalin seluruh direktori, saya hanya menyalin file package.json. Ini memungkinkan saya memanfaatkan chaced layer Docker. Selain itu, npm membantu menyediakan proses build yang lebih  faster, reliable, reproducible untuk lingkungan produksi kedepannya

### Membundle source code aplikasi ke dalam Image Docker dengan perintah COPY

![alt text](asset/16d.png)

### Menentukan port sesuai info yang didapat dari source code tugas dengan menggunakan perintah EXPOSE, hal ini bermaksud untuk pemetaan yang dilakukan docker daemon

![alt text](asset/17d.png)

### Untuk perintah menjalankan aplikasi gunakan CMD yang akan menentukan runtime aplikasi. Di sini saya akan menggunakan node main.js untuk memulainya

![alt text](asset/18d.png)

### Tampilan keselurah dari bentuk Dockerfile yang saya buat

![alt text](asset/20d.png)