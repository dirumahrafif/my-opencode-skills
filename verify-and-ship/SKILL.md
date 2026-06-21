---
name: verify-and-ship
description: Double-check tasks using Automated (Unit/Integration) and Manual testing. Use when: user says "verifikasi", "siap ship", "cek fitur", or "selesai coding".
---

# Skill: Verification & Shipment (Double Check)

## 🎯 Tujuan
Memastikan kualitas fitur melalui dua lapis verifikasi: Otomasi teknis (Automated Testing) dan Validasi pengalaman pengguna (Manual UX Testing).

## 📋 Cara Penggunaan
Gunakan setelah semua item di implementation plan atau task list selesai dikerjakan. Skill ini akan memastikan kode tidak hanya "jalan" secara teknis, tapi juga sesuai dengan kebutuhan Anda.

## 🛠 Workflow (Double Check System)

### 1. Jalur Pertama: Automated Verification (Oleh Agent)
Sebelum meminta user melakukan pengetesan, agent akan melakukan:
- **Scan Tests:** Mencari file `.test.ts`, `spec.js`, atau perintah di `package.json`.
- **Run Tests:** Menjalankan unit & integration test yang ada.
- **Static Analysis:** Menjalankan linter (`npm run lint`) dan type-check (`tsc`).
- **Auto-Fix:** Jika ada kegagalan teknis kecil (seperti linting), agent akan langsung memperbaikinya.

### 2. Jalur Kedua: Manual QA Checklist (Oleh User)
Setelah otomasi lulus, agent menghasilkan file panduan di `.agents/verification/2026/[YYYYMMDD]-[Prioritas]-[nama-fitur]-qa.md`:
- **Skenario Pengujian:** Langkah-langkah detail untuk dicoba user.
- **Ekspektasi Hasil:** Apa yang seharusnya terjadi secara visual atau fungsional.
- **Slot Konfirmasi:** Tempat user menandai `PASS` atau `FAIL`.

### 3. Finalisasi (Shipment)
Jika kedua jalur lulus (PASS):
- Pindahkan file tugas dari `.agents/tasks/` ke `.agents/tasks/completed/`.
- Tutup GitHub Issues terkait menggunakan `gh issue close`.
- Tampilkan ringkasan "Shipment Report" di chat.

## 💾 Instruksi Penyimpanan
- Simpan panduan QA di `.agents/verification/2026/`.
- Arsip tugas yang selesai di `.agents/tasks/completed/`.

## 🎯 Trigger Keywords
- "Verifikasi fitur ini"
- "Jalankan double check testing"
- "Siap untuk ship"
- "Selesai coding, lanjut testing"
- "Buat skenario QA"
