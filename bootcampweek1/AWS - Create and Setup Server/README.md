# Membuat Server Public dan Private

1. Pertama pilih Launch a Virtul Machine EC2

![40](../assets/Capture40.PNG)

2. Pilih OS Ubuntu Server 18.04 LTS 64-bit

![41](../assets/Capture41.PNG)

3. Gunakan type machine t2-micro

![42](../assets/Capture42.PNG)

4. Pada step ini disable Auto-assign Public IP

![43](../assets/Capture43.PNG)

6. edit storage sesuikan kebutuhan, defultnya adalah 8GB

![44](../assets/Capture44.PNG)


7. Beri nama security group (optional), buka port seperti gambar berikut :
    * 22 : port untuk akses SSH
    * 80 : port untuk akses HTTP
    * 443 : port untuk akses HTTPS

![45](../assets/Capture45.PNG)


8. kemudian buat keypair untuk mengakses server menggunakan SSH, beri nama dan download keypair, kemudian launch instances untuk membuat.

![46](../assets/Capture46.PNG)


9. Masuk ke menu Sidebar Network and Security kemudian pilih menu Elastics IP, lau klik Allocate

![47](../assets/Capture47.PNG)


10. Pilih Elastic IP yaang sudah dialokasikan, pada menu action pilih Associates Elastic IP Address.

![48](../assets/Capture48.PNG)


11. Kemudian cari instances yang sudah kita buat sebelumnya, setelah klik Associate

![49](../assets/Capture49.PNG)

# Create Private Server


12. Untuk proses tahapan pembuatan server sama seperti diatas bedanya disini pada bagian tidak ada yg perlu dirubah kecuali bagian security yang harus menerima semua traffic, setting seperti berikut :
* Rubah Type menjadi All Traffic artinya server akan menerima traffic dari port 0-65535
* Source rubah menjadi My IP yaitu menggunakan ip kita untuk melakukan remote nantinya (untuk sementara).kemudian launch instances

![50](../assets/Capture50.PNG)


# Akses Semua Server dengan SSH


13. akses server dengan perintah ssh -i keypair-kit username@ip-public.
kemudian tambahkan user baru dengan command adduser anwar dengan detail seperti pada gambar, dan tambahkan user ke grup dengan command usermod -aG sudo anwar

![51](../assets/Capture51.PNG)

14. kemudian ubah config sshd agar setiap login hanya perlu mengisikan password buat dengan keypair lagi
* ubah autentikasi menjadi PasswordAuthentication yes

![52](../assets/Capture52.PNG)

15. restart services ssh dengan perintah systemctl restart sshd kemudian keluar dan coba login kembali dengan user yang sudah dibuat ssh anwar@ip-public

![53](../assets/Capture53.PNG)
