---
name: verify
description: Double-check tasks using Automated (Unit/Integration) and Manual testing. Use when: user says "verifikasi", "cek fitur", or "selesai coding".
---

# SKILL: VERIFY (Vibe Coding Ready)

---

## 📋 Metadata
- **Nama:** Verify
- **Versi:** 1.0
- **Output:** Laporan verifikasi
- **Dependensi:** TASKS.md (wajib), dokumen lain opsional

---

## 🎯 Trigger Keywords
Otomatis aktif saat user menyebut:
- "Verifikasi"
- "Cek fitur"
- "Selesai coding"
- "Review hasil"
- "Test task"
- "Cek implementasi"

## 📝 Deskripsi
Skill ini memverifikasi task yang sudah diimplementasikan dengan mengecek kode, menjalankan test, dan memastikan task berfungsi sesuai acuan.

## 📂 Baca/Menyimpan File
- **Baca Task (WAJIB):** `@.agents/TASKS.md`
- **Baca Tech Spec:** `@.agents/TECH-SPEC.md` (opsional)
- **Baca PRD:** `@.agents/PRD.md` (opsional)
- **Simpan Laporan:** `.agents/REVIEW.md`

## ⚙️ Cara Kerja Skill

### FASE 1: Deteksi Trigger & Baca Dokumen
**WAJIB:** Sebelum verifikasi, AI HARUS:
1. Cek file `.agents/TASKS.md` — cari task dengan status "Done"
2. Jika ada dokumen lain (PRD, Tech Spec) → baca sebagai referensi tambahan
3. Jika tidak ada: minta user buat Task dulu atau tentukan task yang akan diverifikasi

**Auto-detect boilerplate (opsional):**
AI cek file kunci project untuk konteks:
- `package.json` / `composer.json` / `pyproject.toml` / `go.mod` / `Cargo.toml` / `Gemfile` / `pubspec.yaml`

### FASE 2: Pilih Task
1. Tampilkan daftar task dengan status "Done"
2. Tanyakan: "Task mana yang ingin diverifikasi?"

**Format tampilan:**
```
📋 Daftar Task Selesai:
1. T-01: Setup Project (High) — Setup
2. T-02: Setup Database (High) — Setup
3. T-03: Create User Model (High) — Auth
...
Task mana yang ingin diverifikasi?
```

Jika user tidak memilih, ambil task pertama.

### FASE 3: Proses Verifikasi (3 Aspek)
AI melakukan verifikasi terhadap task dengan 3 aspek:

1. **Kesesuaian dengan Acuan**
   - Apakah implementasi sesuai deskripsi task?
   - Apakah business rules terpenuhi? (jika ada PRD/Tech Spec)

2. **Kualitas & Keamanan Kode**
   - Apakah ada code smell, celah keamanan, atau input validation yang kurang?
   - Apakah struktur dan penamaan sesuai best practice framework?

3. **Fungsionalitas**
   - Apakah kode bisa dijalankan? (cek sintaks, import, dependensi)
   - Apakah ada test yang bisa dijalankan untuk memverifikasi?

### FASE 4: Hasil Verifikasi
Setelah verifikasi selesai, AI menampilkan laporan singkat:

```
📋 Hasil Verifikasi T-03: Create User Model

Status: ✅ Lolos / ⚠️ Catatan / ❌ Gagal

Temuan:
- [Issue] — [lokasi] — [severity]

Saran:
- [Saran perbaikan jika ada]
```

### Update Status
- Jika lolos → status tetap "Done" di TASKS.md
- Jika ada catatan → tulis laporan ke `.agents/REVIEW.md`, user bisa perbaiki lalu review ulang

