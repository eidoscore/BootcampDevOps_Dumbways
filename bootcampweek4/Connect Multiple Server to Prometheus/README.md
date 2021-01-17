# Connect Multiple Server to Prometheus

- Donwload Prometheus dan buat folder untuk prometheus

```
wget https://github.com/prometheus/prometheus/releases/download/v2.22.1/prometheus-2.22.1.linux-amd64.tar.gz

tar -xf prometheus-2.22.1.linux-amd64.tar.gz

sudo mv prometheus-2.22.1.linux-amd64/prometheus prometheus-2.22.1.linux-amd64/promtool /usr/local/bin

sudo mkdir /etc/prometheus /var/lib/prometheus

sudo mv prometheus-2.22.1.linux-amd64/consoles prometheus-2.22.1.linux-amd64/console_libraries /etc/prometheus
```

![6](../assets/6.PNG)

- create file configure 
```
sudo nano /etc/prometheus/prometheus.yml

global:
  scrape_interval: 5s
scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['10.50.2.186:9090']
  - job_name: 'node_exporter'
    static_configs:
      - targets: ['3.208.152.85:9100','10.50.2.150:9100','10.50.2.126:9100','10.50.2.87:9100','10.50.2.41:9100','10.50.2.189:9100','10.50.2.186:9100']


# JANGAN LUPA GANTI IP TARGET
```  
![7](../assets/7.PNG)

- add user and 
```
sudo useradd -rs /bin/false prometheus

sudo chown -R prometheus: /etc/prometheus /var/lib/prometheus

ls -ls /etc
```
![8](../assets/8.PNG)

- buat konfigurasi file sudo vi /etc/systemd/system/prometheus.service


```
[Unit]
Description=Prometheus
After=network.target
[Service]
User=prometheus
Group=prometheus
Type=simple
ExecStart=/usr/local/bin/prometheus \
   --config.file /etc/prometheus/prometheus.yml \
   --storage.tsdb.path /var/lib/prometheus/ \
   --web.console.templates=/etc/prometheus/consoles \
   --web.console.libraries=/etc/prometheus/console_libraries
[Install]
WantedBy=multi-user.target
```

- run the application service
```
sudo systemctl daemon-reload

sudo systemctl enable prometheus

sudo systemctl start prometheus.service

sudo systemctl status prometheus.service

sudo netstat -ntlp
```

![9](../assets/9.PNG)
![10](../assets/10.PNG)
![11](../assets/11.PNG)

- edit buat file config untuk reverse proxy pada nginx
![12](../assets/12.PNG)
![13](../assets/13.PNG)

![14](../assets/14.PNG)
![15](../assets/15.PNG)

- buka web monitoring dan login dengan username/password ```admin```

![16](../assets/16.PNG)

- buat username dan password baru

![17](../assets/17.PNG)

- tambahkan data source

![18](../assets/18.PNG)

- pilih data source dari prometheus

![19](../assets/19.PNG)

- tambahkan ssl pada subdomain

![20](../assets/20.PNG)

- masukan data source yaitu alamat web prometheus

![22](../assets/22.PNG)

- buat panel baru untuk monitoring

![23](../assets/23.PNG)

- buat panel baru untuk monitoring

![24](../assets/24.PNG)
![24](../assets/25.PNG)