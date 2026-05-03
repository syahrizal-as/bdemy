# Curriculum & Product Requirements Document (PRD)
## Bootcamp: Junior Web Development with Laravel

**Metadata Pelatihan**
*   **Nama Program:** Junior Web Development Training Program
*   **Instruktur Utama:** Syahrizal Ali Sadikin
*   **Target Peserta:** Junior Web Developer / Mahasiswa IT / Pemula dengan pemahaman dasar pemrograman.
*   **Tech Stack:** PHP 8.x, Laravel 13.x, MySQL/PostgreSQL, Bootstrap 5.
*   **Studi Kasus Aplikasi:** "LaraStock" (Sistem Manajemen Inventaris Sederhana)
*   **Periode Pelaksanaan:** 6 - 8 Mei 2026

---

## 1. Executive Summary
Program pelatihan intensif selama 3 hari ini dirancang untuk menjembatani peserta dari pemahaman pemrograman dasar menuju alur kerja pengembangan web modern. Menggunakan ekosistem PHP dan Laravel, peserta akan dibimbing mulai dari pemahaman arsitektur fundamental (MVC), perancangan *database*, pembuatan antarmuka pengguna yang responsif, hingga praktik *debugging* dan dokumentasi kode berstandar industri. Tujuan akhirnya adalah menghasilkan *Minimum Viable Product* (MVP) berupa aplikasi manajemen inventaris yang berfungsi penuh.

---

## 2. Definisi Studi Kasus: LaraStock (MVP)
Peserta akan membangun **LaraStock**, sebuah aplikasi sistem manajemen inventaris untuk mencatat arus barang di gudang. Fokus utama MVP ini adalah penyelesaian modul CRUD (Create, Read, Update, Delete) pada Master Barang.

**Struktur Database Tabel `items`:**
*   `id` (Primary Key, Auto Increment)
*   `name` (String, max: 255) - Nama barang.
*   `category` (String, max: 100) - Kategori barang (Elektronik, ATK, dsb).
*   `quantity` (Integer) - Jumlah stok barang saat ini.
*   `status` (Boolean/Enum) - Status ketersediaan (Tersedia / Habis).
*   `timestamps` (created_at, updated_at).

---

## 3. Persyaratan Perangkat Lunak (Environment)
Peserta dan instruktur diwajibkan menginstal perangkat lunak berikut sebelum pelatihan dimulai:
*   **PHP Environment:** Laravel Herd (rekomendasi untuk macOS/Windows), atau Laragon / XAMPP (PHP versi 8.2 ke atas).
*   **Package Manager:** Composer.
*   **Database GUI:** TablePlus, DBeaver, atau phpMyAdmin.
*   **Code Editor:** Visual Studio Code dengan ekstensi penunjang Laravel (Laravel Extra Intellisense, PHP Intelephense, dll).
*   **Web Browser:** Google Chrome atau Mozilla Firefox.

---

## 4. Kurikulum & Rencana Pelaksanaan

### HARI 1: Foundation of Modern Web Development
**Tanggal:** 6 Mei 2026
**Tujuan:** Peserta memahami konsep arsitektur web modern, berhasil melakukan *setup project*, dan mampu menghubungkan aplikasi dengan *database* untuk menampilkan data mentah.

**Sesi 0: Teori Fundamental "The Big Picture" (45 Menit)**
*   **Arsitektur Client-Server:** Memahami alur kerja *HTTP Request* dan *Response* antara browser dan server.
*   **Frontend vs Backend:** Analogi "Ruang Makan dan Dapur Restoran" untuk memperjelas cakupan kerja.
*   **Kenapa Menggunakan Framework?:** Perbandingan PHP *Native* (membangun dari nol) vs Laravel (menggunakan fondasi rumah yang sudah aman dan berstandar).
*   **Konsep MVC:** Penjelasan detail peran Model (Koneksi Database), View (Antarmuka/UI), dan Controller (Logika/Otak Aplikasi).

**Sesi 1: Praktik Setup & Core Logic (2.5 Jam)**
*   **Inisialisasi Project:** Membuat *project* baru `larastock` menggunakan Composer.
*   **Konfigurasi Environment:** Menghubungkan aplikasi ke MySQL melalui `.env`.
*   **Database & Eloquent:** 
    *   Membuat *Migration* tabel `items`.
    *   Membuat *Seeder* untuk mengisi *dummy data* awal.
