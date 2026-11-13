# LAPORAN PRAKTIKUM PERTEMUAN 6
## ACTIVITY DIAGRAM: DARI SKENARIO KE ALUR AKTIVITAS

* **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149)
* **Program Studi:** S1 Teknik Informatika – Institut Teknologi Garut
* **Nama Mahasiswa:** `Fajar Alamsyah`
* **NIM:** `2406047`
* **Kelas:** `Informatika B`
* **Tanggal Praktikum:** `06-11-2026`

---

## 1. Tujuan Praktikum
1. Menyusun alur utama *activity diagram* dari Skenario Normal pada tabel skenario Pertemuan 5 dengan tepat satu *initial node*, rangkaian *action* berurutan, dan tepat satu *activity final node* tanpa alur yang terputus.
2. Mengubah Skenario Alternative menjadi cabang *decision* dengan *guard* dalam kurung siku `[...]` yang lengkap dan saling lepas, lalu menggabungkannya kembali melalui *merge* atau mengakhirinya pada *activity final node*.
3. Menggunakan pasangan *fork* dan *join* untuk memodelkan dua proses yang berjalan paralel sebelum alur dilanjutkan.
4. Mengelompokkan setiap *action* ke dalam *swimlane* aktor yang bertanggung jawab sesuai tabel skenario.
5. Menelusurkan setiap *action* pada diagram ke langkah tabel skenario Pertemuan 5 serta memverifikasinya menggunakan *checklist* penilaian.

---

## 2. Struktur Workspace dan Daftar Berkas
Seluruh berkas sumber (`.drawio`) dan hasil ekspor (`.png`) disimpan di dalam folder `IFRWP5149_<NIM>_LabAlat/04_model_analisis/P06/` dengan rincian sebagai berikut:

### A. Folder `P06/LAB/` (7 Activity Diagram Utama)
1. `P06_<NIM>_LAB_activity_lihat_ketersediaan_v01.drawio` & `.png` (Sumber: `LAB-UC01`)
2. `P06_<NIM>_LAB_activity_kelola_data_v01.drawio` & `.png` (Sumber: `LAB-UC02`, varian `LAB-UC08`, `LAB-UC09`, `LAB-UC10`)
3. `P06_<NIM>_LAB_activity_peminjaman_v01.drawio` & `.png` (Sumber: `LAB-UC03`, *include* `LAB-UC04`, *extend* `LAB-UC05`)
4. `P06_<NIM>_LAB_activity_cetak_bukti_v01.drawio` & `.png` (Sumber: `LAB-UC05`)
5. `P06_<NIM>_LAB_activity_keputusan_v01.drawio` & `.png` (Sumber: `LAB-UC06` – Tugas Mandiri)
6. `P06_<NIM>_LAB_activity_pengembalian_v01.drawio` & `.png` (Sumber: `LAB-UC11`, *include* `LAB-UC12`)
7. `P06_<NIM>_LAB_activity_laporan_v01.drawio` & `.png` (Sumber: `LAB-UC07`)

### B. Folder `P06/SIA/` (1 Activity Diagram Tugas Akademik)
1. `P06_<NIM>_SIA_activity_v01.drawio` & `.png` (Sumber: `SIA-UC08` Input Nilai Mata Kuliah sampai `SIA-UC09` Lihat KHS)

---

## 3. Pembahasan & Metadata Studi Kasus LAB

