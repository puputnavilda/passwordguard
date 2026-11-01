# PasswordGuard — Sistem Pemeriksaan Kekuatan Password Berbasis Web

## Isi project
- `index.html` — struktur halaman dan seluruh menu.
- `style.css` — desain responsif Dark Navy.
- `script.js` — autentikasi Supabase, checker, analyzer, generator, history, statistik, dan profil.

## Cara menjalankan
1. Ekstrak ZIP.
2. Buka folder `passwordguard` melalui VS Code.
3. Pasang extension **Live Server** jika belum ada.
4. Klik kanan `index.html` → **Open with Live Server**.

## Mengaktifkan Login/Register sungguhan dengan Supabase
Aplikasi ini sudah memiliki integrasi Supabase Auth. Agar login dan register benar-benar aktif:
1. Buat project di https://supabase.com/
2. Buka **Project Settings → API** (atau bagian API Keys pada dashboard).
3. Salin Project URL dan anon/public key.
4. Buka `script.js`, ganti:
   - `YOUR_SUPABASE_URL` dengan Project URL.
   - `YOUR_SUPABASE_ANON_KEY` dengan anon/public key.
5. Pada Supabase Authentication, atur URL Configuration / Site URL sesuai alamat Live Server atau domain deployment.
6. Untuk uji coba, atur Email provider sesuai kebutuhan. Jika Confirm email aktif, pengguna harus verifikasi email sebelum login.

Jangan pernah memasukkan `service_role` key ke kode frontend. Hanya gunakan anon/public key.

## Fitur
- Landing/login/register, lupa password (melalui email Supabase).
- Dashboard ringkasan dan grafik distribusi.
- Password Checker dengan skor edukatif 0–100 dan enam kriteria.
- Password Analyzer (jumlah karakter, variasi, pola sederhana).
- Password Generator memakai `crypto.getRandomValues()`.
- History & Statistics (hanya tanggal, skor, kategori; tidak menyimpan password).
- Security Tips.
- Profile & Settings.

## Catatan keamanan dan batasan
- Password yang dimasukkan ke Checker/Analyzer diproses di browser dan tidak dikirim ke Supabase.
- Jangan menguji password asli yang sedang dipakai pada akun penting; gunakan password contoh.
- Riwayat tersimpan di `localStorage` browser pada perangkat yang digunakan.
- Pemeriksaan pola umum masih sederhana, bukan pemeriksaan terhadap database kebocoran password dan bukan jaminan password tidak bisa diretas.
- Integrasi login memakai Supabase Auth; konfigurasi Supabase wajib dilakukan sebelum login/register dapat digunakan.
