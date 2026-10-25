# Model Analisis Use Case - Sistem Informasi Akademik (Layanan Hasil Studi)

| Metadata | Keterangan |
|---|---|
| Artefak | Model analisis / katalog use case |
| Kasus | Sistem Informasi Akademik - Layanan Hasil Studi |
| Versi | v01 |
| Diagram terkait | `P04_2406043_SIA_usecase_v01.drawio` dan `P04_2406043_SIA_usecase_v01.png` |
| Deskripsi terkait | `P04_2406043_SIA_deskripsi_v01.md` |
| Sumber utama | Jobsheet Praktikum Pertemuan 4, bagian tugas SIA |

## 1. Batas sistem

Batas sistem pada diagram bernama **Sistem Informasi Akademik - Layanan Hasil Studi**. Diagram bersifat kumulatif dan memuat fungsi jadwal kuliah dari P02, fungsi KRS dari P03, serta layanan hasil studi dan pengelolaan data mahasiswa yang ditambahkan pada P04.

## 2. Aktor dan use case yang diakses

| Aktor | Kedudukan | Use case terkait |
|---|---|---|
| Civitas Akademika | Aktor umum | SIA-UC07 Lihat Kalender Akademik |
| Mahasiswa | Aktor khusus dari Civitas Akademika | SIA-UC01 Lihat Jadwal Kuliah; SIA-UC03 Ajukan KRS; SIA-UC05 Unduh Bukti Pengajuan KRS; SIA-UC09 Lihat KHS. Akses kalender diwarisi dari Civitas Akademika. |
| Dosen | Aktor khusus dari Civitas Akademika | SIA-UC08 Input Nilai Mata Kuliah. Akses kalender diwarisi dari Civitas Akademika. |
| Admin Akademik | Aktor P02 yang dipertahankan | SIA-UC02 Kelola Jadwal Kuliah; SIA-UC10 Kelola Data Mahasiswa |
| Dosen Wali | Aktor P03 yang dipertahankan | SIA-UC06 Proses Keputusan KRS |

## 3. Katalog dan keterlacakan kebutuhan

| ID | Nama use case | Aktor/peran | Sumber kebutuhan | Status |
|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap P02 |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap P02 |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03, terkait SIA-R04 dan SIA-R05 | Tetap P03 |
| SIA-UC04 | Validasi KRS | Disertakan SIA-UC03 | SIA-R04 | Tetap P03 |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap P03 |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap P03 |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru P04 |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08, SIA-R12 | Baru P04 |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09, SIA-R12 | Baru P04 |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10, SIA-R11 | Baru P04; umum |
| SIA-UC11 | Tambah Data Mahasiswa | Khusus dari SIA-UC10 | SIA-R11 | Baru P04 |
| SIA-UC12 | Ubah Data Mahasiswa | Khusus dari SIA-UC10 | SIA-R11 | Baru P04 |
| SIA-UC13 | Hapus Data Mahasiswa | Khusus dari SIA-UC10 | SIA-R11 | Baru P04 |

## 4. Hubungan pada diagram

| No. | Sumber | Jenis hubungan | Tujuan | Arah/aturan |
|---:|---|---|---|---|
| 1 | Mahasiswa | Association | SIA-UC01 | Langsung |
| 2 | Mahasiswa | Association | SIA-UC03 | Langsung |
| 3 | Mahasiswa | Association | SIA-UC05 | Langsung; fungsi tambahan khusus Mahasiswa |
| 4 | Mahasiswa | Association | SIA-UC09 | Langsung |
| 5 | Civitas Akademika | Association | SIA-UC07 | Langsung; fungsi bersama diwariskan |
| 6 | Dosen | Association | SIA-UC08 | Langsung |
| 7 | Admin Akademik | Association | SIA-UC02 | Langsung |
| 8 | Admin Akademik | Association | SIA-UC10 | Langsung |
| 9 | Dosen Wali | Association | SIA-UC06 | Langsung |
| 10 | Mahasiswa | Generalization | Civitas Akademika | Segitiga kosong menunjuk aktor umum |
| 11 | Dosen | Generalization | Civitas Akademika | Segitiga kosong menunjuk aktor umum |
| 12 | SIA-UC03 - Ajukan KRS | `«include»` | SIA-UC04 - Validasi KRS | Setiap pengajuan menjalankan validasi |
| 13 | SIA-UC05 - Unduh Bukti Pengajuan KRS | `«extend»` | SIA-UC03 - Ajukan KRS | Kondisi `[Mahasiswa memilih mengunduh bukti]`; extension point `Konfirmasi penyimpanan tersedia` |
| 14 | SIA-UC11 - Tambah Data Mahasiswa | Generalization | SIA-UC10 - Kelola Data Mahasiswa | Segitiga kosong menunjuk use case umum |
| 15 | SIA-UC12 - Ubah Data Mahasiswa | Generalization | SIA-UC10 - Kelola Data Mahasiswa | Segitiga kosong menunjuk use case umum |
| 16 | SIA-UC13 - Hapus Data Mahasiswa | Generalization | SIA-UC10 - Kelola Data Mahasiswa | Segitiga kosong menunjuk use case umum |
| 17 | SIA-CO01 - Input Nilai Mata Kuliah | Realization | SIA-UC08 - Input Nilai Mata Kuliah | Garis putus-putus, segitiga kosong di use case |
| 18 | SIA-CO02 - Lihat KHS | Realization | SIA-UC09 - Lihat KHS | Garis putus-putus, segitiga kosong di use case |

