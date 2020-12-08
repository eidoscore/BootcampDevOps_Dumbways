# Install Aplikasi Pada Server

1. Pertama lakukan update pada server ubuntu kita (jika belum update saat instalasi) dengan command **"sudo apt update"**
![29](../assets/Capture29.PNG)

1. Kemudian lakukan upgrade dengan command **"sudo apt upgrade"** dan tunggu sampai selesai.
![30](../assets/Capture30.PNG)

1. Kemudian install Web Server Nginx dengan perintah **"sudo apt install nginx"**
![31](../assets/Capture31.PNG)

1. Setelah selesai jalankan services nginx dengan perintah **"sudo systemctl start nginx"**
![32](../assets/Capture32.PNG)

1. Kemudian buka browser dan masukan ip yang sudah di setting di awal yaitu **"192.168.1.7"** maka akan tampil welcome page Nginx
![33](../assets/Capture33.PNG)

1. Setelah itu kemudian node.js dengan perintah **"curl -sL http://deb.nodesource.org/setup_19.x | sudo -E bash -"**
![34](../assets/Capture34.PNG)

1. Setelah proses diatas selesai kemudian dilanjutkan dengan **"sudo apt install -y nodejs"** dan tunggu sampai proses selesai.
![35](../assets/Capture35.PNG)

1. Setelah semua proses instalasi selesai kita bisa lng mendeploy aplikasi ke server dengan contoh deploy aplikasi housy dalam kasus ini kita hanya akan menginstall salah 1 branch saja, ketikan perintah **"git clonde -b 11.Add-Propery https://github.com/DumbwaysDotId/DW15WDTPH_housy.git"**
![36](../assets/Capture36.PNG)

1. Setelah itu masuk ke direktori housy dengan perintah **"cd DW15WDTPH_housy"** setelah masuk install depedensi nodejs dengan perintah "npm install" dan tunggu sampai prosesnya selesai
![37](../assets/Capture37.PNG)

1. Kemudian jalankan services nodejs dengan perintah **"npm start"**
![38](../assets/Capture38.PNG)

1. Kembali lagi ke browser akses aplikasi yang sudah kita deploy dengan memasukan ip address dan port address bar **"192.168.1.7:3000"** jika berhasil maka akan menampilkan aplikasi yang sudah sukses di deploy.
![39](../assets/Capture39.PNG)