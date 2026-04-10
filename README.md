<div align="center">

# KasKelas

![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)
![Version](https://img.shields.io/badge/Version-1.0.0-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?style=flat-square&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.x-7952B3?style=flat-square&logo=bootstrap&logoColor=white)

**Sistem Manajemen Kas Kelas Berbasis Web**

Platform pengelolaan keuangan kelas yang transparan, mudah digunakan, dan dapat diakses oleh seluruh anggota kelas.

</div>

---

## Daftar Isi

- [Deskripsi](#deskripsi)
- [Tujuan](#tujuan)
- [Fitur Utama](#fitur-utama)
- [Teknologi yang Digunakan](#teknologi-yang-digunakan)
- [Struktur Folder](#struktur-folder)
- [Instalasi dan Setup](#instalasi-dan-setup)
- [Konfigurasi Database](#konfigurasi-database)
- [Akun Default](#akun-default)
- [Preview](#preview)
- [Roadmap](#roadmap)
- [Catatan Tambahan](#catatan-tambahan)
- [Developer](#developer)

---

## Deskripsi

**KasKelas** adalah aplikasi web yang dirancang untuk membantu pengelolaan keuangan kas kelas secara digital, terstruktur, dan transparan. Dibangun menggunakan PHP dan MySQL, sistem ini memudahkan bendahara dalam mencatat setiap transaksi pemasukan maupun pengeluaran, sekaligus memberikan akses laporan keuangan yang dapat dilihat oleh seluruh anggota kelas tanpa perlu login.

---

## Tujuan

Proyek ini dibuat dengan tujuan:

- Menggantikan pencatatan kas kelas manual yang rentan terhadap kesalahan dan kehilangan data
- Meningkatkan **transparansi** pengelolaan keuangan kelas kepada seluruh anggota
- Memberikan **akses laporan keuangan secara real-time** tanpa harus menunggu laporan bulanan
- Memudahkan bendahara dalam mencatat, mengedit, dan memantau riwayat transaksi
- Menjadi portofolio proyek berbasis web yang fungsional dan realistis

---

## Fitur Utama

### Untuk Admin (Bendahara)

| Fitur | Keterangan |
|---|---|
| Login & Logout | Autentikasi aman menggunakan session PHP |
| Tambah Pemasukan | Pencatatan pemasukan kas (iuran, donasi, dll.) dengan tanggal dan keterangan |
| Tambah Pengeluaran | Pencatatan pengeluaran kas (pembelian, kegiatan, dll.) |
| Edit Transaksi | Mengubah data transaksi yang telah dicatat |
| Hapus Transaksi | Menghapus transaksi dengan konfirmasi |
| Dashboard Admin | Ringkasan saldo, total pemasukan, dan total pengeluaran |

### Untuk Pengguna Umum (Anggota Kelas)

| Fitur | Keterangan |
|---|---|
| Lihat Saldo Kas | Menampilkan saldo kas kelas terkini |
| Riwayat Transaksi | Daftar lengkap transaksi pemasukan dan pengeluaran |
| Filter Transaksi | Penyaringan data berdasarkan jenis transaksi atau periode |
| Tampilan Responsif | Dapat diakses melalui smartphone maupun komputer |

---

## Teknologi yang Digunakan

### Frontend

- **HTML5** — Struktur halaman web
- **CSS3** — Styling dan tampilan antarmuka
- **Bootstrap 5** — Framework CSS untuk tampilan responsif
- **JavaScript** — Interaktivitas halaman (konfirmasi hapus, validasi form)

### Backend

- **PHP 8.x** — Bahasa pemrograman server-side utama
- **Session PHP** — Manajemen autentikasi pengguna

### Database

- **MySQL 8.0** — Penyimpanan data transaksi dan akun admin

### Tools & Environment

- **XAMPP / Laragon** — Local development server
- **Apache** — Web server
- **phpMyAdmin** — Manajemen database via GUI

---

## Struktur Folder

```
kaskelas/
├── assets/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js
│   └── img/
│       └── logo.png
├── config/
│   └── database.php
├── includes/
│   ├── header.php
│   ├── footer.php
│   ├── navbar.php
│   └── auth.php
├── admin/
│   ├── dashboard.php
│   ├── tambah_transaksi.php
│   ├── edit_transaksi.php
│   └── hapus_transaksi.php
├── public/
│   └── riwayat.php
├── sql/
│   └── kaskelas.sql
├── login.php
├── logout.php
├── index.php
└── README.md
```

---

## Instalasi dan Setup

Ikuti langkah-langkah berikut untuk menjalankan proyek ini di lingkungan lokal:

### Prasyarat

Pastikan perangkat Anda telah terpasang:

- [XAMPP](https://www.apachefriends.org/) atau [Laragon](https://laragon.org/)
- Web browser modern (Chrome, Firefox, Edge)
- Git (opsional)

---

### Langkah 1 — Clone atau Unduh Repositori

```bash
git clone https://github.com/username/kaskelas.git
```

Atau unduh sebagai file `.zip` lalu ekstrak ke folder `htdocs` (XAMPP) atau `www` (Laragon).

---

### Langkah 2 — Pindahkan ke Direktori Server Lokal

```bash
# Untuk XAMPP
C:/xampp/htdocs/kaskelas/

# Untuk Laragon
C:/laragon/www/kaskelas/
```

---

### Langkah 3 — Import Database

1. Jalankan **Apache** dan **MySQL** melalui XAMPP/Laragon
2. Buka browser dan akses `http://localhost/phpmyadmin`
3. Buat database baru dengan nama `kaskelas`
4. Pilih database tersebut, lalu klik tab **Import**
5. Upload file `sql/kaskelas.sql` dan klik **Go**

---

### Langkah 4 — Konfigurasi Koneksi Database

Edit file `config/database.php` dan sesuaikan dengan konfigurasi lokal Anda (lihat bagian [Konfigurasi Database](#konfigurasi-database)).

---

### Langkah 5 — Jalankan Aplikasi

Buka browser dan akses:

```
http://localhost/kaskelas/
```

---

## Konfigurasi Database

Edit file `config/database.php` sesuai dengan pengaturan server lokal Anda:

```php
<?php

define('DB_HOST', 'localhost');
define('DB_USER', 'root');        // Username database Anda
define('DB_PASS', '');            // Password database Anda (kosong jika default XAMPP)
define('DB_NAME', 'kaskelas');

$conn = new mysqli(DB_HOST, DB_USER, DB_PASS, DB_NAME);

if ($conn->connect_error) {
    die('Koneksi database gagal: ' . $conn->connect_error);
}

$conn->set_charset('utf8mb4');
```

> **Catatan:** Jangan menyimpan kredensial database secara langsung di file ini jika proyek akan di-deploy ke server publik. Gunakan variabel lingkungan (`.env`) untuk keamanan lebih baik.

---

### Skema Tabel Database

#### Tabel `admin`

```sql
CREATE TABLE `admin` (
  `id`       INT AUTO_INCREMENT PRIMARY KEY,
  `username` VARCHAR(50)  NOT NULL UNIQUE,
  `password` VARCHAR(255) NOT NULL,
  `nama`     VARCHAR(100) NOT NULL,
  `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

#### Tabel `transaksi`

```sql
CREATE TABLE `transaksi` (
  `id`          INT AUTO_INCREMENT PRIMARY KEY,
  `jenis`       ENUM('pemasukan', 'pengeluaran') NOT NULL,
  `jumlah`      DECIMAL(15, 2) NOT NULL,
  `keterangan`  TEXT NOT NULL,
  `tanggal`     DATE NOT NULL,
  `created_at`  TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## Akun Default

Setelah mengimpor file `kaskelas.sql`, akun admin bawaan tersedia sebagai berikut:

| Role | Username | Password |
|---|---|---|
| Admin (Bendahara) | `admin` | `admin123` |

> **Penting:** Segera ganti password default setelah pertama kali login untuk menjaga keamanan sistem.

---

## Preview

> Screenshot akan ditambahkan setelah tampilan antarmuka selesai dikembangkan.

**Halaman Utama (Publik)**

```
[ Screenshot halaman utama — saldo & riwayat transaksi ]
```

**Dashboard Admin**

```
[ Screenshot dashboard admin — ringkasan keuangan ]
```

**Form Tambah Transaksi**

```
[ Screenshot form pencatatan pemasukan / pengeluaran ]
```

---

## Roadmap

Berikut adalah rencana pengembangan fitur pada versi selanjutnya:

- [ ] **Export laporan** ke format PDF atau Excel
- [ ] **Grafik keuangan** bulanan menggunakan Chart.js
- [ ] **Multi-admin** — dukungan lebih dari satu akun bendahara
- [ ] **Notifikasi** ketika saldo kas mendekati batas minimum
- [ ] **Manajemen anggota** — pencatatan status pembayaran iuran per anggota
- [ ] **Sistem komentar** — anggota dapat memberikan catatan atau pertanyaan
- [ ] **Mode gelap** (Dark Mode) pada antarmuka pengguna
- [ ] **Autentikasi berbasis token** untuk keamanan yang lebih baik

---

## Catatan Tambahan

### Keamanan

- Password admin disimpan menggunakan fungsi `password_hash()` dan diverifikasi dengan `password_verify()` — **jangan** menyimpan password dalam bentuk teks biasa.
- Semua input dari pengguna diproses menggunakan **prepared statements** untuk mencegah serangan SQL Injection.
- Halaman admin dilindungi dengan pengecekan session; akses tanpa login akan diarahkan kembali ke halaman login.
- Disarankan untuk menjalankan aplikasi ini di atas koneksi **HTTPS** jika di-deploy ke server publik.

### Keterbatasan

- Aplikasi ini dirancang untuk skala kelas/komunitas kecil, belum dioptimalkan untuk beban pengguna yang sangat besar.
- Belum terdapat fitur pemulihan password (forgot password) pada versi ini.
- Tidak mendukung multi-tenancy (satu instalasi untuk banyak kelas) pada versi saat ini.

---

## Developer

<div align="center">

**Dikembangkan oleh:**

![Developer](https://img.shields.io/badge/Developer-Nama_Anda-informational?style=flat-square)
![Institution](https://img.shields.io/badge/Institusi-Nama_Sekolah%2FKampus-lightgrey?style=flat-square)

| Informasi | Detail |
|---|---|
| Nama | Nama Lengkap Anda |
| Email | email@example.com |
| GitHub | [github.com/username](https://github.com/username) |
| Institusi | Nama Sekolah / Universitas |
| Tahun | 2025 |

</div>

---

<div align="center">

![MIT License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

Proyek ini dilisensikan di bawah **MIT License** — bebas digunakan, dimodifikasi, dan didistribusikan dengan tetap mencantumkan kredit kepada pengembang asli.

---

*Dibuat dengan dedikasi sebagai proyek pembelajaran pengembangan web berbasis PHP.*

</div>
