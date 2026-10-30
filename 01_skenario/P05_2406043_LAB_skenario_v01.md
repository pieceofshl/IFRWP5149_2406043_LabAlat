# P05 - Lembar Telaah 12 Tabel Skenario Studi Kasus LAB

| Metadata | Keterangan |
|---|---|
| Pertemuan | 5 - Skenario Use Case: dari Diagram ke Langkah Kegiatan |
| Kasus | Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus |
| NIM | 2406043 |
| Versi | v01 |
| Tanggal | 30 Oktober 2026 |
| Diagram acuan | `03_latihan_tools/P04/LAB/P04_2406043_LAB_usecase_v01.drawio` (berkas yang tersedia di repository; tidak diubah) |
| Dokumen jobsheet acuan | `Jobsheet Praktikum Pertemuan 5.md`, bagian C.2 dan C.4 |
| Kebutuhan acuan | LAB-R01 sampai LAB-R11 (`P04_LAB_kebutuhan_v01.md`) |

Dokumen ini adalah **lembar telaah**, bukan penulisan ulang tabel. Kedua belas tabel skenario
studi kasus sudah dimuat lengkap pada Jobsheet Pertemuan 5 bagian C.2 (Tabel 5.1 dan Tabel 5.3
sampai Tabel 5.13), sehingga pekerjaan pada studi kasus adalah mencocokkan setiap tabel dengan
diagram kumulatif Pertemuan 4, bukan menyalin tabel tersebut ke dokumen ini. Diagram P04 tidak
diubah dan tidak ada diagram baru pada Pertemuan 5.

## 1. Ringkasan acuan yang diperiksa

Sebelum membaca tabel, diagram kumulatif P04 diperiksa ulang: **5 aktor**, **12 use case**,
**2 collaboration**, dan **17 hubungan**.

Catatan lokasi berkas: jobsheet menyebut diagram acuan berada pada
`04_model_analisis/P04/LAB/P04_2406043_LAB_usecase_v01.drawio`, tetapi pada repository folder
tersebut baru memuat `P04_2406043_LAB_model_analisis_v01.md`. Berkas diagram LAB yang tersedia
adalah `03_latihan_tools/P04/LAB/P04_2406043_LAB_usecase_v01.drawio`, sehingga berkas itulah yang
dipakai sebagai acuan gambar; daftar 17 hubungan tetap mengikuti Tabel 4.5 pada model analisis P04.
Berkas tersebut tidak diubah pada Pertemuan 5.

| Aktor | Kedudukan | Use case yang diasosiasikan |
|---|---|---|
| Peminjam | Aktor umum (general) | LAB-UC01, LAB-UC03 |
| Mahasiswa | Khusus dari Peminjam | LAB-UC05 (asosiasi khusus) |
| Dosen | Khusus dari Peminjam | - (mewarisi LAB-UC01 dan LAB-UC03) |
| Petugas Laboratorium | Aktor tetap | LAB-UC02, LAB-UC06, LAB-UC11 |
| Kepala Laboratorium | Aktor tetap | LAB-UC07 |

