# 🚀 Panduan Instalasi Skill Opencode (Windows)

Jika Anda ingin menggunakan skill opencode ini, ikuti langkah-langkah mudah berikut:

### Langkah 1: Mengambil Skill dari GitHub
Buka terminal (Git Bash atau Command Prompt) dan jalankan perintah berikut untuk mengunduh repositori:

```bash
git clone https://github.com/dirumahrafif/my-opencode-skills.git
```

### Langkah 2: Menyalin Folder Skill (Manual)
1. Buka folder hasil clone tadi melalui **File Explorer**.
2. **Pilih semua folder skill** yang ingin Anda pasang, lalu tekan `Ctrl + C` (Copy).
3. Tekan tombol `Windows + R` pada keyboard, lalu ketik:
   `%APPDATA%\opencode\skills\`
4. Tekan `Enter`. (Jika folder belum ada, silakan buat folder bernama `skills` di dalam folder `opencode`).
5. Di dalam folder `skills` tersebut, tekan `Ctrl + V` (Paste).

### Langkah 3: Mendaftarkan Skill di `opencode.jsonc`
1. Cari file `opencode.jsonc` di folder `%APPDATA%\opencode\`.
2. Buka dengan Notepad atau VS Code.
3. Tambahkan skill Anda ke dalam daftar `skills`:
   ```json
   {
     "skills": [
       {
         "name": "create-issues",
         "location": "%APPDATA%/opencode/skills/create-issues"
       }
     ]
   }
   ```
   *(Pastikan jalur `location` sesuai dengan lokasi folder di komputer Anda).*

---
**Selesai!** Sekarang skill siap digunakan dengan memanggil *trigger keywords* yang ada di dalam `SKILL.md`.
