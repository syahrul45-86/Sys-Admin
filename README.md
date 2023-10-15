# Sys-Admin
tugas akhir

<h3>Install SSH</h1>

Langkah-Langkah Instalasi SSH Server :
```sh
apt update
```
```sh
apt install openssh-server 
```
```sh
systemctl start ssh
```
```sh
systemctl enable ssh
system status ssh 
```
<h3>Install SSH</h1>

konfigurasi SSH Server
1. masuk ke file konfigurasai SSH :
```sh
nano /etc/ssh/sshd_config
```
2. Hilangkan Tanda Pagar, pada bagian :
```sh
Port 22
PermitRootLogin yes
```
3. Restart service ssh :
```sh
systemctl restart ssh
```