| No. | Sumber | Hubungan | Tujuan |
|---:|---|---|---|
| 1 | Peminjam | Association | LAB-UC01 Lihat Ketersediaan Peralatan |
| 2 | Peminjam | Association | LAB-UC03 Ajukan Peminjaman |
| 3 | Mahasiswa | Association (khusus) | LAB-UC05 Cetak Bukti Pengajuan |
| 4 | Mahasiswa | Generalization | Peminjam |
| 5 | Dosen | Generalization | Peminjam |
| 6 | Petugas Laboratorium | Association | LAB-UC02 Kelola Data Peralatan |
| 7 | Petugas Laboratorium | Association | LAB-UC06 Proses Keputusan Peminjaman |
| 8 | Petugas Laboratorium | Association | LAB-UC11 Catat Pengembalian Peralatan |
| 9 | Kepala Laboratorium | Association | LAB-UC07 Lihat Laporan Peminjaman |
| 10 | LAB-UC03 Ajukan Peminjaman | `<<include>>` | LAB-UC04 Periksa Ketersediaan |
| 11 | LAB-UC05 Cetak Bukti Pengajuan | `<<extend>>` | LAB-UC03 Ajukan Peminjaman |
| 12 | LAB-UC08 Tambah Data Peralatan | Generalization | LAB-UC02 Kelola Data Peralatan |
| 13 | LAB-UC09 Ubah Data Peralatan | Generalization | LAB-UC02 Kelola Data Peralatan |
| 14 | LAB-UC10 Hapus Data Peralatan | Generalization | LAB-UC02 Kelola Data Peralatan |
| 15 | LAB-UC11 Catat Pengembalian Peralatan | `<<include>>` | LAB-UC12 Periksa Kondisi Peralatan |
| 16 | LAB-CO01 Ajukan Peminjaman | Realization | LAB-UC03 Ajukan Peminjaman |
| 17 | LAB-CO02 Catat Pengembalian Peralatan | Realization | LAB-UC11 Catat Pengembalian Peralatan |

Keterangan relasi `<<extend>>` nomor 11 yang tertulis pada diagram: condition
`[mahasiswa memilih cetak]` dan extension point **Bukti pengajuan tersedia**.

## 2. Legenda butir checklist (bagian C.4 jobsheet)

| Kode | Butir checklist |
|---|---|
| C1 | Seluruh field tabel terisi (Nama use case, Aktor, Tujuan, Deskripsi, kolom Kegiatan dan Respon sistem, Skenario Normal, Skenario Alternative, Skenario Akhir) |
| C2 | Langkah berurutan, satu aksi per langkah, penomoran berlanjut dari Skenario Normal ke Skenario Alternative |
| C3 | Kolom Kegiatan hanya aksi aktor, kolom Respon sistem hanya tanggapan sistem |
| C4 | Data yang dimasukkan/ditampilkan disebut eksplisit (nama field, nilai, atau status) |
| C5 | Include ditulis sebagai langkah rujukan pada Skenario Normal dengan nama, ID, dan tabel skenario, tanpa menyalin langkahnya |
| C6 | Extend ditulis sebagai cabang pada Skenario Alternative lengkap dengan condition dan extension point, serta rujukan ke tabel skenario tambahan |
| C7 | Generalization aktor: skenario aktor umum ditulis satu kali ditambah catatan aktor khusus, tanpa tabel ganda |
| C8 | Generalization use case: skenario umum memuat perilaku bersama, skenario khusus memuat perilaku pembeda dan merujuk skenario umum |
| C9 | Collaboration disebut pada keterangan tabel use case yang direalisasikannya dan tidak diberi langkah kegiatan sendiri |
| C10 | Setiap tabel mempunyai Skenario Alternative dan Skenario Akhir |
| C11 | Nama, ID, aktor, condition, dan extension point sama persis dengan diagram kumulatif P04 |
| C12 | Catatan Kepala Laboratorium: LAB-UC07 berdiri sendiri tanpa include, extend, generalization, atau realization |
| C13 | Berkas diagram P04 tidak diubah; dokumen skenario disimpan pada `01_skenario` dengan nama dan versi yang benar |

## 3. Lembar telaah per tabel

