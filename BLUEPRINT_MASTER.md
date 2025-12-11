# 📘 BLUEPRINT MASTER 
## Upam Global — Universal Portable Admin Manager 
### Visi Sukses V20 (Arsitektur Sempurna)

Dokumen ini adalah **Kitab Referensi Pengembangan** untuk Upam Global. 

Semua fitur, logika, dan alur kerja di sini menggambarkan bagaimana sistem bekerja dalam kondisi **100% berhasil**, stabil, dan tanpa celah logika.
Blueprint ini menjadi dasar coding V20 dan memastikan tidak ada fitur “ompong”, tidak ada alur yang putus, dan tidak ada perilaku yang tidak terdefinisi.

---

# ✅ 1. Definisi & Fungsi Sistem

### **Apa itu Upam Global?**
Upam Global adalah **Browser-based Headless CMS** yang sepenuhnya berjalan di sisi klien (client-side), tanpa backend server tradisional.

### **Fungsi Utama**
Mengubah **browser HP** menjadi **Panel Admin portabel** untuk mengelola website statis:
- Artikel 
- Halaman statis 
- Media 
- Pengaturan 
- Template 
- Multi-akun 

Semua dilakukan tanpa server, tanpa database, dan tanpa hosting backend.

---

# ✅ 2. Arsitektur Inti (The Core Logic)

Upam Global bekerja dengan **3 Pilar Utama**. 
Jika salah satu pilar gagal → seluruh sistem gagal.

---

## 🟦 A. The Writer (Ekstensi Upam)
**Posisi:** Browser HP user (Kiwi, Yandex, atau browser yang mendukung ekstensi). 
**Peran:** Panel Admin.

### Tugas:
- Menerima input user (teks, gambar, metadata)
- Mengubah input menjadi format mesin (JSON/Markdown)
- Menyimpan sementara secara lokal (offline-first)
- Mengirim data ke cloud melalui Git API

### Logika Kunci:
- **Offline First, Online Sync** - Data diketik → disimpan lokal → dikirim saat Publish 
- Tidak ada kehilangan data meski koneksi buruk

---

## 🟩 B. The Storage (GitHub / GitLab)
**Posisi:** Cloud server gratis. 
**Peran:** Hardisk utama.

### Tugas:
- Menyimpan seluruh data:
  - `index.json` → database utama
  - `.md` → konten artikel & halaman
  - `config.json` → pengaturan tampilan
  - folder `img/` → media
- Menjadi pusat sinkronisasi antara Writer & Reader

### Logika Kunci:
- Struktur folder **HARUS baku** - Jika struktur rusak → Reader tidak bisa membaca

---

## 🟧 C. The Reader (Template Web)
**Posisi:** Browser pengunjung website. 
**Peran:** Mesin perakit tampilan.

### Tugas:
- Membaca `index.json`
- Mengambil file `.md`
- Menyusun HTML secara dinamis

### Logika Kunci:
- **Client-Side Rendering (CSR)** - Tidak ada proses build di server 
- Browser pengunjung yang merakit tampilan

---

# ✅ 3. Alur Kerja Fitur (Workflow Logic)

Bagian ini menjelaskan bagaimana fitur bekerja saat **100% sukses**.

---

## 🟢 1. Logika WIZARD (Instalasi)
**Masalah Lama:** User bingung mulai dari mana. 
**Solusi V20:** Instalasi otomatis.

### Alur:
1. User membuka menu Wizard 
2. Pilih:
   - **Auto Install** → Upam membuat repo baru + upload template 
   - **Manual Install** → User diarahkan ke GitHub untuk fork 
3. Dalam 10 detik, user punya website siap pakai

### Aksi API:
- Membuat repo baru 
- Upload file dasar:
  - `index.html`
  - `script.js`
  - `index.json`
  - `config.json`
  - folder `posts/`, `pages/`, `img/`

---

## 🔵 2. Logika EDITOR & PUBLISH (Jantung Sistem)
**Masalah Lama:** Toolbar mati, data tidak terkirim. 
**Solusi V20:** Editor stabil + publish atomik.

### Alur Publish:
1. User mengetik artikel 
2. Klik **Publish** 3. Upam melakukan:
   - Fetch `index.json` dari repo 
   - Tambahkan artikel baru ke array (unshift) 
   - Buat file `.md` di `posts/slug.md` 
   - Upload 2 file sekaligus (batch commit) 
4. Feedback visual:
   - ⏳ Mengirim… 
   - ✅ Sukses 

---

## 🟡 3. Logika PROFIL (Multi-Akun)
**Masalah Lama:** Ganti akun crash. 
**Solusi V20:** Sistem profil berbasis objek besar.

### Penyimpanan:
```json
{
  "active_id": "profile_1",
  "profiles": {
    "profile_1": { "nama": "Web Pribadi", "token": "ghp_abc..." },
    "profile_2": { "nama": "Web Toko", "token": "glpat_xyz..." }
  }
}
```

### Switching:
- Hanya mengubah `active_id`
- Refresh konfigurasi API tanpa reload halaman

---

## 🟠 4. Logika SETTINGS (Koneksi)
**Masalah Lama:** User tidak tahu token benar/salah.
**Solusi V20:** Validasi real-time.

### Tombol Tes:
- ✅ **200 OK** → Token Valid
- ❌ **401** → Token Salah
- ⚠️ **404** → Repo Tidak Ditemukan

---

# ✅ 4. Struktur Database (File System)

Agar Writer & Reader sinkron, struktur HARUS seperti ini:

- `index.json` → Database utama
- `config.json` → Pengaturan tampilan
- `posts/` → Artikel (.md)
- `pages/` → Halaman statis (.md)
- `img/` → Media (jpg/png)
- `index.html` → Template web

---

# ✅ 5. Standar Kode V20 (Anti-Gagal)

### ✅ Strict ID Matching
ID di HTML harus sama persis dengan yang dipanggil JS.

### ✅ Safe Binding
Tidak boleh langsung: `document.getElementById('x').addEventListener(...)`
Harus pakai wrapper agar tidak crash jika elemen hilang.

### ✅ Separation of Concern
- `api_driver.js` → urusan API
- `app.js` → logika UI
- `reader.js` → logika template

**Tidak boleh dicampur.**

---

# ✅ 6. Visi Akhir Upam Global
- Panel admin portabel 
- 100% client-side 
- Zero backend 
- Universal deployment 
- Bisa dipakai siapa saja, dari HP 
- Cocok untuk blog, toko kecil, portofolio, dokumentasi, dan website statis lainnya 

---

# ✅ 7. Status Blueprint
Blueprint ini adalah versi **V20 (Beta)**. 
Akan diperbarui seiring pengembangan fitur.

---

# ✅ Penutup
Dokumen ini adalah fondasi utama pengembangan Upam Global. 
Semua fitur, modul, dan alur kerja harus mengikuti blueprint ini agar sistem stabil, konsisten, dan mudah dikembangkan.
