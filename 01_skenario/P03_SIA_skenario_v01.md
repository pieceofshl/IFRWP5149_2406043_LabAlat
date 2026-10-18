<!-- Deskripsi skenario -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

<!-- Tabel kebutuhan -->
| ID      | Kebutuhan tugas                                                            |
|---------|----------------------------------------------------------------------------|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah.                                     |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah.                              |
| SIA-R03 | Mahasiswa dapat mengajukan KRS.                                            |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan.                           |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS.                 |

<!-- Batas sistem dan asumsi -->
- Pengguna telah terautentikasi.
- Data mata kuliah, prasyarat, dan jadwal tersedia.
- Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
- Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
- KRS tersimpan belum berarti disetujui.
- Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

<!-- Tabel identifikasi aktor -->
| Aktor      | Tujuan terhadap sistem                                                       | Sumber kebutuhan |
|------------|------------------------------------------------------------------------------|------------------|
| Mahasiswa  | Mengajukan KRS dan, jika dipilih, mengunduh bukti pada konfirmasi pengajuan. | SIA-R03, SIA-R05 |
| Dosen wali | Menyetujui atau menolak KRS serta memberikan catatan keputusan.              | SIA-R06          |

<!-- Katalog use case -->
| ID       | Nama use case             | Aktor terkait / peran                          | Sumber kebutuhan |
|----------|---------------------------|------------------------------------------------|------------------|
| SIA-UC01 | Ajukan KRS                | Mahasiswa                                      | SIA-R03          |
| SIA-UC02 | Validasi KRS              | Perilaku sistem yang disertakan dalam SIA-UC01 | SIA-R04          |
| SIA-UC03 | Unduh bukti pengajuan KRS | Mahasiswa                                      | SIA-R05          |
| SIA-UC04 | Proses keputusan KRS      | Dosen wali                                     | SIA-R06          |

**Catatan ruang lingkup:** SIA-R01 dan SIA-R02 tetap dipertahankan sebagai kebutuhan jadwal dari Pertemuan 2 dengan identitas yang berbeda. Keduanya tidak dimodelkan sebagai use case pada diagram KRS ini. Karena itu, Admin akademik tidak ditambahkan sebagai aktor dalam diagram KRS.

<!-- Relasi `«include»` -->
| Elemen | Keterangan |
|---|---|
| **Use case utama** | **SIA-UC01 — Ajukan KRS** |
| **Relasi** | `«include»` |
| **Use case yang disertakan** | **SIA-UC02 — Validasi KRS** |
| **Alasan** | Setiap pengajuan memeriksa kelengkapan data, prasyarat mata kuliah, dan benturan jadwal. |

**Arah panah:** `SIA-UC01 — Ajukan KRS` → `SIA-UC02 — Validasi KRS`.

Validasi merupakan bagian dari proses pengajuan. Jika validasi gagal, pengajuan tidak berhasil tersimpan.

<!-- Relasi `«extend»` -->
| Elemen | Keterangan |
|---|---|
| **Use case tambahan** | **SIA-UC03 — Unduh bukti pengajuan KRS** |
| **Relasi** | `«extend»` |
| **Use case dasar** | **SIA-UC01 — Ajukan KRS** |
| **Kondisi** | Mahasiswa memilih mengunduh bukti pada konfirmasi pengajuan. |
| **Extension point** | Bukti pengajuan tersedia pada konfirmasi penyimpanan. |
| **Alasan** | Pengunduhan bukti bersifat opsional dan tidak menentukan keberhasilan pengajuan KRS. |

**Arah panah:** `SIA-UC03 — Unduh bukti pengajuan KRS` → `SIA-UC01 — Ajukan KRS`.

Perilaku tambahan dijalankan hanya ketika kondisi tersebut terpenuhi. Tanpa mengunduh bukti, pengajuan KRS tetap berhasil tersimpan jika validasi berhasil.
