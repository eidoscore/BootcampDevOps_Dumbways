# Create Docker Image

* Login akun docker

![1](../assets/9.PNG)

*  masuk kedalam direktori lalu buat file Dockerfile isi dengan command berikut

``
FROM node:10
WORKDIR /usr/src/app  
COPY . .  
RUN npm install
EXPOSE 5000
CMD ["npm","start"]
``

![1](../assets/10.PNG)

* kemudian buat file .dockerignore

![1](../assets/12.PNG)

* kemudian build image yang sudah di config sebelumnya :

`` docker build -t eidoscore/backend:1.0 . ``

![1](../assets/13.PNG)

* cek image yang sudah dibuat

![1](../assets/14.PNG)

* tambahkan docker key pada server

![1](../assets/16.PNG)