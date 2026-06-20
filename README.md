# MyMDBlog - Blog Pribadi Berbasis Jekyll & GitHub Pages

**MyMDBlog** adalah situs web blog pribadi statis yang dibangun menggunakan engine generator situs statis **Jekyll**, format tulisan **Markdown**, dan di-host secara gratis di **GitHub Pages** menggunakan tema **Architect**. 

Blog ini dirancang agar sangat ringan, minimalis, responsif, dan mudah dikelola tanpa memerlukan database ataupun backend yang rumit. Anda cukup menulis artikel dalam file Markdown (`.md`), melakukan push ke GitHub, dan artikel Anda akan terbit secara otomatis.

---

## 🚀 Fitur Utama
1. **Interactive Sidebar Accordion**: Daftar kategori di sidebar menggunakan menu akordeon interaktif (HTML5 `<details>` & `<summary>`) tanpa bergantung pada JavaScript berat. Klik pada kategori untuk memunculkan/menyembunyikan daftar artikel.
2. **Kategori Dinamis**: Postingan otomatis dikelompokkan berdasarkan kategori yang didefinisikan dalam *Front Matter* postingan Anda.
3. **Desain Responsif & Bersih**: Menggunakan tema **Jekyll Architect** bawaan GitHub Pages yang dioptimalkan untuk berbagai ukuran perangkat (desktop, tablet, dan smartphone).
4. **Relative Path Optimization**: Konfigurasi otomatis subpath `/mymdblog` agar tidak terjadi error 404 pada URL aset maupun link postingan saat di-host di GitHub Pages.
5. **Mudah Dikelola**: Cukup tambahkan file Markdown di folder `_posts` untuk menerbitkan artikel baru.

---

## 📁 Struktur Direktori
Berikut adalah penjelasan singkat mengenai struktur file di dalam repositori ini:

```text
mymdblog/
├── _config.yml          # File konfigurasi utama Jekyll (judul, deskripsi, baseurl, dll)
├── _layouts/            # Berisi template tata letak halaman kustom
│   └── default.html     # Layout utama kustom yang berisi sidebar akordeon kategori
├── _posts/              # Folder tempat semua artikel disimpan
│   └── 2026-06-20-artikel-pertama.md  # Contoh format penulisan artikel
├── index.md             # Halaman beranda blog yang menampilkan daftar postingan terbaru
└── README.md            # Dokumentasi proyek (file ini)
```

---

## 💻 Cara Menjalankan Secara Lokal (Local Development)
Sebelum menjalankan secara lokal, pastikan Anda telah menginstal **Ruby**, **Jekyll**, dan **Bundler** di komputer Anda.

1. **Unduh atau Clone Repositori**:
   ```bash
   git clone https://github.com/atzartech-prog/mymdblog.git
   cd mymdblog
   ```

2. **Instal Dependensi**:
   Jalankan perintah berikut untuk menginstal tema dan plugin yang dibutuhkan Jekyll:
   ```bash
   bundle install
   ```

3. **Jalankan Server Lokal**:
   Mulai server lokal Jekyll dengan perintah:
   ```bash
   bundle exec jekyll serve
   ```
   *Catatan: Jika Anda ingin mencocokkan subpath lokal dengan GitHub Pages, Anda dapat menjalankan perintah:*
   ```bash
   bundle exec jekyll serve --baseurl "/mymdblog"
   ```

4. **Akses Blog**:
   Buka browser Anda dan akses halaman lokal di:
   * **http://localhost:4000/mymdblog/** (jika menggunakan baseurl)
   * **http://localhost:4000/** (jika tanpa baseurl)

---

## ✍️ Cara Menulis Artikel Baru
Semua artikel ditulis menggunakan format Markdown dan disimpan di dalam folder `_posts/`. 

### 1. Aturan Penamaan File
Nama file artikel wajib mengikuti format penulisan tanggal jekyll berikut:
```text
YYYY-MM-DD-judul-artikel.md
```
*Contoh:* `2026-06-21-tips-pemrograman-pemula.md`

### 2. Front Matter (Metadatada Artikel)
Di bagian paling atas file artikel, Anda wajib menambahkan informasi header (*Front Matter*) di antara dua garis pembatas `---`. Berikut adalah templat yang direkomendasikan:

```yaml
---
layout: default
title: "Judul Artikel Anda di Sini"
date: 2026-06-21
categories: blog tutorial
tags: [jekyll, markdown, github]
---
```

**Penjelasan Parameter:**
* `layout`: Wajib diatur ke `default` agar artikel menggunakan tema Architect lengkap dengan header dan sidebar akordeon kategori.
* `title`: Judul tulisan Anda (gunakan tanda kutip).
* `date`: Tanggal publikasi tulisan (format: `YYYY-MM-DD`).
* `categories`: Kategori artikel Anda (pisahkan dengan spasi jika lebih dari satu). Kategori ini otomatis memicu pembuatan grup baru di sidebar.
* `tags`: Tag/kata kunci yang relevan untuk postingan Anda (format dalam kurung siku).

---

## ⚙️ Kustomisasi Blog
Anda dapat mengedit informasi umum situs melalui file `_config.yml`:

```yaml
title: Blog Pribadi Saya                     # Mengubah judul utama di header
description: Tips teknologi & pemrograman    # Mengubah sub-judul di header
theme: jekyll-theme-architect                # Tema yang digunakan
baseurl: "/mymdblog"                         # Subpath subdirektori repositori GitHub Anda
url: "https://atzartech-prog.github.io"       # Domain GitHub Pages Anda
```

Untuk mengubah gaya warna teks kategori pada sidebar, Anda bisa membuka [\_layouts/default.html](_layouts/default.html) dan menyesuaikan kode warna HTML pada baris bergaya:
```html
<p style="color: #000;">    <!-- Mengubah warna teks judul kategori -->
<a style="color: #000;">    <!-- Mengubah warna tautan judul artikel -->
```

---

## ☁️ Cara Deploy / Upload ke GitHub Pages
Jika Anda melakukan perubahan (seperti menambahkan artikel baru di folder `_posts` atau memperbarui sidebar), lakukan langkah berikut untuk meng-upload ke GitHub Pages Anda:

### Metode 1: Menggunakan Git Command Line (Rekomendasi)
Jalankan perintah ini secara berurutan di terminal folder proyek Anda:
```bash
git add .
git commit -m "Menambahkan artikel baru dan memperbarui tema"
git push origin main
```

### Metode 2: Melalui Halaman Website GitHub (Upload Manual)
1. Kunjungi repositori Anda di browser: `https://github.com/atzartech-prog/mymdblog`
2. Klik tombol **Add file** -> **Upload files**.
3. Tarik folder/file yang Anda ubah (misalnya folder `_posts` atau folder `_layouts`) ke browser Anda.
4. Klik **Commit changes**.

Setelah melakukan commit, GitHub Actions akan menjalankan build otomatis. Situs Anda akan diperbarui dalam waktu 1–2 menit di alamat: **`https://atzartech-prog.github.io/mymdblog/`**

---

## 📄 Lisensi
Proyek ini bersifat open-source dan bebas digunakan untuk kebutuhan blog pribadi Anda.
