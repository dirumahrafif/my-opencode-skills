---
name: mini-prd
description: Buat Product Requirement Document singkat dan padat untuk memulai proyek baru. Gunakan ketika: user minta buat PRD, user mau buat produk baru, user minta ringkasan produk, user bilang "saya mau buat aplikasi", user minta spesifikasi produk, atau user mau memulai proyek baru.
---

# Skill: Mini PRD Generator

## 🎯 Tujuan
Membantu membuat Product Requirement Document (PRD) yang ringkas (1-2 halaman) namun mencakup semua elemen penting untuk memulai pengembangan software.

## 📋 Cara Penggunaan
Cukup ceritakan ide produk atau aplikasi yang ingin dibuat, lalu skill ini akan menghasilkan PRD terstruktur.

### Contoh Input:
> "Aku mau buat aplikasi untuk manage inventory gudang. Ada stok barang, masuk barang, keluar barang, dan laporan."

## 📝 Format Output

### 💾 Instruksi Penyimpanan File
Secara otomatis, simpan output PRD ke dalam file dengan aturan:
1. **Lokasi Default:** `.agents/PRD.md`
2. **Kondisi:** Jika folder `.agents` belum ada, buat folder tersebut terlebih dahulu.
3. **Pengecualian:** Jika user secara eksplisit meminta lokasi atau nama file lain, ikuti instruksi user.

### 1. Project Overview
**Nama Proyek:** [Nama Aplikasi]
**Deskripsi Singkat:** [1-2 kalimat tentang aplikasi]
**Tujuan:** [Masalah apa yang diselesaikan?]

### 2. Target Users
- **[User Type 1]:** [Deskripsi dan kebutuhan]
- **[User Type 2]:** [Deskripsi dan kebutuhan]
- **[User Type 3]:** [Deskripsi dan kebutuhan]

### 3. Core Features (MVP)
| Fitur | Deskripsi | Prioritas |
|-------|-----------|-----------|
| Feature 1 | Deskripsi singkat | P0/P1/P2 |
| Feature 2 | Deskripsi singkat | P0/P1/P2 |
| Feature 3 | Deskripsi singkat | P0/P1/P2 |

**Prioritas:**
- **P0 (Wajib)**: Harus ada di MVP, aplikasi tidak jalan tanpa ini
- **P1 (Penting)**: Fitur penting tapi bisa ditunda ke fase berikutnya
- **P2 (Nice-to-have)**: Fitur tambahan, bisa dikerjakan nanti

### 4. User Flow
1. User melakukan A
2. System merespon B
3. User melihat C
4. User menyelesaikan D


### 5. Success Metrics
- ✅ Metric 1: [Target yang ingin dicapai]
- ✅ Metric 2: [Target yang ingin dicapai]
- ✅ Metric 3: [Target yang ingin dicapai]

### 6. Constraints
- **Timeline:** [Berapa lama?]
- **Budget:** [Berapa budget?]
- **Tech Stack:** [Teknologi yang digunakan]
- **Team:** [Siapa yang terlibat?]
- **Other:** [Lainnya]

### 7. Risks & Assumptions
- ⚠️ Risk 1: [Deskripsi risk]
- ⚠️ Risk 2: [Deskripsi risk]
- 💡 Assumption 1: [Asumsi yang dibuat]

### 8. Next Steps
1. **[Action 1]** - [Timeline]
2. **[Action 2]** - [Timeline]
3. **[Action 3]** - [Timeline]

---

## 🔧 Template Pengisian (untuk Referensi)

### Bagian 1: Project Overview
**Nama Proyek:** [Dari ide user]
**Deskripsi Singkat:** [Parafrase dari deskripsi user]
**Tujuan:** [Identifikasi masalah utama yang diselesaikan]

### Bagian 2: Target Users
Identifikasi siapa saja yang akan menggunakan aplikasi:
- Admin/Manager: [Kebutuhan mereka]
- User biasa: [Kebutuhan mereka]
- Guest/Visitor: [Kebutuhan mereka]

### Bagian 3: Core Features
Pilih fitur yang paling esensial:
1. Authentication (Login/Register) - P0
2. Fitur utama aplikasi - P0
3. Dashboard/Overview - P0
4. CRUD operations - P0
5. Reports/Export - P1
6. Advanced features - P2

### Bagian 4: User Flow
Buat skenario paling sederhana:
Login → Dashboard → Fitur Utama → Selesai


### Bagian 5: Success Metrics
Tentukan indikator keberhasilan:
- Response time < 1 detik
- User bisa selesaikan task utama dalam 3 klik
- 100% uptime
- User retention 80%

