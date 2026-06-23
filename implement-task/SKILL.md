---
name: implement-task
description: Execute and automate coding tasks from the .agents/tasks/ directory. Use when: user says "kerjakan task", "lanjutkan implementasi", "selesaikan tugas", or "start working on tasks".
---
# SKILL: IMPLEMENT TASK (Vibe Coding Ready)

---

## 📋 Metadata
- **Nama:** Implement Task
- **Versi:** 1.0
- **Output:** Kode implementasi dari task yang dipilih
- **Dependensi:** TASKS.md (wajib dibaca)

## 🎯 Trigger Keywords
Otomatis aktif saat user menyebut:
- "Implement task"
- "Kerjakan task"
- "Mulai implementasi"
- "Coding task"
- "Buat kode untuk task"
- "Jalankan task"

## 📝 Deskripsi
Skill ini membaca daftar task dari `.agents/TASKS.md` dan mengimplementasikannya satu per satu. Konten implementasi menyesuaikan stack apapun.

## 📂 Baca/Menyimpan File
- **Baca Task (WAJIB):** `@.agents/TASKS.md`
- **Baca Tech Spec:** `@.agents/TECH-SPEC.md` (opsional, untuk referensi)
- **Update Task:** `.agents/TASKS.md` (update status task)

## ⚙️ Cara Kerja Skill

### FASE 1: Deteksi Trigger & Baca Task
**WAJIB:** Sebelum implementasi, AI HARUS:
1. Cek file `.agents/TASKS.md`
2. Jika ada: baca dan cari task dengan status "Todo"
3. Jika tidak ada: minta user buat Task dulu

**Auto-detect boilerplate (opsional):**
AI cek file kunci project untuk mengetahui state:
- `package.json` / `composer.json` / `pyproject.toml` / `go.mod` / `Cargo.toml` / `Gemfile` / `pubspec.yaml`
- Jika ada → project sudah ada, task setup bisa dilewati
- Jika tidak ada → project baru

### FASE 2: Pilih Task
1. Tampilkan daftar task dengan status "Todo"
2. Beri nomor pada setiap task
3. Tanyakan: "Task mana yang ingin diimplementasikan?"

**Format tampilan:**
```
📋 Daftar Task Todo:
1. T-01: Setup Project (High) — Setup
2. T-02: Setup Database (High) — Setup
3. T-03: Create User Model (High) — Auth
...
```
*(Tampilkan modul jika ada, skip jika task tanpa modul dari input langsung)*

Jika user tidak memilih, ambil task dengan prioritas **High** pertama.

### FASE 3: Implementasi Task
1. Baca detail task yang dipilih (judul, deskripsi, dependensi, file yang diubah)
2. Cek dependensi: apakah task sebelumnya sudah selesai?
   - Jika belum: beri peringatan dan tawarkan untuk implementasi task dependensi dulu
   - Jika sudah: lanjut ke step 3
3. Baca file yang akan diubah (jika sudah ada)
4. Tulis kode implementasi ke file — sesuaikan dengan stack dan konteks project
5. Update status task menjadi "Done" di file TASKS.md

### FASE 4: Finalisasi & Next Step
Setelah task selesai diimplementasikan:
1. Beri tahu user file apa saja yang berubah
2. Tanyakan: "Lanjut ke task berikutnya? (y/n)"

**Contoh respons:**
```
✅ Task T-03: Create User Model selesai!

File yang diubah:
- [path sesuai stack]

Lanjut ke task berikutnya? (y/n)
```

## 📝 Format Output Implementasi

Setiap task selesai, AI HARUS menampilkan:
1. ✅ **Konfirmasi selesai** — Task T-XX: [Nama Task] ✅
2. **File yang diubah** — path dan deskripsi singkat perubahan
3. **Testing** — cara menguji hasil implementasi
4. **Ajakan lanjut** — "Lanjut ke task berikutnya? (y/n)"

Kode ditulis langsung ke file — tidak perlu ditampilkan di respons.
