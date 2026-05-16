# 🎓 Undangan Digital Pelepasan Siswa (Kelulusan Sekolah)

Template undangan digital berbasis web premium untuk acara perpisahan / pelepasan siswa sekolah. Dilengkapi dengan **Sistem Keamanan Validasi Tamu (Guest Validation)** di mana hanya nama siswa yang terdaftar di *database* yang dapat membuka isi undangan.

Dibuat menggunakan HTML, **Tailwind CSS**, dan Vanilla JavaScript. Sangat ringan, elegan, responsif, dan dapat diedit langsung dari browser menggunakan **GitHub Codespaces** lalu di-online-kan gratis via **Vercel**.

![Preview Undangan](https://img.shields.io/badge/Status-Siap_Pakai-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

## ✨ Fitur Keunggulan
- **Sistem Verifikasi Nama:** Terdapat layar *Akses Ditolak* (Error Screen) jika ada pihak luar yang mencoba membuka link tanpa nama yang terdaftar di sistem.
- **Data Dinamis (Nama & Kelas):** Nama dan Kelas siswa akan muncul secara otomatis dan elegan di layar sampul berdasarkan link URL yang dibagikan.
- **Splash Screen Interaktif:** Animasi "Memverifikasi Daftar Hadir" dengan ikon toga yang melompat.
- **Desain Mewah & Smooth:** Animasi *floating orbs* (cahaya melayang), ornamen sudut klasik, dan font kaligrafi latin.
- **Fitur Lengkap:** Dilengkapi dengan Embed Video Persembahan Angkatan, Grid Galeri Foto Kenangan, dan Google Maps Terintegrasi.

---

## 🛠️ Cara Penggunaan & Kustomisasi

Ikuti panduan ini untuk menyesuaikan undangan dengan sekolah Anda.

### Langkah 1: Fork & Buka Codespaces
1. **Fork** repository ini ke akun GitHub Anda.
2. Klik tombol hijau **<> Code**, pilih tab **Codespaces**, lalu buat Codespace baru.
3. Di editor web yang terbuka, Anda akan bekerja dengan file `index.html` dan folder `image`.

### Langkah 2: Cara Mengganti Foto, Video, dan Logo
1. Buat folder bernama `image` (jika belum ada) di menu sebelah kiri.
2. Siapkan aset Anda, ubah namanya sesuai daftar di bawah, lalu seret (*drag & drop*) ke dalam folder `image`:
   - `logo.png` (Logo sekolah, pastikan background transparan)
   - `gedung.jpg` (Foto gedung / foto angkatan untuk background atas)
   - `video-angkatan.mp4` (Video kenangan kelas XII)
   - `galeri1.jpg`, `galeri2.jpg`, `galeri3.jpg`, `galeri4.jpg` (4 foto kegiatan)

### Langkah 3: Cara Memasukkan Ratusan Data Siswa (Trik Excel)
Anda tidak perlu mengetik ratusan data satu per satu. Gunakan trik ini:
1. Buka file Excel data siswa Anda. Misal: **Kolom A** berisi *Nama Siswa*, dan **Kolom B** berisi *Kelas*.
2. Di **Kolom C** (kolom kosong sebelahnya), paste rumus Excel ini:
   `="{ nama: """ & A1 & """, kelas: """ & B1 & """ },"`
3. Tekan Enter, lalu tarik (drag) rumus tersebut ke bawah sampai semua siswa (misal 900 siswa) terkena rumus.
4. **Copy** seluruh hasil dari Kolom C tersebut.
5. Buka file `index.html` di Codespaces, cari bagian `const daftarSiswaValid = [ ... ]` (di bagian bawah kode).
6. **Paste** hasil Excel tadi ke dalam tanda kurung siku `[ ]`.

### Langkah 4: Simpan & Kirim ke GitHub
1. Tekan `Ctrl + S` untuk menyimpan file `index.html`.
2. Klik ikon **Source Control** di menu kiri (ikon bercabang).
3. Ketik pesan (misal: "Update data 900 siswa dan media").
4. Klik **Commit**, kemudian klik **Sync Changes**.

---

## 🚀 Langkah 5: Online-kan via Vercel (Gratis)
1. Buka [Vercel.com](https://vercel.com/) dan login menggunakan **GitHub**.
2. Klik **Add New...** -> **Project**.
3. Import repository undangan kelulusan ini.
4. Tidak perlu ubah pengaturan apapun, langsung klik **Deploy**.
5. Tunggu 30 detik, dan web Anda sudah resmi online! Anda akan mendapatkan link domain (contoh: `https://pelepasan-smk.vercel.app`).

---

## 💌 Cara Membagikan Link ke Wali Murid
Agar sistem keamanan bekerja, Anda **WAJIB** menambahkan parameter `?to=[Nama Siswa]` di belakang link Vercel Anda. 

Nama yang diketik di link harus sama persis (huruf besar/kecil tidak masalah, tapi ejaan harus sama) dengan yang ada di data Excel Anda.

**Format:**
`https://[link-vercel-anda].vercel.app/?to=[Nama Siswa]`

**Skenario Keamanan:**
- ❌ Jika link dibuka biasa (`https://...vercel.app/`): Layar merah **Akses Ditolak** akan muncul.
- ❌ Jika link dibuka dengan nama yang salah (`...?to=Hacker`): Layar merah **Akses Ditolak** akan muncul.
- ✅ Jika link dibuka dengan nama yang benar (`...?to=Budi Santoso`): Splash screen verifikasi berhasil, dan **Undangan Resmi** akan terbuka!

---

### Tips Tambahan saat Uji Coba (Live Server)
Gunakan ekstensi **Live Server** di Codespaces untuk melihat perubahan secara *real-time* sebelum di-Deploy ke Vercel. Ingat, saat tab preview terbuka, Anda harus menambahkan `?to=NamaSiswaYangAdaDiData` pada URL browser Anda agar bisa masuk ke halaman utama undangan.

---
**Dibuat dengan ❤️ untuk merayakan kelulusan generasi penerus bangsa.**