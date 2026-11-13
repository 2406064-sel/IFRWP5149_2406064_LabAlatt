<!-- Ajukan KRS -->
|   Elemen   |                                          Isi                                           |
|------------|----------------------------------------------------------------------------------------|
|     ID     |                               & Nama SIA-UC03 Ajukan KRS                               |
|   Sumber   |                          Kebutuhan SIA-R03, SIA-R04, SIA-R05                           |
|   Tujuan   |Menghasilkan pengajuan KRS yang tersimpan dengan status menunggu persetujuan dosen wali |
|   Aktor    |                                    Utama Mahasiswa                                     |
|   Pemicu   |                          Mahasiswa memilih menu pengajuan KRS                          |
| Prasyarat  |          Mahasiswa telah terautentikasi; data mata kuliah dan jadwal tersedia          |
|Pascakondisi|    Berhasil Pengajuan KRS tersimpan dengan status "Menunggu persetujuan dosen wali"    |
|Pascakondisi|                          Gagal Pengajuan KRS tidak tersimpan                           |
|  Include   |                                 SIA-UC04 Validasi KRS                                  |
| Extension  |                 Point Konfirmasi pengajuan tersimpan (pada langkah 5)                  |
|   Extend   |                   SIA-UC05 jika [mahasiswa memilih mengunduh bukti]                    |

<!-- Validasi KRS -->
|   Elemen   |                              Isi                               |
|------------|----------------------------------------------------------------|
|     ID     |                        & Nama SIA-UC04                         |
|  Validasi  |                              KRS                               |
|   Sumber   |                       KebutuhannSIA-R04                        |
|   Tujuan   |                 Memastikan isian KRS lengkap,                  |
| prasyarat  |      mata kuliah terpenuhi, dan tidak ada benturan jadwal      |
|   Aktor    |   Utama Mahasiswa (melalui pemanggilan sistem dari SIA-UC03)   |
|   Pemicu   |       Dipanggil oleh SIA-UC03 saat pengajuan KRS dikirim       |
| Prasyarat  |        Data isian KRS telah dikirimkan untuk diperiksa         |
|Pascakondisi|               Berhasil Data KRS dinyatakan valid               |
|Pascakondisi|Gagal Data KRS dinyatakan tidak valid beserta rincian alasannya |

<!-- Pengajuan KRS -->
|       Elemen        |                                 Isi                                 |
|---------------------|---------------------------------------------------------------------|
|         ID          |              & Nama SIA-UC05 Unduh bukti pengajuan KRS              |
|       Sumber        |                          Kebutuhan SIA-R05                          |
|       Tujuan        |Menyediakan berkas bukti pengajuan KRS untuk disimpan oleh mahasiswa |
|     Aktor_Utama     |                              Mahasiswa                              |
|       Pemicu        |     Mahasiswa memilih tombol unduh bukti pada layar konfirmasi      |
|      Prasyarat      |   Pengajuan KRS telah tersimpan dan layar konfirmasi ditampilkan    |
|Pascakondisi_Berhasil|     Berkas bukti pengajuan KRS terunduh ke perangkat mahasiswa      |
| Pascakondisi_Gagal  |              Berkas bukti pengajuan KRS gagal terunduh              |

 <!-- Keputusan KRS -->
 |   Elemen   |                                               Isi                                                |
 |------------|--------------------------------------------------------------------------------------------------|
 |     ID     |                               & Nama SIA-UC06 Proses keputusan KRS                               |
 |   Sumber   |                                        Kebutuhan SIA-R06                                         |
 |   Tujuan   |          Menetapkan persetujuan atau penolakan pengajuan KRS beserta catatan keputusan           |
 |   Aktor    |                                         Utama Dosen wali                                         |
 |   Pemicu   |                       Dosen wali memilih pengajuan KRS mahasiswa bimbingan                       |
 | Prasyarat  |  Dosen wali terautentikasi; terdapat pengajuan KRS berstatus "Menunggu persetujuan dosen wali"   |
 |Pascakondisi|Berhasil Status KRS diperbarui menjadi "Disetujui" atau "Ditolak" dan catatan keputusan tersimpan |
 |Pascakondisi|                            GagalStatus KRS tidak mengalami perubahan                             |