### 3.1 Tabel 5.1 - LAB-UC03 Ajukan Peminjaman (kelompok peminjaman)

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Nama, Aktor, Tujuan, Deskripsi, kolom, kedua bagian skenario, dan Skenario Akhir terisi. |
| C2 | Sesuai | 12 langkah, satu aksi per langkah; nomor 1-6 (normal) dilanjutkan 7-12 (alternative) tanpa pengulangan. |
| C3 | Sesuai | Langkah 1, 3, 5 pada kolom Kegiatan; langkah 2, 4, 6 pada kolom Respon sistem. |
| C4 | Sesuai | Disebut eksplisit: tanggal pinjam, tanggal rencana kembali, keperluan peminjaman, status Menunggu Keputusan, nomor pengajuan. |
| C5 | Sesuai | Langkah 2 merujuk Tabel skenario LAB-UC04 Periksa Ketersediaan (relasi 10) tanpa menyalin langkahnya. |
| C6 | Sesuai dengan catatan | Langkah 11-12 merujuk Tabel skenario LAB-UC05 dengan condition `[mahasiswa memilih cetak]` dan extension point Bukti pengajuan tersedia (relasi 11). Lihat temuan F2. |
| C7 | Sesuai | Aktor ditulis Peminjam (berlaku untuk Mahasiswa dan Dosen), sejalan dengan relasi 2, 4, dan 5. Cabang cetak dibatasi hanya untuk mahasiswa (relasi 3). |
| C8 | Tidak berlaku | Bukan use case umum pada generalization use case. |
| C9 | Sesuai dengan catatan | LAB-CO01 disebut pada keterangan tabel tanpa langkah kegiatan (relasi 16), tetapi ditulis "LABCO01" tanpa tanda hubung. Lihat temuan F3. |
| C10 | Sesuai | Skenario Alternative langkah 7-12 dan Skenario Akhir tersedia. |
| C11 | Sesuai | ID dan nama use case sama dengan diagram. Lihat temuan F1 untuk penulisan hasil include sebagai cabang. |
| C12 | Tidak berlaku | Bukan tabel LAB-UC07. |
| C13 | Sesuai | Diagram P04 tidak diubah; dokumen telaah disimpan pada `01_skenario`. |

### 3.2 Tabel 5.3 - LAB-UC01 Lihat Ketersediaan Peralatan

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 4 langkah; nomor 1-2 normal, 3-4 alternative. |
| C3 | Sesuai | Langkah 1 kolom Kegiatan; langkah 2 kolom Respon sistem. |
| C4 | Sesuai | "daftar peralatan beserta status ketersediaannya" disebut eksplisit. |
| C7 | Sesuai | Aktor Peminjam (berlaku untuk Mahasiswa dan Dosen) = relasi 1 ditambah relasi 4 dan 5. Tidak ada tabel ganda untuk Mahasiswa/Dosen. |
| C10 | Sesuai | Alternative langkah 3-4 dan Skenario Akhir tersedia. |
| C11 | Sesuai | ID dan nama use case sama dengan diagram. |
| C5, C6, C8, C9, C12 | Tidak berlaku | LAB-UC01 tidak menyertakan, tidak memperluas, bukan use case umum, tidak direalisasikan collaboration, dan bukan LAB-UC07. |
| C13 | Sesuai | Dokumen telaah berada pada `01_skenario`; diagram tidak diubah. |

