# Physical View — CineTix

## Infrastruktur & Deployment

```
[Browser / Mobile App]   (Client)
          |
          | HTTPS
          v
   [Load Balancer]
          |
   -------------------
   |                 |
[Web Server 1]   [Web Server 2]   (Application Server - menjalankan business logic)
   |                 |
   -------------------
          |
          v
   [Database Server]   (menyimpan data film, jadwal, pengguna, transaksi)
          |
          v
   [Backup Server]   (replikasi data secara periodik)

Layanan Eksternal:
- [Payment Gateway API]                — diakses Application Server untuk pembayaran.
- [Email / Push Notification Service]  — mengirim e-tiket & pengingat jadwal.
- [CDN]                                 — menyimpan aset statis (poster film, ikon).
```

**Penjelasan:**

- **Client** mengakses sistem melalui browser atau aplikasi mobile via koneksi HTTPS.
- **Load Balancer** membagi traffic ke beberapa **Web/Application Server** agar sistem
  tetap responsif saat banyak pengguna mengakses secara bersamaan.
- **Database Server** menyimpan seluruh data transaksional, dengan **Backup Server**
  untuk mencegah kehilangan data.
- Sistem terintegrasi dengan **Payment Gateway** pihak ketiga untuk proses pembayaran,
  serta layanan **notifikasi** untuk mengirim e-tiket.
- **CDN** digunakan untuk mempercepat pengiriman aset statis seperti poster film ke
  pengguna di berbagai lokasi.
