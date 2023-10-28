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
4. cek ip address :
```sh
if config
```

<h3>Instalasi NGINX</h1>

1. Install nginx  :
```sh
apt install nginx
```
2. karena belum menginstall ssl, maka disarankan mengaktifkan firewall dan mengizinkan lalu lintas
   yang diperlukan saja, disini saya mengizinkan lalu lintas HTTP di port 80 menggunakan perintah
```sh
sudo ufw enable
```
```sh
sudo ufw allow 'nginx HTTTP'
```
3. Untuk mengakses nginx gunakan perintah dibawah ini  :
```sh
hostname -I
```
4. Kemudian copy alamat ip dan coba di browser pilihan anda  :


<h3>Instalasi MySQL</h1>

1. Install Mysql  :
```sh
sudo apt install mysql-server
```
2. Setelah selesai instalasi, disarankan menjalankan skrip keamanan yang sudah diinstall oleh MySQL,<br> skirp ini menghapus pengaturan default yang tidak aman dan menggunci akses ke sistem database:
```sh
sudo mysql_secure_installation
```
3. ketika di berikan pertanyaan jawab Y,dan buatlah kata sandi untuk pengguna root MySQL,
   setelah itu masukan perintah y:

4. Untuk menjalankan perintah MySQL gunakan perintah   :
```sh
sudo mysql
```

<h3>Instalasi PHP</h1>
<h4>Disini saya menggunakan nginx maka dari itu saya menginstall php8.1-fpm</h4>

1. Install PHP 8.1 dan tunggu installasinya selesai.  :
```sh
sudo apt install php8.1-fpm php-mysql
```
