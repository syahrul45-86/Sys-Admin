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
<h3>konfigurasi SSH Server</h1>

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

<h3>Konfigurasi Ip Address static | Netplan </h1>

1. masuk ke file /etc/netplan/00–installer-config.yaml :
```sh
nano /etc/netplan/00-installer-config.yaml
```
2. Konfigurasi Ip addres, seperti berikut :
```sh
network:
  ethernets:
    enp0s3:
      dhcp4: true
    enp0s8:
      dhcp4: no
      addresses: [192.168.56.108/24] 
      nameservers:
              addresses: [8.8.8.8]
  version: 2

```
3. Setelah konfigurasi selesai, selanjutnya untuk menerapkan konfigurasi gunakan perintah berikut:
```sh
sudo netplan apply
```
3. cek ip address :
```sh
if config
```

