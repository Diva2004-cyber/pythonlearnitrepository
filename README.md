Dokumentasi Rancangan Aplikasi: WarungKita

1. Deskripsi Umum WarungKita adalah aplikasi berbasis mobile/web yang ditujukan untuk membantu UMKM seperti warung dan toko kelontong dalam mencatat transaksi keuangan, memisahkan uang pribadi dan usaha, serta menghasilkan laporan keuangan secara otomatis. Aplikasi ini dirancang agar mudah digunakan oleh pengguna non-teknis dan mendukung pencatatan yang efisien tanpa perlu pemahaman akuntansi mendalam.

2. Tujuan Aplikasi

Mempermudah pencatatan transaksi harian

Memisahkan keuangan pribadi dan usaha

Menyediakan laporan laba rugi dan stok secara otomatis

Mengurangi kesalahan pengelolaan keuangan manual


3. Target Pengguna

Pemilik warung atau toko kecil

Pelaku usaha mikro di pedesaan dan perkotaan


4. Fitur Utama

4.1. Pencatatan Transaksi

Input pembelian: nama barang, harga beli, jumlah

Input penjualan: nama barang, harga jual, jumlah

Auto-kalkulasi total transaksi


4.2. Manajemen Stok Otomatis

Tambah stok otomatis saat input pembelian

Kurangi stok otomatis saat input penjualan

Notifikasi stok rendah


4.3. Pemisahan Keuangan Pribadi dan Usaha

Dua jenis dompet: Dompet Usaha dan Dompet Pribadi

Transfer antar dompet tercatat sebagai transaksi internal


4.4. Laporan Keuangan

Ringkasan penjualan/pembelian harian, mingguan, bulanan

Grafik arus kas dan laba bersih

Estimasi HPP (Harga Pokok Penjualan)


4.5. Hutang / Piutang

Catat nama pelanggan, jumlah utang/piutang, tanggal jatuh tempo

Update status lunas atau belum


5. Arsitektur Sistem Firebase

Frontend:

Mobile App: Flutter + Firebase SDK atau React Native + react-native-firebase

Web App: React.js + Firebase Web SDK


Backend:

Cloud Firestore untuk database

Firebase Authentication untuk login

Firebase Storage untuk penyimpanan gambar (opsional)

Cloud Functions untuk logika backend tambahan (opsional)


6. Struktur Data Firestore (NoSQL)

Koleksi: Barang

id_barang (auto ID)

nama_barang

stok

harga_beli

harga_jual


Koleksi: Transaksi

id_transaksi (auto ID)

jenis (jual/beli)

id_barang (ref ke barang)

jumlah

total

tanggal (timestamp)


Koleksi: Dompet

id_dompet (auto ID atau "usaha"/"pribadi")

jenis_dompet

saldo


Koleksi: HutangPiutang

id_hp (auto ID)

nama_orang

jumlah

tanggal_jatuh_tempo (timestamp)

status (lunas/belum lunas)


7. User Flow

1. Pengguna login/register (Firebase Auth)


2. Akses dashboard (melihat saldo, stok, dan ringkasan transaksi)


3. Menambahkan transaksi (jual/beli)


4. Sistem update stok dan saldo dompet otomatis


5. Pengguna melihat laporan dan status hutang/piutang



8. Keunggulan dan Nilai Tambah

Antarmuka ringan dan ramah pemula

Bisa digunakan offline (Flutter + local cache / SQLite opsional)

Sinkronisasi realtime antar perangkat (Firestore)

Penggunaan Firebase memudahkan skalabilitas


9. Roadmap Pengembangan (Opsional)

v1.0: Core features (transaksi, stok, dompet, laporan)

v1.1: Fitur hutang/piutang & reminder

v1.2: Mode kasir & scan barcode

v2.0: Dukungan multi-user, ekspor PDF, integrasi WhatsApp bisnis


10. Penutup WarungKita diharapkan dapat menjadi solusi digitalisasi praktis bagi UMKM Indonesia, membantu pemilik usaha mengelola keuangan mereka secara lebih baik, akurat, dan efisien, dengan memanfaatkan layanan Firebase sebagai platform utama dalam pengembangan aplikasi.

