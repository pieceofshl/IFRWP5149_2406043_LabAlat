# P04 - Skenario Tugas Sistem Informasi Akademik: Layanan Hasil Studi

| Metadata | Keterangan |
|---|---|
| Pertemuan | 4 - Generalization dan Collaboration |
| Kasus | Sistem Informasi Akademik, Layanan Hasil Studi |
| Versi | v01 |
| Kebutuhan | `P04_SIA_kebutuhan_v01.md` |
| Diagram | `P04_2406043_SIA_usecase_v01.drawio` dan `.png` |

## 1. Deskripsi skenario

Mahasiswa dan dosen sama-sama merupakan **Civitas Akademika** yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, **Input Nilai Mata Kuliah** dan **Lihat KHS**, ditunjukkan realisasinya oleh collaboration yang bersesuaian.

Diagram Pertemuan 4 bersifat kumulatif: fungsi jadwal kuliah dari Pertemuan 2 dan fungsi KRS dari Pertemuan 3 tetap digambar; elemen baru ditambahkan tanpa menimpa berkas P02/P03.

## 2. Identifikasi aktor

| Aktor | Kedudukan | Tujuan/interaksi | Sumber |
|---|---|---|---|
| Civitas Akademika | Aktor umum (*general*), baru P04 | Melihat kalender akademik; asosiasi ini diwariskan kepada Mahasiswa dan Dosen. | SIA-R07 |
| Mahasiswa | Aktor khusus dari Civitas Akademika; aktor lama | Melihat jadwal kuliah, mengajukan KRS, memilih unduh bukti pengajuan, dan melihat KHS; mewarisi akses kalender akademik. | SIA-R01, SIA-R03, SIA-R05, SIA-R07, SIA-R09 |
| Dosen | Aktor khusus dari Civitas Akademika, baru P04 | Melihat kalender akademik dan menginput nilai mata kuliah yang diampunya. | SIA-R07, SIA-R08 |
| Admin Akademik | Aktor lama dari P02 | Mengelola jadwal kuliah dan mengelola data mahasiswa. | SIA-R02, SIA-R10, SIA-R11 |
| Dosen Wali | Aktor lama dari P03 | Memproses keputusan KRS. Aktor ini tetap terpisah sesuai skenario sebelumnya. | SIA-R06 |

**Keputusan generalization aktor:**

1. Mahasiswa adalah bentuk khusus dari Civitas Akademika karena Mahasiswa dan Dosen berbagi fungsi melihat kalender akademik.
2. Dosen adalah bentuk khusus dari Civitas Akademika dengan alasan yang sama.
3. Asosiasi SIA-UC07 digambar satu kali dari Civitas Akademika. Jangan menambahkan garis langsung Mahasiswa–SIA-UC07 atau Dosen–SIA-UC07 karena keduanya mewarisi fungsi tersebut.
4. Asosiasi lain yang khusus bagi peran masing-masing tetap dibuat langsung: Mahasiswa ke SIA-UC01, SIA-UC03, SIA-UC05, dan SIA-UC09; Dosen ke SIA-UC08; Admin Akademik ke SIA-UC02 dan SIA-UC10; Dosen Wali ke SIA-UC06.

## 3. Katalog use case kumulatif

| ID | Nama use case | Aktor terkait/peran | Sumber kebutuhan | Status dalam model |
|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap dari P02 |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap dari P02 |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03; terkait SIA-R04 dan SIA-R05 | Tetap dari P03 |
| SIA-UC04 | Validasi KRS | Perilaku sistem yang disertakan SIA-UC03 | SIA-R04 | Tetap dari P03 |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap dari P03 |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap dari P03 |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru P04 |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08 | Baru P04; direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09 | Baru P04; direalisasikan SIA-CO02 |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10, SIA-R11 | Baru P04; use case umum |
| SIA-UC11 | Tambah Data Mahasiswa | Bentuk khusus SIA-UC10 | SIA-R11 | Baru P04 |
| SIA-UC12 | Ubah Data Mahasiswa | Bentuk khusus SIA-UC10 | SIA-R11 | Baru P04 |
| SIA-UC13 | Hapus Data Mahasiswa | Bentuk khusus SIA-UC10 | SIA-R11 | Baru P04 |

### Perilaku pembeda generalization use case

| Use case khusus | Use case umum | Perilaku pembeda |
|---|---|---|
| SIA-UC11 - Tambah Data Mahasiswa | SIA-UC10 - Kelola Data Mahasiswa | Membuat dan menyimpan data mahasiswa baru. |
| SIA-UC12 - Ubah Data Mahasiswa | SIA-UC10 - Kelola Data Mahasiswa | Memperbarui data mahasiswa yang sudah terdaftar. |
| SIA-UC13 - Hapus Data Mahasiswa | SIA-UC10 - Kelola Data Mahasiswa | Menghapus data mahasiswa hanya jika mahasiswa tidak memiliki data akademik aktif. |

