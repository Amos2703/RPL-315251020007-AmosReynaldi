# Maintenance Plan — CineTix (Aplikasi Pemesanan Tiket Bioskop)

Dokumen ini berisi rencana pemeliharaan perangkat lunak untuk sistem **CineTix**,
diklasifikasikan ke dalam 4 kategori: Corrective, Adaptive, Perfective, dan Preventive.

## Corrective

1. Memperbaiki bug status kursi yang masih tertampil "tersedia" padahal sudah dipesan
   pengguna lain akibat race condition saat dua orang checkout bersamaan.
2. Memperbaiki kesalahan perhitungan total harga ketika pengguna menggunakan kode
   voucher diskon.
3. Memperbaiki notifikasi e-tiket yang tidak terkirim ke email setelah pembayaran berhasil.

## Adaptive

4. Menyesuaikan integrasi API payment gateway karena penyedia mengubah versi endpoint
   pembayaran.
5. Menyesuaikan sistem terhadap kebijakan baru pembatasan kapasitas studio (misalnya
   regulasi protokol kesehatan dari bioskop).
6. Memperbarui SDK aplikasi mobile agar tetap kompatibel dengan versi terbaru Android/iOS.

## Perfective

7. Menambahkan fitur rekomendasi film berdasarkan riwayat pemesanan pengguna.
8. Mempercepat waktu loading halaman pemilihan kursi dengan optimasi query database.
9. Menambahkan fitur filter pencarian film berdasarkan genre dan jam tayang.

## Preventive

10. Melakukan refactoring pada modul booking untuk mengurangi duplikasi kode antara
    proses pemesanan tiket reguler dan tiket promo.
11. Memperbarui dokumentasi API internal agar tim pengembang baru lebih mudah onboarding.
12. Menambahkan automated testing pada modul pembayaran untuk mendeteksi bug lebih awal
    sebelum rilis ke production.
