# Use Case Description - Sistem Informasi Akademik: Layanan Hasil Studi

| Metadata | Keterangan |
|---|---|
| Mata kuliah | Praktikum Analisis dan Desain Berorientasi Objek |
| Identitas artefak | P04 / SIA |
| Versi | v01 |
| Sumber | Jobsheet Praktikum Pertemuan 4, bagian tugas SIA, halaman 64-65 |
| Catatan | Deskripsi ini melengkapi diagram kumulatif P02 + P03 + P04; deskripsi use case lama tetap berada pada artefak pertemuan sebelumnya. |

## SIA-UC08 - Input Nilai Mata Kuliah

| Elemen | Deskripsi |
|---|---|
| ID dan nama | **SIA-UC08 - Input Nilai Mata Kuliah** |
| Sumber kebutuhan | SIA-R08 dan SIA-R12 |
| Tujuan | Menyimpan nilai mata kuliah yang diampu Dosen setelah masa perkuliahan berakhir, tanpa otomatis mempublikasikan nilai tersebut. |
| Aktor utama | Dosen |
| Aktor pendukung | Tidak ada aktor pendukung eksternal yang disebutkan dalam skenario. |
| Pemicu | Setelah masa perkuliahan berakhir, Dosen memilih fungsi Input Nilai Mata Kuliah untuk mata kuliah yang diampunya. |
| Prasyarat | Dosen telah terautentikasi; Dosen merupakan pengampu mata kuliah terkait; masa perkuliahan mata kuliah tersebut telah berakhir. |
| Pascakondisi berhasil | Nilai berhasil disimpan untuk mata kuliah terkait dan tetap berstatus belum dipublikasikan sampai dinyatakan resmi sesuai ketentuan institusi. Nilai tersebut belum ditampilkan pada KHS sebelum dipublikasikan. |
| Pascakondisi gagal | Operasi yang ditolak tidak menghasilkan nilai baru yang tersimpan; data nilai yang telah ada tidak berubah dan nilai di luar rentang sah tidak disimpan. |
| Collaboration | **SIA-CO01 - Input Nilai Mata Kuliah** |

### Alur utama

| Langkah | Tindakan Dosen | Respons sistem |
|---:|---|---|
| 1 | Memilih fungsi Input Nilai Mata Kuliah. | Menampilkan mata kuliah yang dapat diakses sesuai hak Dosen. |
| 2 | Memilih mata kuliah yang diampunya. | Memeriksa bahwa Dosen adalah pengampu mata kuliah dan masa perkuliahan telah berakhir. |
| 3 | Mengisi nilai untuk peserta mata kuliah. | Menerima data nilai untuk divalidasi. |
| 4 | Memeriksa kembali nilai yang diisikan. | Memvalidasi setiap nilai berdasarkan rentang nilai sah yang berlaku di institusi. |
| 5 | Mengirim data nilai yang valid untuk disimpan. | Menyimpan nilai dengan status belum dipublikasikan dan tidak mengubahnya menjadi nilai yang sudah dipublikasikan. |
| 6 | Melihat hasil proses. | Menampilkan konfirmasi bahwa penyimpanan nilai berhasil. |

### Alur alternatif / pengecualian

- **A1 - Dosen bukan pengampu (pada langkah 2):** Sistem menolak proses input untuk mata kuliah tersebut. Tidak ada nilai baru yang disimpan oleh operasi yang ditolak; data sebelumnya tetap tidak berubah.
- **A2 - Masa perkuliahan belum berakhir (pada langkah 2):** Sistem belum mengizinkan input nilai untuk mata kuliah tersebut. Tidak ada nilai baru yang disimpan.
- **A3 - Nilai di luar rentang sah (pada langkah 4):** Sistem menolak nilai yang tidak sah, menampilkan informasi koreksi, dan tidak menyimpan nilai yang ditolak. Nilai harus diperbaiki dan divalidasi ulang. Angka batas rentang mengikuti ketentuan institusi dan tidak diasumsikan dalam jobsheet.
- **A4 - Penyimpanan gagal (pada langkah 5):** Sistem menampilkan kegagalan penyimpanan. Operasi tidak dikonfirmasi berhasil dan data nilai sebelumnya tidak diubah oleh operasi yang gagal.

## SIA-UC09 - Lihat KHS

| Elemen | Deskripsi |
|---|---|
| ID dan nama | **SIA-UC09 - Lihat KHS** |
| Sumber kebutuhan | SIA-R09 dan SIA-R12 |
| Tujuan | Menampilkan Kartu Hasil Studi mahasiswa untuk semester yang dipilih dengan hanya menyertakan nilai yang sudah dipublikasikan. |
| Aktor utama | Mahasiswa |
| Pemicu | Mahasiswa memilih fungsi Lihat KHS dan menentukan semester. |
| Prasyarat | Mahasiswa telah terautentikasi dan sistem dapat mengidentifikasi data akademik mahasiswa tersebut. |
| Alur utama | Mahasiswa memilih semester; sistem mengambil nilai untuk mahasiswa pada semester tersebut; sistem hanya menampilkan nilai yang telah dipublikasikan; sistem menampilkan KHS. |
| Alur alternatif | Jika belum ada nilai yang dipublikasikan untuk semester tersebut, sistem menampilkan bahwa belum ada nilai yang tersedia. Nilai yang belum dipublikasikan tidak ditampilkan. |
| Pascakondisi berhasil | KHS ditampilkan dengan hanya nilai yang telah dipublikasikan untuk semester yang dipilih. |
| Pascakondisi gagal | Tidak ada nilai yang belum dipublikasikan yang ditampilkan. Jika KHS tidak dapat ditampilkan, sistem tidak menyatakan operasi berhasil. |
| Collaboration | **SIA-CO02 - Lihat KHS** |

### Catatan konsistensi

- SIA-UC07 **Lihat Kalender Akademik** berbeda dari SIA-UC01 **Lihat Jadwal Kuliah**.
- SIA-UC08 tidak memiliki relasi `«include»`/`«extend»` baru yang dinyatakan oleh skenario; relasinya dengan SIA-CO01 adalah **realization**.
- SIA-UC09 tidak boleh menampilkan nilai yang belum dipublikasikan; relasinya dengan SIA-CO02 adalah **realization**.
