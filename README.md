# Berkas — alpha

Alat PDF client-side (PWA). Semua proses jalan di browser, gak ada file yang diunggah ke server.

## Cara deploy (pola sama kayak project ditolabs lainnya)
1. Push folder ini ke repo baru, mis. `ditolabs/berkas`
2. Aktifkan GitHub Pages (branch `main`, root) — atau connect ke Cloudflare Pages
3. Akses via `https://ditolabs.github.io/berkas/`
4. Buka di HP → menu browser → "Add to Home Screen" biar keinstall kayak app

## Status alpha — sudah jalan
- Gabung PDF
- Pisah Halaman (rentang atau per-halaman, hasil .zip)
- Putar Halaman
- Tera Air (teks)
- JPG/PNG ke PDF
- PDF ke JPG (per halaman, hasil .zip)
- PDF ke Word (alpha: ekstrak teks polos aja, tabel/kolom/gambar belum ikut, .docx dibangun manual pakai JSZip — bukan library docx)

## Belum ada (placeholder "segera" di UI)
- Kompres
- Kunci / Buka Kunci PDF (butuh library enkripsi tambahan)

## Catatan teknis
- Library: pdf-lib (manipulasi), pdf.js (render halaman ke gambar), JSZip (bundling hasil)
- Semua library dimuat dari CDN (cdnjs) — butuh koneksi internet saat pertama buka, setelah itu service worker cache app shell-nya
- Ikon di /icons masih placeholder sederhana, ganti kalau udah ada desain final