*   **Routing & Controller:** Membuat `ItemController`, mengatur *route*, dan me-*return* data dari Model `Item` ke layar browser dalam bentuk JSON.
*   *Key Deliverable Hari 1:* Project berjalan di lokal, terhubung ke *database*, dan mampu mengekstraksi data secara dinamis.

---

### HARI 2: Building Interactive Web Applications
**Tanggal:** 7 Mei 2026
**Tujuan:** Peserta mampu mengubah data mentah menjadi UI yang rapi menggunakan komponen pihak ketiga dan menerapkan standar validasi input.

**Sesi 1: Integrasi UI & Blade Templating (1.5 Jam)**
*   **Blade Engine:** Pembuatan `layout/app.blade.php` utama dan memecah komponen (*yield*, *extends*).
*   **Bootstrap 5 Integration:** Memasang CDN Bootstrap 5 untuk merapikan tampilan aplikasi.
*   **View Data (Read):** Merancang tabel responsif di file `index.blade.php` untuk menampilkan daftar *items* menggunakan *looping* `@foreach`.

**Sesi 2: Form & Clean Code Validation (1.5 Jam)**
*   **Form Input (Create):** Membuat halaman dan *form* penambahan barang.
*   **Security Basic:** Implementasi `@csrf` pada setiap *form* Laravel.
*   **Form Request Validation:** Mencegah *Fat Controllers* dengan memisahkan logika validasi ke `StoreItemRequest` (misal: *quantity* harus berupa angka bulat dan *name* wajib diisi).
*   **Flash Messages:** Menampilkan notifikasi *alert* Bootstrap saat data berhasil atau gagal ditambahkan.
*   *Key Deliverable Hari 2:* Aplikasi CRUD memiliki visual profesional, *responsive*, dan kebal terhadap input *user* yang salah (tervalidasi).

---

### HARI 3: Professional Developer Workflow
**Tanggal:** 8 Mei 2026
**Tujuan:** Membekali peserta dengan alur kerja nyata di industri, fokus pada penyelesaian masalah, analisis *error*, dan pendokumentasian kode.

**Sesi 1: Effective Debugging (1.5 Jam)**
*   **Membaca Ignition:** Simulasi *error syntax* dan pengenalan cara membaca *stack trace* Laravel yang berwarna merah untuk mencari akar masalah.
*   **Die and Dump:** Penggunaan fungsi `dd()` dan `dump()` untuk melacak *flow* data dari *Route* hingga *View*.
*   **Log Handling:** Cara mencatat aktivitas atau kegagalan sistem ke dalam `storage/logs/laravel.log`.

**Sesi 2: Dokumentasi & Finalisasi (1.5 Jam)**
*   **PHPDoc Standard:** Latihan menambahkan blok komentar dokumentasi (`/** ... */`) untuk fungsi-fungsi krusial agar mudah dibaca oleh developer lain.
*   **Penyelesaian Modul:** Melengkapi sisa modul aplikasi (Update & Delete) secara ringkas.
*   **Evaluasi Kode:** *Review* hasil kerja peserta, sesi Q&A, dan *sharing best practice*.
*   *Key Deliverable Hari 3:* Peserta mandiri dalam mengatasi *error* dasar dan memiliki *source code* yang terdokumentasi dan siap dipelihara.

---

## 5. Indikator Keberhasilan (Success Metrics)
Pelatihan ini dianggap berhasil jika memenuhi parameter berikut:
1.  **Tingkat Penyelesaian (Completion Rate):** 80% peserta berhasil merampungkan aplikasi LaraStock (minimal fitur Read dan Create).
2.  **Kualitas Kode (Code Quality):** Logika validasi data tidak diletakkan secara kotor di dalam Controller, melainkan menggunakan Form Request yang proper.
3.  **Kemandirian Debugging (Problem Solving):** Peserta mampu mengidentifikasi baris *error* dari tampilan log Ignition dan menemukan solusinya tanpa intervensi langsung dari instruktur.