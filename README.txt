SOLARTRACK — MANAJEMEN SOLAR

Isi:
- index.html: tampilan aplikasi
- style.css: tema gelap responsif
- app.js: IndexedDB, pencatatan, laporan, backup/restore
- manifest.webmanifest + icon.svg: instalasi PWA dan ikon home screen
- sw.js: cache shell agar halaman dapat dibuka offline setelah kunjungan pertama

CARA PASANG DI GITHUB PAGES
1. Buat repository GitHub (Public jika memakai GitHub Free Pages).
2. Upload SELURUH isi folder ini ke root repository.
3. Settings > Pages > Deploy from a branch > main > /(root) > Save.
4. Tunggu publikasi, lalu buka URL GitHub Pages.
5. Chrome Android > menu ⋮ > Tambahkan ke layar utama / Instal aplikasi.

PENYIMPANAN DAN BACKUP
- Catatan utama disimpan di IndexedDB pada browser/perangkat ini.
- Aplikasi meminta persistent storage kepada browser. Persetujuan tidak dijamin.
- Snapshot lokal mingguan dibuat ketika aplikasi dibuka. Pengingat backup mingguan juga muncul saat aplikasi dibuka.
- Tombol Unduh backup membuat file JSON yang sebaiknya disimpan di Google Drive/perangkat lain.
- Pulihkan backup menerima file JSON SolarTrack.
- Migrasi otomatis mencoba membaca format localStorage lama: tanggal DD/MM/YYYY atau YYYY-MM-DD berisi array {unit,liter}.

PENTING TENTANG CACHE
Menghapus CACHE browser saja biasanya tidak menghapus IndexedDB. Namun memilih "Hapus data situs", "Clear storage/site data", menghapus data Chrome, atau uninstall/clear data browser dapat menghapus IndexedDB. Tidak ada aplikasi web yang bisa menjamin data tetap ada setelah pengguna menghapus seluruh data situs. Untuk keamanan, unduh backup JSON berkala dan simpan di lokasi lain.

PENGINGAT TERJADWAL
Browser web tidak dapat menjamin tugas backup berjalan di latar belakang saat aplikasi ditutup. Karena itu, snapshot dan pengingat mingguan diproses saat aplikasi dibuka. File backup eksternal harus diunduh dan disimpan oleh pengguna.

CATATAN
- PWA perlu HTTPS (GitHub Pages menyediakan HTTPS).
- Ikon SVG didukung oleh browser modern; jika browser tertentu menolak ikon SVG untuk instalasi, tambahkan PNG 192x192 dan 512x512.
- Google Fonts hanya digunakan untuk tampilan; aplikasi tetap menggunakan font fallback jika offline.
