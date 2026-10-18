# Model Analisis Use Case — Sistem Informasi Akademik (KRS)

| Metadata | Keterangan |
|---|---|
| Artefak | Model analisis / katalog use case |
| Kasus | Pengajuan dan Persetujuan KRS |
| Versi | v02 — telah diperiksa terhadap tiga skenario uji |
| Diagram terkait | `P03_2406043_SIA_usecase_v02.drawio` dan `P03_2406043_SIA_usecase_v02.png` |
| Deskripsi terkait | `P03_2406043_SIA_deskripsi_v02.md` |

## 1. Batas sistem

Batas sistem pada diagram diberi nama **Sistem Informasi Akademik — Pengajuan dan Persetujuan KRS**. Hanya perilaku pengajuan, validasi, unduh bukti, dan keputusan KRS yang digambarkan pada diagram baru.

## 2. Aktor

| Aktor | Tujuan/interaksi | Use case terkait |
|---|---|---|
| Mahasiswa | Mengirim pengajuan KRS dan memilih unduh bukti pada konfirmasi penyimpanan. | SIA-UC03, SIA-UC05 |
| Dosen wali | Memproses persetujuan atau penolakan KRS dan memberikan catatan keputusan. | SIA-UC06 |

SIA-UC04 bukan interaksi yang dimulai secara langsung oleh aktor eksternal; validasi dipanggil sebagai bagian dari SIA-UC03. Admin akademik tidak ditambahkan hanya karena muncul dalam tugas pengelolaan jadwal pada Pertemuan 2.

## 3. Katalog use case dan keterlacakan kebutuhan

| ID | Nama use case | Aktor terkait | Sumber kebutuhan | Peran |
|---|---|---|---|---|
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03; berelasi dengan SIA-R04 dan SIA-R05 | Use case dasar untuk pengajuan KRS |
| SIA-UC04 | Validasi KRS | Dipanggil oleh SIA-UC03 | SIA-R04 | Perilaku wajib yang disertakan oleh SIA-UC03 |
| SIA-UC05 | Unduh bukti pengajuan KRS | Mahasiswa | SIA-R05 | Perilaku tambahan yang dijalankan secara opsional |
| SIA-UC06 | Proses keputusan KRS | Dosen wali | SIA-R06 | Memproses persetujuan/penolakan dan catatan keputusan |

### Kebutuhan dari Pertemuan 2

SIA-R01 (Mahasiswa dapat melihat jadwal kuliah) dan SIA-R02 (Admin akademik dapat mengelola jadwal kuliah) dipertahankan sebagai identitas kebutuhan dari Pertemuan 2. Keduanya tidak dimodelkan ulang pada diagram KRS ini; penyelesaian diagram jadwal harus ditelusuri melalui artefak Pertemuan 2 yang terpisah.

## 4. Hubungan pada diagram

| Sumber | Relasi | Tujuan | Penjelasan |
|---|---|---|---|
| Mahasiswa | Association | SIA-UC03 — Ajukan KRS | Mahasiswa mengajukan KRS. |
| Mahasiswa | Association | SIA-UC05 — Unduh bukti pengajuan KRS | Mahasiswa memilih unduh secara langsung pada konfirmasi. |
| Dosen wali | Association | SIA-UC06 — Proses keputusan KRS | Dosen wali memutuskan persetujuan/penolakan. |
| SIA-UC03 | `«include»` | SIA-UC04 — Validasi KRS | Validasi merupakan bagian wajib dari pengajuan; panah mengarah ke use case yang disertakan. |
| SIA-UC05 | `«extend»` | SIA-UC03 — Ajukan KRS | Unduh hanya dijalankan bila dipilih; panah mengarah ke use case dasar. |

**Extension point pada SIA-UC03:** `Konfirmasi penyimpanan tersedia`.

**Kondisi extend:** `[mahasiswa memilih mengunduh bukti]`.

**Alasan include:** setiap pengajuan yang dikirim perlu diperiksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Validasi tetap dijalankan meskipun hasilnya gagal.

**Alasan extend:** pengajuan yang lolos validasi sudah berhasil disimpan sebelum pilihan unduh dilakukan. Tanpa unduh bukti, pengajuan tetap berhasil dan berstatus Menunggu persetujuan dosen wali.

## 5. Pemeriksaan konsistensi tiga situasi

| Situasi | Perilaku yang diharapkan | Konsisten? |
|---|---|---|
| A. Validasi berhasil dan mahasiswa tidak mengunduh bukti | SIA-UC04 mengembalikan hasil valid; SIA-UC03 menyimpan KRS dengan status Menunggu persetujuan dosen wali. Kondisi extend tidak terpenuhi sehingga SIA-UC05 tidak dijalankan. | Ya |
| B. Validasi gagal | SIA-UC04 mengembalikan hasil tidak valid; SIA-UC03 tidak menyimpan pengajuan sebagai pengajuan berhasil. Extension point konfirmasi penyimpanan tidak tercapai dan SIA-UC05 tidak dijalankan. | Ya |
| C. Validasi berhasil dan mahasiswa memilih mengunduh bukti | SIA-UC03 menyimpan KRS dengan status Menunggu persetujuan dosen wali, lalu mencapai extension point. Karena kondisi terpenuhi, SIA-UC05 dijalankan. Hasil unduhan tidak mengubah status KRS. | Ya |

## 6. Checklist review

- [x] Setiap aktor mempunyai interaksi yang jelas.
- [x] Use case sesuai kebutuhan dan berada di dalam batas sistem.
- [x] `«include»` mengarah dari SIA-UC03 ke SIA-UC04.
- [x] `«extend»` mengarah dari SIA-UC05 ke SIA-UC03.
- [x] Extension point berada pada use case dasar SIA-UC03.
- [x] Kondisi extend dicantumkan pada diagram dan deskripsi.
- [x] Pengajuan tetap berhasil tanpa perilaku unduh bukti.
- [x] Prasyarat dibedakan dari perilaku wajib `«include»`.
- [x] Alternatif validasi gagal menjelaskan bahwa KRS tidak berhasil tersimpan.
- [x] Diagram dan deskripsi memakai nama serta ID yang sama.
- [x] SIA-R01 dan SIA-R02 ditandai sebagai cakupan Pertemuan 2, bukan dianggap sudah diselesaikan oleh diagram ini.
- [x] Berkas sumber diagram dapat dibuka kembali melalui draw.io.
- [x] Nama dan versi sumber diagram serta ekspor PNG sama.

## 7. Catatan versi

Paket ini memakai **v02** untuk artefak deskripsi, model analisis, dan diagram agar tidak menimpa berkas **v01** yang tampak pada struktur proyek. File kebutuhan dibuat dengan nama `P03_SIA_kebutuhan_v01.md` sesuai instruksi jobsheet. Perubahan utama dalam paket revisi ini adalah penegasan arah panah include/extend, kondisi extend, extension point, serta hasil dari tiga situasi uji.
