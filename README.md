# MomsBakeryPage — Landing Page (Iterasi 1)

Selamat datang di repositori MomsBakeryPage. Ini adalah iterasi pertama sebuah landing page yang dibuat untuk membantu BOLU BOLING PROBOLINGGO memperkenalkan dan memasarkan produk bolu secara online. Tujuan utama proyek ini adalah memberikan kehadiran digital dasar yang responsif, SEO-friendly, dan mudah diupdate secara manual sehingga toko dapat menjangkau pelanggan baru dan meningkatkan penjualan yang saat ini berjalan lambat.

> Catatan penting: Semua aset (gambar), harga, rating, dan deskripsi masih bersifat dummy. Data akan diperbarui setelah diskusi dan konfirmasi dengan manajer toko BOLU BOLING PROBOLINGGO.

---

## Ringkasan tujuan
- Membuat landing page sederhana namun modern untuk BOLU BOLING PROBOLINGGO.
- Mempermudah pemasaran online dan perolehan pelanggan baru lewat website.
- Menyediakan struktur dasar SEO (meta tags, OG tags, JSON-LD) agar mudah dioptimasi lebih lanjut.
- Menyimpan konten sementara (dummy) agar tim dapat meninjau desain & alur sebelum memasukkan data final.

---

## Fitur (Iterasi 1)
- Halaman landing responsif (desktop & mobile).
- Seksi produk/varian dengan gambar, harga, rating (dummy).
- Seksi "Tentang Kami", "Kontak", dan "Lokasi" (dummy).
- Pengaturan meta dasar untuk SEO dan preview media sosial (Open Graph / Twitter Card).
- Struktur mudah diupdate secara manual (assets, teks, harga).
- Build scripts standar (lihat bagian Instalasi & Pengembangan).

---

## Teknologi
- Vue (utama) — frontend SPA atau SSG (tergantung konfigurasi repo).
- JavaScript
- HTML / CSS

> Komposisi bahasa repo: Vue ~90.7%, JavaScript ~6.6%, HTML ~2.7%

---

## Persyaratan
- Node.js (direkomendasikan LTS terbaru)
- npm atau yarn
- (Opsional) akun hosting untuk deployment: GitHub Pages / Netlify / Vercel / hosting lainnya

---

## Cara menjalankan (lokal)
1. Clone repo:
   - git clone https://github.com/HHHAAAANNNNN/MomsBakeryPage.git
2. Masuk ke folder repo:
   - cd MomsBakeryPage
3. Install dependency:
   - npm install
   - atau: yarn
4. Jalankan development server:
   - Jika menggunakan Vite: `npm run dev`
   - Jika menggunakan Vue CLI: `npm run serve`
   - Periksa `package.json` untuk skrip yang tersedia (contoh: `dev`, `serve`, `build`, `start`).

5. Build untuk produksi:
   - `npm run build` (atau `yarn build`)
   - Hasil build biasanya berada di folder `dist/` (atau sesuai konfigurasi).

---

## Struktur proyek (umum)
Catatan: struktur aktual bisa berbeda — periksa repo Anda.
- public/ — file statis (index.html, favicon, robots.txt)
- src/
  - assets/ — gambar & aset statis
  - components/ — komponen Vue
  - views/ atau pages/ — halaman / sections
  - router/ — pengaturan rute (jika SPA)
  - store/ — state management (Vuex / Pinia), jika ada
  - data/ atau store/products.* — tempat biasa menyimpan data produk dummy
- package.json — skrip & dependency

---

## Panduan memperbarui konten secara manual
Berikut langkah umum untuk mengganti data dummy dengan data final nanti:

1. Gambar / Logo
   - Ganti file di `src/assets/` (atau `public/`) dengan file gambar baru.
   - Perbarui path di komponen yang menampilkan gambar (contoh: `src/components/ProductCard.vue`).

2. Daftar produk (harga, nama, deskripsi, rating)
   - Cari file data produk (mis. `src/data/products.js`, `src/store/products.js`, atau langsung di `components`).
   - Contoh format data JSON sederhana:
     ```js
     export default [
       {
         id: 1,
         name: "Bolu Boling Original",
         price: 25000,
         rating: 4.5,
         image: "/assets/bolu-original.jpg",
         description: "Bolu lembut tradisional khas Probolinggo."
       },
       ...
     ];
     ```
   - Update nilai `price`, `rating`, `description` sesuai data dari manajer.

3. Kontak & Lokasi
   - Update `src/views/About.vue` atau file yang memuat alamat/kontak.
   - Sertakan link Google Maps (embed) untuk mempermudah pelanggan menemukan toko.

