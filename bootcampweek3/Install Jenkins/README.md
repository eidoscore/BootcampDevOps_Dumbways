# Install Jenkins

* Buat Instance private baru untuk server jenkins dan perhatikan spesifikasi yang dibutuhkan, install docker menggunakan docker image :

``docker pull jenkins``

![1](../assets/17.PNG)

* jalankan image docker run menggunakan port expose 8080 dan juga port master slave 50000 seperti berikut serta tambahkan volume untuk menyimpan konfigurasi jenkins:

``docker run -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/usr/app jenkins/jenkins ``

![1](../assets/19.PNG)

* reverse proxy server jenkins pada web server dan tambahkan sub domain :


![1](../assets/20.PNG)

* install ssl pada subdomain :


![1](../assets/21.PNG)

* buka direktori jenkins untuk melihat initial password aplikasi jenkins :


![1](../assets/23.PNG)

* buka jenkins pada browser dan mulai instalasi pilih ``Install Suggested Plugins`` :

![1](../assets/24.PNG)
![1](../assets/25.PNG)

* buat penggunana admin kemudian Save and Continue :

![1](../assets/26.PNG)

* Setting Jenkins URL bisa sudah otomatis di set :

![1](../assets/27.PNG)
![1](../assets/28.PNG)

* Install Plugin ``Publish Over SSH`` :

![1](../assets/29.PNG)

* Tambahkan credential dari masing-masing server :

![1](../assets/31.PNG)
![1](../assets/32.PNG)
![1](../assets/33.PNG)
![1](../assets/34.PNG)

* Buat personal akses token pada akun github kita pada setting > appliation dan tambahkan token yang sudah dibuat pada jenkins :

![1](../assets/35.PNG)
![1](../assets/36.PNG)

* pada Global Configuration tambahkan konfigurasi juga dari semua server agar nantinya bisa membuat job pada jenkins :

![1](../assets/37.PNG)

