# instalation
Berikut adalah format README.md untuk instalasi dan konfigurasi web server serta FTP server:

```markdown
# Instalasi dan Konfigurasi Web Server dan FTP Server di Ubuntu

Dokumen ini menjelaskan langkah-langkah instalasi dan konfigurasi web server menggunakan Apache dan FTP server menggunakan `vsftpd` di Ubuntu.

---

## 📂 Instalasi Web Server

### 1. Update Sistem
Jalankan perintah berikut untuk memperbarui paket di sistem Anda:





### 2. Instalasi Apache
```bash
sudo apt update
```
Gunakan perintah berikut untuk menginstal Apache:
```bash
sudo apt install apache2
```

### 3. Konfigurasi Firewall
Izinkan profil Apache untuk akses penuh (HTTP dan HTTPS):
```bash
sudo ufw allow 'Apache Full'
```

### 4. Cek Status Apache
Pastikan Apache sudah berjalan:
```bash
sudo systemctl status apache2
```

### 5. Tes Web Server
- Dapatkan IP address server dengan perintah:
  ```bash
  ifconfig
  ```
- Akses IP tersebut melalui browser Anda untuk memastikan server berjalan dengan baik.

---

## 📂 Instalasi dan Konfigurasi FTP Server

### 1. Update Sistem
Perbarui paket-paket sistem Anda:
```bash
sudo apt update
```

### 2. Instalasi vsftpd
Pasang layanan FTP server:
```bash
sudo apt install vsftpd
```

### 3. Mulai dan Atur Layanan
Jalankan layanan `vsftpd` dan atur agar berjalan otomatis saat boot:
```bash
sudo systemctl start vsftpd
sudo systemctl enable vsftpd
```

### 4. Backup File Konfigurasi Default
Buat cadangan file konfigurasi bawaan:
```bash
sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.bak
```

### 5. Edit File Konfigurasi
Edit file konfigurasi `vsftpd`:
```bash
sudo nano /etc/vsftpd.conf
```
Tambahkan pengaturan tambahan sesuai kebutuhan.

### 6. Buat Direktori FTP
Buat direktori untuk FTP dan atur hak akses:
```bash
sudo mkdir -p /home/username/ftp
sudo chown nobody:nogroup /home/username/ftp
```

### 7. Buat Direktori Unggahan
Buat direktori untuk mengunggah file:
```bash
sudo mkdir /home/username/ftp/upload
sudo chown username:username /home/username/ftp/upload
```

### 8. Restart Layanan vsftpd
Terapkan perubahan konfigurasi dengan me-restart layanan:
```bash
sudo systemctl restart vsftpd
```

---

## 🔧 Troubleshooting
- Jika ada masalah dengan web server, cek log Apache:
  ```bash
  sudo tail -f /var/log/apache2/error.log
  ```
- Untuk masalah dengan FTP server, cek status layanan:
  ```bash
  sudo systemctl status vsftpd
  ```

---

## 📘 Referensi
- Dokumentasi resmi Ubuntu
- Dokumentasi resmi Apache
- Dokumentasi resmi vsftpd

---


