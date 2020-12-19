# Setup Deployment Backend Application

* masuk ke server backend, lakukan update dan upgrade dan install mysql client

````
sudo apt update && sudo apt upgrade
sudo apt install mysql-client
````

![13](../assets/img_17.PNG)

* Clone repo housy backend rename menjadi housy

![15](../assets/img_8.PNG)

* *setelah itu install node js pada server dengan perintah berikut :

```
 curl -sL https://deb.nodesource.com/setup_10.x | bash -
 sudo apt install nodejs -y
```
 * masuk ke direktori backend 

 ```
 npm install
 npm install -g sequelize-cli
 npm install -g pm2
 ```

![16](../assets/img_19.PNG)

* lakukan test remote ke server database yang sudah kita config

```
sudo mysql -u username -h ip-server-database -p
```
![17](../assets/img_18.PNG)


* kemudian setting config database pada aplikasi backend dengan database dan user yang sudah kita buat

```
sudo vi config/config.json
```
![18](../assets/img_20.png)

setelah selesai config database production pada config.json, lakukan migrasi database :

```
sequelize-cli db:migrate
```