### 3.1 Activity Diagram Peminjaman (`LAB-UC03`)
* **Tabel skenario sumber:** `LAB-UC03` (Ajukan Peminjaman), `LAB-UC04` (*include* Periksa Ketersediaan), `LAB-UC05` (*extend* Cetak Bukti Pengajuan).
* **Swimlane:** Mahasiswa, Sistem, Petugas Laboratorium.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Decision* (`Peralatan tersedia?` dengan *guard* `[tersedia]` & `[tidak tersedia]`, serta `Mahasiswa memilih cetak bukti?` dengan *guard* `[ya, memilih cetak]` & `[tidak]`), *Merge*, *Activity final node*.
* **Unsur proses baru, bila ada:** Tidak ada.
* **Ringkasan Alur:** Mahasiswa mengisi formulir pengajuan peminjaman, Sistem menyimpan data dan menjalankan langkah wajib *include* `Periksa Ketersediaan (dari LAB-UC04)`. Jika `[tidak tersedia]`, Mahasiswa menerima pemberitahuan pengajuan tidak terpenuhi; jika `[tersedia]`, Petugas Laboratorium memproses keputusan peminjaman. Kedua jalur digabung melalui *merge* untuk mencatat hasil akhir pengajuan, dilanjutkan cabang *extend* cetak bukti sebelum berakhir pada *activity final node*.

### 3.2 Activity Diagram Pengembalian (`LAB-UC11`)
* **Tabel skenario sumber:** `LAB-UC11` (Catat Pengembalian Peralatan) dan `LAB-UC12` (*include* Periksa Kondisi Peralatan).
* **Swimlane:** Mahasiswa, Sistem, Petugas Laboratorium.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Fork*, *Join*, *Decision* (`Kondisi peralatan baik dan lengkap?` dengan *guard* `[baik dan lengkap]` & `[rusak atau tidak lengkap]`), *Merge*, *Activity final node*.
* **Unsur proses baru, bila ada:** `Periksa kelengkapan aksesori peralatan` (ditambahkan pada Tahap 5 untuk melatih penggunaan pasangan *fork* dan *join* secara paralel bersama pemeriksaan kondisi fisik `LAB-UC12`).

### 3.3 Activity Diagram Lihat Ketersediaan Peralatan (`LAB-UC01`)
* **Tabel skenario sumber:** `LAB-UC01` (Lihat Ketersediaan Peralatan).
* **Swimlane:** Peminjam, Sistem.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Decision* (`Peralatan tersedia?` dengan *guard* `[tersedia]` & `[tidak tersedia]`), *Merge*, *Activity final node*.
* **Unsur proses baru, bila ada:** Tidak ada.

### 3.4 Activity Diagram Kelola Data Peralatan (`LAB-UC02`)
* **Tabel skenario sumber:** `LAB-UC02` (Kelola Data Peralatan), serta varian `LAB-UC08` (Tambah), `LAB-UC09` (Ubah), dan `LAB-UC10` (Hapus).
* **Swimlane:** Petugas Laboratorium, Sistem.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Decision* (`Bentuk pengelolaan yang dipilih?` dengan cabang `[tambah]`, `[ubah]`, `[hapus]`; `Data peralatan ditemukan?`; `Syarat penghapusan terpenuhi?`; `Data lengkap dan sah?`), *Merge*, *Activity final node*.
* **Unsur proses baru, bila ada:** Tidak ada.

### 3.5 Activity Diagram Cetak Bukti Pengajuan (`LAB-UC05`)
* **Tabel skenario sumber:** `LAB-UC05` (Cetak Bukti Pengajuan – perilaku *extend* dari `LAB-UC03` pada *extension point* Bukti pengajuan tersedia).
* **Swimlane:** Mahasiswa, Sistem.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Decision* (`Mahasiswa memilih cetak bukti?` dengan *guard* `[ya, memilih cetak]` & `[tidak]`), *Merge*, *Activity final node*.
* **Unsur proses baru, bila ada:** Tidak ada.

### 3.6 Activity Diagram Proses Keputusan Peminjaman (`LAB-UC06` – Tugas Mandiri)
* **Tabel skenario sumber:** `LAB-UC06` (Proses Keputusan Peminjaman).
* **Swimlane:** Petugas Laboratorium, Sistem.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Decision* (`Pengajuan dapat diproses?` dengan *guard* `[dapat diproses]` & `[tidak dapat diproses]`, serta `Pengajuan disetujui?` dengan *guard* `[disetujui]` & `[ditolak]`), *Merge*, *Activity final node*.
* **Unsur proses baru, bila ada:** Tidak ada.

