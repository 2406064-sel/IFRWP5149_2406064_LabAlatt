# Laporan Review dan Evaluasi Diagram Use Case

**Metadata Dokumen**
* Nama File: `P03_2406064_jobsheet_review_v01.md`[cite: 8]
* Mata Kuliah: Praktikum Analisis dan Desain Berorientasi Objek[cite: 1]
* Kasus: Sistem Informasi Akademik (SIA)[cite: 8, 14]

---

### 1. Ringkasan Evaluasi
Laporan ini mencatat temuan kesalahan pemodelan notasi UML Use Case Diagram serta langkah perbaikan yang diperlukan untuk memastikan model sesuai dengan standar Notasi UML 2.5.1 dan spesifikasi kebutuhan Sistem Informasi Akademik[cite: 14, 17].

---

### 2. Matriks Temuan dan Perbaikan

| No | Temuan | Perbaikan yang Diperlukan | Alasan |
| :-: | :--- | :--- | :--- |
| **1** | Aktor Mahasiswa diletakkan di dalam batas sistem. | Pindahkan posisi aktor Mahasiswa ke luar kotak batas sistem. | Aktor mewakili entitas eksternal yang berinteraksi dengan sistem, sehingga posisinya harus selalu berada di luar batas sistem[cite: 3]. |
| **2** | Fungsi Lihat jadwal kuliah digambar sebagai kotak biasa. | Ubah simbol fungsi menjadi bentuk elips (oval). | Sesuai standar notasi UML, fungsionalitas Use Case digambarkan dengan simbol elips[cite: 2, 6]. |
| **3** | Aktor Mahasiswa dihubungkan dengan Kelola jadwal kuliah. | Hapus garis penghubung antara aktor Mahasiswa dengan use case Kelola jadwal kuliah. | Mahasiswa tidak memiliki hak akses/wewenang untuk mengelola jadwal kuliah[cite: 14]. |
| **4** | Identitas diagram menggunakan judul sistem laboratorium. | Ubah judul batas sistem menjadi yang relevan (misal: Sistem Informasi Akademik). | Judul batas sistem harus akurat mencerminkan ruang lingkup sistem yang sedang dibahas[cite: 6, 14]. |

---

### 3. Status Verifikasi Notasi
* **Batas Sistem**: Seluruh aktor berada di luar batas sistem, sedangkan seluruh use case berada di dalam batas[cite: 3].
* **Notasi Bentuk**: Seluruh fungsi digambarkan menggunakan elips dan dinamai menggunakan kata kerja[cite: 2, 4].
* **Hak Akses**: Asosiasi hanya menghubungkan aktor ke fungsi yang sesuai dengan wewenang perannya[cite: 3, 14].
* **Identitas Sistem**: Batas sistem menggunakan nama yang akurat sesuai kasus SIA[cite: 6, 14].