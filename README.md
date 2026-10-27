# Livewire Shop Demo

Demo toko berbasis Laravel 7 dan Livewire 1 untuk produk, keranjang, serta checkout Midtrans.

## Yang tersedia

- Komponen Livewire untuk menambah, melihat, dan memperbarui produk.
- Keranjang berbasis helper/facade dan ringkasan belanja.
- Form checkout yang meminta token Snap Midtrans.

## Menjalankan demo

Laravel v7.15.0, PHP ^7.2.5, Composer, serta MySQL/MariaDB. Aset frontend memakai perintah pada package.json. Dependency Composer dan Node tidak disertakan.

1. Pakai versi PHP yang memenuhi composer.json dan lockfile. Aktifkan ekstensi PDO MySQL, mbstring, OpenSSL, tokenizer, XML, ctype, dan fileinfo.
2. Salin .env.example menjadi .env bila belum ada, lalu isi koneksi database sendiri. Jangan commit .env.
3. Jalankan `composer install`, lalu `php artisan key:generate`.
4. Buat database demo kosong, lalu jalankan `php artisan migrate`. Baca isi seeder sebelum menjalankan `php artisan db:seed`.
5. Untuk aset yang berasal dari source, jalankan `npm install` dan script development/production atau build yang tersedia pada package.json. Toolchain Node legacy belum diuji ulang.
6. Jalankan `php artisan serve` dan buka alamat yang dicetak terminal.

Isi MIDTRANS_SERVERKEY dan MIDTRANS_CLIENTKEY milik sandbox sendiri. Biarkan MIDTRANS_IS_PRODUCTION=false untuk latihan.

## Struktur yang perlu dibaca

`app/` menyimpan controller/model atau komponen Livewire, `routes/` memetakan URL, `resources/views/` menyimpan Blade, `database/migrations/` berisi skema, dan `public/` adalah web root. `tests/` yang tersedia sebagian besar masih contoh bawaan framework.

## Batas implementasi

- Checkout memerlukan akun sandbox dan kunci Midtrans sendiri. Tidak ada transaksi pembayaran yang dijalankan saat persiapan publikasi.
- Laravel 7.15.0, Livewire 1.2.0, dan Laravel Mix 5 merupakan toolchain legacy; kompatibilitas pemasangan saat ini belum diverifikasi.
- Route admin produk memakai autentikasi, tetapi tidak terlihat pemisahan peran admin khusus. Jangan menganggap semua kontrol otorisasi telah lengkap.
- Sumber lokal bernama wireshop-master tidak memiliki metadata Git untuk memastikan URL upstream. Lisensi framework pada composer.json tidak otomatis menetapkan lisensi seluruh proyek atau aset.

## Pemeriksaan publikasi

- PHP lint: 74/74 berkas PHP non-Blade lolos menggunakan PHP 8.1.12.
- Salinan publik tidak menyertakan .env aktual, dependency Composer/Node, log, database dump, arsip, sesi, atau unggahan lokal.
- Tes framework, koneksi database, pengoperasian UI, build aset, dan API eksternal belum dijalankan pada salinan ini. Lint hanya memeriksa sintaks; tidak membuktikan seluruh fitur berfungsi.

## Asal source dan lisensi

Disiapkan dari salinan lokal livewire-shop-demo/wireshop-master. Tidak ada URL upstream yang dipastikan dari metadata Git untuk proyek ini. Jangan menganggap lisensi framework atau aset otomatis melisensikan seluruh kode proyek.

Aset UI statis yang dirujuk aplikasi tetap disertakan beserta lisensi yang tersedia. Konten merek dan gambar mengikuti hak pemilik aslinya. Perubahan untuk publikasi ini meliputi dokumentasi, pemisahan konfigurasi lokal, skema demo bila diperlukan, dan koreksi terbatas yang dicatat pada persiapan proyek.
