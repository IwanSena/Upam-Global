# 🗺️ Upam Global – Roadmap Resmi  
## Universal Portable Admin Manager  
### V20 Development Roadmap (Blueprint-Based)

Roadmap ini disusun berdasarkan **Blueprint Master V20** dan menggambarkan perjalanan pengembangan Upam Global dari versi awal hingga versi stabil.  
Tujuan roadmap ini adalah memastikan pengembangan berjalan terarah, konsisten, dan sesuai visi jangka panjang.

---

# ✅ Tahap 1 — Fondasi Proyek (Foundation Phase)

### 🎯 Tujuan:
Menyiapkan dasar proyek agar pengembangan fitur dapat berjalan stabil dan konsisten.

### ✅ Checklist:
- [ ] Menetapkan arsitektur inti berdasarkan Blueprint V20  
- [ ] Menyusun struktur folder awal (`src/`, `api/`, `reader/`, dll.)  
- [ ] Menyiapkan file dasar: README, LICENSE, ROADMAP, BLUEPRINT_MASTER  
- [ ] Menentukan format penyimpanan data (JSON, Markdown, struktur folder)  
- [ ] Menentukan standar coding V20 (Strict ID Matching, Safe Binding, SoC)  
- [ ] Membuat prototipe UI dashboard minimal  

---

# ✅ Tahap 2 — Modul Konten Dasar (Content Core)

### 🎯 Tujuan:
Mengimplementasikan fitur inti yang menjadi jantung Upam Global.

### ✅ Checklist:
- [ ] **Write Module** — Editor artikel ringan  
- [ ] **Manage Module** — Daftar konten + status  
- [ ] **Pages Module** — Halaman statis (About, Contact, dll.)  
- [ ] **Gallery Module** — Upload & preview media  
- [ ] Integrasi antar modul (Write → Manage → Pages)  
- [ ] Validasi input dasar (judul wajib, slug otomatis, dll.)  

---

# ✅ Tahap 3 — Sistem Penyimpanan & Sinkronisasi (Storage & Sync)

### 🎯 Tujuan:
Menghubungkan Writer → Storage → Reader secara sempurna.

### ✅ Checklist:
- [ ] Implementasi **Offline First → Online Sync**  
- [ ] Fetch & update `index.json` secara aman  
- [ ] Pembuatan file `.md` otomatis untuk artikel & halaman  
- [ ] Upload batch commit ke Git API  
- [ ] Penanganan error (401, 404, rate limit, dsb.)  
- [ ] Optimasi struktur folder:
**posts/** **pages/** **img/** **index.json** **config.json**


---

# ✅ Tahap 4 — Modul Pengaturan & Multi-Akun (Settings & Profiles)

### 🎯 Tujuan:
Membuat Upam Global dapat digunakan oleh banyak website & banyak akun.

### ✅ Checklist:
- [ ] **Settings Module** — Token, repo, nama situs, bahasa  
- [ ] Validasi token real-time (200 OK, 401, 404)  
- [ ] **Profiles Module** — Multi-akun, multi-website  
- [ ] Penyimpanan profil di localStorage (struktur objek besar)  
- [ ] Switching akun tanpa reload halaman  
- [ ] Pengaturan API driver (GitHub/GitLab)  

---

# ✅ Tahap 5 — Wizard & Template Engine (Installation & Rendering)

### 🎯 Tujuan:
Memudahkan user baru memulai tanpa bingung.

### ✅ Checklist:
- [ ] **Wizard Auto Install** — Buat repo baru + upload template  
- [ ] **Wizard Manual Install** — Link ke GitHub fork  
- [ ] Template Reader:
- [ ] Render artikel dari `.md`  
- [ ] Render halaman statis  
- [ ] Render daftar konten dari `index.json`  
- [ ] Client-Side Rendering penuh (tanpa build server)  
- [ ] Optimasi kecepatan load  

---

# ✅ Tahap 6 — Dokumentasi & Ekosistem (Docs & Community)

### 🎯 Tujuan:
Membangun ekosistem Upam Global agar mudah dipelajari dan dikembangkan.

### ✅ Checklist:
- [ ] Dokumentasi resmi (Upam Docs)  
- [ ] Panduan instalasi, penggunaan, dan troubleshooting  
- [ ] Q&A dan FAQ  
- [ ] Video tutorial  
- [ ] Halaman donasi & dukungan  
- [ ] Integrasi dengan:
- Website Aliansiena Foundation  
- Komunitas Telegram  
- Linktree  

---

# ✅ Tahap 7 — Stabilitas & Rilis (Stabilization & Release)

### 🎯 Tujuan:
Menyiapkan rilis publik yang stabil.

### ✅ Checklist:
- [ ] Pengujian fitur lengkap  
- [ ] Perbaikan bug kritis  
- [ ] Optimasi performa  
- [ ] Penulisan changelog  
- [ ] Rilis versi:
- ✅ v2.0.beta (current)
- [ ] v2.0.rc (release candidate)
- [ ] v2.0.stable  

---

# ✅ Tahap 8 — Pengembangan Lanjutan (Future Expansion)

### 🎯 Rencana Masa Depan:
- [ ] Mode Dark/Light  
- [ ] Plugin System  
- [ ] Template Marketplace  
- [ ] Mode Offline Full (tanpa internet sama sekali)  
- [ ] Integrasi API eksternal (Notion, Google Drive, dsb.)  
- [ ] Mode Multi-User dengan izin granular  

---

# ✅ Status Roadmap

Roadmap ini mengikuti **Blueprint Master Dari versi Betanya Hingga V20** dan akan diperbarui secara berkala sesuai progres pengembangan Upam Global.
