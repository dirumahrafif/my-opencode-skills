---
name: write-tech-spec
description: Write technical specifications for features, changes, or bug fixes. Produces a markdown file in .agents/tech-specs/<YEAR>/ for user review, then creates issues after approval. Gunakan ketika: user minta tech spec, user minta spesifikasi teknis, user minta implementation plan, user minta dokumentasi teknis, atau user mendeskripsikan fitur yang butuh perencanaan sebelum coding.
---

# SKILL: TECH SPEC GENERATOR (Vibe Coding Ready)

---

## 📋 Metadata
- **Nama:** Tech Spec Generator
- **Versi:** 1.0
- **Output:** Tech Spec 5 bagian
- **Lokasi File:** `.agents/TECH-SPEC.md`
- **Dependensi:** PRD.md (wajib dibaca)

## 🎯 Trigger Keywords
Otomatis aktif saat user menyebut:
- "Buat Tech Spec"
- "Buat spesifikasi teknis"
- "Buat technical specification"
- "Buat dokumen teknis"
- "Buat spec dari PRD"
- "Baca TECH-SPEC saya"
- "Load Tech Spec"

## 📝 Deskripsi
Skill ini membaca PRD dari `.agents/PRD.md` dan menghasilkan Tech Spec ringkas tapi detail. Berisi tech stack, database, interface, dan alur teknis — konten menyesuaikan stack apapun. Siap pakai untuk Tasking dan Implementasi.

## 📂 Baca/Menyimpan File
- **Baca PRD (WAJIB):** `@.agents/PRD.md`
- **Baca Tech Spec:** `@.agents/TECH-SPEC.md`
- **Simpan Tech Spec:** `.agents/TECH-SPEC.md`

## ⚙️ Cara Kerja Skill

### FASE 1: Deteksi Trigger & Baca PRD
**WAJIB:** Sebelum membuat Tech Spec, AI HARUS:
1. Cek file `.agents/PRD.md`
2. Jika ada: baca dan jadikan acuan
3. Jika tidak ada: minta user buat PRD dulu

### FASE 2: Klarifikasi (3 Pertanyaan)
Tanyakan 3 hal ini sebelum mulai:
1. **Tech Stack pilihan?** (Frontend & Backend — stack apapun, e.g., Next.js / React+Vite / Vue / Svelte / Django / FastAPI / Go / Laravel / Spring / Ruby on Rails / ASP.NET / Phoenix)
2. **Database?** (PostgreSQL/MySQL/MongoDB)
3. **Hosting?** (Vercel/AWS/DigitalOcean)

Default jika user tidak menentukan:
- Frontend: [Framework, e.g., Next.js 14+ / React / Vue / Svelte / Django Templates]
- Backend: [Runtime, e.g., Node.js+Express / Python+FastAPI / Go+Chi / Java Spring]
- Database: [Database, e.g., PostgreSQL / MySQL / MongoDB / SQLite]
- ORM: [ORM, e.g., Prisma / Drizzle / TypeORM / SQLAlchemy / Mongoose]
- Hosting: [Hosting, e.g., Vercel / AWS / Railway / DigitalOcean / Fly.io]

> **Catatan:** List di atas hanya contoh. AI harus bisa menangani stack apapun yang dipilih user (Ruby on Rails, ASP.NET, Phoenix, SvelteKit, dll.) dengan mengikuti best practice resmi dari framework tersebut.

### FASE 3: Produksi Tech Spec (5 Bagian)
Hasilkan per bagian. User ketik `lanjut` untuk melanjutkan.

### FASE 4: Finalisasi
Setelah bagian 5 selesai:
1. Ucapkan selamat.
2. Instruksikan simpan ke `.agents/TECH-SPEC.md`.
3. Rekomendasikan lanjut ke **Task Generator**.

## 📑 5 Bagian Tech Spec
1. Tech Stack & Arsitektur
2. Database Design
3. Interface Design
4. Alur Logika & Business Rules
5. Keamanan, Performa, & Deployment

## 📄 BAGIAN 1: Tech Stack & Arsitektur

### Tech Stack
| Layer | Technology | Version |
|-------|------------|---------|
| Frontend | [Framework] | [Versi] |
| Language | TypeScript | 5.x |
| Styling | [Tailwind / Bootstrap / CSS Modules / none] | [Versi] |
| State | [Zustand/Redux/Context/Pinia/Vuex/none] | - |
| Backend | [Framework] | [Versi] |
| Database | [PostgreSQL/MySQL/MongoDB/SQLite] | [Versi] |
| ORM | [Prisma/Drizzle/SQLAlchemy/Mongoose/none] | [Versi] |
| Auth | [JWT/Session/OAuth/bcrypt] | - |
| Hosting | [Vercel/AWS/Railway/Fly.io] | - |
| Caching | [Redis/Memcached/Valkey/none] | [Versi] |


### Arsitektur Sistem
Frontend → Backend/API → Database
↓ ↓
[File Storage] [Cache Layer]
### Struktur Folder

```struktur folder mengikuti best practice resmi dari framework yang dipilih user.```

> AI HARUS generate struktur folder sesuai framework. Contoh:
> - **Laravel 11** → `app/Http/Controllers`, `app/Models`, `database/migrations`, `routes/`
> - **Next.js 14+** → `src/app`, `src/components`, `src/lib`
> - **Go 1.22+** → `cmd/`, `internal/handler`, `internal/model`, `internal/service`
> - **Django 5.x** → `app_name/api/`, `app_name/models.py`, `app_name/services/`
> - **FastAPI** → `app/api/`, `app/models/`, `app/schemas/`, `app/services/`
> - **Ruby on Rails 8** → `app/controllers`, `app/models`, `config/routes.rb`
> - Stack lain → cari best practice resmi framework tersebut
### Justifikasi
- **[Framework]:** [Alasan singkat, e.g., "Performance & DX"]
- **[Database]:** [Alasan, e.g., "Struktur data relasional"]
- **[Hosting]:** [Alasan, e.g., "Mudah deploy & scale"]

