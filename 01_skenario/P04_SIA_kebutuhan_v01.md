# P04 - Kebutuhan Tugas Sistem Informasi Akademik: Layanan Hasil Studi

| Metadata | Keterangan |
|---|---|
| Mata kuliah | Praktikum Analisis dan Desain Berorientasi Objek |
| Pertemuan | 4 - Generalization dan Collaboration |
| Kasus | Sistem Informasi Akademik, Layanan Hasil Studi |
| Versi | v01 |
| Sumber utama | Jobsheet Praktikum Pertemuan 4, bagian 4, halaman 63-67 |

## 1. Deskripsi skenario

Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, **Input Nilai Mata Kuliah** dan **Lihat KHS**, ditunjukkan realisasinya oleh collaboration yang bersesuaian.

## 2. Kebutuhan baru Pertemuan 4

| ID | Kebutuhan |
|---|---|
| SIA-R07 | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik. |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan. |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa. |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS. |

## 3. Kebutuhan dari pertemuan sebelumnya

Kebutuhan berikut tetap berlaku dan identitasnya tidak diganti. Keterangan lengkapnya mengacu ke artefak Pertemuan 2 dan Pertemuan 3 di repository.

| ID | Kebutuhan yang dipertahankan | Asal |
|---|---|---|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah. | Pertemuan 2 |
| SIA-R02 | Admin Akademik dapat mengelola jadwal kuliah. | Pertemuan 2 |
| SIA-R03 | Mahasiswa dapat mengajukan KRS. | Pertemuan 3 |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian dari pengajuan. | Pertemuan 3 |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. | Pertemuan 3 |
| SIA-R06 | Dosen Wali dapat memproses persetujuan atau penolakan KRS. | Pertemuan 3 |

## 4. Batas sistem dan asumsi

- Pengguna telah terautentikasi dan memiliki hak akses sesuai perannya.
- Kalender akademik adalah agenda resmi institusi, misalnya awal semester, batas KRS, dan masa ujian. Kalender akademik **berbeda** dari jadwal kuliah SIA-R01.
- Nilai hanya dapat diinput oleh Dosen pengampu mata kuliah terkait setelah masa perkuliahan berakhir.
- Nilai yang baru diinput belum dianggap dipublikasikan. KHS hanya menampilkan nilai yang statusnya sudah dipublikasikan secara resmi.
- Hapus Data Mahasiswa hanya diperbolehkan bagi mahasiswa yang tidak memiliki data akademik aktif. Aturan ini bersifat fiktif untuk latihan.
- Fungsi jadwal kuliah dan fungsi KRS tetap ada pada diagram kumulatif. Pembayaran dan perancangan basis data berada di luar tugas ini.
- Rentang nilai yang sah dan mekanisme resmi publikasi nilai tidak diberi nilai angka/prosedur khusus oleh jobsheet. Gunakan aturan institusi yang berlaku; jangan menambahkan rentang angka atau alur publikasi yang tidak bersumber dari tugas.

## 5. Skenario uji konsistensi yang diwajibkan

| Situasi | Kondisi | Hasil yang harus terjadi |
|---|---|---|
| A | Mahasiswa melihat kalender akademik tanpa asosiasi langsung dari aktor Mahasiswa ke SIA-UC07. | Benar. Mahasiswa mewarisi asosiasi SIA-UC07 dari aktor umum Civitas Akademika melalui generalization; asosiasi tidak digambar ulang dari Mahasiswa. |
| B | Dosen yang bukan pengampu mata kuliah mencoba menginput nilai. | Sistem menolak operasi untuk mata kuliah tersebut. Tidak ada nilai baru yang tersimpan dari operasi yang ditolak dan data yang sudah ada tidak berubah. |
| C | Admin Akademik menghapus data mahasiswa yang masih memiliki data akademik aktif. | Sistem menolak penghapusan dan mempertahankan data mahasiswa. |

## 6. Kriteria penerimaan

- Diagram kumulatif memuat SIA-UC01 sampai SIA-UC13 tanpa mengubah nama/arti use case lama.
- SIA-UC01 dan SIA-UC02 (jadwal), serta SIA-UC03 sampai SIA-UC06 (KRS), tetap ada.
- Mahasiswa dan Dosen merupakan aktor khusus dari Civitas Akademika; panah generalization berujung pada Civitas Akademika.
- SIA-UC11, SIA-UC12, dan SIA-UC13 merupakan bentuk khusus dari SIA-UC10; panah generalization berujung pada SIA-UC10.
- SIA-UC03 menyertakan SIA-UC04 dengan `«include»`; SIA-UC05 memperluas SIA-UC03 dengan `«extend»`, kondisi, dan extension point yang tetap dicantumkan.
- SIA-CO01 merealisasikan SIA-UC08 dan SIA-CO02 merealisasikan SIA-UC09. Nama collaboration harus sama persis dengan nama use case yang direalisasikan dan tidak terhubung langsung ke aktor.
- Aktor berada di luar batas sistem; use case dan collaboration berada di dalam batas sistem.
- Katalog, deskripsi, diagram Draw.io, dan ekspor PNG memiliki ID serta nama yang konsisten.
- Berkas P02/P03 asli tidak ditimpa. Jika hasil review mengubah isi, simpan sebagai v02 dan catat perubahan.