### 3.3 Tabel 5.4 - LAB-UC04 Periksa Ketersediaan

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 6 langkah; nomor 1-4 normal, 5-6 alternative. |
| C3 | Sebagian sesuai | Langkah 1 dan 3 menyebut pelaku alur/ sistem pada kolom Kegiatan; dapat diterima karena UC04 adalah perilaku yang disertakan, tetapi lihat temuan F5. |
| C4 | Sesuai | "jumlah dan status peralatan" disebut eksplisit. |
| C5 | Tidak berlaku | UC04 adalah target include (relasi 10), bukan sumber include. |
| C10 | Sesuai | Alternative langkah 5-6 dan Skenario Akhir tersedia. |
| C11 | Sesuai dengan catatan | ID dan nama sama; baris Aktor "Peminjam (berjalan di dalam LAB-UC03)" bertentangan dengan Deskripsi yang menyatakan tidak ada interaksi langsung dengan aktor. Lihat temuan F5. |
| C6, C7, C8, C9, C12 | Tidak berlaku | Tidak ada extend, bukan aktor umum, bukan use case umum, tidak direalisasikan, bukan LAB-UC07. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.4 Tabel 5.5 - LAB-UC05 Cetak Bukti Pengajuan

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 6 langkah; nomor 1-4 normal, 5-6 alternative. |
| C3 | Sesuai | Langkah 1 dan 3 kolom Kegiatan; langkah 2 dan 4 kolom Respon sistem. |
| C4 | Sesuai | "nomor pengajuan", "status Menunggu Keputusan", "pencetakan" disebut eksplisit. |
| C6 | Sesuai | Baris Deskripsi memuat condition `[mahasiswa memilih cetak]` dan extension point Bukti pengajuan tersedia sesuai relasi 11; tabel ini adalah tabel skenario tambahan yang dirujuk Tabel 5.1. |
| C11 | Sesuai | Aktor Mahasiswa sejalan dengan asosiasi khusus relasi 3; ID dan nama sama dengan diagram. |
| C5, C7, C8, C9, C12 | Tidak berlaku | Tidak menyertakan use case lain, bukan aktor umum, bukan use case umum, tidak direalisasikan, bukan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 5-6 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.5 Tabel 5.6 - LAB-UC02 Kelola Data Peralatan (kelompok pengelolaan data)

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 10 langkah; nomor 1-8 normal, 9-10 alternative. |
| C3 | Sesuai | Langkah 1, 3, 5, 7 kolom Kegiatan; langkah 2, 4, 6, 8 kolom Respon sistem. |
| C4 | Sesuai | "bentuk pengelolaan, yaitu tambah, ubah, atau hapus" dan "konfirmasi" disebut eksplisit. |
| C8 | Sesuai | Perilaku bersama ditulis sekali; bentuk khusus tidak dijabarkan di sini, tetapi dirujuk ke tabel khususnya. Sejalan dengan relasi 12-14. |
| C11 | Sesuai | Aktor Petugas Laboratorium sejalan dengan relasi 6; ID dan nama sama dengan diagram. |
| C5, C6, C7, C9, C12 | Tidak berlaku | Tidak ada include, extend, aktor umum, collaboration, atau keterkaitan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 9-10 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.6 Tabel 5.7 - LAB-UC08 Tambah Data Peralatan

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 8 langkah; nomor 1-6 normal, 7-8 alternative. |
| C3 | Sesuai | Langkah 1, 3, 5 kolom Kegiatan; langkah 2, 4, 6 kolom Respon sistem. |
| C4 | Sesuai | "data peralatan baru" dan "konfirmasi" disebut eksplisit. |
| C8 | Sesuai | Generalization use case dari LAB-UC02 (relasi 12): keterangan menyebut use case khusus, perilaku pembeda "data baru tersimpan", dan langkah bersama merujuk Tabel skenario LAB-UC02. |
| C11 | Sesuai | ID dan nama sama dengan diagram; aktor Petugas Laboratorium diwarisi dari asosiasi ke use case umum. |
| C5, C6, C7, C9, C12 | Tidak berlaku | Tidak ada include, extend, aktor umum, collaboration, atau keterkaitan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 7-8 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.7 Tabel 5.8 - LAB-UC09 Ubah Data Peralatan

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 8 langkah; nomor 1-6 normal, 7-8 alternative. |
| C3 | Sesuai | Langkah 1, 3, 5 kolom Kegiatan; langkah 2, 4, 6 kolom Respon sistem. |
| C4 | Sesuai | "data peralatan saat ini" dan "perubahan data" disebut eksplisit. |
| C8 | Sesuai | Generalization use case dari LAB-UC02 (relasi 13): perilaku pembeda "data peralatan berubah" dan rujukan ke Tabel skenario LAB-UC02 tertulis pada keterangan. |
| C11 | Sesuai | ID dan nama sama dengan diagram. |
| C5, C6, C7, C9, C12 | Tidak berlaku | Tidak ada include, extend, aktor umum, collaboration, atau keterkaitan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 7-8 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.8 Tabel 5.9 - LAB-UC10 Hapus Data Peralatan

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai dengan catatan | Baris Keterangan pada tabel jobsheet tercetak menyatu dengan baris Skenario Akhir sehingga sel tabel tampak bergeser; isi field tetap lengkap. Lihat temuan F6. |
| C2 | Sesuai | 6 langkah; nomor 1-4 normal, 5-6 alternative. |
| C3 | Sesuai | Langkah 1 dan 3 kolom Kegiatan; langkah 2 dan 4 kolom Respon sistem. |
| C4 | Sesuai | Syarat "tidak sedang dipinjam dan tidak memiliki pengajuan aktif" disebut eksplisit. |
| C8 | Sesuai | Generalization use case dari LAB-UC02 (relasi 14): perilaku pembeda "data peralatan terhapus" beserta syaratnya, dan rujukan ke Tabel skenario LAB-UC02. |
| C11 | Sesuai | ID dan nama sama dengan diagram. |
| C5, C6, C7, C9, C12 | Tidak berlaku | Tidak ada include, extend, aktor umum, collaboration, atau keterkaitan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 5-6 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.9 Tabel 5.10 - LAB-UC06 Proses Keputusan Peminjaman (kelompok keputusan dan laporan)

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai dengan catatan | 8 langkah, penomoran berlanjut, tetapi langkah 5 dirujuk sebagai "cabang dari langkah 4" padahal penetapan keputusan terjadi pada langkah 3. Lihat temuan F4. |
| C3 | Sesuai | Langkah 1, 3, 5 kolom Kegiatan; langkah 2, 4, 6 kolom Respon sistem. |
| C4 | Sesuai | Status Menunggu Keputusan, Disetujui, dan Ditolak disebut eksplisit. |
| C11 | Sesuai | Aktor Petugas Laboratorium sejalan dengan relasi 7; ID dan nama sama dengan diagram. |
| C5, C6, C7, C8, C9, C12 | Tidak berlaku | Tidak ada include, extend, aktor umum, generalization use case, collaboration, atau keterkaitan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 5-8 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.10 Tabel 5.11 - LAB-UC07 Lihat Laporan Peminjaman

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 6 langkah; nomor 1-4 normal, 5-6 alternative. |
| C3 | Sesuai | Langkah 1 dan 3 kolom Kegiatan; langkah 2 dan 4 kolom Respon sistem. |
| C4 | Sesuai | "daftar periode laporan", "periode", dan "laporan peminjaman" disebut eksplisit. |
| C12 | Sesuai | Tabel berdiri sendiri: tidak ada langkah include, extend, generalization, maupun realization, sesuai catatan Kepala Laboratorium pada jobsheet. |
| C11 | Sesuai dengan catatan | ID dan nama sama dengan diagram, tetapi aktor Kepala Laboratorium belum tergambar sebagai aktor pada berkas diagram P04 LAB di repository. Lihat temuan F7. |
| C5, C6, C7, C8, C9 | Tidak berlaku | Tidak ada include, extend, aktor umum, generalization use case, atau collaboration. |
| C10 | Sesuai | Alternative langkah 5-6 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.11 Tabel 5.12 - LAB-UC11 Catat Pengembalian Peralatan (kelompok pengembalian)

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi, termasuk prasyarat status Dipinjam pada Deskripsi. |
| C2 | Sesuai | 16 langkah; nomor 1-10 normal dilanjutkan 11-16 alternative tanpa pengulangan nomor. |
| C3 | Tidak sesuai | Langkah 5 "Sistem memeriksa status peminjaman harus Dipinjam" ditulis pada kolom Kegiatan padahal tanggapan sistem. Lihat temuan F8. |
| C4 | Sesuai | Status Dipinjam dan Selesai, tanggal kembali, serta nilai kondisi disebut eksplisit. |
| C5 | Sesuai | Langkah 6 merujuk Tabel skenario LAB-UC12 Periksa Kondisi Peralatan (relasi 15) tanpa menyalin langkahnya. |
| C9 | Sesuai | Keterangan menyebut LAB-CO02 Catat Pengembalian Peralatan tanpa langkah kegiatan sendiri (relasi 17). |
| C11 | Sesuai | Aktor Petugas Laboratorium sejalan dengan relasi 8; ID dan nama sama dengan diagram. |
| C6, C7, C8, C12 | Tidak berlaku | Tidak ada extend, aktor umum, generalization use case, atau keterkaitan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 11-16 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

