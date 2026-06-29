# Logical View — CineTix

## Komponen/Modul Utama

1. **Auth Module** — menangani registrasi, login, dan manajemen sesi pengguna
   (pelanggan & admin).
2. **Movie & Schedule Module** — menyimpan dan menampilkan data film, jadwal tayang,
   dan studio.
3. **Booking & Seat Module** — menangani pemilihan kursi, validasi ketersediaan, dan
   penguncian kursi sementara selama proses checkout.
4. **Payment Module** — memproses pembayaran melalui integrasi dengan payment gateway
   pihak ketiga.
5. **Ticket & Notification Module** — menerbitkan e-tiket (QR code) dan mengirim
   notifikasi (email/push notification).
6. **Admin Module** — mengelola data film, jadwal, harga tiket, dan laporan penjualan.

## Hubungan Antarmodul (Diagram Teks)

```
[Pelanggan]
    |
    v
[Auth Module] --> [Movie & Schedule Module]
    |                     |
    v                     v
[Booking & Seat Module] <-+
    |
    v
[Payment Module] --> (Payment Gateway pihak ketiga)
    |
    v
[Ticket & Notification Module] --> Email / Push Notification

[Admin] --> [Admin Module] --> [Movie & Schedule Module]
```

**Penjelasan alur:**

- Pelanggan login melalui Auth Module, lalu melihat daftar film dari
  Movie & Schedule Module.
- Setelah memilih film & jadwal, pelanggan diarahkan ke Booking & Seat Module untuk
  memilih kursi.
- Setelah kursi dipilih, Payment Module memproses transaksi melalui payment gateway
  eksternal.
- Setelah pembayaran berhasil, Ticket & Notification Module menerbitkan e-tiket dan
  mengirim notifikasi.
- Admin mengelola data film/jadwal melalui Admin Module yang terhubung langsung ke
  Movie & Schedule Module.
