# P05 - Lembar Skenario Tugas SIA: Layanan Hasil Studi

| Metadata | Keterangan |
|---|---|
| Mata kuliah | Praktikum Analisis dan Desain Berorientasi Objek |
| Pertemuan | 5 - Skenario use case: dari diagram ke langkah kegiatan |
| Kasus | Sistem Informasi Akademik, Layanan Hasil Studi |
| Nama / NIM | Rival Arizal Sutisna / 2406064 |
| Versi | v01 |
| Tanggal | 30 Oktober 2026 |
| Dokumen acuan | `04_model_analisis/P04/SIA/P04_2406064_SIA_model_analisis_v01.md`; diagram kumulatif P04 SIA |
| Berkas diagram | `03_latihan_tools/P04/SIA/P04_2406064_SIA_usecase_v01.drawio` (acuan, tidak diubah) |
| Kebutuhan acuan | SIA-R07 sampai SIA-R12 (Jobsheet Pertemuan 4) |

Tugas ini merupakan kelanjutan dari kasus SIA Pertemuan 4. Diagram acuannya adalah diagram kumulatif SIA Pertemuan 4, dan kebutuhan acuannya adalah SIA-R07 sampai SIA-R12 (lihat Jobsheet Pertemuan 4, Tabel 4.6). Keterampilan baru pada tugas ini adalah penulisan skenario, bukan perancangan kasus baru, sehingga mahasiswa tidak menambah use case, aktor, atau kebutuhan di luar diagram SIA Pertemuan 4. 

## 1. Indeks tabel skenario SIA

| Tabel | ID | Nama use case | Aktor | Catatan pemetaan |
|---|---|---|---|---|
| 5.14 | SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | Ditulis satu kali atas nama Civitas Akademika; berlaku untuk Mahasiswa dan Dosen |
| 5.15 | SIA-UC08 | Input Nilai Mata Kuliah | Dosen | Prasyarat: dosen pengampu mata kuliah; alternatif: nilai di luar rentang yang sah ditolak; direalisasikan SIA-CO01 |
| 5.16 | SIA-UC09 | Lihat KHS | Mahasiswa | Hanya nilai yang sudah dipublikasikan yang ditampilkan; direalisasikan SIA-CO02 |
| 5.17 | SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | Skenario umum pengelolaan; langkah bersama yang dirujuk UC11, UC12, dan UC13 |
| 5.18 | SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | Khusus dari UC10; perilaku pembeda: data mahasiswa baru tersimpan |
| 5.19 | SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | Khusus dari UC10; perilaku pembeda: data mahasiswa berubah |
| 5.20 | SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | Khusus dari UC10; perilaku pembeda: data mahasiswa terhapus; syarat: tidak ada data akademik aktif |

---

## 2. Tabel Skenario

### Tabel 5.14 Skenario Use Case SIA-UC07 Lihat Kalender Akademik

| Nama use case | SIA-UC07 Lihat Kalender Akademik |
| :--- | :--- |
| **Aktor** | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen) |
| **Tujuan** | Civitas Akademika dapat melihat jadwal kalender akademik |
| **Deskripsi** | Civitas Akademika membuka fungsi kalender dan melihat jadwal akademik yang tersedia |

| Kegiatan | Respon sistem | Penelusuran Relasi |
| :--- | :--- | :--- |
| **Skenario Normal** | | |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik | | Generalization aktor: Mahasiswa dan Dosen mewarisi ke Civitas Akademika. |
| | 2. Sistem menampilkan daftar jadwal akademik | |
| **Skenario Alternative** | | |
| 3. Jadwal akademik belum tersedia (cabang dari langkah 2) | | |
| | 4. Sistem menampilkan pesan jadwal belum tersedia | |
| **Skenario Akhir** | Use case selesai jika jadwal kalender akademik ditampilkan; jika belum tersedia, use case selesai dengan pesan tersebut. | |

---

### Tabel 5.15 Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah

| Nama use case | SIA-UC08 Input Nilai Mata Kuliah |
| :--- | :--- |
| **Aktor** | Dosen |
| **Tujuan** | Nilai mata kuliah mahasiswa tersimpan |
| **Deskripsi** | Dosen menginput nilai mahasiswa untuk mata kuliah yang diampu. Prasyarat: dosen pengampu mata kuliah |

| Kegiatan | Respon sistem | Penelusuran Relasi |
| :--- | :--- | :--- |
| **Skenario Normal** | | |
| 1. Dosen memilih mata kuliah yang diampu | | Direalisasikan oleh collaboration SIA-CO01. |
| | 2. Sistem menampilkan daftar mahasiswa | |
| 3. Dosen menginput nilai mahasiswa | | |
| | 4. Sistem memvalidasi rentang nilai yang sah | |
| 5. Dosen menyimpan data nilai | | |
| | 6. Sistem menyimpan nilai dan menampilkan konfirmasi | |
| **Skenario Alternative** | | |
| 7. Nilai di luar rentang yang sah (cabang dari langkah 4) | | |
| | 8. Sistem menolak penyimpanan dan menampilkan pesan kesalahan nilai | |
| **Skenario Akhir** | Use case selesai jika nilai tersimpan; jika nilai di luar rentang, nilai tidak tersimpan. | |
| **Keterangan** | Use case ini direalisasikan oleh collaboration SIA-CO01. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. | |

---

### Tabel 5.16 Skenario Use Case SIA-UC09 Lihat KHS

| Nama use case | SIA-UC09 Lihat KHS |
| :--- | :--- |
| **Aktor** | Mahasiswa |
| **Tujuan** | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) |
| **Deskripsi** | Mahasiswa membuka fungsi KHS untuk melihat nilai yang sudah dipublikasikan |

