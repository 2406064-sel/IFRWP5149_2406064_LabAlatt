# P05 - Lembar Skenario Studi Kasus LAB: Peminjaman dan Pengembalian Peralatan Laboratorium

| Metadata | Keterangan |
|---|---|
| Mata kuliah | Praktikum Analisis dan Desain Berorientasi Objek |
| Pertemuan | 5 - Skenario use case: dari diagram ke langkah kegiatan |
| Kasus | Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus |
| Nama / NIM | Rival Arizal Sutisna / 2406064 |
| Versi | v01 |
| Tanggal | 30 Oktober 2026 |
| Dokumen acuan | `04_model_analisis/P04/LAB/P04_2406064_LAB_model_analisis_v01.md`; diagram kumulatif P04 LAB |
| Berkas diagram | `03_latihan_tools/P04/LAB/P04_2406064_LAB_usecase_v01.drawio` (acuan, tidak diubah) |
| Kebutuhan acuan | LAB-R01 sampai LAB-R11 (Jobsheet Pertemuan 4) |

Studi kasus ini memakai diagram kumulatif Pertemuan 4 sebagai acuan.
Kebutuhan LAB-R01 sampai LAB-R11 dan spesifikasi 17 hubungan pada
diagram dirujuk dari Jobsheet Pertemuan 4 (khususnya Tabel 4.5); tidak ada
kebutuhan baru dan tidak ada use case baru pada pertemuan ini. Seluruh
tabel skenario studi kasus dimuat lengkap pada bagian ini sebagai bahan
kajian, sehingga mahasiswa tidak lagi ditugasi menulis tabel studi kasus.
Pekerjaan mahasiswa pada studi kasus adalah menelaah kedua belas tabel
tersebut terhadap diagram acuan.
## 1. Indeks tabel skenario

| Tabel | ID | Nama use case | Aktor | Tabel jobsheet |
|---|---|---|---|---|
| 5.1 | LAB-UC01 | Lihat Ketersediaan Peralatan | Peminjam (Mahasiswa, Dosen) | Tabel 5.3 |
| 5.2 | LAB-UC03 | Ajukan Peminjaman | Peminjam (Mahasiswa, Dosen) | Tabel 5.1 |
| 5.3 | LAB-UC04 | Periksa Ketersediaan | Peminjam (di dalam UC03) | Tabel 5.4 |
| 5.4 | LAB-UC05 | Cetak Bukti Pengajuan | Mahasiswa | Tabel 5.5 |
| 5.5 | LAB-UC02 | Kelola Data Peralatan | Petugas Laboratorium | Tabel 5.6 |
| 5.6 | LAB-UC08 | Tambah Data Peralatan | Petugas Laboratorium | Tabel 5.7 |
| 5.7 | LAB-UC09 | Ubah Data Peralatan | Petugas Laboratorium | Tabel 5.8 |
| 5.8 | LAB-UC10 | Hapus Data Peralatan | Petugas Laboratorium | Tabel 5.9 |
| 5.9 | LAB-UC06 | Proses Keputusan Peminjaman | Petugas Laboratorium | Tabel 5.10 |
| 5.10 | LAB-UC07 | Lihat Laporan Peminjaman | Kepala Laboratorium | Tabel 5.11 |
| 5.11 | LAB-UC11 | Catat Pengembalian Peralatan | Petugas Laboratorium | Tabel 5.12 |
| 5.12 | LAB-UC12 | Periksa Kondisi Peralatan | Petugas Laboratorium (di dalam UC11) | Tabel 5.13 |