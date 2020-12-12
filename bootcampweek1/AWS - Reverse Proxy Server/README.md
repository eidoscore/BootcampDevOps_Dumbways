# Reverse Proxy Web Server

1. lakukan update dan upgrade pada server public kita

````
sudo apt update && sudo apt upgrade
````

![76](../assets/Capture76.PNG)

2. setelah itu install Nginx pada server dengan perintah berikut :

```
 sudo apt install nginx
```
![77](../assets/Capture77.PNG)
![78](../assets/Capture78.PNG)



3. buat file baru pada direktori ```/etc/nginx/site-available/``` buat config dengan nama ```housy.conf```

![79](../assets/Capture79.PNG)

* Setelah itu hubungkan file config kita ke direktori site-enable dan restart nginx dengan cara berikut :

```
ln -s /etc/nginx/site-available/housy.conf /etc/nginx/site-enabled/housy.conf
sudo systemctl restart nginx
```

