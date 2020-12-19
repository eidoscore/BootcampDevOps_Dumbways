# SSL CONFIGURATION

* kemudian install SSL certificate pada sub domain ``api.khaerul.instructype.com`` dengan perintah berikut :

```
sudo certbot --nginx -d api.khaerul.instructype
choose 2
```

![21](../assets/img_26.PNG)

* kemudian cek apakah SSL sudah terinstal pada backend config, di kasus saya SSL gagal diinstal sehingga terpaksa harus mengganti domain.

```
cat backend.conf
```

![24](../assets/img_27.PNG)
![25](../assets/img_28.PNG)

* terakhir adalah rubah base URL dari API pada server frontend menggunakan alamat api yang sudah di setting

![26](../assets/img_29.PNG)
![27](../assets/img_30.PNG)
