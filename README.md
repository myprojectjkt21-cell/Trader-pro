# Institutional Trader Pro v10.3 — PWA

Multi-Asset Intelligence Terminal: SMC Konsep, Elliott Wave, Fibonacci, Struktur Market Generik, Risk Engine & News Guard.

## Fitur v10.3
- **Model Strategi Pilih:** Generik, SMC, Elliott, Fibonacci, Combo (Panel 1)
- **SMC:** BOS / CHoCH, Order Block, FVG, Liquidity Sweep, Premium/Discount
- **SMC v10.3 Baru - Kill Zone WIB:** Asia 07:00-10:00 WIB, London 14:00-17:00 WIB, New York 19:00-22:00 WIB, London Close 22:00-00:00 WIB. Badge di header update tiap 30 detik, skor SMC naik kalau sedang di Kill Zone.
- **Elliott Wave:** Wave count 1-5 + A-B-C, validasi Wave 2/3/4, Fibonacci Wave
- **Elliott v10.3 Baru - Fibonacci Time Zone:** Proyeksi waktu reversal dari panjang Wave 1 x Fibonacci 1,2,3,5,8,13,21,34,55. Ditampilkan di Panel 2B Elliott dengan status Sudah lewat / Mendatang / DEKAT - Waspada Reversal.
- **Fibonacci:** Retracement + Extension, Golden Zone 50%-61.8%
- **PWA Full:** Install di Android / iOS / PC, offline shell, caching

## File dalam repo ini
```
index.html              -> Aplikasi utama (v10.3)
manifest.webmanifest    -> Manifest PWA
sw.js                   -> Service Worker (cache v10.3)
icon-192.png            -> Ikon 192x192
icon-512.png            -> Ikon 512x512 (maskable)
.nojekyll               -> Agar GitHub Pages tidak memproses Jekyll
```

## Cara Upload ke GitHub + Aktifkan GitHub Pages

### Opsi A - Via Web GitHub (paling cepat, tanpa terminal)
1. Buka github.com > New repository
   - Nama contoh: `trader-pro` (bebas)
   - Pilih Public
   - Jangan centang Add README (karena kita sudah punya file)
   - Create repository
2. Di halaman repo baru, klik **uploading an existing file** atau **Add file > Upload files**
3. Drag & drop SEMUA file dari folder ini: `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `.nojekyll`, `README.md`
   - Penting: `.nojekyll` kadang tersembunyi di file explorer. Kalau tidak ikut ter-upload, buat manual di GitHub: Add file > Create new file > nama `.nojekyll` > kosongkan isi > Commit.
4. Klik **Commit changes**
5. Aktifkan Pages: **Settings > Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / Folder: **/ (root)**
   - Save
6. Tunggu 1-2 menit. Link akan muncul di atas: `https://username.github.io/trader-pro/`
7. Buka link itu di HP / PC. Untuk install:
   - **Android Chrome:** Menu titik tiga > Install app / Add to Home screen
   - **iOS Safari:** Share > Add to Home Screen
   - **PC Chrome/Edge:** Ikon Install di address bar

### Opsi B - Via Git (kalau sudah pakai terminal)
```bash
git init
git add .
git commit -m "v10.3 PWA"
git branch -M main
git remote add origin https://github.com/username/trader-pro.git
git push -u origin main
```
Lalu aktifkan Pages seperti langkah 5 di atas.

## Cara Update Versi Berikutnya
1. Ganti `index.html` dengan versi baru.
2. Di `sw.js`, naikkan `CACHE_NAME` misal `itp-v10-4` agar HP pengunjung tidak pakai cache lama.
3. Commit + push. Pengunjung perlu tutup dan buka ulang app 1x untuk dapat versi baru.

## Catatan Penting
- API Key Twelve Data disimpan di LocalStorage browser, tidak ikut ter-upload ke GitHub.
- Data IDX pakai Stooq Daily gratis + fallback Paste CSV.
- Tool ini bukan nasihat keuangan. Confluence Score bukan probabilitas profit.

## Cek PWA sudah benar
- Buka DevTools > Application > Manifest: harus muncul nama, ikon, start_url.
- DevTools > Application > Service Workers: harus Active.
- Lighthouse > PWA: skor installable harus lolos.
