|NO|--------------------|Temuan|----------------------------------------|------------------Perbaikan yang di perlukan-----------------------------------------------
|1| Aktor Mahasiswa diletakkan di dalam system boundary (batas sistem). | Pindahkan mahasiswa ke luar kotak
|2| Fungsi Lihat jadwal kuliah digambar sebagai kotak biasa.            | Ubah notasi fungsi menjadi simbol elips (oval).
|3| Aktor Mahasiswa dihubungkan dengan Kelola jadwal kuliah.            | Mahasiswa → Lihat jadwal kuliah, dan Admin akademik → Kelola jadwal kuliah.
|4| Identitas diagram menggunakan judul sistem laboratorium.            | Ubah judul system boundary dan isi metadata menjadi Sistem Informasi Akademik.


|N0|--------------------------------------------------------|Alasan|-------------------------------------------------------------------------------------------------
|1| Aktor merupakan entitas eksternal (pengguna/sistem luar) yang berinteraksi dengan sistem, sehingga secara notasi wajib berada di luar batas sistem.
|2|Dalam standar notasi UML Use Case Diagram, use case disimbolkan dengan elips, sedangkan bentuk persegi digunakan untuk class, component, atau boundary.
|3|Garis asosiasi harus sesuai dengan hak akses pada skenario. Mahasiswa hanya membaca jadwal, sedangkan pengelolaan data merupakan wewenang khusus Admin akademik.
|4|Nama sistem pada artefak harus konsisten dengan skenario yang dibahas agar tidak terjadi ketidaksesuaian artefak (artifact mismatch).

| NO |                                 Temuan                                                |                                                 Perbaikan yang diperlukan                                                                    |
| 1 | Arah panah relasi <<include></include>> kurang jelas.                                  | Memperjelas arah panah dari SIA-UC01 Ajukan KRS menuju SIA-UC02 Validasi KRS.                                                                |
| 2 | Arah panah relasi <<extend></extend>> kurang jelas.                                    | Memperjelas arah panah dari SIA-UC03 Unduh Bukti Pengajuan KRS menuju SIA-UC01 Ajukan KRS.                                                   |
| 3 | Keterangan extension point dan kondisi belum jelas.                                    | Menambahkan extension point Konfirmasi penyimpanan dan kondisi [pengajuan berhasil disimpan dan mahasiswa memilih unduh bukti].              |
| 4 | Judul batas sistem belum lengkap.                                                      | Menggunakan judul Sistem Informasi Akademik (SIA) pada batas sistem.                                                                         |
| 5 | Nama use case keputusan KRS perlu diperjelas.                                          | Menggunakan nama Proses Keputusan KRS pada SIA-UC04.                                                                                         |
| 6 | Status pengajuan setelah berhasil disimpan perlu dicantumkan dalam deskripsi use case. | Menambahkan status Menunggu Persetujuan Dosen Wali setelah pengajuan KRS berhasil disimpan.                                                  |


| NO |                                  Alasan                                                          |
| 1 | Validasi KRS merupakan bagian wajib dari proses pengajuan KRS.                                    |
| 2 | Unduh bukti merupakan proses tambahan yang hanya dilakukan jika mahasiswa memilihnya.             |
| 3 | Keterangan tersebut menjelaskan kapan proses unduh bukti dapat dilakukan.                         |
| 4 | Judul yang lengkap memperjelas nama sistem yang dimodelkan.                                       |
| 5 | Nama tersebut menjelaskan aktivitas dosen wali dalam menyetujui atau menolak pengajuan KRS.       |
| 6 | Status tersebut menjelaskan kondisi pengajuan sebelum diproses oleh dosen wali.                   |