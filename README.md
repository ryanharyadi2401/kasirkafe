# Kasir Kedai Kopi: Panduan Membuat APK

Ada dua cara. Cara A tidak perlu memasang apa pun di komputer.

## Cara A: Build otomatis lewat GitHub (disarankan)
1. Buat akun di github.com, lalu buat repository baru (boleh private).
2. Klik "Add file" > "Upload files", lalu unggah SEMUA isi folder ini
   (www, .github, package.json, capacitor.config.json, .gitignore).
   - Folder `.github` kadang tersembunyi. Di Mac tekan Cmd+Shift+. di Finder.
   - Jika `.github` tidak ikut terunggah: "Add file" > "Create new file", ketik nama
     `.github/workflows/build-apk.yml`, lalu tempel isi file build-apk.yml dari zip ini.
3. Buka tab "Actions". Pilih "Build APK", lalu "Run workflow". Tunggu sekitar 5 sampai 10 menit.
4. Buka hasil build yang sudah hijau, lalu unduh "kasir-apk" di bagian Artifacts.
5. Ekstrak zip-nya. Di dalamnya ada `app-debug.apk`.
6. Kirim APK ke HP kasir (WhatsApp, kabel, atau Google Drive), buka file, lalu izinkan
   "Instal dari sumber tidak dikenal" jika diminta.

## Cara B: Di komputer sendiri
Syarat: Node.js 20, JDK 17, Android Studio.
    npm install
    npx cap add android
    npx cap sync android
    npx cap open android
Di Android Studio: Build > Build APK(s).

## Catatan
- APK ini adalah versi debug: cukup untuk dipasang di HP kasir, tetapi belum untuk Play Store.
  Untuk Play Store dibutuhkan build release yang ditandatangani (AAB).
- Data (akun, produk, transaksi) tersimpan di tiap HP, tidak tersinkron antar HP.
- Untuk mengubah nama aplikasi atau ID paket, edit capacitor.config.json.
