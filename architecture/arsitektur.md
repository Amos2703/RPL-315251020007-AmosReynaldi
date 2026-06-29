# Gaya Arsitektur — CineTix

## Pola yang Digunakan

CineTix menggunakan kombinasi **Client-Server Architecture** dengan struktur internal
**Layered Architecture (3-tier)** pada sisi server, yang terdiri dari:

1. **Presentation Layer** — antarmuka pengguna (web/mobile app) yang menampilkan
   daftar film, jadwal tayang, dan seat map.
2. **Business Logic Layer** — menangani aturan bisnis seperti validasi ketersediaan
   kursi, perhitungan harga, dan proses pemesanan.
3. **Data Access Layer** — mengelola penyimpanan dan pengambilan data dari database
   (data film, jadwal, transaksi, dan pengguna).

## Alasan Pemilihan

- **Client-Server** dipilih karena sistem perlu diakses oleh banyak pengguna secara
  bersamaan dari berbagai device (web maupun mobile), sementara data dan logika bisnis
  dikelola terpusat di server agar tetap konsisten.
- **Layered Architecture** dipilih karena memisahkan tanggung jawab antar lapisan,
  sehingga memudahkan pengembangan, pengujian, dan pemeliharaan secara independen.
  Misalnya, perubahan pada tampilan tidak akan memengaruhi logika perhitungan harga,
  dan sebaliknya.
- Arsitektur ini relatif sederhana untuk diimplementasikan dan dipahami oleh tim kecil,
  dibandingkan microservices yang lebih kompleks namun belum diperlukan pada skala
  aplikasi ini.
