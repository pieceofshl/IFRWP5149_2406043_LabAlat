# Use Case Description P04 LAB

## LAB-UC11: Catat Pengembalian Peralatan

| Elemen | Isi |
|---|---|
| ID dan nama | LAB-UC11: Catat Pengembalian Peralatan |
| Sumber kebutuhan | LAB-R09 dan LAB-R10 |
| Tujuan | Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui |
| Aktor utama | Petugas Laboratorium |
| Aktor pendukung | Tidak ada |
| Pemicu | Petugas memilih fungsi pencatatan pengembalian dan menentukan peminjaman yang akan dikembalikan |
| Prasyarat | Petugas telah terautentikasi; peminjaman terpilih berstatus Dipinjam |
| Pascakondisi berhasil | Pengembalian tercatat dengan tanggal kembali dan kondisi peralatan; status peminjaman menjadi Selesai |
| Pascakondisi gagal | Tidak ada pengembalian baru yang tercatat; status peminjaman tidak berubah |
| Include | LAB-UC12: Periksa Kondisi Peralatan |
| Generalization | Tidak ada (bukan use case umum maupun khusus) |
| Collaboration | LAB-CO02: Catat Pengembalian Peralatan |
| Aturan bisnis/asumsi | Kondisi dicatat sebagai Baik, Rusak Ringan, atau Rusak Berat. Keterlambatan dan denda belum dimodelkan. |

### Alur utama

| Langkah | Tindakan petugas | Respon sistem |
|---:|---|---|
| 1 | Memilih peminjaman yang akan dikembalikan | Menampilkan data peminjaman terpilih dan statusnya |
| 2 | Mengonfirmasi alat yang kembali dan jumlahnya | Menampung konfirmasi petugas |
| 3 | Tidak ada | Memeriksa status peminjaman harus Dipinjam |
| 4 | Tidak ada | Menjalankan LAB-UC12: memeriksa dan mencatat kondisi peralatan |
| 5 | Menyimpan pencatatan pengembalian | Menyimpan tanggal kembali dan kondisi; mengubah status peminjaman menjadi Selesai |
| 6 | Melihat konfirmasi | Menampilkan ringkasan pengembalian |

### Alur alternatif atau pengecualian

- **A1 - Status bukan Dipinjam (langkah 3):** sistem menolak pencatatan dan menampilkan status peminjaman saat ini. Pascakondisi gagal berlaku; tidak ada data yang disimpan.
- **A2 - Kondisi Rusak Ringan atau Rusak Berat (langkah 4):** sistem tetap menyimpan pencatatan, menandai kondisi tersebut pada data peralatan, dan pengembalian tetap tercatat. Kerusakan tidak otomatis menimbulkan denda pada model ini.
- **A3 - Jumlah alat yang kembali tidak sesuai (langkah 2):** sistem meminta petugas memeriksa kembali isian sebelum penyimpanan; pencatatan tidak disimpan sampai jumlah sesuai atau dikoreksi.
