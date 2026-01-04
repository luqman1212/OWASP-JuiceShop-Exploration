# OWASP Juice Shop - Security Exploration Lab
Proyek ini berisi dokumentasi setup dan vulnerability pada aplikasinya

## Prerequisites
- Docker Engine / Docker Desktop
- Docker Compose

## Setup
Untuk menjalankan lab ini, gunakan perintah ini di terminal:
```bash
docker-compose up -d
```

Akses Aplikasi Melalui Web http://localhost:3000

### Temuan Vulnerability
#### **A. SQL Injection (Authentication Bypass)**
* **Vulnerability:** SQL Injection pada form login.
* **Payload:** `' or 1=1 --`
* **Hasil:** Berhasil masuk ke akun administrator tanpa mengetahui kata sandi yang asli.

#### **B. Cross-Site Scripting (Reflected XSS)**
* **Vulnerability:** Kurangnya sanitasi input pada fitur pencarian (search bar)
* **Payload:** `<img src=x onerror=alert('Hacked')>`
* **Hasil:** Script berhasil dieksekusi oleh browser dan memunculkan jendela alert 'Hacked'

### Bukti Visual

## Evidence
![XSS Alert](xss-alert.png)
