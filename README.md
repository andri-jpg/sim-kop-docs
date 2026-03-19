# 📘 BUKU PANDUAN PENGGUNA SIM-KOP
**Sistem Informasi Manajemen Koperasi Terpadu**

Aplikasi desktop berbasis *offline-first* (Electron & React) untuk mendigitalisasi operasional koperasi simpan pinjam secara terpadu. Dikembangkan oleh **Ether Labs**.

---

## 📋 Daftar Isi

- [1. Pengenalan Fitur Utama](#1-pengenalan-fitur-utama)
- [2. Alur Operasional Koperasi (SOP)](#2-alur-operasional-koperasi-sop)
- [3. Panduan Penggunaan Sistem (Langkah demi Langkah)](#3-panduan-penggunaan-sistem-langkah-demi-langkah)
  - [A. Akses Sistem & Pemulihan Password](#a-akses-sistem--pemulihan-password)
  - [B. Mendaftarkan Anggota Baru](#b-mendaftarkan-anggota-baru)
  - [C. Setor, Tarik, & Cetak Buku Simpanan](#c-setor-tarik--cetak-buku-simpanan)
  - [D. Pengajuan & Pembayaran Pinjaman (Waterfall)](#d-pengajuan--pembayaran-pinjaman-waterfall)
  - [E. Pencatatan Akuntansi Manual](#e-pencatatan-akuntansi-manual)
  - [F. Menghitung & Membagikan SHU](#f-menghitung--membagikan-shu)
  - [G. Pengaturan Keamanan & Backup (Admin)](#g-pengaturan-keamanan--backup-admin)
- [4. Pusat Bantuan](#4-pusat-bantuan)

---

## 1. Pengenalan Fitur Utama
SIM-KOP dirancang untuk menyederhanakan tugas kompleks koperasi menjadi sistem yang serba otomatis:
* **Multi-User & RBAC:** Dukungan jaringan lokal (Server-Client) dengan pembatasan hak akses per peran (Admin, Manager, Kasir).
* **Akuntansi Otomatis:** Menggunakan sistem *Double-Entry* di mana Jurnal, Neraca, dan Laba Rugi terbentuk otomatis dari transaksi sehari-hari.
* **Metode Pinjaman Waterfall:** Pembayaran angsuran secara cerdas memprioritaskan pelunasan Denda $\rightarrow$ Bunga $\rightarrow$ Pokok.
* **Kalkulator SHU:** Perhitungan proporsional SHU (Jasa Modal & Jasa Usaha) hanya dengan satu klik.
* **Keamanan Tingkat Tinggi:** Dilengkapi *Audit Trail* untuk merekam setiap aktivitas *user*.

---

## 2. Alur Operasional Koperasi (SOP)
Untuk kasir atau petugas harian, ini adalah siklus kerja rutin yang dilakukan di aplikasi:
1. **Pendaftaran:** Input data anggota baru $\rightarrow$ Terima Setoran Pokok & Wajib awal.
2. **Transaksi Harian:** Terima setoran/tarikan Simpanan Sukarela $\rightarrow$ Cetak mutasi ke buku tabungan fisik.
3. **Kredit:** Input pengajuan pinjaman anggota $\rightarrow$ Tunggu persetujuan Manager $\rightarrow$ Cairkan dana $\rightarrow$ Terima pembayaran angsuran bulanan.
4. **Tutup Buku:** Cek Laporan Laba Rugi di akhir periode $\rightarrow$ Hitung dan distribusikan SHU ke akun anggota.

---

## 3. Panduan Penggunaan Sistem (Langkah demi Langkah)

### A. Akses Sistem & Pemulihan Password
**Cara Login:**
1. Buka aplikasi SIM-KOP di PC Anda.
2. Masukkan Username dan Password sesuai peran yang diberikan.
3. Klik **Masuk ke Sistem**.

**Cara Reset Password (Khusus Super Admin):**
Sistem ini berjalan *offline* dan tidak menggunakan reset via email demi keamanan.
1. Klik teks biru **Lupa password?** di halaman login.
2. Hubungi Developer (Ether Labs) di nomor WhatsApp yang tertera di layar.
3. Masukkan **Kode Rahasia** yang diberikan Developer ke dalam kolom *Bypass Key*.
4. Klik **Reset Password Superadmin** dan buat sandi baru.

### B. Mendaftarkan Anggota Baru
1. Di menu kiri, klik **Anggota**.
2. Klik tombol biru **+ Tambah Anggota** di pojok kanan atas.
3. Isi formulir pendaftaran (Nama, NIK, Alamat, dll). Sistem akan otomatis membuatkan **NBA** (Nomor Buku Anggota).
4. Klik **Simpan**. Status anggota akan menjadi `PENDING` hingga mereka membayar Simpanan Pokok awal.

### C. Setor, Tarik, & Cetak Buku Simpanan
**Cara Melakukan Transaksi:**
1. Cari anggota di dasbor atau menu **Simpanan**, lalu klik namanya untuk masuk ke **Profil Anggota**.
2. Buka tab **Rekening**, pilih jenis simpanan (misal: Simpanan Sukarela).
3. Klik tombol **Setor** (Hijau) atau **Tarik** (Merah).
4. Masukkan nominal uang dan klik **Simpan**. (Sistem otomatis mencatat jurnal kas).

**Cara Mencetak Buku Tabungan:**
1. Masih di Profil Anggota, buka tab **Cetak Buku**.
2. Masukkan buku tabungan fisik ke *Printer Passbook* (Epson PLQ-35).
3. Perhatikan baris *progress* di layar. Sistem sudah mengingat baris terakhir yang dicetak.
4. Klik tombol **Cetak** untuk mem- *print* mutasi terbaru.

### D. Pengajuan & Pembayaran Pinjaman (Waterfall)
**Cara Mengajukan & Mencairkan Pinjaman:**
1. Buka menu **Pinjaman** $\rightarrow$ **Buat Pinjaman Baru**.
2. Pilih nama anggota, masukkan **Plafon** (jumlah pinjaman), **Tenor**, dan **Bunga**. Klik **Ajukan**.
3. *Manager/Super Admin* membuka detail pinjaman tersebut lalu klik **Approve**.
4. Setelah disetujui, klik **Cairkan Dana** agar uang masuk ke anggota.

**Cara Menerima Pembayaran Angsuran:**
1. Buka menu **Pinjaman**, cari pinjaman anggota yang berstatus `ACTIVE`.
2. Klik **Detail** $\rightarrow$ klik tombol **Bayar Angsuran**.
3. Sistem akan memunculkan rincian tagihan minimal. Masukkan nominal uang yang dibayar anggota di kolom input.
4. *Sistem Waterfall* akan otomatis membagi uang tersebut untuk melunasi Bunga terlebih dahulu, baru sisanya memotong Pokok. Klik **Proses Pembayaran**.

### E. Pencatatan Akuntansi Manual
Transaksi anggota otomatis masuk ke buku besar. Gunakan menu ini HANYA untuk operasional internal koperasi:
1. Buka menu **Akuntansi**.
2. Untuk mencatat biaya operasional bulanan, klik **+ Catat Pengeluaran**.
3. Pilih akun beban (misal: Beban Listrik, Beban Gaji), masukkan nominal dan deskripsi.
4. Klik **Simpan**.

### F. Menghitung & Membagikan SHU
Lakukan ini pada akhir tahun buku:
1. Masuk ke menu **Laporan** $\rightarrow$ tab **Pembagian SHU**.
2. Pilih Tahun Buku (misal: 2026), lalu klik **Hitung Ulang**.
3. Sistem akan menarik data *Net Income* (Laba Bersih) dan membaginya sesuai persentase AD/ART.
4. Lihat ke bagian **Rincian Dividen per Anggota**. Anda bisa melihat secara transparan berapa Jasa Modal dan Jasa Usaha yang didapat masing-masing anggota.
5. Klik **Cetak Laporan** untuk arsip fisik.

### G. Pengaturan Keamanan & Backup (Admin)
Hanya bisa diakses oleh *Super Admin*:
* **Manajemen Akses (RBAC):** Buka **Pengaturan > Roles & Permissions**. Centang *checkbox* untuk mengatur fitur apa saja yang boleh diakses oleh Kasir atau Teller.
* **Audit Trail:** Buka tab **Audit Trail** untuk memantau siapa yang menghapus, mengubah, atau membuat transaksi. Bisa difilter berdasarkan tanggal dan aksi.
* **Backup Database:** WAJIB dilakukan rutin. Buka tab **Backup & Restore**, klik **Buat Backup** untuk menyimpan data *offline* koperasi ke *flashdisk* eksternal untuk menghindari kehilangan data jika PC rusak.

---

## 4. Pusat Bantuan

Jika menemukan kendala teknis, kerusakan sistem, atau butuh bantuan konfigurasi jaringan lokal (LAN), hubungi pengembang aplikasi:

**Ether Labs**
- 👤 **Andrian Syah Putra**
- 📞 **WhatsApp:** 0831-8645-9539

---
*Dokumentasi ini dibuat dan diperbarui secara otomatis.*
