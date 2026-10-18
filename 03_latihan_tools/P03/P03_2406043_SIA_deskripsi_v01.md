# Use Case Description — Sistem Informasi Akademik (KRS)

## Metadata dokumen

| Metadata          | Keterangan                                       |
| ----------------- | ------------------------------------------------ |
| Mata kuliah       | Praktikum Analisis dan Desain Berorientasi Objek |
| Identitas artefak | P03 / SIA                                        |
| Versi             | v02 — hasil pemeriksaan konsistensi              |
| Sumber            | Jobsheet Praktikum Pertemuan 3, halaman 41–43    |

---

## SIA-UC03 — Ajukan KRS

### Deskripsi use case

| Elemen                | Deskripsi                                                                                                      |
| --------------------- | -------------------------------------------------------------------------------------------------------------- |
| ID dan nama           | **SIA-UC03 — Ajukan KRS**                                                                                      |
| Sumber kebutuhan      | SIA-R03; terkait dengan validasi SIA-R04 dan pilihan bukti SIA-R05.                                            |
| Tujuan                | Menyimpan pengajuan KRS yang lolos validasi dengan status **Menunggu persetujuan dosen wali**.                 |
| Aktor utama           | Mahasiswa                                                                                                      |
| Aktor pendukung       | Tidak ada aktor eksternal lain yang memulai pengajuan. SIA-UC04 dijalankan sebagai perilaku yang disertakan.   |
| Pemicu                | Mahasiswa memilih fungsi Ajukan KRS.                                                                           |
| Prasyarat             | Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia.                              |
| Include               | **SIA-UC04 — Validasi KRS**, karena validasi menjadi bagian dari setiap pengajuan.                             |
| Extension point       | **Konfirmasi penyimpanan tersedia**, setelah KRS berhasil disimpan dan konfirmasi ditampilkan.                 |
| Extend                | **SIA-UC05 — Unduh bukti pengajuan KRS**, jika kondisi `[mahasiswa memilih mengunduh bukti]` terpenuhi.        |
| Pascakondisi berhasil | Pengajuan KRS tersimpan dengan status **Menunggu persetujuan dosen wali**. Pengunduhan bukti tidak diwajibkan. |
| Pascakondisi gagal    | Tidak ada pengajuan baru yang berhasil tersimpan.                                                              |

### Alur utama

| Langkah | Tindakan mahasiswa                                   | Respons sistem                                                                                                                  |
| ------: | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| 1       | Membuka fungsi Ajukan KRS.                           | Menampilkan formulir pengajuan KRS.                                                                                             |
| 2       | Memilih mata kuliah yang akan diajukan.              | Menampung pilihan mahasiswa.                                                                                                    |
| 3       | Mengirim pengajuan KRS.                              | Memulai pemeriksaan pengajuan dan menjalankan **SIA-UC04 — Validasi KRS**.                                                      |
| 4       | Menunggu hasil validasi.                             | Memeriksa hasil validasi dari SIA-UC04. Jika lolos, menyimpan pengajuan dengan status **Menunggu persetujuan dosen wali**.      |
| 5       | Melihat konfirmasi penyimpanan.                      | Menampilkan konfirmasi dan status pengajuan, lalu mencapai extension point **Konfirmasi penyimpanan tersedia**.                 |
| 6       | Mengakhiri pengajuan atau memilih tindakan lanjutan. | Pengajuan tetap tersimpan dan menunggu keputusan dosen wali. Jika mahasiswa memilih mengunduh bukti, SIA-UC05 dapat dijalankan. |

### Alur alternatif / pengecualian

- **A1 — Data pengajuan tidak lengkap (langkah 4):** Validasi menyatakan pengajuan tidak lengkap. Sistem menampilkan informasi bahwa pengajuan belum lolos validasi dan tidak menyimpannya sebagai pengajuan berhasil. Mahasiswa dapat memperbaiki isian dan mengirim ulang.
- **A2 — Prasyarat mata kuliah tidak terpenuhi (langkah 4):** Validasi gagal. Sistem menampilkan hasil kegagalan dan pengajuan tidak berhasil tersimpan.
- **A3 — Terjadi benturan jadwal (langkah 4):** Validasi gagal. Sistem menampilkan hasil kegagalan dan pengajuan tidak berhasil tersimpan.
- **A4 — Mahasiswa tidak memilih mengunduh bukti (langkah 5):** SIA-UC05 tidak dijalankan. Pengajuan tetap berhasil tersimpan dengan status **Menunggu persetujuan dosen wali**.
- **A5 — Mahasiswa memilih mengunduh bukti (langkah 5):** Jalankan **SIA-UC05 — Unduh bukti pengajuan KRS**. Hasil unduhan tidak mengubah status pengajuan yang sudah tersimpan.

