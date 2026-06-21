---
name: write-tech-spec
description: Write technical specifications for features, changes, or bug fixes. Produces a markdown file in .agents/tech-specs/<YEAR>/ for user review, then creates issues after approval. Gunakan ketika: user minta tech spec, user minta spesifikasi teknis, user minta implementation plan, user minta dokumentasi teknis, atau user mendeskripsikan fitur yang butuh perencanaan sebelum coding.
---

# Skill: Technical Specification Generator

## 🎯 Tujuan
Membantu merancang spesifikasi teknis (Tech Spec) yang mendalam untuk fitur baru, perubahan sistem, atau perbaikan bug sebelum implementasi dimulai. Skill ini menjembatani antara kebutuhan produk (PRD) dan implementasi kode.

## 📋 Cara Penggunaan
Deskripsikan fitur atau masalah yang ingin ditangani. 

**Integrasi PRD:**
Jika file `.agents/PRD.md` tersedia, skill ini secara otomatis akan menggunakannya sebagai referensi utama untuk memahami kebutuhan bisnis dan fungsional sebelum menyusun detail teknis.

## 💾 Instruksi Penyimpanan File
Secara otomatis, simpan output Tech Spec ke dalam file dengan aturan:
1. **Lokasi Default:** `.agents/tech-specs/2026/[YYYYMMDD]-[Prioritas]-[nama-fitur].md`
   - *Contoh:* `20260617-P0-inventory-management.md`
2. **Penentuan Prioritas:** Ambil tingkat prioritas (P0/P1/P2) dari `.agents/PRD.md` jika tersedia. Jika tidak ada, gunakan `P0` sebagai default.
3. **Format Tanggal:** Gunakan `YYYYMMDD` (tahun, bulan, hari) saat spec dibuat.
4. **Kondisi:** Jika folder `.agents` atau subfolder `tech-specs/2026` belum ada, buat folder tersebut terlebih dahulu.
5. **Pengecualian:** Jika user secara eksplisit meminta lokasi atau nama file lain, ikuti instruksi user.

## 📝 Format Output
Dokumen yang dihasilkan harus mengikuti struktur berikut:

### 1. Overview
- **Konteks**: Mengapa perubahan ini diperlukan? (Referensi dari PRD jika ada).
- **Tujuan**: Apa yang ingin dicapai secara teknis?

### 2. Analisis Sistem Saat Ini
- Hasil penelusuran codebase menggunakan tool search.
- Komponen, file, atau API yang terdampak.
- Kendala atau batasan teknis yang ditemukan.

### 3. Usulan Perubahan
- **Arsitektur/Logic**: Perubahan alur kerja atau struktur data.
- **API/Interface**: Definisi endpoint baru atau perubahan UI.
- **Data Model**: Perubahan skema database jika diperlukan.

### 4. Rencana Implementasi
- Daftar tugas teknis langkah-demi-langkah yang siap dikerjakan oleh agent.

### 5. Verifikasi & Pengujian
- Rencana unit test, integration test, atau manual testing.

### 6. Rencana Issue
- Daftar issue yang akan dibuat di GitHub/Project Tracker setelah spec ini disetujui.

## 🎯 Trigger Keywords
- "Buat tech spec untuk..."
- "Buat spesifikasi teknis..."
- "Buat implementation plan..."
- "Buat dokumentasi teknis..."
- "Gunakan PRD untuk buat tech spec..."

## 🛠 Workflow
1. Baca `.agents/PRD.md` jika ada.
2. Eksplorasi codebase untuk mengidentifikasi area yang terdampak.
3. Tulis draft Tech Spec ke `.agents/tech-specs/2026/`.
4. Minta review user.
5. Setelah disetujui, tawarkan untuk membuat issue atau mulai implementasi.