### 3.7 Activity Diagram Lihat Laporan Peminjaman (`LAB-UC07`)
* **Tabel skenario sumber:** `LAB-UC07` (Lihat Laporan Peminjaman).
* **Swimlane:** Kepala Laboratorium, Sistem.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Decision* (`Ada data peminjaman?` dengan *guard* `[ada]` & `[tidak ada]`), *Merge*, *Activity final node*.
* **Unsur proses baru, bila ada:** Tidak ada.

---

## 4. Catatan Perbandingan Tugas Mandiri (`LAB-UC06`)
*(Sesuai Langkah 10 Bagian C.2: perbandingan antara hasil pengerjaan mandiri dengan berkas pembanding pada Lampiran)*

| Aspek yang Dibandingkan | Hasil Pengerjaan Mandiri Awal | Berkas Pembanding Lampiran | Perbaikan yang Dilakukan |
| :--- | :--- | :--- | :--- |
| **Swimlane** | Petugas Laboratorium, Sistem | Petugas Laboratorium, Sistem (tanpa Mahasiswa) | Sudah sesuai, Mahasiswa tidak digambar karena tidak terlibat langkah pada `LAB-UC06`. |
| **Decision & Guard** | Menggunakan percabangan status persetujuan | Terdapat 2 *decision*: `Pengajuan dapat diproses?` (`[dapat diproses]` / `[tidak dapat diproses]`) dan `Pengajuan disetujui?` (`[disetujui]` / `[ditolak]`) | `<Sesuaikan dengan hasil koreksi diagram Anda, misal: Menambahkan decision pengecekan apakah pengajuan masih dapat diproses>` |
| **Penamaan Status** | `<Isi kondisi awal Anda>` | Menggunakan status baku Pertemuan 4: `Menunggu Keputusan`, `Disetujui`, `Ditolak` | Menyesuaikan label status pada *action* agar konsisten dengan aturan model Pertemuan 4. |
| **Merge & Final Node** | `<Isi kondisi awal Anda>` | Seluruh cabang bermuara ke *merge* dan satu *activity final node* | Memastikan tidak ada jalur cabang yang menggantung tanpa muara akhir. |

---

## 5. Pembahasan & Metadata Tugas SIA (`SIA-UC08` sampai `SIA-UC09`)

### 5.1 Metadata Diagram SIA
* **Nama Berkas:** `P06_<NIM>_SIA_activity_v01.drawio` dan `P06_<NIM>_SIA_activity_v01.png`
* **Tabel skenario sumber:** `SIA-UC08` (Input Nilai Mata Kuliah) dan `SIA-UC09` (Lihat KHS) dari dokumen skenario SIA Pertemuan 5.
* **Swimlane:** Dosen, Sistem, Admin Akademik, Mahasiswa.
* **Unsur activity yang digunakan:** *Initial node*, *Action*, *Decision* (`Nilai sudah lengkap?` dengan *guard* `[lengkap]` dan `[belum lengkap]`), *Merge*, *Fork*, *Join*, *Activity final node*.
* **Unsur proses baru, bila ada:** Tidak ada.

### 5.2 Penjelasan Alur Aktivitas SIA
1. **Alur Awal & Input Nilai (`SIA-UC08`):** Dimulai dari *initial node* pada *swimlane* **Dosen**, Dosen melakukan *action* memasukkan nilai mata kuliah, kemudian **Sistem** menyimpan nilai tersebut.
2. **Validasi Kelengkapan Nilai (*Decision* & *Merge*):** Sistem memeriksa kelengkapan nilai melalui *decision* `Nilai sudah lengkap?`. Jika `[belum lengkap]`, alur kembali ke **Dosen** untuk melengkapi nilai mata kuliah yang belum lengkap, lalu bergabung kembali melalui *merge* sebelum proses pengesahan. Jika `[lengkap]`, alur berlanjut ke **Admin Akademik**.
3. **Pengesahan & Publikasi Paralel (*Fork* & *Join*):** **Admin Akademik** memeriksa dan mengesahkan nilai. Setelah nilai disahkan, **Sistem** menyiapkan publikasi hasil studi dan membagi alur menggunakan *fork* menjadi dua proses paralel: `Menerbitkan KHS pada portal akademik` dan `Mengirim pemberitahuan hasil studi kepada mahasiswa`. Keduanya disatukan kembali dengan *join*.
4. **Lihat KHS (`SIA-UC09`):** Setelah proses publikasi paralel selesai disatukan oleh *join*, **Mahasiswa** melakukan *action* `Melihat KHS` dan alur ditutup oleh satu *activity final node*.

