# Changelog

## 0.1.1

- Sinkron dengan compiler: tambah keyword `henti`, `lanjut`, `coba`, `tangkap`, `cocok`.
- Tambah ~35 builtin baru (math: `eksp`/`ln`/`sin`/`cos`/`tan`/`tanh`/`lantai`/`langit`; OS/berkas: `infoOS`/`lingkungan`/`jalankan`/`daftarBerkas`/`buatDir`/...; util: `argumen`/`waktu`/`waktuMili`/`pangkas`/`keBesar`/`keKecil`/`tanggal`/konversi; uji: `tegas`/`tegasSama`/`tegasSamaBulat`).
- Urutkan varian `-Raw` sebelum nama dasar agar highlight benar (`sha256Raw` vs `sha256`).
- Tambah berkas LICENSE (MIT).

## 0.1.0

- Rilis awal: syntax highlighting `.tenun` (keyword, tipe, konstanta, builtin, string+escape, angka, komentar, operator) dan `.batik` (`{{variabel}}`, seksi `{{#jika}}`/`{{#kecuali}}`, komentar) di atas HTML.
- Konfigurasi bahasa: auto-close kurung/kutip, komentar baris, indentasi.
