# Berkas — alpha

Alat PDF client-side (PWA). Semua proses jalan di browser, gak ada file yang diunggah ke server.

## Cara menggunakan
1. Akses via `https://ditolabs.github.io/berkas/`
2. Buka di HP → menu browser → "Add to Home Screen" / "Install app" biar keinstall kayak app
3. Bisa juga dibuka langsung dari browser laptop/tablet — tampilan otomatis nyesuaiin diri (mode desktop)

## Status alpha — sudah jalan
- Gabung PDF
- Pisah Halaman (rentang atau per-halaman, hasil .zip)
- Putar Halaman
- Tera Air (teks)
- Kompres (alpha: rapikan struktur file & buang metadata — efeknya kecil untuk PDF berisi gambar besar)
- JPG/PNG ke PDF
- PDF ke JPG (per halaman, hasil .zip)
- PDF ke Word (alpha: ekstrak teks polos aja, tabel/kolom/gambar belum ikut, .docx dibangun manual pakai JSZip — bukan library docx)
- Kunci PDF (alpha: password protection RC4 128-bit via `@pdfsmaller/pdf-encrypt-lite`, kebuka di reader PDF manapun)

## Tampilan & UX
- Filter kategori (Susun / Ubah Format / Keamanan) di beranda
- Responsive — grid tools & daftar file otomatis nyesuaiin di layar tablet/desktop, bukan cuma mobile
- Notifikasi toast otomatis muncul kalau ada versi baru ter-deploy, dengan tombol "Muat ulang"

## Bahasa
- UI mendukung Indonesia & Inggris, toggle di pojok kanan atas beranda. Preferensi disimpan di localStorage HP.

## Belum ada
- Kunci PDF versi lanjutan (permission granular: boleh print tapi gak boleh edit, dll — butuh engine enkripsi AES yang lebih berat, mis. QPDF via WASM)
- PDF ke Word dengan layout terjaga (tabel, kolom, gambar)

## Catatan teknis
- Library: pdf-lib (manipulasi PDF), pdf.js (render halaman ke gambar), JSZip (bundling hasil), @pdfsmaller/pdf-encrypt-lite (kunci PDF)
- Semua library dimuat dari CDN (cdnjs / esm.sh) — butuh koneksi internet saat pertama buka, setelah itu service worker cache app shell-nya
- Manifest PWA pakai icon terpisah untuk purpose "any" dan "maskable" biar installability check lebih konsisten di berbagai browser
- Ikon di /icons masih placeholder sederhana, ganti kalau udah ada desain final
