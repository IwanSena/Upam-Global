# 🤝 Panduan Kontribusi 
## Upam Global — Universal Portable Admin Manager

Terima kasih telah tertarik berkontribusi pada **Upam Global**. 

Proyek ini dibangun dengan visi jangka panjang, dan kontribusi Anda sangat berarti untuk menjadikannya lebih stabil, kuat, dan bermanfaat bagi semua pengguna.
Dokumen ini menjelaskan cara berkontribusi, standar teknis, dan alur kerja yang digunakan dalam pengembangan Upam Global.

---

# ✅ 1. Cara Melaporkan Bug

Jika Anda menemukan bug, lakukan langkah berikut:

1. Buka tab **Issues** di GitHub 
2. Pilih template **Bug Report** 3. Sertakan informasi berikut:
   - Ringkasan masalah 
   - Langkah untuk mereproduksi 
   - Perilaku yang diharapkan 
   - Screenshot atau log (jika ada) 
   - Informasi perangkat (browser, OS, versi) 

> **Catatan:** Bug yang jelas dan lengkap akan lebih cepat ditangani.

---

# ✅ 2. Mengusulkan Fitur Baru

Untuk usulan fitur:

1. Buka **Issue** baru 
2. Gunakan label `enhancement` 
3. Sertakan:
   - Masalah yang ingin diselesaikan 
   - Ide solusi 
   - Contoh penggunaan 
   - Dampak terhadap user 

Usulan fitur yang selaras dengan **Blueprint Master V20** akan diprioritaskan.

---

# ✅ 3. Kontribusi Kode

Sebelum mengirimkan kode, pastikan Anda memahami:
- **Blueprint Master V20** - **Roadmap resmi** - **Standar coding V20**:
  - Strict ID Matching 
  - Safe Binding 
  - Separation of Concern 

### ✅ Alur Kontribusi Kode
1. **Fork** repo ini 
2. Buat branch baru:
   ```bash
   feature/nama-fitur
   fix/nama-bug
   improve/nama-perbaikan
   ```
3. Lakukan perubahan di folder `src/` 
4. Pastikan:
   - Tidak ada error di console 
   - Struktur folder tidak rusak 
   - Tidak ada logika yang melanggar Blueprint 
5. Buat **Pull Request** dengan deskripsi jelas 
6. Tunggu review dari maintainer

---

# ✅ 4. Standar Penulisan Commit

Gunakan format commit berikut agar rapi dan mudah dilacak:

```text
feat: menambahkan modul gallery
fix: memperbaiki error publish
docs: memperbarui dokumentasi
refactor: merapikan struktur app.js
style: memperbaiki indentasi
chore: update dependensi
```

Commit yang rapi memudahkan tracking perubahan.

---

# ✅ 5. Struktur Folder Proyek

Kontribusi harus mengikuti struktur berikut:

```text
src/
├── app/      → logika UI
├── api/      → driver Git API
├── reader/   → template web
├── utils/    → helper & wrapper
└── assets/   → ikon, gambar, dll.
```

> Jangan mencampur logika API dengan UI. 
> Jangan menaruh file di luar struktur tanpa alasan kuat.

---

# ✅ 6. Aturan Tambahan

- Jangan mengirimkan file build atau hasil kompresi 
- Jangan mengirimkan token, API key, atau data sensitif 
- Jangan mengubah lisensi tanpa diskusi 
- Jangan menambahkan library besar tanpa alasan kuat 
- Pastikan perubahan Anda tidak merusak kompatibilitas backward 

---

# ✅ 7. Komunikasi & Diskusi

Untuk diskusi cepat, Anda dapat bergabung ke komunitas resmi:

- **Telegram:** https://t.me/Aliansiena 
- **Website:** https://aliansiena.pages.dev 
- **Dokumentasi:** https://iwansena.github.io/Upam-Docs/ 

---

# ✅ 8. Terima Kasih

Kontribusi Anda membantu membangun ekosistem Upam Global menjadi lebih kuat dan bermanfaat. 

Setiap ide, laporan bug, dan baris kode sangat berarti.
Mari membangun masa depan **Universal Portable Admin Manager** bersama‑sama.
