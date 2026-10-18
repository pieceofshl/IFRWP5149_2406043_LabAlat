# Laporan Singkat Review Jobsheet Pertemuan 3

**Mata kuliah:** Praktikum Analisis dan Desain Berorientasi Objek  
**Kasus:** Sistem Informasi Akademik — Pengajuan dan Persetujuan KRS  
**Fokus review:** Skenario, aktor, katalog use case, relasi UML, dan konsistensi deskripsi use case.

Tabel berikut merangkum hal-hal yang perlu diperhatikan dalam penyusunan model P03, perbaikan yang dilakukan atau perlu dipastikan, serta alasan pemodelannya.

| No. | Temuan | Perbaikan yang Diperlukan | Alasan |
| --- | --- | --- | --- |
| 1 | Kebutuhan SIA-R01 dan SIA-R02 berasal dari tugas pengelolaan jadwal pada Pertemuan 2, sedangkan P03 berfokus pada proses KRS. | Pertahankan SIA-R01 dan SIA-R02 sebagai kebutuhan terdahulu, tetapi batasi diagram P03 pada SIA-R03 sampai SIA-R06. | Batas cakupan harus jelas agar use case jadwal dari pertemuan sebelumnya tidak tercampur dengan model pengajuan KRS. |
| 2 | Aktor harus berada di luar batas sistem. | Letakkan aktor **Mahasiswa** dan **Dosen wali** di luar kotak batas sistem. | Aktor adalah pihak eksternal yang berinteraksi dengan sistem, bukan bagian dari sistem yang dimodelkan. |
| 3 | Mahasiswa berinteraksi dengan fungsi pengajuan KRS dan unduh bukti pengajuan. | Hubungkan Mahasiswa dengan **SIA-UC03 — Ajukan KRS** dan **SIA-UC05 — Unduh bukti pengajuan KRS**. | Hubungan aktor dan use case harus sesuai dengan peran yang dijelaskan dalam skenario. |
| 4 | Dosen wali bertanggung jawab memproses keputusan KRS. | Hubungkan Dosen wali dengan **SIA-UC06 — Proses keputusan KRS**. | Aktor harus dihubungkan hanya dengan fungsi yang memang dijalankannya. |
| 5 | Validasi merupakan bagian wajib dari proses pengajuan KRS. | Gambarkan relasi `«include»` dari **SIA-UC03 — Ajukan KRS** menuju **SIA-UC04 — Validasi KRS**. | Setiap pengajuan harus diperiksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Arah panah include menuju use case yang disertakan. |
| 6 | Unduh bukti hanya dilakukan apabila mahasiswa memilih opsi tersebut setelah pengajuan tersimpan. | Gambarkan relasi `«extend»` dari **SIA-UC05 — Unduh bukti pengajuan KRS** menuju **SIA-UC03 — Ajukan KRS**. Cantumkan kondisi `[mahasiswa memilih mengunduh bukti]` dan extension point **Konfirmasi penyimpanan tersedia**. | Unduh bukti bersifat opsional. Arah panah extend menuju use case dasar yang diperluas. |
| 7 | Pengajuan dapat gagal apabila hasil validasi tidak memenuhi ketentuan. | Jelaskan alur alternatif ketika data tidak lengkap, prasyarat tidak terpenuhi, atau jadwal bentrok. | Pengajuan yang gagal divalidasi tidak boleh digambarkan sebagai pengajuan yang berhasil tersimpan. |
| 8 | Pengajuan yang lolos validasi belum berarti telah disetujui dosen wali. | Tetapkan pascakondisi bahwa KRS tersimpan dengan status **Menunggu persetujuan dosen wali**. | Status ini membedakan keberhasilan pengajuan dari keputusan akhir dosen wali. |
| 9 | Dosen wali dapat menyetujui atau menolak pengajuan. | Pada **SIA-UC06**, dokumentasikan kedua hasil keputusan dan catatan keputusan yang menyertainya. | Alur utama dan alternatif harus mencakup hasil persetujuan maupun penolakan sesuai skenario. |
| 10 | Nama, ID, dan relasi pada diagram harus konsisten dengan dokumen deskripsi use case. | Samakan ID SIA-UC03 sampai SIA-UC06, nama use case, kondisi extend, extension point, serta status pengajuan di seluruh artefak. | Konsistensi memudahkan penelusuran kebutuhan dan mencegah perbedaan informasi antara skenario, diagram, dan deskripsi use case. |

## Kesimpulan

Review P03 berfokus pada ketepatan batas sistem KRS, penempatan dan asosiasi aktor, serta arah dan kondisi relasi `«include»` dan `«extend»`. Deskripsi use case juga perlu konsisten dengan diagram, terutama pada hasil validasi, sifat opsional pengunduhan bukti, dan keputusan dosen wali. Kebutuhan SIA-R01 dan SIA-R02 tetap dicatat sebagai konteks Pertemuan 2 dan tidak dimodelkan ulang dalam diagram KRS ini.
