<!-- Laporan Uji Konsistensi -->

**1. Situasi A: Validasi Berhasil & Mahasiswa Tidak Mengunduh Bukti**[cite: 16]
* **Ekspektasi Skenario**: KRS tersimpan, bukti tidak diunduh, dan pengajuan tetap sukses[cite: 14].
* **Hasil pada Diagram**: `SIA-UC03` memanggil `SIA-UC04` melalui `<<include>>`[cite: 13, 14]. `SIA-UC05` tidak dipicu karena relasi `<<extend>>` bersifat opsional[cite: 4, 13, 14].
* **Hasil pada Deskripsi**: Alur utama `SIA-UC03` selesai di langkah 6[cite: 14, 15]. Extension point tercapai tanpa mengeksekusi `SIA-UC05`[cite: 14, 15].
* **Status**: Konsisten[cite: 16].

**2. Situasi B: Validasi Gagal**[cite: 16]
* **Ekspektasi Skenario**: Pengajuan dibatalkan, pesan kesalahan muncul, dan KRS tidak tersimpan[cite: 14].
* **Hasil pada Diagram**: `SIA-UC03` wajib memanggil `SIA-UC04` (`<<include>>`)[cite: 3, 13, 14]. Extension point `SIA-UC05` tidak pernah tercapai[cite: 10, 14].
* **Hasil pada Deskripsi**: Alur beralih ke alur alternatif 3a pada `SIA-UC03`[cite: 14, 15]. Proses berakhir pada pascakondisi gagal[cite: 14, 15].
* **Status**: Konsisten[cite: 16].

**3. Situasi C: Validasi Berhasil & Mahasiswa Memilih Mengunduh Bukti**[cite: 16]
* **Ekspektasi Skenario**: KRS tersimpan dan berkas bukti berhasil diunduh[cite: 14].
* **Hasil pada Diagram**: `SIA-UC03` memanggil `SIA-UC04` (`<<include>>`)[cite: 13, 14]. Kondisi `[mahasiswa memilih mengunduh bukti]` terpenuhi sehingga memicu `SIA-UC05` (`<<extend>>`)[cite: 4, 13, 14].
* **Hasil pada Deskripsi**: Alur utama `SIA-UC03` mencapai extension point pada langkah 5[cite: 14, 15], lalu mengeksekusi alur utama `SIA-UC05`[cite: 14, 15].
* **Status**: Konsisten[cite: 16].