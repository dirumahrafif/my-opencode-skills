---
name: create-issues
description: Create local task lists from a Tech Spec file or direct input (bugs, small tasks), with recursive breakdown into atomic, actionable sub-tasks until the whole piece of work is fully decomposed and trackable end-to-end. Use when: user says "buat task", "ada bug", "tambah task", "eksekusi rencana task", "pecah task", "breakdown pekerjaan", or "detailkan task".
---

# SKILL: TASK GENERATOR (Vibe Coding Ready)

## 📋 Metadata
- **Nama:** Task Generator
- **Versi:** 1.0
- **Output:** Task list terperinci
- **Lokasi File:** `.agents/TASKS.md`
- **Dependensi:** TECH-SPEC.md (opsional — bisa langsung input user)

## 🎯 Trigger Keywords
Otomatis aktif saat user menyebut:
- "Buat Task"
- "Buat tugas"
- "Buat daftar tugas"
- "Buat task list"
- "Buat implementation task"
- "Baca TASKS saya"
- "Load Task"

## 📝 Deskripsi
Skill ini membaca Tech Spec dari `.agents/TECH-SPEC.md` dan menghasilkan daftar tugas (Task) yang terperinci — konten task menyesuaikan stack apapun. Setiap task berisi: judul, deskripsi, prioritas, status, dan dependensi. Siap pakai untuk Implementasi.

## 📂 Baca/Menyimpan File
- **Baca Tech Spec:** `@.agents/TECH-SPEC.md` (jika ada)
- **Baca Task:** `@.agents/TASKS.md`
- **Simpan Task:** `.agents/TASKS.md`

## ⚙️ Cara Kerja Skill

### FASE 1: Deteksi Trigger & Analisa Input

**Langkah 1 — Cek input user:**
- Apakah user sudah memberikan deskripsi langsung? (bug report, fitur kecil, dll)
- Atau hanya trigger kata kunci tanpa deskripsi?

**Langkah 2 — Cek sumber acuan:**
- Jika ada TECH-SPEC.md → baca dan jadikan acuan untuk breakdown
- Jika user memberikan input langsung (bug/task sederhana) → langsung proses tanpa Tech Spec, gunakan input user sebagai acuan
- Jika tidak ada TECH-SPEC.md DAN user tidak memberikan input → minta user buat Tech Spec dulu

**Langkah 3 — Auto-detect boilerplate (opsional, jika di direktori project):**
AI cek apakah project sudah ada atau masih baru dengan mencari file kunci:
- `package.json` / `composer.json` / `pyproject.toml` / `go.mod` / `Cargo.toml` / `Gemfile` / `pubspec.yaml`
- Jika ada → sudah ada boilerplate
- Jika tidak ada → project baru

### FASE 2: Konfirmasi Scope

Tanyakan 1 hal:
- **Prioritas utama?** (Fitur inti dulu atau semua sekaligus?)

Default:
- Project baru → setup dulu, lalu fitur sesuai modul
- Boilerplate sudah ada → skip setup, langsung task fitur

### FASE 3: Produksi Task

Dua mode tergantung sumber acuan:
- **Tech Spec** → hasilkan task per modul. User ketik `lanjut` untuk ke modul berikutnya.
- **Input langsung (bug/task)** → hasilkan semua task langsung, tanpa pembagian modul.

### FASE 4: Finalisasi
Setelah semua task selesai:
1. Tampilkan task list ke user untuk review.
2. Instruksikan simpan ke `.agents/TASKS.md`.
3. Rekomendasikan lanjut ke **Implementation**.

## 📑 Struktur Task
Setiap task memiliki format:
- **ID:** T-XX
- **Judul:** [Nama task]
- **Deskripsi:** [Penjelasan singkat]
- **Modul:** [Nama modul]
- **Prioritas:** High/Mid/Low
- **Status:** Todo/In Progress/Done
- **Dependensi:** [ID task yang harus selesai dulu]
- **Estimasi:** [Jam/hari]
- **File yang diubah:** [Path file]

## 📄 TASK LIST

> AI generate task. Task bersifat konkret dan actionable.
>
> **Sumber acuan untuk task:**
> - Tech Spec → breakdown fitur per modul
> - Input langsung (bug/task) → breakdown langsung dari deskripsi user
>
> **Task yang muncul tergantung konten + hasil auto-detect — tidak ada template tetap:**
> - Project baru → include Setup Project
> - Boilerplate sudah ada → skip Setup Project, langsung fitur
> - Ada database → task setup DB + model/entity + migrasi
> - Ada interface/API → task routing/endpoint/action
> - Ada frontend → task komponen/halaman/layout
> - Ada autentikasi → task auth flow
> - Tidak ada database → skip semua task terkait DB
> - Static/frontend-only → skip backend, fokus ke UI

=== GENERATE OLEH AI BERDASARKAN ACUAN (TECH SPEC / INPUT USER) ===

AI tentukan skenario berdasarkan hasil FASE 1 & 2:
- **Input langsung (bug/task)** → breakdown langsung dari deskripsi user, tanpa modul
- **Project baru + Tech Spec** → mulai dari T-01: Setup Project, lalu task fitur per modul
- **Boilerplate + Tech Spec** → skip T-01 Setup Project, mulai dari task fitur langsung

AI urutkan task berdasarkan dependensi. Jangan buat task yang tidak relevan (e.g., skip database jika tidak pakai DB, skip auth jika tidak disebut acuan).


