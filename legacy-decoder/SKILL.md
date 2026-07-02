---
name: legacy-decoder
description: Reverse-engineer legacy code into structured documentation (Tech Spec + Tasks). Use when: user says "pahami kode", "analisis legacy", "reverse engineer", "mapping kode", "dokumentasi kode existing".
---

# SKILL: LEGACY DECODER

## 📋 Metadata
- **Nama:** Legacy Decoder
- **Versi:** 1.0
- **Output:** Analisis arsitektur + Tech Spec (opsional) + Task List
- **Lokasi File:** `.agents/4-LEGACY-DECODER.md`
- **Dependensi:** Tidak ada (bekerja dari kode existing)

## 🎯 Trigger Keywords
- "Pahami kode"
- "Analisis legacy"
- "Reverse engineer"
- "Mapping kode"
- "Dokumentasi kode existing"
- "Baca legacy code"
- "Review codebase"
- "Baca hasil analisis"
- "Load legacy analysis"

## 📂 Baca/Menyimpan File
- **Baca:** `@.agents/4-LEGACY-DECODER.md`
- **Simpan:** `.agents/4-LEGACY-DECODER.md`
- **Output Tech Spec:** `.agents/2-TECH-SPEC.md` (opsional)
- **Output Tasks:** `.agents/3-TASKS.md`

## ⚙️ Cara Kerja Skill

### FASE 0: Deteksi Trigger
- Jika user bilang **"baca"** atau **"load"** → Baca `.agents/4-LEGACY-DECODER.md` dan beri ringkasan.
- Jika user bilang **"pahami"**, **"analisis"**, **"reverse"**, **"mapping"**, atau **"review"** → Lanjut ke FASE 1.

### FASE 1: Discovery
1. Scan struktur folder project
2. Baca file konfigurasi (`package.json`, `composer.json`, `pyproject.toml`, `go.mod`, `Cargo.toml`, `Gemfile`, `pubspec.yaml`, `CMakeLists.txt`, `pom.xml`, dll.)
3. Identifikasi framework, runtime, database, dan dependency utama
4. Simpan ringkasan stack + struktur folder ke `.agents/4-LEGACY-DECODER.md` (append)

### FASE 2: Codebase Mapping
1. Petakan struktur direktori (controller/model/service/route/view)
2. Identifikasi entry point dan alur request
3. Simpan dependency graph / arsitektur tingkat tinggi ke `.agents/4-LEGACY-DECODER.md` (append)

### FASE 3: Business Logic Extraction
1. Ekstrak daftar routes/endpoints/actions
2. Identifikasi entities/models utama dan relasinya
3. Catat business rules yang terlihat dari kode
4. Simpan ringkasan business logic ke `.agents/4-LEGACY-DECODER.md` (append)

### FASE 4: Database Reverse (jika ada DB)
1. Baca migration files / schema definition
2. Petakan entity-relationship
3. Catat index, constraint, trigger
4. Simpan database overview ke `.agents/4-LEGACY-DECODER.md` (append)

### FASE 5: Output Generation
Setelah FASE 1-4 selesai dan semua tersimpan:

**Opsional — Tech Spec (`2-TECH-SPEC.md`):**
1. Tanyakan: "Buat Tech Spec dari hasil analisis? (y/n)"
2. Jika ya → generate 5 bagian (Tech Stack, DB Design, Interface, Alur, Keamanan)
3. Simpan ke `.agents/2-TECH-SPEC.md`

**Wajib — Tasks (`3-TASKS.md`):**
1. Generate task list berdasarkan temuan (refactor, bug fix, optimasi, dokumentasi)
2. Simpan ke `.agents/3-TASKS.md`

### FASE 6: Finalisasi
1. Tampilkan ringkasan hasil analisis
2. Rekomendasikan lanjut ke **implement-task** atau **verify**
