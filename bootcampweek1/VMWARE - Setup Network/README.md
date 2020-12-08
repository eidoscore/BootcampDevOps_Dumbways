# Konfigurasi Adapter Agar Dapat Terhubung Ke Internet


1. Buka Settings Pada Mesin VirtualBox kita.

![25](../assets/Capture25.PNG)

2. Masuk Tab **Network** > Pada Adapter 1 Rubah dari **NAT** ke **Bridge Adapter.**

![26](../assets/Capture26.PNG)

3. Jalankan VM kembali dan rubah settingan ip dari DHCP ke Static dengan menjalan perintah **"sudo vi /etc/netplan/00-installer-config.yaml"** tekan **e** untuk edit, setelah tekan **i** untuk melakukan insert data. edit seprti pada gambar.

![27](../assets/Capture27.PNG)

4. kemudian restart servicesnya dengan perintah **"sudo netplan apply"** jika semuanya benar akan tampil seperti gambar.

![28](../assets/Capture28.PNG)