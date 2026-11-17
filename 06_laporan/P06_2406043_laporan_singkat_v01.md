# Laporan Singkat Pertemuan 6

Written for: dosen dan asisten praktikum ADBO, sebagai ringkasan pekerjaan P06.

**Mata kuliah:** Praktikum Analisis dan Desain Berorientasi Objek
**NIM:** 2406043
**Status:** draf v01 siap diperiksa; review rekan/asisten belum dilakukan.

## Activity diagram LAB (7 diagram)
Berkas sumber `.drawio` dan ekspor `.png` berada di `04_model_analisis/P06/LAB/` dengan pola `P06_2406043_LAB_activity_<slug>_v01`.

| Slug | Sumber skenario | Swimlane | Unsur yang dipakai |
|---|---|---|---|
| lihat_ketersediaan | LAB-UC01 | Peminjam, Sistem | decision, merge |
| kelola_data | LAB-UC02, UC08, UC09, UC10 | Petugas Laboratorium, Sistem | decision tiga cabang varian, decision syarat hapus, decision kelengkapan data, merge |
| peminjaman | LAB-UC03 (include UC04, extend UC05) | Mahasiswa, Sistem, Petugas Laboratorium | decision, merge |
| cetak_bukti | LAB-UC05 (extend) | Mahasiswa, Sistem | decision `[ya, memilih cetak]` dan `[tidak]`, merge |
| keputusan | LAB-UC06 (tugas mandiri) | Petugas Laboratorium, Sistem | decision, merge |
| pengembalian | LAB-UC11 (include UC12) | Mahasiswa, Sistem, Petugas Laboratorium | fork, join, decision, merge |
| laporan | LAB-UC07 | Kepala Laboratorium, Sistem | decision, merge |

- **Unsur proses baru:** action "Periksa kelengkapan aksesori peralatan" pada activity pengembalian ditandai sebagai unsur proses baru, karena jobsheet menetapkannya untuk latihan fork dan join. Action ini tidak berasal dari LAB-R01 sampai LAB-R11 maupun tabel skenario P05.
- **Kepala Laboratorium:** hanya muncul pada activity laporan.
- **Collaboration:** tidak digambar pada activity mana pun.
- **Metadata:** `02_template/P06_metadata_artefak_v01.md`.

## Activity diagram SIA (1 diagram)
- **Diagram:** `04_model_analisis/P06/SIA/P06_2406043_SIA_activity_v01.drawio` dan `.png`.
- **Cakupan:** Input Nilai Mata Kuliah sampai Lihat KHS, dengan empat swimlane (Dosen, Sistem, Admin Akademik, Mahasiswa).
- **Decision:** `Nilai sudah lengkap?` dengan guard `[lengkap]` dan `[belum lengkap]`. Cabang belum lengkap kembali ke Dosen melalui merge.
- **Fork dan join:** menerbitkan KHS dan mengirim pemberitahuan berjalan paralel, lalu disatukan join sebelum Mahasiswa melihat KHS.

## Yang belum selesai
- Review rekan atau asisten untuk seluruh activity.
- Berkas pembanding Lampiran jobsheet tidak tersedia di repository, sehingga pencocokan tahap 1 dan final dilakukan lewat checklist C.4, bukan berkas pembanding.
- Pemeriksaan visual tata letak dan swimlane belum dilakukan terhadap PNG; yang diperiksa adalah struktur sumber.
