# 🚀 Panduan Deployment ke GitHub Pages

## 📋 Persiapan

Pastikan project Anda sudah di-push ke GitHub repository `Web-Porto`.

## 🔧 Metode 1: Automatic Deployment (Recommended)

### Langkah-langkah:

1. **Push semua perubahan ke GitHub:**
   ```bash
   git add .
   git commit -m "Setup GitHub Pages deployment"
   git push origin master
   ```

2. **Aktifkan GitHub Pages:**
   - Buka repository `Web-Porto` di GitHub
   - Masuk ke **Settings** > **Pages**
   - Di bagian **Source**, pilih **GitHub Actions**
   - GitHub Actions workflow akan otomatis berjalan setiap kali ada push ke branch master

3. **Website akan tersedia di:**
   ```
   https://hilmanfqr.github.io/Web-Porto/
   ```

## 🔧 Metode 2: Manual Deployment

### Langkah-langkah:

1. **Jalankan script deployment:**
   ```bash
   npm run deploy
   ```

2. **Atau jalankan manual:**
   ```bash
   npm run build
   cd dist
   git init
   git add -A
   git commit -m 'deploy'
   git push -f git@github.com:hilmanfqr/Web-Porto.git main:gh-pages
   ```

3. **Aktifkan GitHub Pages:**
   - Buka repository di GitHub
   - Masuk ke **Settings** > **Pages**
   - Di bagian **Source**, pilih **Deploy from a branch**
   - Pilih branch **gh-pages** dan folder **/ (root)**

## ✅ Verifikasi Deployment

1. Cek di tab **Actions** repository untuk melihat status deployment
2. Setelah berhasil, website akan tersedia di: `https://hilmanfqr.github.io/Web-Porto/`
3. Perubahan biasanya butuh 5-10 menit untuk terlihat

## 🔄 Update Website

Setiap kali Anda push perubahan ke branch master, website akan otomatis ter-update (jika menggunakan GitHub Actions).

## 🛠️ Troubleshooting

### Jika ada error dengan gambar:
- Pastikan semua file gambar ada di folder `src/assets/thumbnails/`
- File yang dibutuhkan: `tokokita.png`, `cms.png`, `porto.png`, `budget.png`

### Jika website tidak muncul:
1. Cek tab Actions untuk error
2. Pastikan GitHub Pages sudah diaktifkan
3. Tunggu 5-10 menit setelah deployment

### Custom Domain (Opsional):
Jika ingin menggunakan domain sendiri, edit file `.github/workflows/deploy.yml` dan tambahkan domain di bagian `cname`.

## 📝 Catatan Penting

- Website akan tersedia di: `https://hilmanfqr.github.io/Web-Porto/`
- Setiap push ke master akan trigger auto-deployment
- Pastikan semua asset (gambar, dll) sudah ter-commit ke repository
