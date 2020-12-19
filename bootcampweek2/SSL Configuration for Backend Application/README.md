# SSL CONFIGURATION

* kemudian install SSL certificate pada sub domain ``api.khaerul.instructype.com`` dengan perintah berikut :

```
sudo certbot --nginx -d api.khaerul.instructype
choose 2
```

![21](../assets/21.PNG)

* kemudian cek apakah SSL sudah terinstal pada backend config, di kasus saya SSL gagal diinstal sehingga terpaksa harus mengganti domain.

```
cat backend.conf
```

![22](../assets/22.PNG)
![23](../assets/23.PNG)

* terakhir adalah rubah base URL dari API pada server frontend menggunakan alamat api yang sudah di setting

![24](../assets/24.PNG)
![25](../assets/25.PNG)