4. Meta tags & SEO
   - Perbarui `public/index.html` (atau `src/meta.js`) untuk:
     - title
     - meta description
     - open graph tags (`og:title`, `og:description`, `og:image`)
     - twitter card tags
   - Tambahkan JSON-LD (structured data) di head untuk LocalBusiness jika perlu:
     ```html
     <script type="application/ld+json">
     {
       "@context": "https://schema.org",
       "@type": "Bakery",
       "name": "BOLU BOLING PROBOLINGGO",
       "image": "https://example.com/assets/logo.jpg",
       "address": {
         "@type": "PostalAddress",
         "streetAddress": "Jl. Contoh No.1",
         "addressLocality": "Probolinggo",
         "addressRegion": "Jawa Timur",
         "postalCode": "672xx",
         "addressCountry": "ID"
       },
       "telephone": "+62-xxx-xxx-xxxx",
       "url": "https://your-deployed-site.example.com"
     }
     </script>
     ```

5. Bahasa & Konten
   - Pastikan semua teks yang muncul di UI diletakkan di satu tempat (mis. file `src/i18n`, `src/data/content.js` atau langsung dalam komponen) supaya mudah diubah.

---

## SEO & Marketing — rekomendasi singkat
Agar website membantu pemasaran online:
- Perbarui title dan meta description dengan kata kunci relevan (contoh: "Bolu Probolinggo", "Bolu Boling", "Kue Tradisional Probolinggo").
- Gunakan heading terstruktur (H1 untuk nama toko / tagline, H2 untuk kategori).
- Optimalkan gambar: kompres, gunakan atribut `alt`, dan set ukuran yang sesuai.
- Tambahkan Open Graph & Twitter Card untuk tampilan share yang baik di sosial media.
- Tambahkan sitemap.xml dan robots.txt.
- Daftarkan usaha ke Google Business Profile (sebagai langkah berikutnya) — sertakan link atau data kontak di website.
- Pantau performa SEO dasar dengan Google Search Console setelah deploy.

---

## Deployment — opsi cepat
- Netlify: hubungkan repo → automatic deploy pada push branch utama.
- Vercel: sangat cocok untuk proyek Vue + Vite.
- GitHub Pages: bisa dengan `gh-pages` jika SPA sederhana.
- Atau hosting tradisional: upload folder `dist/`.

Setelah deploy, pastikan:
- URL canonical dikonfigurasi (jika perlu).
- OG images punya absolute URL (https://domain/...).
- SSL/HTTPS aktif.

---

## Checklist untuk diskusi dengan manajer toko (untuk update konten final)
1. Logo resolusi tinggi (PNG / SVG)
2. Foto produk asli (untuk tiap varian) + penamaan file
3. Daftar produk lengkap: nama, SKU (opsional), harga jual, bahan utama, berat/ukuran
4. Deskripsi singkat & panjang untuk tiap produk
5. Jam operasional & hari buka
6. Kontak: nomor telepon, WhatsApp, e-mail
7. Alamat lengkap & Google Maps link
8. Rating / testimonial (jika mau tampilkan)
9. Metode pemesanan: telepon, WA, order online, antar (delivery)
10. Kebijakan pengembalian / refund (jika ada)

---

## Hal yang masih dummy / catatan
- Semua data produk (nama, harga, rating, gambar) sifatnya dummy.
- Jangan gunakan data dummy untuk promosi resmi; update setelah konfirmasi.
- Pastikan hak cipta dan izin foto sudah jelas sebelum publikasi.

---

## Kontribusi
Jika Anda ingin menambah fitur atau memperbaiki konten:
1. Buat branch baru dari `main`:
   - git checkout -b feat/ubah-konten
2. Commit perubahan
3. Buat pull request dan deskripsikan perubahan
Jika Anda bekerja sendiri, Anda bisa langsung commit ke branch utama lalu deploy.

---

## Lisensi
Lisensi default: MIT. (Sesuaikan jika organisasi punya ketentuan lain.)

---

## Kontak
Repositori ini dibuat untuk membantu digitalisasi BOLU BOLING PROBOLINGGO. Untuk update isi konten, silakan kumpulkan data dari manajer toko dan masukkan ke file-file yang disebutkan di atas. Setelah Anda siap, lakukan commit & push sehingga perubahan dapat dideploy.

---

Terima kasih — semoga iterasi pertama ini membantu BOLU BOLING PROBOLINGGO untuk mulai menjangkau pelanggan baru melalui dunia digital. Jika Anda mau, saya bisa bantu menyiapkan template email atau daftar pertanyaan untuk wawancara singkat dengan manajer toko yang bisa Anda gunakan untuk mengumpulkan data final.
