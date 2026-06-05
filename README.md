# Tenun for VS Code

Syntax highlighting untuk bahasa pemrograman [Tenun](https://github.com/TenunLang/Tenun) (`.tenun`) dan template Batik (`.batik`).

## Fitur

- Pewarnaan `.tenun`: keyword (`biar`, `fungsi`, `kalau`, `selama`, `untuk`, `kembali`, `impor`, ...), tipe (`bulat`, `desimal`, `teks`, `bool`, `peta`, `fungsi`, `dinamis`), konstanta (`benar`, `salah`, `kosong`), builtin (`cetak`, `layani`, `httpKirim`, ...), string + escape, angka, komentar `//`, operator.
- Pewarnaan `.batik`: `{{variabel}}`, seksi `{{#jika ...}}` / `{{#kecuali ...}}`, komentar `{{! ... }}`, di atas HTML.
- Auto-close kurung & kutip, komentar baris, indentasi.

## Pasang (dari sumber)

Salin folder ini ke direktori ekstensi VS Code:

```
# Windows
%USERPROFILE%\.vscode\extensions\tenun

# Linux / macOS
~/.vscode/extensions/tenun
```

Lalu muat ulang VS Code. Atau buat paket `.vsix`:

```
npm install -g @vscode/vsce
vsce package
code --install-extension tenun-0.1.0.vsix
```

## Contoh

```tenun
fungsi salam(nama: teks): teks {
    kembali "Halo, " + nama;
}

biar daftar: []teks = ["a", "b"];
untuk i dari 0 sampai panjang(daftar) {
    cetak(salam(daftar[i]));
}
```

## Lisensi

MIT.