---

## SIA-UC04 — Validasi KRS

### Deskripsi use case

| Elemen                | Deskripsi                                                                                                                                   |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| ID dan nama           | **SIA-UC04 — Validasi KRS**                                                                                                                 |
| Sumber kebutuhan      | SIA-R04                                                                                                                                     |
| Tujuan                | Menilai apakah pengajuan KRS memenuhi kelengkapan dan prasyarat mata kuliah, serta tidak memiliki benturan jadwal.                          |
| Aktor utama           | Tidak dimulai langsung oleh aktor eksternal; dipanggil oleh **SIA-UC03 — Ajukan KRS**.                                                      |
| Aktor pendukung       | Mahasiswa sebagai pengaju melalui SIA-UC03.                                                                                                 |
| Pemicu                | Mahasiswa mengirim pengajuan dan SIA-UC03 meminta validasi.                                                                                 |
| Prasyarat             | Data pengajuan telah diterima dalam alur SIA-UC03; data mata kuliah, prasyarat, dan jadwal tersedia.                                        |
| Pascakondisi berhasil | Hasil validasi menyatakan lolos dan dikembalikan kepada SIA-UC03 untuk menyimpan pengajuan. Use case ini sendiri tidak menyimpan pengajuan. |
| Pascakondisi gagal    | Hasil validasi menyatakan gagal dan dikembalikan kepada SIA-UC03. Pengajuan tidak boleh dianggap berhasil tersimpan.                        |

### Alur utama

| Langkah | Tindakan aktor / pemanggil                          | Respons sistem                                                                 |
| ------: | --------------------------------------------------- | ------------------------------------------------------------------------------ |
| 1       | SIA-UC03 meminta validasi atas pengajuan mahasiswa. | Menerima data pengajuan untuk diperiksa.                                       |
| 2       | —                                                   | Memeriksa kelengkapan pengajuan.                                               |
| 3       | —                                                   | Memeriksa prasyarat mata kuliah yang dipilih.                                  |
| 4       | —                                                   | Memeriksa benturan jadwal mata kuliah yang dipilih.                            |
| 5       | —                                                   | Jika seluruh pemeriksaan lolos, mengembalikan hasil **Valid** kepada SIA-UC03. |

### Alur alternatif / pengecualian

- **A1 — Kelengkapan gagal (langkah 2):** Sistem mengembalikan hasil **Tidak valid: data tidak lengkap** kepada SIA-UC03.
- **A2 — Prasyarat gagal (langkah 3):** Sistem mengembalikan hasil **Tidak valid: prasyarat tidak terpenuhi** kepada SIA-UC03.
- **A3 — Benturan jadwal ditemukan (langkah 4):** Sistem mengembalikan hasil **Tidak valid: benturan jadwal** kepada SIA-UC03.
- Jika lebih dari satu pemeriksaan gagal, prioritas atau penggabungan pesan belum ditetapkan oleh skenario dan tidak diasumsikan di sini.

---

## SIA-UC05 — Unduh bukti pengajuan KRS

### Deskripsi use case

| Elemen                | Deskripsi                                                                                                                                      |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| ID dan nama           | **SIA-UC05 — Unduh bukti pengajuan KRS**                                                                                                       |
| Sumber kebutuhan      | SIA-R05                                                                                                                                        |
| Tujuan                | Menyediakan bukti pengajuan KRS yang telah berhasil disimpan kepada mahasiswa yang memilih mengunduhnya.                                       |
| Aktor utama           | Mahasiswa                                                                                                                                      |
| Aktor pendukung       | Tidak ada.                                                                                                                                     |
| Pemicu                | Pada konfirmasi penyimpanan, mahasiswa memilih mengunduh bukti pengajuan.                                                                      |
| Prasyarat             | SIA-UC03 berhasil menyimpan pengajuan dan konfirmasi penyimpanan tersedia.                                                                     |
| Relasi                | **SIA-UC05 «extend» SIA-UC03**, dengan kondisi `[mahasiswa memilih mengunduh bukti]` pada extension point **Konfirmasi penyimpanan tersedia**. |
| Pascakondisi berhasil | Bukti pengajuan disediakan untuk diunduh; status KRS tetap **Menunggu persetujuan dosen wali**.                                                |
| Pascakondisi gagal    | Pengajuan KRS yang sudah tersimpan tetap tersimpan. Kegagalan pengunduhan tidak membatalkan pengajuan.                                         |

