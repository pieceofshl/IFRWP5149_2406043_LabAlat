# P03 LAB - Aktor, Katalog Use Case, dan Relasi

## Aktor
| Aktor | Tujuan terhadap sistem |
|---|---|
| Mahasiswa | Melihat ketersediaan, mengajukan peminjaman, dan mencetak bukti |
| Petugas laboratorium | Mengelola peralatan dan memproses keputusan |
| Kepala laboratorium | Melihat laporan peminjaman |

## Katalog use case
| ID | Nama use case | Peran dalam model | Sumber kebutuhan |
|---|---|---|---|
| LAB-UC01 | Lihat ketersediaan peralatan | Fungsi utama mahasiswa | LAB-R01 |
| LAB-UC02 | Kelola data peralatan | Fungsi utama petugas | LAB-R02 |
| LAB-UC03 | Ajukan peminjaman | Fungsi utama mahasiswa | LAB-R03 |
| LAB-UC04 | Periksa ketersediaan | Perilaku yang disertakan UC03 | LAB-R03 |
| LAB-UC05 | Cetak bukti pengajuan | Tambahan bersyarat pada UC03 | LAB-R04 |
| LAB-UC06 | Proses keputusan peminjaman | Fungsi utama petugas | LAB-R05 |
| LAB-UC07 | Lihat laporan peminjaman | Fungsi utama kepala laboratorium | LAB-R06 |

Lihat ketersediaan menyediakan informasi bagi pengguna, sedangkan Periksa ketersediaan memvalidasi alat, jumlah, dan rentang waktu dalam pengajuan. Keduanya tidak disamakan.

## Relasi
- LAB-UC03 «include» LAB-UC04. Alasan: pemeriksaan menjadi bagian validasi pengajuan.
- LAB-UC05 «extend» LAB-UC03. Extension point: Bukti pengajuan tersedia. Kondisi: [mahasiswa memilih cetak]. Alasan: pengajuan tetap berhasil tanpa pencetakan.