---

## 6. Checklist Penilaian Mandiri (Bagian C.4)
- ✅ Tepat satu *initial node* dan minimal satu *activity final node*; tidak ada *action* yang terputus dari alur.
- ✅ Setiap *decision* mempunyai *guard* pada semua alur keluarnya; *guard* saling lepas dan bersama-sama menutup semua kemungkinan.
- ✅ Setiap cabang *decision* kembali melalui *merge* atau bermuara ke *activity final node* dengan keadaan akhir yang jelas.
- ✅ *Fork* selalu berpasangan dengan *join*; proses paralel disatukan oleh *join*, bukan oleh *merge*.
- ✅ Setiap *action* berada pada *swimlane* aktor yang melakukannya pada tabel skenario; respon sistem berada pada *swimlane* Sistem.
- ✅ Setiap *action* tertelusur ke langkah tabel skenario Pertemuan 5 dan nama *action* sama dengan bunyi langkah sumbernya.
- ✅ *Include* digambar sebagai *action* wajib pada alur utama (*Periksa Ketersediaan* pada peminjaman; *Periksa Kondisi Peralatan* pada pengembalian) dan *extend* digambar sebagai cabang bersyarat dengan *condition* yang sama, yaitu `[ya, memilih cetak]`.
- ✅ Unsur proses baru Tahap 5, yaitu *Periksa kelengkapan aksesori peralatan*, diberi keterangan unsur proses baru dan tidak diklaim berasal dari Pertemuan 3, 4, atau 5.
- ✅ *Collaboration* tidak digambar sebagai *action* atau sebagai *swimlane*.
- ✅ Kepala Laboratorium tidak muncul pada Activity Peminjaman dan Activity Pengembalian, karena fungsinya, yaitu Lihat Laporan Peminjaman, bukan bagian dari kedua alur ini; kemunculannya menandakan diagram tidak diturunkan dari skenario `LAB-UC03` dan `LAB-UC11`. Kepala Laboratorium hanya muncul sebagai aktor pada Activity Lihat Laporan Peminjaman (`LAB-UC07`).
- ✅ Ketujuh *activity diagram* LAB untuk tujuh *use case* utama tersedia lengkap, masing-masing sebagai berkas `v01` beserta ekspor PNG: `lihat_ketersediaan` (`LAB-UC01`), `kelola_data` (`LAB-UC02`), `peminjaman` (`LAB-UC03`), `cetak_bukti` (`LAB-UC05`), `keputusan` (`LAB-UC06`), `pengembalian` (`LAB-UC11`), dan `laporan` (`LAB-UC07`).
- ✅ `LAB-UC04`, `LAB-UC12`, `LAB-UC08`, `LAB-UC09`, dan `LAB-UC10` tidak dibuatkan *activity* tersendiri: `LAB-UC04` tercakup sebagai *action include* pada Activity Peminjaman, `LAB-UC12` tercakup sebagai *action include* pada Activity Pengembalian, dan `LAB-UC08`, `LAB-UC09`, serta `LAB-UC10` tercakup sebagai cabang varian `[tambah]`, `[ubah]`, dan `[hapus]` pada Activity Kelola Data Peralatan.
- ✅ Nama aktor, nama *action*, dan ID konsisten dengan Jobsheet Pertemuan 4 dan 5; berkas `P04` dan dokumen `P05` tidak diubah.
- ✅ Berkas sumber dapat dibuka kembali dan disunting; ekspor PNG sesuai sumber terkini; nomor versi sumber dan ekspor sama.