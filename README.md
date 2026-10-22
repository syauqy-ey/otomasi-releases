# Automation

Otomasi berganti nama menjadi **Automation** mulai versi 2.2.2. Data, pengaturan, dan jalur pembaruan tetap digunakan.

Aplikasi jaringan untuk Windows x86_64 dan Mac Apple Silicon. Unduh versi terbaru dari [halaman Releases](https://github.com/syauqy-ey/otomasi-releases/releases/latest).

## Windows

Unduh ZIP Windows, ekstrak seluruh isinya, lalu buka `Otomasi/Otomasi.exe`. Simpan folder `_internal` bersama executable. Instalasi Windows yang dikelola pada komputer utama berada di drive D.

## Mac Apple Silicon

Unduh ZIP Mac, ekstrak `Otomasi.app`, lalu pindahkan ke `~/Applications` dan buka dari Finder. Paket dibangun dan diuji pada macOS 15 arm64. Nama tampilan aplikasi adalah Automation; nama berkas internal `Otomasi.app` dipertahankan agar versi sebelumnya bisa memperbarui aplikasi. Pindahkan aplikasi menggunakan Finder setelah aplikasi ditutup, lalu buka salinan di `~/Applications` untuk menghindari lokasi sementara yang hanya bisa dibaca. Python tidak diperlukan untuk menjalankan aplikasi yang sudah dikemas.

Paket Mac belum ditandatangani dengan Apple Developer ID atau dinotariskan. Jika macOS meminta verifikasi saat pertama dibuka, ikuti [panduan resmi Apple](https://support.apple.com/en-au/102445) untuk aplikasi yang Anda percaya.

## Cek PTP berdasarkan Activity Type

Mulai versi 2.3.0, gunakan satu menu **Cek PTP 5G + BC**. Pilih `dataptp.xlsx` dengan kolom **Activity Type**:

- `PTP 5G Clock` memakai aturan pemeriksaan 5G.
- `PTP BC Enablement` memakai aturan pemeriksaan BC.

Klik **Periksa Input** untuk melihat jumlah masing-masing jenis, lalu **Tes SSH** dan jalankan pemeriksaan. Activity Type kosong atau tidak dikenal dilaporkan bersama nomor baris sebelum koneksi dimulai. Hasil hanya `ptp_result.xlsx` langsung di folder pilihan, mengikuti urutan input dan menyertakan Activity Type pada kolom V. Generator BC dan 5G tetap terpisah.

## Pembaruan

Aplikasi memeriksa rilis baru dan menyediakan tombol **Cek pembaruan** / **Update**. Satu rilis memuat paket Windows dan Mac dari revisi source yang sama. Aplikasi memilih paket yang sesuai dan memeriksa tanda tangan, ukuran, serta checksum sebelum memasang. Mulai versi 2.2.1, unduhan yang sudah siap membiarkan aplikasi tetap terbuka dan bisa digunakan. Selesaikan pekerjaan lalu tutup Automation sendiri untuk memasang update. Setelah pemasangan berhasil atau versi lama dipulihkan, aplikasi tetap tertutup sampai Anda membukanya sendiri.

Untuk beralih dari versi 2.2.0 tanpa penutupan/pembukaan otomatis oleh updater lama, unduh paket terbaru secara manual, tutup Automation sendiri, lalu ganti aplikasinya. Di Mac, ganti `Otomasi.app` di `~/Applications`; input dan pengaturan tetap berada di folder terpisah.

Input, folder hasil, pengaturan, dan koneksi VPN tetap dipilih pada masing-masing komputer. Siapkan VPN sebelum pemeriksaan SSH.

Repository ini hanya berisi unduhan publik dan manifest pembaruan. Source aplikasi disimpan dalam repository private yang terpisah.

Versi 2.3.1 memakai menu Generate BC Enablement, Generate 5G Clock, dan Generate ServisProv serta logo A emas untuk Automation di Windows dan Mac.

Versi 2.3.2 memperbaiki pembacaan lampiran log lengkap pada Generate BC Enablement dan Generate 5G Clock. File HOSTNAME_IP yang cocok langsung digunakan bila log hostname khusus tidak tersedia atau kosong. Hasil Log PTP tidak perlu digandakan atau diganti namanya; log IP lain tidak dipakai.