### 3.12 Tabel 5.13 - LAB-UC12 Periksa Kondisi Peralatan

| Kode | Hasil | Relasi yang ditelusur dan hasil pencocokan |
|---|---|---|
| C1 | Sesuai | Seluruh field terisi. |
| C2 | Sesuai | 6 langkah; nomor 1-4 normal, 5-6 alternative. |
| C3 | Sebagian sesuai | Langkah 1 "Alur pengembalian memanggil Periksa Kondisi Peralatan" dan langkah 3 memuat aksi petugas; keduanya masih menggambarkan alur yang disertakan. Lihat temuan F5. |
| C4 | Sesuai | Nilai kondisi Baik, Rusak Ringan, dan Rusak Berat disebut eksplisit. |
| C5 | Tidak berlaku | UC12 adalah target include (relasi 15), bukan sumber include. |
| C11 | Sesuai dengan catatan | ID dan nama sama dengan diagram; baris Aktor menyebut Petugas Laboratorium padahal Deskripsi menyatakan tidak ada interaksi langsung dengan aktor. Lihat temuan F5. |
| C6, C7, C8, C9, C12 | Tidak berlaku | Tidak ada extend, aktor umum, generalization use case, collaboration, atau keterkaitan LAB-UC07. |
| C10 | Sesuai | Alternative langkah 5-6 dan Skenario Akhir tersedia. |
| C13 | Sesuai | Diagram tidak diubah. |

