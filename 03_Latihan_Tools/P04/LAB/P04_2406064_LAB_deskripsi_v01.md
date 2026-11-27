|            Elemen LAB-UC11: Catat Pengembalian Peralatan            |
|---------------------------------------------------------------------|
|                          Sumber kebutuhan                           |
|                         LAB-R09 dan LAB-R10                         |
|                               Tujuan                                |
|                             Aktor utama                             |
|      Pengembalian tercatat dan status peminjaman serta kondisi      |
|                         peralatan terbarui                          |
|                        Petugas Laboratorium                         |
|                               Pemicu                                |
|         Petugas memilih fungsi pencatatan pengembalian dan          |
|            menentukan peminjaman yang akan dikembalikan             |
|                              Prasyarat                              |
|     Petugas telah terautentikasi; peminjaman terpilih berstatus     |
|                              Dipinjam                               |
|                            Pascakondisi                             |
|                              berhasil                               |
|      Pengembalian tercatat dengan tanggal kembali dan kondisi       |
|            peralatan; status peminjaman menjadi Selesai             |
|Pascakondisi gagal Tidak ada pengembalian baru yang tercatat; status |
|                      peminjaman tidak berubah                       |
|                               Include                               |
|                            Collaboration                            |
|                 LAB-UC12: Periksa Kondisi Peralatan                 |
|               LAB-CO02: Catat Pengembalian Peralatan                |


|             Alur utama              |
|-------------------------------------|
|               Langkah               |
|          Tindakan petugas           |
|                  1                  |
|    Memilih peminjaman yang akan     |
|            dikembalikan             |
|           Respons sistem            |
|Menampilkan data peminjaman terpilih |
|            dan statusnya            |
|                  2                  |
|   Mengonfirmasi alat yang kembali   |
|            dan jumlahnya            |
|    Menampung konfirmasi petugas     |
|                  3                  |
|              Tidak ada              |
|  Memeriksa status peminjaman harus  |
|              Dipinjam               |
|                  4                  |
|              Tidak ada              |
|   Menjalankan LAB-UC12: memeriksa   |
|   dan mencatat kondisi peralatan    |
|                  5                  |
|        Menyimpan pencatatan         |
|            pengembalian             |
|    Menyimpan tanggal kembali dan    |
| kondisi; mengubah status peminjaman |
|           menjadi Selesai           |
|                  6                  |
|         Melihat konfirmasi          |
|  Alur alternatif atau pengecualian  |
| Menampilkan ringkasan pengembalian  |
