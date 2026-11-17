# P04 - Kebutuhan Kasus LAB: Generalization dan Collaboration

| Metadata | Keterangan |
|---|---|
| Mata kuliah | Praktikum Analisis dan Desain Berorientasi Objek |
| Pertemuan | 4 - Use Case Diagram Lanjutan |
| Kasus | Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus |
| NIM | 2406043 |
| Versi | v01 |

## 1. Skenario

Skenario ini melanjutkan potongan model Pertemuan 3. Selain mahasiswa, dosen juga meminjam peralatan laboratorium untuk kegiatan praktikum dan penelitian. Mahasiswa dan dosen sama-sama dapat melihat ketersediaan peralatan dan mengajukan peminjaman. Petugas laboratorium mengelola data peralatan: menambah peralatan baru, mengubah data peralatan, dan menghapus data peralatan yang tidak lagi dipakai. Setelah peminjaman disetujui dan alat diambil, petugas mencatat pengembalian peralatan. Pada saat mencatat pengembalian, petugas memeriksa dan mencatat kondisi peralatan. Dua use case utama, Ajukan Peminjaman dan Catat Pengembalian Peralatan, ditunjukkan realisasinya oleh collaboration yang bersesuaian.

## 2. Kebutuhan

LAB-R01 sampai LAB-R06 tetap berlaku dan tidak berubah arti (lihat `P03_LAB_skenario_v01.md`). Kebutuhan baru Pertemuan 4:

| ID | Kebutuhan |
|---|---|
| LAB-R07 | Mahasiswa dan Dosen, sebagai Peminjam, dapat melihat ketersediaan peralatan dan mengajukan peminjaman. |
| LAB-R08 | Petugas laboratorium mengelola data peralatan dalam tiga bentuk khusus: tambah, ubah, dan hapus data peralatan. |
| LAB-R09 | Petugas laboratorium dapat mencatat pengembalian peralatan untuk peminjaman yang berstatus Dipinjam. |
| LAB-R10 | Sistem memeriksa dan mencatat kondisi peralatan sebagai bagian dari pencatatan pengembalian. |
| LAB-R11 | Model menunjukkan collaboration yang merealisasikan Ajukan Peminjaman dan Catat Pengembalian Peralatan. |

## 3. Batas sistem dan aturan

- Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak terjadi di dalam perangkat lunak (tetap dari Pertemuan 3).
- Pengguna telah terautentikasi dan memiliki hak akses sesuai peran (tetap dari Pertemuan 3).
- Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam. Peminjaman yang masih Menunggu Keputusan atau Ditolak tidak dapat dicatat pengembaliannya.
- Kondisi peralatan pada pengembalian dicatat dengan salah satu nilai: Baik, Rusak Ringan, atau Rusak Berat.
- Hapus Data Peralatan hanya untuk peralatan yang tidak sedang dipinjam dan tidak memiliki pengajuan aktif.
- Kriteria penerimaan model: semua kebutuhan LAB-R01 sampai LAB-R11 mempunyai representasi pada diagram kumulatif, arah generalization dan realization benar, dan diagram konsisten dengan deskripsinya.

## 4. Pertanyaan terbuka

Hal berikut belum dimodelkan pada pertemuan ini dan tidak boleh dianggap sebagai aturan:

- Keterlambatan pengembalian: batas waktu dan akibatnya belum ditetapkan.
- Denda: ada atau tidaknya denda, besarnya, dan kerusakan yang menimbulkan denda belum ditetapkan.
