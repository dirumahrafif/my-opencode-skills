# 🚀 Panduan Instalasi Skill Opencode

Jika Anda ingin menggunakan skill opencode ini, ikuti langkah-langkah berikut:

### Langkah 1: Mengambil Skill dari GitHub
Buka terminal dan jalankan perintah berikut:

```bash
git clone https://github.com/dirumahrafif/my-opencode-skills.git
```

### Langkah 2: Menyalin Folder Skill

**Untuk Pengguna Windows:**
1. Buka folder hasil clone melalui **File Explorer**.
2. Salin folder skill yang ingin dipasang.
3. Tekan `Windows + R`, ketik `%APPDATA%\opencode\skills\`, lalu tekan `Enter`.
4. Tempel (Paste) folder tersebut di sana.

**Untuk Pengguna Mac & Linux:**
1. Buka terminal dan masuk ke folder hasil clone.
2. Salin folder skill ke direktori konfigurasi opencode:
   ```bash
   cp -r my-opencode-skills ~/.config/opencode/skills/
   ```

### Langkah 3: Mendaftarkan Skill di `opencode.jsonc`
1. Buka file konfigurasi:
   - **Windows:** `%APPDATA%\opencode\opencode.jsonc`
   - **Mac/Linux:** `~/.config/opencode/opencode.jsonc`
2. Tambahkan skill ke dalam daftar `skills`:
   ```json
   {
     "skills": [
       {
         "name": "create-issues",
         "location": "/path/to/opencode/skills/create-issues"
       }
     ]
   }
   ```

---
**Selesai!** Sekarang skill siap digunakan dengan memanggil *trigger keywords* yang ada di dalam `SKILL.md`.
