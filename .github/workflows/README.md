# Productivity Hub — aplikasi Android (WebView)

Proyek Android siap-bangun yang membungkus aplikasi web menjadi APK: ikon sendiri di layar HP, layar penuh, tarik-ke-bawah untuk muat ulang, tombol kembali mengikuti riwayat halaman, unduhan PDF/Excel lewat Download Manager, dan penyimpanan (PIN & koneksi) tetap tersimpan.

Alamat yang dibuka diatur di `app/src/main/res/values/strings.xml` → `app_url`. Bawaannya URL `/exec`. **Disarankan** diganti ke alamat GitHub Pages Ustadz agar penyimpanan browser lebih stabil dan bisa jalan sebagai PWA.

## Cara paling mudah: bangun APK lewat GitHub (tanpa instal apa pun)
1. Buat repository baru, mis. `productivity-hub-android`.
2. Upload **seluruh isi folder `android/`** ke root repository, termasuk folder tersembunyi `.github/`.
3. Buka tab **Actions** → jalankan workflow **Build APK** (otomatis jalan setiap push ke `main`).
4. Setelah selesai (±5 menit), buka hasil build → **Artifacts** → unduh `ProductivityHub-apk` → di dalamnya ada `app-debug.apk`.
5. Kirim APK ke HP, buka, izinkan **Install dari sumber tidak dikenal**, lalu pasang.

## Alternatif: Android Studio
`File → Open` folder `android/` → tunggu Gradle sync → **Build → Build Bundle(s)/APK(s) → Build APK(s)**.
Hasil: `app/build/outputs/apk/debug/app-debug.apk`.

## Alternatif tanpa koding: PWABuilder
Buka <https://www.pwabuilder.com>, masukkan alamat GitHub Pages Ustadz, pilih **Android → Generate package**. APK/AAB dibuat otomatis dari manifest PWA yang sudah disertakan.

## Catatan
- APK ini ditandatangani dengan kunci debug: cukup untuk dipakai sendiri/dibagikan langsung, tetapi tidak untuk diunggah ke Play Store. Untuk Play Store, buat keystore sendiri dan isi `signingConfigs`.
- Aplikasi butuh internet. Data tetap di Google Sheets; APK hanya pembungkus tampilan.
