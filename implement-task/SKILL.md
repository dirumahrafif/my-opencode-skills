---
name: implement-task
description: Execute and automate coding tasks from the .agents/tasks/ directory. Use when: user says "kerjakan task", "lanjutkan implementasi", "selesaikan tugas", or "start working on tasks".
---

# Skill: Task Implementer

## 🎯 Tujuan
Mengotomatiskan eksekusi coding berdasarkan daftar tugas yang ada di folder `.agents/tasks/`. Skill ini memastikan setiap langkah dikerjakan sesuai spesifikasi dan dicatat progresnya.

## 📋 Cara Penggunaan
Skill ini bekerja dengan membaca file tugas terbaru di `.agents/tasks/2026/`. Jika tidak ada tugas yang sedang berjalan, skill akan menawarkan untuk memulai tugas dengan prioritas tertinggi (P0).

## 🛠 Workflow
1. **Identifikasi Tugas:** Cari file `.md` di `.agents/tasks/2026/` yang masih memiliki checklist kosong `[ ]`.
2. **Konteks:** Baca Technical Specification terkait (jika ada) di `.agents/tech-specs/2026/` untuk memahami detail implementasi.
3. **Eksekusi Coding:**
   - Pilih satu sub-tugas yang belum selesai.
   - Lakukan perubahan kode menggunakan tool `Read`, `Edit`, atau `Write`.
   - Patuhi konvensi kode yang ada di project.
4. **Verifikasi:** 
   - Jalankan perintah test atau lint (jika tersedia).
   - Jika gagal, perbaiki kode hingga lulus verifikasi.
5. **Pencatatan Progres:**
   - Update file tugas dengan mengisi `[x]` dan timestamp `[Selesai: YYYY-MM-DD]`.
   - Berikan ringkasan apa yang telah dikerjakan kepada user.

## 💾 Pembaruan File Tugas
Skill ini wajib memperbarui file di `.agents/tasks/` setiap kali satu sub-tugas selesai:
- Ubah `[ ]` menjadi `[x]`.
- Isi `[Selesai: ]` dengan tanggal hari ini.

## 🎯 Trigger Keywords
- "Kerjakan task dari daftar"
- "Lanjutkan implementasi"
- "Selesaikan tugas selanjutnya"
- "Start working on tasks"
- "Implementasikan fitur ini"
