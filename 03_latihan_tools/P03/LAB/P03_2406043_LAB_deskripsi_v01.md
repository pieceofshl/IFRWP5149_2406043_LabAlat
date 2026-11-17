# Use Case Description P03 LAB

## LAB-UC03 - Ajukan peminjaman
| Elemen | Isi |
|---|---|
| ID dan nama | LAB-UC03 - Ajukan peminjaman |
| Sumber kebutuhan | LAB-R03 dan LAB-R04 |
| Tujuan | Menghasilkan pengajuan peminjaman yang tersimpan |
| Aktor utama | Mahasiswa |
| Pemicu | Mahasiswa memilih fungsi pengajuan peminjaman |
| Prasyarat | Mahasiswa telah terautentikasi; data peralatan tersedia |
| Include | LAB-UC04 - Periksa ketersediaan |
| Extension point | Bukti pengajuan tersedia, pada langkah 6 |
| Extend | LAB-UC05 jika [mahasiswa memilih cetak] |
| Pascakondisi berhasil | Pengajuan tersimpan dengan nomor dan status Menunggu keputusan |
| Pascakondisi gagal | Tidak ada pengajuan baru yang berhasil tersimpan |

| Langkah | Tindakan mahasiswa | Respons sistem |
|---:|---|---|
| 1 | Membuka pengajuan | Menampilkan formulir |
| 2 | Memilih alat, jumlah, rentang waktu, dan tujuan | Menampung isian |
| 3 | Mengirim pengajuan | Memeriksa kelengkapan data |
| 4 | - | Menjalankan LAB-UC04 |
| 5 | - | Jika tersedia, menyimpan pengajuan dan memberikan nomor |
| 6 | Melihat konfirmasi | Menampilkan nomor dan status; mencapai extension point |
| 7 | Mengakhiri pengajuan | Menutup proses pengajuan |

**Alternatif:** A1 (langkah 4) peralatan tidak tersedia: sistem menampilkan pesan dan tidak menyimpan pengajuan. A2 (langkah 3) data tidak lengkap: sistem meminta melengkapi isian dan tidak menyimpan pengajuan. A3 (langkah 6) mahasiswa memilih cetak: jalankan LAB-UC05; pengajuan tetap tersimpan jika tidak mencetak.

## LAB-UC05 - Cetak bukti pengajuan
| Elemen | Isi |
|---|---|
| ID dan nama | LAB-UC05 - Cetak bukti pengajuan |
| Sumber kebutuhan | LAB-R04 |
| Tujuan | Bukti pengajuan tercetak sebagai tambahan bersyarat |
| Aktor utama | Mahasiswa |
| Pemicu | Mahasiswa memilih cetak pada konfirmasi pengajuan |
| Prasyarat | LAB-UC03 berhasil menyimpan pengajuan; extension point Bukti pengajuan tersedia tercapai |
| Relasi | LAB-UC05 «extend» LAB-UC03, kondisi [mahasiswa memilih cetak] |
| Pascakondisi berhasil | Bukti pengajuan tercetak; status pengajuan tetap Menunggu keputusan |
| Pascakondisi gagal | Pengajuan yang tersimpan tidak berubah |

| Langkah | Tindakan mahasiswa | Respons sistem |
|---:|---|---|
| 1 | Memilih cetak bukti | Menampilkan bukti dengan nomor dan status |
| 2 | Mengonfirmasi pencetakan | Mencetak bukti pengajuan |

**Alternatif:** A1 (langkah 1) mahasiswa tidak memilih cetak: use case tidak dijalankan dan pengajuan tetap berhasil.
