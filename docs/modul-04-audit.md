# Audit Modul 4 - Flexbox, Grid, dan Responsive Desig
## Hasil uji viewport
| Viewport | Gejala awal | Penyebab | Perbaikan | Hasil uji ulang |
|---|---|---|---|---|
| 360 px | Navigasi/layout mengalami horizontal scroll | Elemen melebihi lebar layar mobile | Menambahkan `flex-wrap: wrap` dan `max-width: 100%` pada media | Tampilan menjadi 1 kolom rapi tanpa horizontal scroll |
| 768 px | Layout hero dan form masih bertumpuk vertikal | Media query belum aktif di ukuran layar sedang | Menambahkan media query `(min-width: 48rem)` untuk flex-direction row dan form grid 2 kolom | Hero dan form berubah menjadi 2 kolom dengan seimbang |
| 1280 px | Jumlah kolom katalog terbatas atau terlalu renggang | Pengaturan grid belum otomatis mengikuti lebar layar | Menggunakan `grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr))` | Katalog mengisi ruang layar dengan jumlah kolom yang menyesuaikan otomatis |
## Audit overflow
- **Elemen yang menyebabkan overflow:** Gambar/elemen media dan judul panjang pada kartu
- **Bukti dari DevTools:** Timbul scrollbar horizontal di bagian bawah viewport 360 px
- **Aturan penyebab:** Ukuran elemen fixed/belum diatur sifat responsifnya
- **Perbaikan:** Menambahkan `max-width: 100%` & `height: auto` pada elemen `img, svg, video`
- **Hasil uji ulang:** Tidak ada overflow horizontal di seluruh ukuran viewport (360px, 768px, 1280px)