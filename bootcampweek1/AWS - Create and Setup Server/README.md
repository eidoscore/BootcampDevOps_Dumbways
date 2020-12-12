# Create and Setup Server

1. Pertama Buatlah Sebuah VPC berinama VPC, disini saya menggunakan dari block 10.50.0.0/16
* IPV4 CIDR block : 10.50.0.0/16

![40](../assets/Capture40.PNG)

2. kemudian kita buat subnet Subnet Public dan Private, berikut detail ip untuk Public dan Private Subnet.
* PublicNet : 10.50.1.0/24
* PrivateNet : 10.50.2.0/24


![41](../assets/Capture41.PNG)
![42](../assets/Capture42.PNG)
![43](../assets/Capture43.PNG)

3. Buat Internet Gateway dan berinama dan kemudian Attach atau hubungkan pada VPC yang sudah kita buat sebelumnya.

![44](../assets/Capture44.PNG)
![45](../assets/Capture45.PNG)

4. Buat Route Tables untuk Public Route, hubungkan ke VPC tadi

![46](../assets/Capture46.PNG)

* pada tab Route klik edit Routes

![47](../assets/Capture47.PNG)

* tambahkan destination 0.0.0.0/0 dan Targetnya adalah Internet Gateway yang sudah kita buat sebelumnya.

![48](../assets/Capture48.PNG)

* kemudian pada tab association edit dan asosiasikan dengan PublicNet

![49](../assets/Capture49.PNG)


6. Buat NAT Instances baru Pilih pilih AMI Community pilih image seperti gambar

![50](../assets/Capture50.PNG)
![51](../assets/Capture51.PNG)


7. kemudian pada step ini sesuaikan seperti berikut:
* Network : Gunakan VPC-Server yang sudah dibuat sebelumnya
* Subnet : Gunakan Public Subnet
* Auto-Assign Public IP : enable

![52](../assets/Capture52.PNG)
![53](../assets/Capture53.PNG)

* pada bagian Security Group gunakan all Traffic dan source rubah menjadi ip network Private server.

![54](../assets/Capture54.PNG)
![55](../assets/Capture55.PNG)

8. Kemudian Disable Source/Dstination NAT Instances agar private server dapat terhubung ke internet

![56](../assets/Capture56.PNG)
![57](../assets/Capture57.PNG)


9. Kemudian buat route table untuk private Network

![58](../assets/Capture58.PNG)

* Edit Route tambahkan destination 0.0.0.0/0 dan source menjadi NAT Instances yang sudah kita buat.

![59](../assets/Capture59.PNG)
![60](../assets/Capture60.PNG)

* Terakhir assosiasikan pada PrivateNet
![61](../assets/Capture61.PNG)


# Buat Public dan Private Server

10. Buat Instances Pilih Ubuntu 18.04

![62](../assets/Capture62.PNG)
![63](../assets/Capture63.PNG)

11. kemudian pada step ini sesuaikan seperti berikut:
* Network : Gunakan VPC-Server yang sudah dibuat sebelumnya
* Subnet : Gunakan Public Subnet
* Auto-Assign Public IP : disable

![64](../assets/Capture64.PNG)
![65](../assets/Capture65.PNG)

12. Beri nama security group (optional), buka port seperti gambar berikut :
    * 22 : port untuk akses SSH
    * 80 : port untuk akses HTTP
    * 443 : port untuk akses HTTPS

![66](../assets/Capture66.PNG)
![67](../assets/Capture67.PNG)

# Private Server

13. Pada Server Private pada step ini sesuaikan seperti berikut:
* Network : Gunakan VPC-Server yang sudah dibuat sebelumnya
* Subnet : Gunakan Private Subnet
* Auto-Assign Public IP : disable

dan konfigursi seperti berikut rubah source menjadi ip network public server :
![68](../assets/Capture68.PNG)

# Elastic IP Public Server
14. Buat Elastic IP untuk public server agar server bisa diakses di internet dan ip tidak berubah-ubah.
![69](../assets/Capture69.PNG)
![70](../assets/Capture70.PNG)
![71](../assets/Capture71.PNG)

# Remote Server yang sudah Dibuat

15. remote server dengan ssh, kemudian buat user baru pada server public seperti dibawah

![72](../assets/Capture72.PNG)

* edit config sshd agar ketika login tanpa menggunakan keypair lagi edit di /etc/ssh/sshd_config ubah authentication menjadi yes, setelah restart dan coba login dengan user baru tadi.

![73](../assets/Capture73.PNG)

# Remote private Server
setelah selesai kita akan simpan keypair private di public server, buat file keypair baru dan paste keypair kita disini, kemudian chmod 0600 untuk keypair dan kemudian coba akses, ulangi seperti langkah diatas buat user baru.

![74](../assets/Capture74.PNG)
![75](../assets/Capture75.PNG)