Panah generalization untuk ketiga use case khusus berawal dari use case khusus dan menunjuk ke SIA-UC10. Aktor Admin Akademik cukup dihubungkan dengan use case umum SIA-UC10; hubungan aktor tidak perlu digambar ulang ke setiap use case khusus.

## 4. Relasi use case lama yang tetap dipertahankan

| Sumber | Relasi | Tujuan | Ketentuan |
|---|---|---|---|
| SIA-UC03 - Ajukan KRS | `«include»` | SIA-UC04 - Validasi KRS | Setiap pengajuan menjalankan validasi kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Panah menuju SIA-UC04. |
| SIA-UC05 - Unduh Bukti Pengajuan KRS | `«extend»` | SIA-UC03 - Ajukan KRS | Kondisi: `[Mahasiswa memilih mengunduh bukti]`. Extension point pada SIA-UC03: **Konfirmasi penyimpanan tersedia**. Panah menuju SIA-UC03. |

## 5. Collaboration dan realization

| ID collaboration | Nama collaboration (sama persis dengan use case) | Use case yang direalisasikan | Kebutuhan |
|---|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 - Input Nilai Mata Kuliah | SIA-R08, SIA-R12 |
| SIA-CO02 | Lihat KHS | SIA-UC09 - Lihat KHS | SIA-R09, SIA-R12 |

Masing-masing collaboration digambar sebagai elips bergaris putus-putus di dalam batas sistem. Hubungan realization juga bergaris putus-putus dengan segitiga kosong yang menunjuk ke use case. Aktor tidak dihubungkan langsung dengan collaboration.

## 6. Ringkasan hubungan diagram

| No. | Sumber | Hubungan | Tujuan |
|---:|---|---|---|
| 1 | Mahasiswa | Association | SIA-UC01 - Lihat Jadwal Kuliah |
| 2 | Mahasiswa | Association | SIA-UC03 - Ajukan KRS |
| 3 | Mahasiswa | Association | SIA-UC05 - Unduh Bukti Pengajuan KRS |
| 4 | Mahasiswa | Association | SIA-UC09 - Lihat KHS |
| 5 | Civitas Akademika | Association | SIA-UC07 - Lihat Kalender Akademik |
| 6 | Dosen | Association | SIA-UC08 - Input Nilai Mata Kuliah |
| 7 | Admin Akademik | Association | SIA-UC02 - Kelola Jadwal Kuliah |
| 8 | Admin Akademik | Association | SIA-UC10 - Kelola Data Mahasiswa |
| 9 | Dosen Wali | Association | SIA-UC06 - Proses Keputusan KRS |
| 10 | Mahasiswa | Generalization | Civitas Akademika |
| 11 | Dosen | Generalization | Civitas Akademika |
| 12 | SIA-UC03 - Ajukan KRS | `«include»` | SIA-UC04 - Validasi KRS |
| 13 | SIA-UC05 - Unduh Bukti Pengajuan KRS | `«extend»` | SIA-UC03 - Ajukan KRS |
| 14 | SIA-UC11 - Tambah Data Mahasiswa | Generalization | SIA-UC10 - Kelola Data Mahasiswa |
| 15 | SIA-UC12 - Ubah Data Mahasiswa | Generalization | SIA-UC10 - Kelola Data Mahasiswa |
| 16 | SIA-UC13 - Hapus Data Mahasiswa | Generalization | SIA-UC10 - Kelola Data Mahasiswa |
| 17 | SIA-CO01 | Realization | SIA-UC08 - Input Nilai Mata Kuliah |
| 18 | SIA-CO02 | Realization | SIA-UC09 - Lihat KHS |

## 7. Pemeriksaan konsistensi

- [ ] Mahasiswa dan Dosen mewarisi kalender akademik dari Civitas Akademika; tidak ada asosiasi langsung mereka ke SIA-UC07.
- [ ] Dosen yang bukan pengampu tidak dapat menginput nilai untuk mata kuliah tersebut.
- [ ] Nilai di luar rentang sah ditolak; rentang angka tidak ditetapkan sendiri di artefak ini.
- [ ] KHS hanya menampilkan nilai yang sudah dipublikasikan.
- [ ] Admin Akademik tidak dapat menghapus mahasiswa yang masih memiliki data akademik aktif.
- [ ] Panah generalization mengarah dari khusus ke umum.
- [ ] Panah realization mengarah dari collaboration ke use case.
- [ ] Aktor berada di luar batas sistem; use case dan collaboration di dalam batas sistem.
- [ ] Tidak ada panah langsung dari aktor ke collaboration.
- [ ] Nama dan ID di katalog, deskripsi, dan diagram sama persis.
