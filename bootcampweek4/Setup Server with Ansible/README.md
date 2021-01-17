# Setup Server with Ansible

*  Buat 1 server baru untuk ansible dan berikut ada security group untuk server ansible

![40](../assets/40.PNG)
![41](../assets/41.PNG)

- buat file inventory yang berisi host dari semua server

![42](../assets/42.PNG)

- buat file ansible config

![43](../assets/43.PNG)

- buat file config, copy public key ssh kita ke semua server dengan perintah ```ssh-copy-id .ssh/id_rsa.pub username@host``` dan jalankan update untuk semua server

![44](../assets/44.PNG)
![45](../assets/45.PNG)
![46](../assets/46.PNG)
![47](../assets/47.PNG)

- buat user baru di masin-masing server

![48](../assets/48.PNG)
![49](../assets/49.PNG)

- install nginx pada server public berikut scriptnya kemudian jalankan

![50](../assets/50.PNG)
![51](../assets/51.PNG)

- install docker pada masing-masing server yang sudah di grouping docker

![52](../assets/52.PNG)
![53](../assets/53.PNG)

- kemudian install dan buat database pada server database

![54](../assets/54.PNG)
![55](../assets/55.PNG)
![56](../assets/56.PNG)
![57](../assets/57.PNG)

- lakukan reverse proxy

![58](../assets/58.PNG)
![59](../assets/59.PNG)
![60](../assets/60.PNG)
![61](../assets/61.PNG)
![62](../assets/62.PNG)

- Install Monitoring, pertama buat file untuk config frontend, backend dan lainnya, kemudian jalankan ansible.

![63](../assets/63.PNG)
![64](../assets/64.PNG)
![65](../assets/65.PNG)


# Hasil Setup Server Menggunakan Ansible

![0](../assets/Capture.PNG)
![0](../assets/Capture0.PNG)
![0](../assets/Capture2.PNG)
![0](../assets/Capture3.PNG)
![0](../assets/Capture4.PNG)

