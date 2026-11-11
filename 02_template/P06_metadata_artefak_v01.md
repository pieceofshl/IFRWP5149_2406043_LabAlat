# Metadata Artefak - Pertemuan 6

| Elemen | Keterangan |
|---|---|
| ID artefak | P06 |
| Judul | Activity Diagram: dari Skenario ke Alur Aktivitas |
| Mata kuliah | Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149) |
| Repository | `IFRWP5149_2406043_LabAlat` |
| Pertemuan | P06 |
| NIM | 2406043 |
| Versi dan tanggal | v01 / 11-11-2026 |
| Kakas | draw.io |
| Pembuat | Muhammad Luthfi Nabih |
| Jenis/status | Activity diagram / draf v01 |
| Asumsi | Hak akses dan autentikasi di luar latihan; status yang dipakai adalah status pada model Pertemuan 4 (Menunggu Keputusan, Disetujui, Ditolak, Dipinjam, Selesai, Belum Dipublikasikan) |
| Pemeriksaan | Diperiksa dengan checklist bagian C.4 jobsheet P06 |

## Berkas dan unsur activity

| Diagram | Berkas sumber dan ekspor | Tabel skenario sumber | Unsur activity yang digunakan | Unsur proses baru |
|---|---|---|---|---|
| Activity Lihat Ketersediaan Peralatan | `P06_2406043_LAB_activity_lihat_ketersediaan_v01.drawio` / `.png` | Tabel 5.3 LAB-UC01 | decision, merge | - |
| Activity Kelola Data Peralatan | `P06_2406043_LAB_activity_kelola_data_v01.drawio` / `.png` | Tabel 5.6 LAB-UC02; Tabel 5.7 LAB-UC08; Tabel 5.8 LAB-UC09; Tabel 5.9 LAB-UC10 | decision tiga cabang varian, decision syarat hapus, decision kelengkapan data, merge | - |
| Activity Peminjaman | `P06_2406043_LAB_activity_peminjaman_v01.drawio` / `.png` | Tabel 5.1 LAB-UC03; Tabel 5.4 LAB-UC04 (include); Tabel 5.5 LAB-UC05 (extend) | decision, merge | - |
| Activity Cetak Bukti Pengajuan | `P06_2406043_LAB_activity_cetak_bukti_v01.drawio` / `.png` | Tabel 5.5 LAB-UC05 (extend pada extension point Bukti pengajuan tersedia) | decision, merge | - |
| Activity Proses Keputusan Peminjaman | `P06_2406043_LAB_activity_keputusan_v01.drawio` / `.png` | Tabel 5.10 LAB-UC06 | decision, merge | - |
| Activity Pengembalian | `P06_2406043_LAB_activity_pengembalian_v01.drawio` / `.png` | Tabel 5.12 LAB-UC11; Tabel 5.13 LAB-UC12 (include) | fork, join, decision, merge | Periksa kelengkapan aksesori peralatan |
| Activity Lihat Laporan Peminjaman | `P06_2406043_LAB_activity_laporan_v01.drawio` / `.png` | Tabel 5.11 LAB-UC07 | decision, merge | - |
| Activity SIA Input Nilai Mata Kuliah sampai Lihat KHS | `P06_2406043_SIA_activity_v01.drawio` / `.png` | Tabel 5.16 SIA-UC08; Tabel 5.17 SIA-UC09 | decision, merge, fork, join | - |

## Catatan unsur dan keterlacakan

- Include digambar sebagai action wajib pada alur utama: `Periksa Ketersediaan` (dari LAB-UC04) pada Activity Peminjaman dan `Periksa Kondisi Peralatan` (dari LAB-UC12) pada Activity Pengembalian.
- Extend digambar sebagai cabang bersyarat dengan condition yang sama dengan diagram P04, yaitu `[ya, memilih cetak]`, dengan extension point Bukti pengajuan tersedia.
- `Periksa kelengkapan aksesori peralatan` pada Activity Pengembalian diberi keterangan **unsur proses baru**; action ini ditetapkan jobsheet P06 untuk melatih fork dan join dan tidak berasal dari LAB-R01 sampai LAB-R11, diagram P04, maupun tabel skenario P05.
- LAB-UC04 dan LAB-UC12 tidak dibuatkan activity tersendiri (menjadi action include); LAB-UC08, LAB-UC09, dan LAB-UC10 tidak dibuatkan activity tersendiri (menjadi cabang `[tambah]`, `[ubah]`, `[hapus]` pada Activity Kelola Data Peralatan).
- Kepala Laboratorium hanya muncul pada Activity Lihat Laporan Peminjaman, sesuai kedudukan LAB-UC07.
- Collaboration tidak digambar sebagai action maupun swimlane pada activity mana pun.
- Berkas P03, P04, dan dokumen P05 tidak diubah pada pertemuan ini.

## Kebijakan versi

- v01 adalah draf yang disiapkan untuk pemeriksaan.
- Perubahan isi setelah review disimpan sebagai v02 tanpa menimpa v01; nama berkas sumber, nama ekspor PNG, nomor versi, metadata, dan logbook diperbarui bersamaan.
