# Cara Publish ke VS Code Marketplace

## 1. Buat publisher (sekali saja)

1. Buka https://marketplace.visualstudio.com/manage
2. Login dengan akun Microsoft.
3. "Create publisher". **Publisher ID** harus sama dengan field `"publisher"` di `package.json` (sekarang: `TenunLang`). Ganti salah satunya bila berbeda.

## 2. Ambil Personal Access Token (PAT)

1. Buka https://dev.azure.com (buat organisasi bila belum ada).
2. User settings (kanan atas) -> Personal Access Tokens -> New Token.
3. Organization: **All accessible organizations**.
4. Scopes: **Custom defined** -> **Marketplace** -> centang **Manage**.
5. Create -> salin token (tampil sekali).

## 3. Publish

```bash
npm install -g @vscode/vsce
cd tenun-vscode
vsce login TenunLang          # tempel PAT saat diminta
vsce publish                  # naikkan versi: vsce publish minor
```

Atau langsung:

```bash
vsce publish -p <PAT>
```

Ekstensi muncul di Marketplace beberapa menit kemudian.

## 4. (Opsional) Auto-publish via GitHub Actions

Workflow `.github/workflows/publish.yml` mem-publish saat push tag `v*`.

Tambahkan secret di repo (Settings -> Secrets -> Actions):
- `VSCE_PAT` = PAT Marketplace
- `OVSX_PAT` = token Open VSX (opsional, untuk VSCodium/Cursor; daftar di https://open-vsx.org)

Lalu:

```bash
git tag v0.1.0 && git push origin v0.1.0
```

## 5. (Opsional) Open VSX

Agar terpasang di VSCodium/Cursor:

```bash
npm install -g ovsx
ovsx publish -p <OVSX_PAT>
```

## Uji lokal sebelum publish

```bash
vsce package                  # hasilkan tenun-0.1.0.vsix
code --install-extension tenun-0.1.0.vsix
```
