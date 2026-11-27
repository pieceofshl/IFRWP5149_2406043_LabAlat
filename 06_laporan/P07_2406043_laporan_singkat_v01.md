# Laporan Singkat Pertemuan 7

**Mata kuliah:** Praktikum Analisis dan Desain Berorientasi Objek
**NIM:** 2406043
**Status:** draf v01; review rekan/asisten belum dilakukan.
**Berkas:** setiap diagram memiliki sumber `.drawio` dan ekspor `.png` dengan nama yang sama.

## Sequence diagram LAB
Berkas ada di `04_model_analisis/P07/LAB/`.

- **LAB-UC03 Ajukan Peminjaman** (`P07_2406043_LAB_sequence_peminjaman_v01.drawio`): ref LAB-UC04, alt ketersediaan dan kelengkapan isian, serta opt extend LAB-UC05.
- **LAB-UC11 Catat Pengembalian Peralatan** (`P07_2406043_LAB_sequence_pengembalian_v01.drawio`): alt jumlah alat, alt status Dipinjam, ref LAB-UC12, dan alt kondisi.
- **LAB-UC06 Proses Keputusan Peminjaman**, tugas mandiri (`P07_2406043_LAB_sequence_keputusan_v01.drawio`): alt pengajuan dapat diproses, dengan alt setuju atau tolak di dalamnya.

## Sequence diagram SIA
- **SIA-UC08 Input Nilai Mata Kuliah sampai SIA-UC09 Lihat KHS** (`04_model_analisis/P07/SIA/P07_2406043_SIA_sequence_v01.drawio`): alt dosen pengampu, alt kelengkapan dan rentang nilai, par publikasi, dan alt semester dipublikasikan.

## Perbaikan yang dilakukan
- Diagram LAB dipisah menjadi satu use case per berkas dan diberi judul berisi ID serta nama use case.
- Tata letak keempat diagram ditata ulang agar teks tidak tertimpa.
- Activation bar dirapikan pada LAB-UC11 dan dilengkapi pada diagram SIA.
- **LAB-UC11:** pesan alur normal dinomori berurutan, langkah petugas melihat konfirmasi dan balasan `periksaKondisi()` ditambahkan, cabang kondisi rusak menyatakan pengembalian tetap dicatat tanpa denda, dan `alt` jumlah alat dipindah setelah pesan 3.
- **SIA:** pesan KHS menyebut indeks prestasi semester, pemeriksaan rentang nilai diarahkan ke `:Nilai Mata Kuliah`, serta nama status dan alur input nilai mengikuti jobsheet P07. Perbedaannya dengan artefak P05 dan P06 dicatat di logbook.
- Notasi diseragamkan mengikuti contoh jobsheet: garis utuh untuk pesan sistem ke aktor, garis putus untuk balasan antarobjek, pesan asinkron untuk pemberitahuan, dan aktor berbentuk kotak.

## Yang belum selesai
- Diagram class pendamping LAB dan SIA belum ada, sehingga validasi method (Indikator 6.3) belum bisa dilakukan.
- Perbandingan diagram LAB dengan berkas pembanding, termasuk catatan perbaikan LAB-UC06, belum dilakukan karena Lampiran tidak tersedia.
- Review rekan/asisten belum dilakukan.