## 4. Temuan penelaahan dan rekomendasi

Temuan disusun berdasarkan hasil pencocokan pada bagian 3. Tidak ada berkas P04 yang diubah
pada Pertemuan 5; perbaikan diagram, bila disetujui, harus disimpan sebagai versi baru (v02)
tanpa menimpa v01.

| Kode | Tabel | Temuan | Dampak terhadap checklist | Rekomendasi |
|---|---|---|---|---|
| F1 | Tabel 5.1 | Hasil include (peralatan tidak tersedia) ditulis sebagai cabang alternatif dari langkah 2, padahal aturan pemetaan menyatakan include tidak pernah ditulis sebagai alternatif karena perilakunya selalu terjadi. | C5/C11: penulisan cabang perlu diperjelas sebagai hasil pemeriksaan, bukan sebagai relasi include yang menjadi alternatif. | Pertahankan langkah 2 sebagai rujukan include; tulis cabang 7 sebagai "Hasil pemeriksaan pada langkah 2 menyatakan peralatan tidak tersedia" agar yang bercabang adalah hasil pemeriksaan, bukan relasi include. |
| F2 | Tabel 5.1 | Penulisan condition dan extension point sudah lengkap, tetapi cabang hanya dibatasi untuk mahasiswa pada langkah 11 dan tidak ada catatan bahwa Dosen tidak memiliki asosiasi ke LAB-UC05. | C6/C7: perlu catatan aktor khusus. | Tambahkan catatan pada langkah 11 bahwa asosiasi LAB-UC05 hanya dimiliki Mahasiswa (relasi 3), sehingga Dosen yang mewarisi LAB-UC03 tidak menjalankan cabang ini. |
| F3 | Tabel 5.1 | Keterangan tabel menulis collaboration "LABCO01", sedangkan diagram menulis "LAB-CO01". | C9/C11: nama collaboration tidak sama persis dengan diagram. | Tulis "LAB-CO01 Ajukan Peminjaman" pada keterangan tabel; tidak perlu mengubah diagram. |
| F4 | Tabel 5.10 | Langkah 5 menyebut "cabang dari langkah 4", padahal penetapan persetujuan atau penolakan terjadi pada langkah 3; langkah 4 adalah tanggapan sistem. | C2: rujukan cabang menunjuk langkah yang keliru. | Ubah rujukan menjadi "cabang dari langkah 3" atau pindahkan penetapan persetujuan/penolakan ke satu langkah keputusan yang eksplisit dan rujuk langkah tersebut. |
| F5 | Tabel 5.4 dan Tabel 5.13 | Baris Aktor menyebut Peminjam dan Petugas Laboratorium "(berjalan di dalam ...)", sedangkan Deskripsi menyatakan use case tidak mempunyai interaksi langsung dengan aktor. | C11: baris Aktor tidak konsisten dengan Deskripsi. | Tulis baris Aktor sebagai "Tidak ada aktor langsung; dipanggil oleh LAB-UC03 Ajukan Peminjaman" dan sejenisnya untuk UC12, atau hapus pernyataan "tidak ada interaksi langsung" pada Deskripsi dan pertahankan pelaku alur. Pilih satu gaya dan pakai konsisten. |
| F6 | Tabel 5.9 | Baris Keterangan tercetak menyatu dengan baris Skenario Akhir sehingga batas sel tabel bergeser pada dokumen jobsheet. | C1: kelengkapan field secara isi tetap terpenuhi, tetapi keterbacaan tabel terganggu. | Tidak ada perubahan isi; cukup pastikan salinan tabel yang dikumpulkan memisahkan baris Keterangan di bawah tabel. |
| F7 | Tabel 5.11 | Aktor Kepala Laboratorium (relasi 9) belum ada pada berkas diagram P04 LAB di repository; asosiasi Lihat Laporan Peminjaman tergambar dari "Petugas Laboran", dan nama aktor petugas pada diagram berbeda dengan katalog ("Petugas Laboratorium"). | C11: nama aktor tidak sama persis dengan diagram. | Siapkan perbaikan diagram v02: ganti label "Petugas Laboran" menjadi "Petugas Laboratorium" dan tambahkan aktor Kepala Laboratorium dengan asosiasi ke LAB-UC07. Sampai perbaikan disetujui, acuan penamaan mengikuti katalog P04 (Tabel 4.5) seperti yang dipakai kedua belas tabel. |
| F8 | Tabel 5.12 | Langkah 5 berisi tanggapan sistem tetapi ditulis pada kolom Kegiatan. | C3: pemisahan kolom tidak terpenuhi. | Pindahkan langkah 5 ke kolom Respon sistem dan sisakan kolom Kegiatan kosong. |

