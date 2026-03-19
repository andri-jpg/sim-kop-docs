# Koperasi Produsen CU. Tuandibangarna Sejahtera Bersama - Panduan Penggunaan

# Buku Panduan Pengguna SIM-KOP
**(Sistem Informasi Manajemen Koperasi)**

---

## 📋 Daftar Isi

1. [Pendahuluan](#1-pendahuluan)
2. [Persiapan Awal](#2-persiapan-awal)
3. [Dashboard](#3-dashboard)
4. [Manajemen Anggota](#4-manajemen-anggota)
5. [Simpanan (Tabungan & Deposito)](#5-simpanan)
6. [Pinjaman (Kredit)](#6-pinjaman)
7. [Akuntansi & Keuangan](#7-akuntansi--keuangan)
8. [Laporan](#8-laporan)
9. [Pengaturan Sistem](#9-pengaturan-sistem)

---

## 1. Pendahuluan

SIM-KOP adalah aplikasi desktop untuk mengelola operasional koperasi simpan pinjam, mulai dari pendaftaran anggota, transaksi simpanan, pengelolaan pinjaman, hingga pelaporan keuangan dan akuntansi otomatis.

### Fitur Utama
- **Multi-User**: Mendukung login Admin, Teller, Manager (Coming Soon).
- **Real-time Accounting**: Jurnal otomatis terbentuk saat transaksi terjadi.
- **Offline First**: Data tersimpan lokal, tidak butuh internet terus-menerus.
- **Laporan Lengkap**: Neraca, Laba Rugi, Buku Besar, Kartu Piutang.

---

## 2. Persiapan Awal

### Login
Gunakan akun yang telah didaftarkan.
- **Default Super Admin**:
  - Username: `admin`
  - Password: `admin123`

> ⚠️ **PENTING**: Segera ganti password default setelah login pertama demi keamanan data.

### Navigasi
Menu utama (Sidebar) di sebelah kiri layar digunakan untuk mengakses seluruh fitur aplikasi.

---

## 3. Dashboard
Halaman utama menampilkan ringkasan performa koperasi secara real-time:

- **Kartu Ringkasan**:
  - **Total Aset**: Jumlah seluruh aset (Kas + Bank + Piutang + Inventaris).
  - **Saldo Simpanan**: Total dana anggota yang dihimpun (Wajib, Pokok, Sukarela, Deposito).
  - **Piutang Beredar**: Total pokok pinjaman yang belum lunas.
  - **Anggota Aktif**: Jumlah anggota yang berstatus `ACTIVE`.

- **Grafik**:
  - **Pertumbuhan Aset**: Tren kenaikan aset per bulan.
  - **Komposisi Simpanan**: Pie chart perbandingan jenis simpanan.

---

## 4. Manajemen Anggota
Menu: **Anggota**

### Menambah Anggota Baru
1. Klik tombol **+ Tambah Anggota** di pojok kanan atas.
2. Isi formulir pendaftaran:
   - **Nama Lengkap**: Sesuai KTP.
   - **Kelompok**: (Opsional) Pilih kelompok untuk memudahkan penagihan kolektif.
   - **Data Pribadi**: NIK, Alamat, No HP, Pekerjaan, Nama Ibu Kandung.
3. Klik **Simpan**.

### Status Anggota
- **PENDING**: Baru mendaftar, belum melunasi Simpanan Pokok.
- **ACTIVE**: Anggota sah, sudah lunas Simpanan Pokok & Wajib awal.
- **INACTIVE**: Anggota keluar/dinonaktifkan.

### Profil Anggota
Klik pada nama anggota di tabel untuk masuk ke halaman **Profil Anggota**.
Di sini Anda bisa melihat:
- **Ringkasan**: Saldo simpanan, sisa pinjaman, riwayat aktivitas.
- **Rekening**: Daftar akun simpanan (SP, SW, SR, Deposito).
- **Pinjaman**: Daftar kontrak pinjaman aktif dan lunas.
- **Buku Tabungan**: Cetak riwayat transaksi simpanan sukarela.

---

## 5. Simpanan
Menu: **Simpanan** & **Deposito**

### Jenis Simpanan
1. **Simpanan Pokok (SP)**: Modal awal, dibayar sekali saat daftar. Tidak bisa ditarik.
2. **Simpanan Wajib (SW)**: Iuran wajib bulanan. Tidak bisa ditarik sebagian.
3. **Simpanan Sukarela (SR)**: Tabungan harian, setor/tarik fleksibel. Bunga harian.
4. **Simpanan Berjangka (Deposito)**: Investasi, bunga lebih tinggi, dikunci selama tenor (1-12 bulan).

### Transaksi Setor/Tarik
1. Masuk ke **Profil Anggota** > Tab **Rekening**.
2. Pilih rekening yang akan ditransaksikan.
3. Klik tombol **Setor** (Hijau) atau **Tarik** (Merah).
4. Masukkan **Jumlah**.
5. (Opsional) Isi **Keterangan** tambahan.
6. Klik **Simpan**. Struk transaksi akan muncul (opsional).

### Deposito
- **Pembukaan**: Menu Profil Anggota > Buka Rekening Baru > Pilih "Simpanan Berjangka".
- **Jatuh Tempo**: Sistem otomatis menghitung tanggal jatuh tempo. Pencairan sebelum tanggal tersebut akan dikenakan penalti (jika diatur).

---

## 6. Pinjaman
Menu: **Pinjaman**

### Mengajukan Pinjaman Baru
1. Masuk menu **Pinjaman**.
2. Klik **Buat Pinjaman Baru**.
3. Pilih **Anggota** peminjam.
4. Pilih **Produk Pinjaman** (Misal: Pinjaman Umum, Mikro, Multiguna).
5. Masukkan parameter:
   - **Plafon**: Jumlah pinjaman yang diajukan.
   - **Tenor**: Lama angsuran (Bulan/Minggu).
   - **Bunga**: % Bunga (Per Tahun/Bulan tergantung produk).
6. Klik **Simulasi** untuk cek angsuran per bulan.
7. Klik **Ajukan Pinjaman**.

### Proses Persetujuan (Approval)
1. Pinjaman baru masuk status `PENDING`.
2. Pengurus membuka detail pinjaman, melakukan analisa (Sisa gaji, riwayat, agunan).
3. Jika layak, klik tombol **Setujui (Approve)**. Status menjadi `APPROVED`.
4. Jika ditolak, klik **Tolak (Reject)**.

### Pencairan Dana (Disbursement)
1. Buka pinjaman `APPROVED`.
2. Klik tombol **Cairkan Dana**.
3. Sistem akan membuat jurnal pengeluaran kas dan saldo pinjaman aktif. Status berubah `ACTIVE`.

### Pembayaran Angsuran
1. Buka detail pinjaman `ACTIVE`.
2. Klik tombol **Bayar Angsuran**.
3. Sistem menghitung otomatis alokasi pembayaran (Waterfall):
   - **Denda** (Jika ada keterlambatan).
   - **Bunga** tertunggak.
   - **Pokok** pinjaman.
4. Masukkan **Jumlah Bayar**.
5. Klik **Proses Pembayaran**.

---

## 7. Akuntansi & Keuangan
Menu: **Akuntansi**

### Jurnal Transaksi
- **Otomatis**: Setiap transaksi simpanan/pinjaman mencatat jurnal secara otomatis.
- **Manual**: Gunakan tombol **Catat Pemasukan / Pengeluaran** untuk:
  - Biaya Operasional (Listrik, Gaji, ATK).
  - Pembelian Aset Inventaris.
  - Pendapatan Non-Operasional.

### Kontrol Kas (Cash Opname)
Fitur untuk validasi saldo fisik kasir.
1. Buka tab **Kontrol Kas (Opname)**.
2. Hitung uang fisik di laci/brankas.
3. Masukkan jumlahnya di kolom **Jumlah Uang Fisik**.
4. Sistem menghitung selisih dengan saldo buku.
5. Klik **Simpan**. Selisih akan dicatat sebagai koreksi audit.

---

## 8. Laporan
Menu: **Laporan**

Cetak laporan kapan saja dengan periode fleksibel.
- **Neraca (Balance Sheet)**: Posisi Keuangan (Aset = Kewajiban + Modal).
- **Laba Rugi (Profit & Loss)**: Kinerja Operasional (Pendapatan - Beban).
- **Arus Kas**: Laporan keluar masuk kas.
- **Laporan Simpanan**: Daftar saldo simpanan seluruh anggota.
- **Laporan Pinjaman**: Status NPL (Kredit Macet) dan kolektibilitas.
- **Laporan SHU**: Estimasi pembagian SHU anggota.

---

## 9. Pengaturan Sistem
Menu: **Pengaturan** (Akses Super Admin)

- **Manajemen User**: Tambah petugas/kasir baru.
- **Master Data**:
  - Konfigurasi produk simpanan & pinjaman.
  - Suku bunga, denda, biaya admin.
- **Chart of Accounts (COA)**: Tambah/Edit akun GL (General Ledger).
- **Backup & Restore**: Amankan database secara berkala.
- **Migrasi Data**: Import data anggota dari Excel.

---

**SIM-KOP v1.0.0**
*Sistem Informasi Manajemen Koperasi Terpadu*
\n\n---\n\n# 📘 Panduan Penggunaan SIM-KOP (v0.0.1 Alpha)
**Sistem Informasi Manajemen Koperasi**

---

## 📋 Daftar Isi
- [📘 Panduan Penggunaan SIM-KOP (v0.0.1 Alpha)](#-panduan-penggunaan-sim-kop-v001-alpha)
  - [📋 Daftar Isi](#-daftar-isi)
  - [1. Pendahuluan](#1-pendahuluan)
  - [2. Persyaratan Sistem](#2-persyaratan-sistem)
  - [3. Alur Utama Aplikasi](#3-alur-utama-aplikasi)
  - [4. Manajemen Anggota](#4-manajemen-anggota)
  - [5. Manajemen Simpanan](#5-manajemen-simpanan)
  - [6. Manajemen Pinjaman](#6-manajemen-pinjaman)
  - [7. Manajemen Deposito](#7-manajemen-deposito)
  - [8. Akuntansi \& Laporan](#8-akuntansi--laporan)
  - [9. Pengaturan \& Backup](#9-pengaturan--backup)

---

## 1. Pendahuluan
SIM-KOP adalah aplikasi desktop berbasis Electron & React yang dirancang untuk mendigitalisasi operasional koperasi. Sistem ini mendukung pencatatan simpanan, pinjaman, deposito, dan pelaporan keuangan otomatis berbasis standar akuntansi.

## 2. Persyaratan Sistem
- Windows 10/11 (64-bit)
- RAM Minimal 4GB
- Penyimpanan Kosong Minimal 500MB

## 3. Alur Utama Aplikasi
1. **Registrasi Anggota**: Masukkan data anggota baru di menu Anggota.
2. **Setoran Simpanan**: Anggota melakukan setoran Pokok, Wajib, dan Sukarela.
3. **Pengajuan Pinjaman**: Anggota mengajukan pinjaman, disetujui, dan dicairkan.
4. **Pembayaran Angsuran**: Anggota membayar bulanan sesuai jadwal.
5. **Pelaporan**: Lihat Neraca, Laba Rugi, dan Arus Kas secara real-time.

## 4. Manajemen Anggota
- **Tambah Anggota**: Klik tombol "Tambah Anggota" di sidebar atau menu Anggota. Setiap anggota akan mendapatkan NBA (Nomor Buku Anggota) otomatis.
- **Profil Anggota**: Klik pada nama anggota untuk melihat riwayat simpanan dan pinjaman mereka.

## 5. Manajemen Simpanan
- **Setor/Tarik Tunai**: Gunakan fitur "Aksi Cepat" di Dashboard atau menu Simpanan.
- **Tipe Simpanan**:
  - **Simpanan Pokok (SP)**: Setoran awal saat menjadi anggota.
  - **Simpanan Wajib (SW)**: Setoran bulanan rutin.
  - **Simpanan Sukarela (SR)**: Tabungan yang bisa diambil kapan saja.

## 6. Manajemen Pinjaman
- **Pengajuan**: Pilih anggota, tentukan plafon, tenor (bulan), dan bunga (flat/anuitas).
- **Pencairan**: Setelah disetujui, klik "Cairkan" untuk menambah kas anggota dan mencatat piutang.
- **Bayar Angsuran**: Pilih pinjaman aktif dan masukkan jumlah bayar. Sistem otomatis memecah pokok dan bunga.

## 7. Manajemen Deposito
- **Buka Deposito**: Anggota menempatkan dana besar dengan jangka waktu tetap (misal 12 bulan).
- **Perhitungan Bunga**: Sistem menghitung bunga terakru secara otomatis setiap bulan.
- **Pencairan**: Deposito yang jatuh tempo dapat dicairkan. Jika dicairkan sebelum jatuh tempo, sistem mendukung input penalty.

## 8. Akuntansi & Laporan
- **Neraca**: Menampilkan posisi Aset, Kewajiban, dan Modal.
- **Laba Rugi**: Menampilkan Pendapatan (Bunga, Adm) dan Beban (Operasional).
- **Jurnal Umum**: Seluruh transaksi otomatis tercatat di Jurnal. Anda dapat melihatnya di menu Akuntansi.

## 9. Pengaturan & Backup
- **Backup Rutin**: Buka Pengaturan > Backup & Restore. Klik "Buat Backup" untuk menyimpan file .db.
- **Restore**: Jika ingin pindah komputer atau reset, gunakan file backup sebelumnya.
- **Konfigurasi SHU**: Atur persentase pembagian Sisa Hasil Usaha (SHU) di menu Pengaturan.

---

**Kontak Support:**
Jika menemukan kendala, silakan hubungi:
**Andrian Syah Putra (Ether Labs)**
Whatsapp: 083186459539

---
*Dokumen ini diperbarui secara otomatis oleh sistem.*
# Panduan Setup Multi-Komputer (Embedded Database)

Aplikasi SIM-KOP versi terbaru ini sudah **Otomatis** membawa database sendiri. Anda **TIDAK PERLU** lagi menginstall Laragon, XAMPP, atau MySQL secara terpisah.

---

## 1. Komputer PERTAMA (HOST / SERVER)
Komputer ini akan menjadi pusat penyimpanan data. Komputer ini **WAJIB MENYALA** dan membuka aplikasi SIM-KOP agar komputer lain bisa terhubung.

### Cara Memulai
1. Cukup **Install & Jalankan** Aplikasi SIM-KOP.
2. Saat aplikasi terbuka, Database akan otomatis berjalan di belakang layar.
   - (Akan muncul pesan Firewall Windows: Klik **Allow Access/Izinkan** agar komputer lain bisa connect).

### Cek IP Address
Untuk menghubungkan komputer lain, Anda perlu tahu IP Address komputer ini.
1. Tekan tombol `Windows + R`, ketik `cmd`, tekan Enter.
2. Ketik `ipconfig` lalu Enter.
3. Catat **IPv4 Address**. Contoh: `192.168.1.10`.

---

## 2. Komputer KEDUA (CLIENT / KASIR)
Komputer ini menumpang data ke komputer pertama.

### Setting Koneksi
1. Pastikan Komputer Pertama sudah membuka aplikasi.
2. Di Komputer Kedua, buka folder aplikasi SIM-KOP.
3. Cari file `.env` (biasanya di dalam folder instalasi atau folder config).
4. Edit baris:
   ```ini
   DATABASE_URL="mysql://root:@192.168.1.10:3306/simkop"
   ```
   *(Ganti 192.168.1.10 dengan IP Komputer Pertama)*

5. Simpan & Buka Aplikasi.
6. Login dengan user Kasir.

---

## Catatan Penting
- **Jangan Tutup Aplikasi di Komputer Utama**: Jika aplikasi di komputer utama ditutup, database akan mati, dan kasir akan terputus.
- **Backup**: Database tersimpan di folder `AppData/Roaming/sim-kop/mysql_data`. Pastikan rutin membackup folder ini atau gunakan fitur Backup di aplikasi.