### Alur utama

| Langkah | Tindakan mahasiswa                                              | Respons sistem                                                                                         |
| ------: | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| 1       | Memilih opsi untuk mengunduh bukti pada konfirmasi penyimpanan. | Menerima pilihan unduh untuk pengajuan yang berhasil disimpan.                                         |
| 2       | Menunggu proses penyiapan bukti.                                | Menyiapkan bukti pengajuan berdasarkan data yang tersedia.                                             |
| 3       | Mengakses hasil unduhan.                                        | Menyediakan bukti pengajuan untuk diunduh. Status pengajuan tetap **Menunggu persetujuan dosen wali**. |

### Alur alternatif / pengecualian

- **A1 — Bukti gagal disiapkan atau diunduh (langkah 2–3):** Sistem menyampaikan bahwa pengunduhan gagal. Pengajuan yang sudah tersimpan tetap berstatus **Menunggu persetujuan dosen wali**. Penyebab teknis dan mekanisme unduh ulang belum ditentukan oleh skenario.
- **A2 — Mahasiswa tidak memilih unduh:** Use case ini tidak dijalankan. Kondisi ini bukan kegagalan SIA-UC03 dan tidak memengaruhi keberhasilan pengajuan.

---

## SIA-UC06 — Proses keputusan KRS

### Deskripsi use case

| Elemen                            | Deskripsi                                                                                                                        |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| ID dan nama                       | **SIA-UC06 — Proses keputusan KRS**                                                                                              |
| Sumber kebutuhan                  | SIA-R06                                                                                                                          |
| Tujuan                            | Mencatat keputusan persetujuan atau penolakan KRS oleh dosen wali beserta catatan keputusan.                                     |
| Aktor utama                       | Dosen wali                                                                                                                       |
| Aktor pendukung                   | Tidak ada aktor eksternal lain yang disebut dalam skenario.                                                                      |
| Pemicu                            | Dosen wali memilih pengajuan KRS berstatus **Menunggu persetujuan dosen wali** untuk diproses.                                   |
| Prasyarat                         | Dosen wali telah terautentikasi; terdapat pengajuan KRS yang tersimpan dan menunggu persetujuan dosen wali.                      |
| Pascakondisi berhasil — disetujui | Keputusan **Disetujui** dan catatan keputusan tersimpan pada pengajuan KRS.                                                      |
| Pascakondisi berhasil — ditolak   | Keputusan **Ditolak** dan catatan keputusan tersimpan pada pengajuan KRS.                                                        |
| Pascakondisi gagal                | Jika dosen wali belum menetapkan keputusan, pengajuan belum berubah menjadi Disetujui atau Ditolak dan tetap menunggu keputusan. |

### Alur utama

| Langkah | Tindakan dosen wali                                   | Respons sistem                                                                                |
| ------: | ----------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 1       | Membuka daftar pengajuan KRS yang menunggu keputusan. | Menampilkan pengajuan yang dapat diproses.                                                    |
| 2       | Memeriksa isi pengajuan KRS.                          | Menampilkan data pengajuan yang tersedia untuk ditinjau.                                      |
| 3       | Memilih keputusan **Setujui** atau **Tolak**.         | Menerima pilihan keputusan dosen wali.                                                        |
| 4       | Memberikan catatan keputusan.                         | Mengaitkan catatan dengan keputusan atas pengajuan.                                           |
| 5       | Mengonfirmasi keputusan.                              | Mencatat keputusan dan mengubah status menjadi **Disetujui** atau **Ditolak** sesuai pilihan. |

### Alur alternatif / pengecualian

- **A1 — Dosen wali belum menentukan keputusan (langkah 3):** Proses keputusan belum selesai. Sistem tidak mencatat status Disetujui atau Ditolak; status tetap **Menunggu persetujuan dosen wali**.
- **A2 — Dosen wali memilih Tolak (langkah 3):** Lanjutkan langkah 4–5. Sistem mencatat status **Ditolak** beserta catatan keputusan.
- **A3 — Dosen wali memilih Setujui (langkah 3):** Lanjutkan langkah 4–5. Sistem mencatat status **Disetujui** beserta catatan keputusan.
- Validasi isi catatan, notifikasi kepada mahasiswa, dan proses banding tidak dirinci karena tidak ditetapkan dalam skenario.
