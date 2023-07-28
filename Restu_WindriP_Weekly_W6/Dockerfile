#Hal pertama yang perlu kita lakukan adalah menentukan dari images apa kita ingin membuilding. Di sini saya menggunakan versi terbaru LTS (long term support) 20-alpine3.17 dari node yang tersedia di Docker Hub
FROM node:20-alpine3.17

# Membuat app directory
WORKDIR /usr/src/app

# Mengintstal app dependencies
# Memastikan package.json DAN package-lock.json tersalin
COPY package*.json ./

# Memudahkan saat proses bulding code,jika kedepannya bekerja as a team production
RUN npm install

# Membundle app source
COPY . .

# Menentukan port sesuai info yang didapat dari source code tugas dengan menggunakan perintah EXPOSE, hal ini bermaksud untuk pemetaan yang dilakukan docker daemon
EXPOSE 3001

#Untuk perintah menjalankan aplikasi gunakan CMD yang akan menentukan runtime aplikasi. Di sini saya akan menggunakan node main.js untuk memulainya
CMD ["node","main.js"]