## 📄 BAGIAN 2: Database Design

### Ringkasan Database
| Item | Detail |
|------|--------|
| Database | [PostgreSQL / MySQL / MongoDB / SQLite / Firebase / Supabase / ...] |
| ORM/Driver | [Prisma / Drizzle / Mongoose / SQLAlchemy / Firebase SDK / ...] |
| Pendekatan | [Relational / Document / Key-Value / Graph] |
| Tools Migrasi | [Prisma Migrate / Alembic / Flyway / manual] |

### Entity Overview
*Daftar entitas utama dari PRD, cukup field penting + relasi (detail kolom ditentukan saat implementasi):*

| Entity | Key Fields | Relasi |
|--------|-----------|--------|
| [Entity 1] | id, [field_a], [field_b] | → Entity 2 (1:N) |
| [Entity 2] | id, entity_1_id, [field_c] | ← Entity 1, → Entity 3 |
| [Entity 3] | id, entity_2_id, [field_d] | ← Entity 2 |

### Index Strategy (jika relational)
- **[entity_1].[field]** — lookup by [description]
- **[entity_2].[entity_1_id]** — foreign key index

### Data Flow
[Deskripsi bagaimana data mengalir antar entity, e.g.:
"User membuat Order → Order memiliki OrderItem → setiap OrderItem merefer ke Product"]
## 📄 BAGIAN 3: Interface Design

> Konten bagian ini otomatis menyesuaikan stack yang dipilih di FASE 2.
> AI lihat stack + PRD, tentukan bentuk interface yang tepat, generate secukupnya.
>
> - **Monolith (Laravel/Django/Rails)** → Routes + Controller + View
> - **SPA + Backend API** → REST / GraphQL endpoints
> - **Next.js/SvelteKit/Remix** → Server Actions / API Routes
> - **HTMX** → HTML endpoints (return partial)
> - **Mobile app** → API endpoints
> - **Desktop app (Electron/Tauri)** → IPC channels
> - **Static / Frontend-only** → BAGIAN 3 tidak diperlukan, skip

=== GENERATE OLEH AI BERDASARKAN PRD & STACK ===
| Method | Path / Action | Description | Auth |
|--------|---------------|-------------|------|
| [GET/POST/action] | [path / route name / action name] | [deskripsi dari PRD] | Yes/No/N/A |

*Cukup tabel ringkas — detail request/response ditentukan saat implementasi.*

## 📄 BAGIAN 4: Alur Logika & Business Rules

> AI generate alur dari PRD, format menyesuaikan arsitektur stack yang dipilih.
> Hanya buat alur untuk fitur yang benar-benar ada di PRD.
>
> - **Monolith** → User → Route → Controller → Model → View
> - **SPA + API** → User → Frontend → API → Backend → DB
> - **Serverless** → User → Client → Function → DB/Service
> - **Mobile / Desktop** → User → App → Service/API
>
> Auth flow hanya dibahas jika PRD menyebutkan fitur auth.
> State management sesuaikan frontend stack (React Query / Pinia / Vuex / Signals / Context / dll)

=== GENERATE OLEH AI BERDASARKAN PRD & STACK ===

**Alur [Fitur 1 dari PRD]:**
1. [Langkah sesuai PRD]
2. [Langkah sesuai PRD]
3. [Langkah sesuai PRD]

**Alur [Fitur 2 dari PRD]:**
1. [Langkah sesuai PRD]
2. [Langkah sesuai PRD]

### Business Rules (dari PRD)
- [Rule 1 dari PRD]
- [Rule 2 dari PRD] 

## 📄 BAGIAN 5: Keamanan, Performa, & Deployment

> AI generate konten berdasarkan stack + hosting yang dipilih di FASE 2.
> Hanya cantumkan item yang relevan — jangan copy-paste template.
>
> Contoh:
> - **Next.js + Vercel** → Vercel Analytics, Next.js Image, auto-deploy
> - **Laravel + DO** → Laravel Horizon, Supervisor, Redis, manual deploy
> - **FastAPI + Railway** → Uvicorn workers, Railway auto-deploy, Sentry
> - **Static site + Netlify** → Netlify deploy, skip keamanan backend
> - **Electron desktop** → Auto-update, offline storage, skip deployment

=== GENERATE OLEH AI BERDASARKAN STACK & HOSTING ===

### Keamanan
- **[item relevan dari PRD + stack]**

### Performa
- **[item relevan dari PRD + stack]**

### Deployment
- **[item relevan dari stack + hosting]

### Development Setup

```AI harus generate perintah setup sesuai framework yang dipilih user.```

Contoh:
- **Node.js/TypeScript** → `npm install && npm run dev`
- **Python/FastAPI** → `pip install -r requirements.txt && uvicorn app.main:app --reload`
- **Python/Django** → `pip install -r requirements.txt && python manage.py runserver`
- **Laravel** → `composer install && php artisan serve`
- **Go** → `go mod download && go run ./cmd/server`
- **Ruby on Rails** → `bundle install && rails server`
- **Stack lain** → sesuaikan dengan best practice framework

**🎉 Tech Spec selesai!**

## 🔄 Finalisasi

1. **Simpan file:**
   Simpan seluruh konten Tech Spec sebagai `.agents/TECH-SPEC.md`

2. **Lanjut ke Task Generator:**
   Ketik: `"Buat Task berdasarkan Tech Spec yang sudah dibuat"`
