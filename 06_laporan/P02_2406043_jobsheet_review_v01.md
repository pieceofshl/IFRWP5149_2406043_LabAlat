# Review Jobsheet P02 - Perbaikan Notasi SIA

Diagram awal: `03_latihan_tools/P02/SIA/P02_2406043_SIA_perbaikan_notasi_v01.drawio`. Hasil perbaikan: `P02_2406043_SIA_notasi_v01.drawio`.

| No. | Temuan | Perbaikan yang diperlukan | Alasan |
|---:|---|---|---|
| 1 | Aktor Mahasiswa diletakkan di dalam batas sistem. | Pindahkan Mahasiswa ke luar batas sistem. | Aktor adalah pihak yang berinteraksi dengan sistem, sehingga berada di luar batas sistem. |
| 2 | Fungsi Lihat jadwal kuliah digambar sebagai kotak biasa. | Ubah menjadi elips. | Use case digambar dengan simbol elips. |
| 3 | Mahasiswa dihubungkan dengan Kelola jadwal kuliah. | Hubungkan Mahasiswa dengan Lihat jadwal kuliah, dan Admin akademik dengan Kelola jadwal kuliah. | Hubungan aktor dan fungsi harus sesuai skenario: mahasiswa tidak mengelola jadwal. |
| 4 | Judul diagram memakai Sistem Laboratorium Kampus. | Ganti menjadi Sistem Informasi Akademik. | Identitas diagram harus sesuai dengan sistem yang dibahas. |

## Mengapa garis asosiasi bukan alur proses

Garis asosiasi hanya menyatakan bahwa sebuah aktor berpartisipasi dalam sebuah fungsi. Garis itu tidak menyatakan urutan kegiatan. Urutan langkah dijelaskan pada use case description atau activity diagram.

## Uji buka ulang sumber

| Berkas | Dibuka ulang | Dapat disunting | Catatan |
|---|---|---|---|
| `P02_2406043_SIA_perbaikan_notasi_v01.drawio` | Ya | Ya | Diuji ulang dan dilaporkan oleh penulis |
| `P02_2406043_SIA_notasi_v01.drawio` | Ya | Ya | Diuji ulang dan dilaporkan oleh penulis |
| `P02_2406043_LAB_notasi_usecase_v01.drawio` | Ya | Ya | Diuji ulang dan dilaporkan oleh penulis |

Langkah: tutup berkas di draw.io, buka ulang dari folder proyek, ubah posisi satu elemen, simpan, lalu isi tabel ini.
