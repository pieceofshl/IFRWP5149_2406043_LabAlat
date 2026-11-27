# Metadata Artefak - Pertemuan 7

| Elemen | Keterangan |
|---|---|
| ID artefak | P07 |
| Judul | Sequence Diagram: Interaksi Objek Berdasarkan Skenario dan Kandidat Class |
| Mata kuliah | Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149) |
| Repository | `IFRWP5149_2406043_LabAlat` |
| Pertemuan | P07 |
| NIM | 2406043 |
| Pembuat | Muhammad Luthfi Nabih |
| Versi dan tanggal | v01 / 27-11-2026 |
| Kakas | draw.io |
| Jenis/status | Sequence diagram / draf v01; review rekan/asisten belum dilakukan |
| Pemeriksaan | Tata letak diperiksa lewat koordinat; label dicocokkan dengan Tabel 5.1, 5.10, 5.12 dan ketentuan jobsheet P07. Temuan T1 sampai T9 sudah diperbaiki; rinciannya di logbook P07. Tampilan juga diperiksa pada PNG ekspor draw.io. Validasi method dan perbandingan dengan berkas pembanding belum dilakukan. |

## Berkas dan unsur sequence

Berkas LAB berada di `04_model_analisis/P07/LAB/`, berkas SIA di `04_model_analisis/P07/SIA/`. Setiap berkas sumber memiliki ekspor `.png` dengan nama dasar yang sama.

| Berkas sumber | Use case | Sumber skenario | Peserta | Fragmen |
|---|---|---|---|---|
| `P07_2406043_LAB_sequence_peminjaman_v01.drawio` | LAB-UC03 Ajukan Peminjaman | Tabel 5.1 | Peminjam, `:Sistem Peminjaman`, `:Peminjaman`, `:Peralatan` | ref LAB-UC04, dua alt, opt extend LAB-UC05 |
| `P07_2406043_LAB_sequence_pengembalian_v01.drawio` | LAB-UC11 Catat Pengembalian Peralatan | Tabel 5.12, 5.13 | Petugas Laboratorium, `:Sistem Peminjaman`, `:Pengembalian`, `:Peminjaman`, `:Peralatan` | ref LAB-UC12, tiga alt |
| `P07_2406043_LAB_sequence_keputusan_v01.drawio` | LAB-UC06 Proses Keputusan Peminjaman (tugas mandiri) | Tabel 5.10 | Petugas Laboratorium, `:Sistem Peminjaman`, `:Peminjaman` | dua alt bersarang |
| `P07_2406043_SIA_sequence_v01.drawio` | SIA-UC08 Input Nilai Mata Kuliah sampai SIA-UC09 Lihat KHS | Tabel 5.16, 5.17; activity diagram P06 SIA | Dosen, `:Sistem Hasil Studi`, `:Nilai Mata Kuliah`, Admin Akademik, Mahasiswa | tiga alt, satu par |

## Method pada label pesan

| Method | Class tujuan | Validasi terhadap diagram class |
|---|---|---|
| `periksaKetersediaan()`, `periksaKondisi()` | Peralatan | Belum; diagram class belum tersedia |
| `ajukan()`, `prosesKeputusan()` | Peminjaman | Belum; diagram class belum tersedia |
| `catatPengembalian()` | Pengembalian | Belum; diagram class belum tersedia |
| `inputNilai()`, `publikasikan()` | Nilai Mata Kuliah | Belum; diagram class belum tersedia |

## Belum tersedia

- Diagram class pendamping LAB dan SIA.

## Kebijakan versi

- v01 adalah draf yang disiapkan untuk pemeriksaan; perubahan sebelum pengumpulan masih pada v01.
- Perubahan isi setelah review disimpan sebagai v02 tanpa menimpa v01.
