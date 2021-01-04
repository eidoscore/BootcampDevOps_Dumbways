# Install Docker

* Pertama lakukan update dan upgrade package

``sudo apt update && sudo apt upgrade``

![1](../assets/1.PNG)

* kemudian install software common properties

``sudo apt install apt-transport-https ca-certificates curl software-properties-common
``

![1](../assets/2.PNG)

* tambahkan docker key pada server

``curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
``

![1](../assets/3.PNG)

* tambahkan Repository docker pada masing-masing server

``sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
 ``

![1](../assets/4.PNG)

* kemudian update package yang sudah ditambahkan
`` sudo apt update ``

![1](../assets/5.PNG)

* install package docker dengan command 

`` sudo apt install docker-ce docker-ce-cli containerd.io``

![1](../assets/6.PNG)

* tambahkan docker key pada server

![1](../assets/7.PNG)

* jika tidak ingin menggunakn sudo pada perintah tambahkan command berikut untuk menambahkan docker ke group

``sudo usermod -aG docker ${USER}``
``su - ${USER}``
``id -nG``

![1](../assets/8.PNG)

