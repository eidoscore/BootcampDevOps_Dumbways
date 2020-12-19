# Setup Setup Database

* masuk ke server database melalui server backend, lakukan update dan upgrade

````
sudo apt update && sudo apt upgrade
````

* Install Mysql Server Gunakan MySQL versi 5.7

![0](../assets/5.PNG)
![0](../assets/6.PNG)
![0](../assets/7.PNG)



* Setelah proses instalasi selesai masuk ke mysql

````
sudo mysql -u root -p
````

* pada dasarnya default mysql tidak memiliki password maka dari itu kita akan menambahakn password pada user root dengan perintah dibawah, setelah relog dengan password baru.

![10](../assets/8.PNG)

* disini kita akan membuat user baru untuk mengakses server database agar bis di remote malalui backend.

```
create user 'namauser'@'ip-server-backend' identified by 'password'; 

grant all on *.* to 'namauser'@'ip-server-backend';

FLUSH PRIVILEGES;
```

![11](../assets/9.PNG)
![12](../assets/10.PNG)
![13](../assets/11.PNG)

* Kemudian Setting bind Address dari server database menggunakan ip private server.

![14](../assets/12.PNG)