Total hubungan pada diagram: **18** (9 asosiasi, 2 generalization aktor, 1 include, 1 extend, 3 generalization use case, dan 2 realization).

## 5. Keputusan pemodelan

### Generalization aktor

Mahasiswa dan Dosen adalah bentuk khusus dari Civitas Akademika karena sama-sama dapat melihat kalender akademik. Asosiasi ke SIA-UC07 hanya digambar dari Civitas Akademika. Panah generalization mengarah dari aktor khusus ke aktor umum. Dosen Wali tidak dibuat sebagai specialization dari Dosen karena tugas hanya memerintahkan Civitas Akademika sebagai aktor umum dengan Mahasiswa dan Dosen sebagai dua specialization-nya.

### Generalization use case

SIA-UC10 Kelola Data Mahasiswa adalah use case umum. SIA-UC11 menambah data baru, SIA-UC12 mengubah data yang ada, dan SIA-UC13 menghapus data hanya jika tidak terdapat data akademik aktif. Ketiga panah dimulai dari use case khusus dan berakhir pada SIA-UC10.

### Collaboration dan realization

SIA-CO01 bernama **Input Nilai Mata Kuliah** dan merealisasikan SIA-UC08. SIA-CO02 bernama **Lihat KHS** dan merealisasikan SIA-UC09. Nama collaboration sama persis dengan nama use case yang diwujudkan. Tidak ada asosiasi aktor ke collaboration.

## 6. Batas perilaku yang tidak boleh ditafsirkan berlebihan

- SIA-UC01 Lihat Jadwal Kuliah dan SIA-UC07 Lihat Kalender Akademik adalah dua tujuan berbeda.
- SIA-UC08 hanya boleh dijalankan Dosen pengampu setelah masa perkuliahan berakhir. Nilai baru tidak otomatis menjadi nilai yang telah dipublikasikan.
- SIA-UC09 hanya menampilkan nilai yang sudah dipublikasikan.
- SIA-UC13 tidak boleh menghapus data mahasiswa yang memiliki data akademik aktif.
- Jobsheet tidak memberikan angka rentang nilai yang sah atau rincian alur pengesahan/publikasi. Diagram dan deskripsi tidak menetapkan angka atau langkah tambahan tersebut.

## 7. Checklist review

- [ ] Seluruh UC01-UC06 dipertahankan dari P02/P03.
- [ ] Kedua relasi lama `«include»` dan `«extend»` tetap ada dengan arah, condition, dan extension point yang benar.
- [ ] Dua panah aktor-specialization menunjuk Civitas Akademika.
- [ ] Tiga panah use case specialization menunjuk SIA-UC10.
- [ ] Kedua realization berasal dari collaboration dan menuju use case masing-masing.
- [ ] Nama collaboration sama persis dengan nama use case.
- [ ] Collaboration dan use case berada di dalam batas sistem; aktor di luar batas sistem.
- [ ] Tidak ada aktor yang dihubungkan langsung ke collaboration.
- [ ] Kondisi penginputan dan tampilan nilai konsisten dengan kebutuhan.
- [ ] Diagram Draw.io dapat dibuka kembali dan PNG diekspor dari versi sumber yang sama.
- [ ] Berkas P02/P03 asli tidak diubah; jika ada revisi hasil review, simpan v02 dan catat perubahannya.
