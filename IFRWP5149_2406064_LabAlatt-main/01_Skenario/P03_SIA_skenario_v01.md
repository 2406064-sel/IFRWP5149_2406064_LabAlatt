<!-- skenario -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

<!-- kebutuhan tugas -->
|  ID   |                             Kebutuhan_tugas                              |
|-------|--------------------------------------------------------------------------|
|SIA-R01|                  Mahasiswa dapat melihat jadwal kuliah                   |
|SIA-R02|               Admin akademik dapat mengelola jadwal kuliah               |
|SIA-R03|                      Mahasiswa dapat mengajukan KRS                      |
|SIA-R04|             Sistem memvalidasi KRS sebagai bagian pengajuan              |
|SIA-R05|Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
|SIA-R06|        Dosen wali dapat memproses persetujuan atau penolakan KRS         |

<!-- batas dan asumsi -->
Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas

<!-- Tabel Identifikasi Aktor -->
|    Aktor     |                                                      Tujuan_terhadap_Sistem                                                       |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  Mahasiswa   |            Memeriksa informasi jadwal perkuliahan, mengisi dan mengirim KRS, serta memperoleh dokumen bukti pengajuan.            |
|Admin_Akademik|                   Menyusun, memperbarui, dan memastikan informasi jadwal perkuliahan tersedia di dalam sistem.                    |
|  Dosen_Wali  |Meninjau pengajuan KRS mahasiswa, menentukan persetujuan atau penolakan, dan menyertakan keterangan atas keputusan yang diberikan. |

<!-- Tabel Katalog Use Case -->
|   ID   |   Nama    |   Use   |   Case    |Deskripsi|   Peran   |  dalam  |                                           Model                                            |
|--------|-----------|---------|-----------|---------|-----------|---------|--------------------------------------------------------------------------------------------|
|SIA-UC01|Menampilkan| Jadwal  |Perkuliahan|Fasilitas|   bagi    |mahasiswa|                              untuk mengetahui jadwal kuliah.                               |
|SIA-UC02|Pengaturan | Jadwal  |  Kuliah   |  Fitur  |   yang    |digunakan|             admin akademik untuk menyusun dan memperbarui jadwal perkuliahan.              |
|SIA-UC03| Pengajuan |  Kartu  |  Rencana  |  Studi  |  Proses   |mahasiswa|                     mengirimkan daftar mata kuliah yang ingin diambil.                     |
|SIA-UC04|Pemeriksaan|Kelayakan|    KRS    | Tahapan |pemeriksaan|  yang   |                      menjadi bagian wajib dari proses pengajuan KRS.                       |
|SIA-UC05| Mengunduh | Dokumen |   Bukti   |   KRS   |   Fitur   |tambahan |yang dapat dijalankan apabila mahasiswa memilih mengunduh bukti setelah pengajuan berhasil. |
|SIA-UC06| Penetapan | Status  | Pengajuan |   KRS   |  Proses   |  dosen  |        wali untuk memberikan keputusan menerima atau menolak KRS disertai catatan.         |

<!-- Relasi Include & Extend -->
Relasi <<include>> digunakan ketika suatu use case harus menjalankan proses lain sebagai bagian wajib dari proses utamanya.
Pada Sistem Informasi Akademik (SIA), relasi <<include>> terdapat pada SIA-UC03 – Pengajuan Kartu Rencana Studi dan SIA-UC04 – Pemeriksaan Kelayakan KRS.
Proses pengajuan KRS harus disertai pemeriksaan kelayakan untuk memastikan data pengajuan telah memenuhi ketentuan sistem. Oleh karena itu, pemeriksaan KRS menjadi bagian wajib dari proses pengajuan.
Arah panah relasi <<include>> dimulai dari SIA-UC03 menuju SIA-UC04, dengan label <<include>> pada garis putus-putus di diagram use case.