| Kegiatan | Respon sistem | Penelusuran Relasi |
| :--- | :--- | :--- |
| **Skenario Normal** | | |
| 1. Mahasiswa membuka fungsi Lihat KHS | | Direalisasikan oleh collaboration SIA-CO02. |
| | 2. Sistem menampilkan KHS dengan nilai yang sudah dipublikasikan | |
| **Skenario Alternative** | | |
| 3. Nilai belum dipublikasikan (cabang dari langkah 2) | | |
| | 4. Sistem menampilkan pesan nilai belum dipublikasikan | |
| **Skenario Akhir** | Use case selesai jika KHS ditampilkan; jika nilai belum dipublikasikan, use case selesai dengan pesan tersebut. | |
| **Keterangan** | Use case ini direalisasikan oleh collaboration SIA-CO02. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. | |

---

### Tabel 5.17 Skenario Use Case SIA-UC10 Kelola Data Mahasiswa

| Nama use case | SIA-UC10 Kelola Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terkelola melalui satu fungsi pengelolaan bersama |
| **Deskripsi** | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya |

| Kegiatan | Respon sistem | Penelusuran Relasi |
| :--- | :--- | :--- |
| **Skenario Normal** | | |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa | | Generalization use case: Skenario umum untuk UC11, UC12, UC13. |
| | 2. Sistem menampilkan daftar data mahasiswa | |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus | | |
| | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih | |
| 5. Admin Akademik mengisi atau mengonfirmasi data | | |
| | 6. Sistem memeriksa kelengkapan dan keabsahan data | |
| 7. Admin Akademik menyimpan perubahan | | |
| | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi | |
| **Skenario Alternative** | | |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6) | | |
| | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data | |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. | |

---

### Tabel 5.18 Skenario Use Case SIA-UC11 Tambah Data Mahasiswa

| Nama use case | SIA-UC11 Tambah Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa baru tersimpan |
| **Deskripsi** | Admin Akademik mengisi data mahasiswa baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem | Penelusuran Relasi |
| :--- | :--- | :--- |
| **Skenario Normal** | | |
| 1. Admin Akademik membuka fungsi Tambah Data Mahasiswa | | Generalization use case dari SIA-UC10. Perilaku pembeda: data baru tersimpan. |
| | 2. Sistem menampilkan formulir data mahasiswa baru | |
| 3. Admin Akademik mengisi data mahasiswa baru | | |
| | 4. Sistem memeriksa kelengkapan dan keunikan NIM | |
| 5. Admin Akademik menyimpan data | | |
| | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi | |
| **Skenario Alternative** | | |
| 7. NIM sudah terdaftar (cabang dari langkah 4) | | |
| | 8. Sistem menolak penyimpanan dan meminta Admin mengganti NIM | |
| **Skenario Akhir** | Use case selesai jika data mahasiswa baru tersimpan; jika NIM duplikat atau tidak lengkap, data tidak tersimpan. | |
| **Keterangan** | Use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa baru tersimpan. Langkah bersama mengikuti Tabel skenario SIA-UC10. | |

---

### Tabel 5.19 Skenario Use Case SIA-UC12 Ubah Data Mahasiswa

| Nama use case | SIA-UC12 Ubah Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa berubah |
| **Deskripsi** | Admin Akademik memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem | Penelusuran Relasi |
| :--- | :--- | :--- |
| **Skenario Normal** | | |
| 1. Admin Akademik memilih data mahasiswa yang akan diubah | | Generalization use case dari SIA-UC10. Perilaku pembeda: data mahasiswa berubah. |
| | 2. Sistem menampilkan data mahasiswa saat ini | |
| 3. Admin Akademik mengubah data mahasiswa | | |
| | 4. Sistem memeriksa keabsahan perubahan data | |
| 5. Admin Akademik menyimpan perubahan | | |
| | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi | |
| **Skenario Alternative** | | |
| 7. Data mahasiswa tidak ditemukan (cabang dari langkah 2) | | |
| | 8. Sistem menampilkan pesan data mahasiswa tidak ditemukan | |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. | |
| **Keterangan** | Use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa berubah. Langkah bersama mengikuti Tabel skenario SIA-UC10. | |

---

### Tabel 5.20 Skenario Use Case SIA-UC13 Hapus Data Mahasiswa

| Nama use case | SIA-UC13 Hapus Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terhapus |
| **Deskripsi** | Admin Akademik menghapus data mahasiswa dengan syarat tidak ada data akademik aktif; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem | Penelusuran Relasi |
| :--- | :--- | :--- |
| **Skenario Normal** | | |
| 1. Admin Akademik memilih data mahasiswa yang akan dihapus | | Generalization use case dari SIA-UC10. Syarat: tidak ada data akademik aktif. |
| | 2. Sistem memeriksa data akademik aktif pada mahasiswa tersebut | |
| 3. Admin Akademik mengonfirmasi penghapusan | | |
| | 4. Sistem menghapus data mahasiswa dan menampilkan konfirmasi | |
| **Skenario Alternative** | | |
| 5. Mahasiswa masih memiliki data akademik aktif (cabang dari langkah 2) | | |
| | 6. Sistem menolak penghapusan dan menampilkan pesan data masih aktif | |
| **Skenario Akhir** | Use case selesai jika data mahasiswa terhapus; jika masih memiliki data akademik aktif, data tidak terhapus. | |
| **Keterangan** | Use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa terhapus, dengan syarat tidak ada data akademik aktif. Langkah bersama mengikuti Tabel skenario SIA-UC10. | |