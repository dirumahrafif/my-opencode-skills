---
name: create-issues
description: Create local task lists from a Tech Spec file or direct input (bugs, small tasks). Use when: user says "buat task", "ada bug", "tambah task", or "eksekusi rencana task".
---

# Skill: Issue & Task Creator

## 🎯 Tujuan
Mengotomatiskan pembuatan daftar tugas lokal. Skill ini mendukung dua jalur:
1. **Full Track:** Berdasarkan Technical Specification (untuk fitur kompleks).
2. **Fast Track:** Berdasarkan input langsung (untuk bug fix, hotfix, atau task sederhana).

## 📋 Cara Penggunaan
- **Dari Tech Spec:** Skill akan mencari file terbaru di `.agents/tech-specs/2026/`.
- **Input Langsung:** Cukup katakan "Ada bug di [bagian]" atau "Tambah task untuk [hal]", skill akan langsung memprosesnya tanpa meminta Tech Spec.

## 💾 Instruksi Penyimpanan File
Setiap kali issue atau task dibuat, simpan statusnya ke dalam file pelacakan:
1. **Lokasi:** `.agents/tasks/2026/[YYYYMMDD]-[Prioritas]-[nama-fitur]-tasks.md`
2. **Aturan Penamaan:** 
   - Untuk Tech Spec: Samakan `nama-fitur` dengan file sumber.
   - Untuk Fast Track: Gunakan deskripsi singkat dari user (kebab-case) sebagai `nama-fitur`.
3. **Informasi dalam File:**
    - **Metadata:** Referensi sumber (Tech Spec atau Direct Input), tanggal dibuat, dan kategori (Bug/Task/Improvement).
    - **Daftar Tugas:** Item checklist `[ ]` dengan detail judul.
    - **Timestamp Selesai:** Sediakan placeholder `[Selesai: ]` di setiap item.

## 🛠 Workflow
1. **Analisis Input:**
    - Jika user merujuk ke Tech Spec: Cari file terbaru di `.agents/tech-specs/2026/` dan ekstrak tugasnya.
    - Jika user memberikan input langsung (Bug/Task): Identifikasi judul, deskripsi, dan prioritas secara mandiri.
2. **Eksekusi:** 
    - Hasilkan daftar checklist markdown.
3. **Pencatatan:** Tulis hasil eksekusi ke file di `.agents/tasks/2026/` sebagai log pelacakan.

## 📝 Format yang Diharapkan
Skill ini memproses item list:
- `[ ] Judul: Deskripsi` -> Menjadi item dalam file tugas.

## 🎯 Trigger Keywords
- "Buat task dari tech spec"
- "Ada bug baru..."
- "Tambah task untuk..."
- "Buat hotfix..."
- "Improvement kecil pada..."
- "Eksekusi rencana task"
