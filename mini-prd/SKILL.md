---
name: mini-prd
description: Buat Product Requirement Document singkat dan padat untuk memulai proyek baru. Gunakan ketika: user minta buat PRD, user mau buat produk baru, user minta ringkasan produk, user bilang "saya mau buat aplikasi", user minta spesifikasi produk, atau user mau memulai proyek baru.
---

# SKILL: PRD GENERATOR (Vibe Coding Ready)

## 📋 Metadata
- **Nama:** PRD Generator
- **Versi:** 1.0
- **Output:** PRD 6 bagian
- **Lokasi File:** `.agents/PRD.md`


## 🎯 Trigger Keywords
Otomatis aktif saat user menyebut:
- "Buat PRD untuk..."
- "Buat product requirement..."
- "Saya mau buat aplikasi..."
- "Saya punya ide..."
- "Baca PRD saya"
- "Load PRD"


## 📝 Deskripsi
Skill ini membuat PRD ringkas tapi detail untuk keperluan vibe coding. Cukup untuk lanjut ke Tech Spec dan Implementasi.

## 📂 Baca/Menyimpan File
- **Baca:** `@.agents/PRD.md`
- **Simpan:** `.agents/PRD.md`

## ⚙️ Cara Kerja Skill

### FASE 1: Deteksi Trigger
- Jika user bilang **"baca"** atau **"load"** → Baca `.agents/PRD.md` dan beri ringkasan.
- Jika user bilang **"buat"** atau **"ide"** → Lanjut ke FASE 2.

### FASE 2: Klarifikasi (3 Pertanyaan)
Tanyakan 3 hal ini sebelum mulai:
1. **Target pengguna?** (siapa?)
2. **Masalah utama?** (apa pain point-nya?)
3. **Keunikan produk?** (apa yang beda?)

### FASE 3: Produksi PRD (6 Bagian)
Hasilkan PRD **per bagian**. Setiap bagian minta user ketik `lanjut`.

### FASE 4: Finalisasi
Setelah bagian 6 selesai:
1. Ucapkan selamat.
2. Instruksikan simpan ke `.agents/PRD.md`.
3. Rekomendasikan lanjut ke **Tech Spec Generator**.

## 📑 6 Bagian PRD

1. Visi & Tujuan
2. User Persona (2 persona)
3. User Stories (10-15)
4. Functional Requirements (15-20 FR)
5. Non-Functional Requirements
6. Out of Scope & Dependensi

## 📄 BAGIAN 1: Visi & Tujuan Produk

### Visi Produk
1 paragraf visi besar produk ini.

### Tujuan Utama (3-5)
1. [Tujuan 1] - [Indikator keberhasilan]
2. [Tujuan 2] - [Indikator keberhasilan]
3. [Tujuan 3] - [Indikator keberhasilan]

### Value Proposition
- [Nilai unik 1]
- [Nilai unik 2]
- [Nilai unik 3]

## 📄 BAGIAN 2: User Persona

### Persona 1: [Nama]
- **Usia/Pekerjaan:** [Usia], [Pekerjaan]
- **Level Teknis:** [Pemula/Menengah/Mahir]
- **Tujuan:** [Apa yang ingin dicapai?]
- **Pain Points:** [Masalah yang dihadapi]
- **Motivasi:** [Kenapa pakai produk ini?]

### Persona 2: [Nama]
- **Usia/Pekerjaan:** [Usia], [Pekerjaan]
- **Level Teknis:** [Pemula/Menengah/Mahir]
- **Tujuan:** [Apa yang ingin dicapai?]
- **Pain Points:** [Masalah yang dihadapi]
- **Motivasi:** [Kenapa pakai produk ini?]

## 📄 BAGIAN 3: User Stories

### Format
`Sebagai [peran], saya ingin [tindakan], agar [manfaat].`

### Modul 1: Autentikasi
- Sebagai pengguna baru, saya ingin mendaftar dengan email, agar bisa mulai menggunakan aplikasi.
- Sebagai pengguna, saya ingin login, agar bisa mengakses data saya.
- Sebagai pengguna, saya ingin reset password, agar bisa mengakses akun jika lupa.

### Modul 2: [Sesuaikan]
- Sebagai [peran], saya ingin [tindakan], agar [manfaat].
- [Lanjutkan minimal 3-5 per modul]

### Modul 3: [Sesuaikan]
- Sebagai [peran], saya ingin [tindakan], agar [manfaat].
- [Lanjutkan minimal 3-5 per modul]

*(Total 10-15 user stories)*

## 📄 BAGIAN 4: Functional Requirements

### Format
**FR-XX: [Nama Fitur]**
- **Input:** [Data masuk]
- **Proses:** [Apa yang dilakukan sistem]
- **Output:** [Hasil yang diberikan]
- **Aturan Bisnis:** [Rules]

### Modul 1: Autentikasi

**FR-01: Registrasi Pengguna**
- **Input:** Email, password, nama
- **Proses:** Validasi email unik, hash password, simpan ke DB
- **Output:** Akun terdaftar, email verifikasi terkirim
- **Aturan:** Password minimal 8 karakter, email harus valid

**FR-02: Login Pengguna**
- **Input:** Email, password
- **Proses:** Verifikasi kredensial, generate JWT token
- **Output:** Token akses, redirect ke dashboard
- **Aturan:** 5x gagal = blokir 15 menit

### Modul 2: [Sesuaikan]

**FR-03: [Nama Fitur]**
- **Input:** [Data masuk]
- **Proses:** [Apa yang dilakukan sistem]
- **Output:** [Hasil]
- **Aturan:** [Rules]

*(Total 15-20 FR, lanjutkan untuk semua modul)*

## 📄 BAGIAN 5: Non-Functional Requirements

### Performa
- Waktu muat halaman < 2 detik
- API response < 500ms
- Support 1000 user concurrent

### Keamanan
- Password di-hash (bcrypt)
- HTTPS wajib
- JWT token expiry 24 jam
- Role-based access control

### Skalabilitas
- Target 10.000 user aktif
- Bisa scale horizontal (load balancer)
- Database siap sharding

### Usability
- Responsive (mobile, tablet, desktop)
- Bahasa Indonesia
- Dark mode support

## 📄 BAGIAN 6: Out of Scope & Dependensi

### Out of Scope (Tidak Dikerjakan di V1)
- [Fitur 1] - ditunda ke v2
- [Fitur 2] - ditunda ke v2
- [Fitur 3] - ditunda ke v2

### Dependensi
- [Library/API 1] - untuk [fungsi]
- [Library/API 2] - untuk [fungsi]
- [Infrastruktur] - hosting, database, dll.

### Asumsi
- User punya koneksi internet stabil
- User memiliki email yang aktif
- [Asumsi lain sesuai produk]

## 🔄 Finalisasi

1. **Simpan file:**
   Simpan seluruh konten PRD sebagai `.agents/PRD.md`

2. **Lanjut ke Tech Spec:**
   Ketik: `"Buat Tech Spec berdasarkan PRD yang sudah dibuat"`






