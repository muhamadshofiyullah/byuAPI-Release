# 📌 Panduan Penggunaan byuAPI (v1.1.0)

Dokumen ini berisi panduan praktis dan mudah dipahami untuk menjalankan serta mengelola aplikasi **byuAPI**.

---

## 💡 Apa itu byuAPI?

**byuAPI** adalah aplikasi perantara (backend service) yang digunakan untuk memproses transaksi paket data, pulsa, topping, dan cek nomor secara otomatis. Aplikasi ini dirilis dalam bentuk file executable standalone (`byuapi_release.exe`) yang siap dijalankan di sistem operasi Windows tanpa perlu mengunduh atau mengkonfigurasi Node.js secara manual. Aplikasi ini juga dilengkapi dengan sistem pengantrean transaksi, serta penyimpanan riwayat transaksi ke database SQLite.

---

## 📋 Langkah-Langkah Penggunaan

### 1. Persiapan Awal
Pastikan Anda sudah mengekstrak file rilis dan meletakkan file **`byuapi_release.exe`** di dalam folder yang sama dengan file konfigurasi `.env`.

### 2. Pengaturan File `.env`
Buat atau edit file bernama `.env` di dalam folder yang sama dengan `byuapi_release.exe` dan isi dengan pengaturan berikut:

```ini
PORT=4001
DEV=false
MSISDN=085851234567
WHITELIST_IPS=127.0.0.1,::1
CALLBACK_URL=http://127.0.0.1:8889/host
TIMEOUT=120
```

* **PORT**: Port tempat aplikasi berjalan (default: `4001`).
* **WHITELIST_IPS**: Daftar alamat IP yang diizinkan mengakses aplikasi.
* **CALLBACK_URL**: Alamat URL server Anda yang akan menerima laporan hasil transaksi (SUKSES / GAGAL).

---

## 🚀 Cara Jalankan Aplikasi

Cukup klik dua kali pada file **`byuapi_release.exe`**, atau jalankan melalui Command Prompt / PowerShell:
```cmd
byuapi_release.exe
```

---

## 📊 Cara Melihat Dashboard Transaksi

Setelah aplikasi berjalan, Anda bisa membuka browser dan mengetik alamat:
👉 **`http://localhost:4001`**

Di dashboard ini Anda bisa melihat:
- Tabel riwayat transaksi pulsa, paket data, dan topping.
- Filter berdasarkan tanggal (mulai dan selesai).
- Status transaksi (SUKSES, PENDING, GAGAL, TIMEOUT) beserta Kode SN / QR string payment.

---