### Bagian 6: Constraints
- Timeline: 2 minggu untuk MVP
- Budget: $0 (open source)
- Tech Stack: Next.js + Prisma + PostgreSQL
- Team: Solo developer

### Bagian 7: Risks
- Tech risk: Framework baru yang belum dikuasai
- Scope risk: Fitur bertambah di tengah jalan
- Timeline risk: Underestimate effort

### Bagian 8: Next Steps
1. Buat Tech Spec - Minggu 1
2. Setup Project - Minggu 1
3. Implementasi Core Features - Minggu 2
4. Testing & Deployment - Minggu 2

---

## 💡 Contoh Output Lengkap

### 📄 Mini PRD: Inventory Management System

#### 1. Project Overview
**Nama Proyek:** SmartStock Inventory Management  
**Deskripsi Singkat:** Aplikasi web untuk mengelola stok barang di gudang dengan tracking real-time  
**Tujuan:** Membantu bisnis kecil-menengah melacak stok secara akurat, mencegah kehabisan stok, dan menghasilkan laporan mutasi barang

#### 2. Target Users
- **Admin Gudang:** Input barang masuk/keluar, cek stok, generate laporan
- **Manager:** Lihat dashboard, analisis stok, approve permintaan
- **Staff:** Input data barang, cek ketersediaan stok

#### 3. Core Features (MVP)
| Fitur | Deskripsi | Prioritas |
|-------|-----------|-----------|
| **Product Management** | CRUD produk (nama, SKU, harga, kategori, stok) | P0 |
| **Stock In** | Input barang masuk dengan qty, supplier, tanggal | P0 |
| **Stock Out** | Input barang keluar dengan qty, tujuan, tanggal | P0 |
| **Stock Dashboard** | Lihat stok terkini + alert stok menipis | P0 |
| **Stock History** | Histori mutasi stok per produk | P1 |
| **Reports** | Generate laporan mutasi stok per periode (PDF/CSV) | P1 |
| **User Roles** | Admin, Manager, Staff dengan akses berbeda | P2 |

#### 4. User Flow
1. User login → Dashboard
2. Dashboard menampilkan stok terkini & alert
3. Admin klik "Tambah Stok" → Form input barang masuk
4. System update stok otomatis
5. User bisa lihat histori di "Riwayat Stok"
6. Generate laporan di "Laporan" → Pilih periode → Download PDF


#### 5. Success Metrics
- ✅ Stok update dalam < 1 detik
- ✅ Alert stok menipis muncul otomatis saat stok < 5
- ✅ Laporan bisa di-download dalam 3 klik
- ✅ 99% akurasi data stok

#### 6. Constraints
- **Timeline:** 2 minggu untuk MVP
- **Budget:** $0 (open source)
- **Tech Stack:** Next.js 14, Prisma, PostgreSQL, NextAuth.js, shadcn/ui
- **Team:** 1 Fullstack Developer
- **Target Platform:** Web (mobile-responsive)

#### 7. Risks & Assumptions
- ⚠️ **Risk:** Performance issue jika data stok sangat besar (> 10.000 produk)
  - Mitigasi: Implementasi pagination dan indexing database
- ⚠️ **Risk:** User salah input qty (negatif atau terlalu besar)
  - Mitigasi: Validasi ketat di frontend dan backend
- 💡 **Assumption:** Semua user punya akses internet stabil
- 💡 **Assumption:** Data produk tidak akan melebihi 1.000 dalam 6 bulan pertama

#### 8. Next Steps
1. **Buat Tech Spec** - 1 hari
2. **Setup Project + Database Schema** - 1 hari
3. **Implementasi Authentication** - 1 hari
4. **Implementasi Product Management** - 2 hari
5. **Implementasi Stock In/Out** - 2 hari
6. **Implementasi Dashboard & Alerts** - 1 hari
7. **Implementasi Reports** - 1 hari
8. **Testing & Deployment** - 1 hari

---

## 🎯 Trigger Keywords
Skill ini akan otomatis aktif ketika user mengatakan:
- "Buat PRD untuk..."
- "Saya mau buat aplikasi..."
- "Buat ringkasan produk..."
- "Saya punya ide aplikasi..."
- "Rencana produk untuk..."
- "Buat product requirement untuk..."

## 📚 Tips Membuat PRD yang Baik
1. **Fokus ke masalah**, bukan solusi
2. **Prioritaskan fitur** (jangan semua P0)
3. **Realistis dengan timeline**
4. **Libatkan user** dalam validasi
5. **Keep it simple** (1-2 halaman sudah cukup)