## 5. Kesimpulan telaah

1. Kedua belas tabel memenuhi kelengkapan field (C1), penomoran berlanjut (C2), dan penyebutan
   data secara eksplisit (C4); setiap tabel memiliki Skenario Alternative dan Skenario Akhir (C10).
2. Pemetaan relasi diagram sudah tertelusur: include nomor 10 dan 15 menjadi langkah rujukan pada
   Tabel 5.1 dan Tabel 5.12; extend nomor 11 menjadi cabang bersyarat pada Tabel 5.1 dengan
   condition dan extension point lengkap; generalization aktor nomor 4 dan 5 diterapkan satu kali
   pada Tabel 5.1 dan 5.3; generalization use case nomor 12-14 diterapkan pada Tabel 5.6 sampai
   Tabel 5.9; realization nomor 16 dan 17 hanya disebut pada keterangan tabel.
3. Tiga butir belum terpenuhi dan perlu diperbaiki sebelum pengumpulan: pemisahan kolom pada
   Tabel 5.12 langkah 5 (F8), rujukan cabang pada Tabel 5.10 langkah 5 (F4), dan kesamaan nama
   collaboration serta nama aktor dengan diagram (F3, F7).
4. Berkas diagram P04 tidak diubah. Perbaikan F7 memerlukan versi diagram baru (v02) dan
   keputusan dosen/asisten, bukan perubahan langsung pada berkas acuan Pertemuan 5.
