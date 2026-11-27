# Laporan Singkat Pertemuan 4

**Mata kuliah:** Praktikum Analisis dan Desain Berorientasi Objek
**NIM:** 2406043
**Status:** draf v01 dan v02 siap diperiksa; review rekan/asisten belum dilakukan.

## Studi kasus LAB
- **Diagram:** `04_model_analisis/P04/LAB/P04_2406043_LAB_usecase_v02.drawio` dan `.png`. Berisi 5 aktor (Peminjam, Mahasiswa, Dosen, Petugas Laboratorium, Kepala Laboratorium), 12 use case, 2 collaboration, dan 17 relasi sesuai Tabel 4.5.
- **Perubahan dari v01:** aktor Kepala Laboratorium ditambahkan; label "Petugas Laboran" disatukan menjadi "Petugas Laboratorium"; relasi extend LAB-UC05 ke LAB-UC03 ditambahkan; nama use case diseragamkan dengan ID.
- **Versi lama:** `P04_2406043_LAB_usecase_v01.drawio` dan `.png` dipertahankan.
- **Kebutuhan:** `01_skenario/P04_LAB_kebutuhan_v01.md` memuat LAB-R07 sampai LAB-R11. Keterlambatan dan denda ditulis sebagai pertanyaan terbuka.
- **Skenario:** `01_skenario/P04_LAB_skenario_v01.md` (perbaikan nama file dari `skebnario`).
- **Deskripsi use case:** `03_latihan_tools/P04/LAB/P04_2406043_LAB_deskripsi_v01.md` untuk LAB-UC11 Catat Pengembalian Peralatan, dengan alur utama, alur alternatif A1–A3, dan baris Include, Generalization, serta Collaboration.

## Tugas SIA Layanan Hasil Studi
- **Kebutuhan dan skenario:** `01_skenario/P04_SIA_kebutuhan_v01.md` memuat SIA-R07 sampai SIA-R12 dan skenario uji konsistensi situasi A, B, dan C. `01_skenario/P04_SIA_skenario_v01.md` memuat skenario.
- **Deskripsi:** `03_latihan_tools/P04/SIA/P04_2406043_SIA_deskripsi_v01.md` untuk Input Nilai Mata Kuliah (dengan prasyarat pengampu dan alternatif nilai di luar rentang) dan Lihat KHS (hanya nilai terpublikasi).
- **Model analisis:** `04_model_analisis/P04/SIA/P04_2406043_SIA_model_analisis_v01.md`.
- **Diagram:** `04_model_analisis/P04/SIA/P04_2406043_SIA_usecase_v01.drawio` dan `.png`. Berisi 18 relasi: 9 asosiasi, 2 generalization aktor, 3 generalization use case, 2 realization, 1 include, dan 1 extend.

## Yang belum selesai
- Review rekan/asisten untuk arah generalization dan realization, nama collaboration, dan pascakondisi.
- Keputusan review belum dicatat di logbook dan metadata.
- Batas nilai yang sah pada SIA-UC08 belum ditetapkan oleh jobsheet.
