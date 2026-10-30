Institut Teknologi Garut 

S1 Teknik Informatika 

# **PERTEMUAN 5** 

## **SKENARIO USE CASE: DARI DIAGRAM KE LANGKAH KEGIATAN** 

### **A. TUJUAN PEMBELAJARAN** 

Setelah mengikuti praktikum, mahasiswa mampu: 

1. Menyusun tabel skenario untuk satu use case dengan struktur lengkap yaitu baris Nama use case, Aktor, Tujuan, dan Deskripsi, dilanjutkan kolom Kegiatan dan Respon sistem, bagian Skenario Normal, bagian Skenario Alternative, dan baris Skenario Akhir, tanpa ada field yang kosong. 

2. Menulis langkah skenario secara berurutan dengan satu aksi pada setiap langkah, pemisahan yang benar antara aksi aktor pada kolom Kegiatan dan tanggapan sistem pada kolom Respon sistem, serta penomoran langkah yang berlanjut dari Skenario Normal ke Skenario Alternative. 

3. Memetakan relasi include menjadi langkah wajib di dalam Skenario Normal dan relasi extend menjadi cabang bersyarat pada Skenario Alternative yang dilengkapi condition dan extension point. 

4. Menerapkan generalization aktor dengan menulis skenario satu kali atas nama aktor umum ditambah catatan perbedaan aktor khusus, dan menerapkan generalization use case dengan menulis skenario use case umum ditambah skenario khusus yang hanya memuat perilaku pembeda. 

5. Menelaah 12 tabel skenario studi kasus laboratorium dari diagram kumulatif Pertemuan 4 dengan mencocokkan setiap tabel terhadap diagram acuan, dan menyusun 7 tabel skenario untuk tugas akademik, dengan nama, ID, aktor, dan relasi yang sama persis dengan diagram acuan. 

Tujuan di atas terukur melalui produk yang dihasilkan mahasiswa, yaitu lembar skenario atas 12 tabel skenario studi kasus laboratorium dan 7 tabel skenario tugas akademik. Produk tersebut diperiksa dengan checklist pada bagian C.4 dan dinilai dengan rubrik praktik RPS. 

Praktikum Analisis dan Desain Berorientasi Objek  |  69 

Institut Teknologi Garut 

S1 Teknik Informatika 

### **B. TEORI ATAU PRINSIP DASAR PRAKTIKUM** 

### **1. Pengertian skenario use case** 

Skenario use case adalah uraian langkah demi langkah tentang interaksi antara aktor dan sistem untuk satu use case. Skenario menjawab pertanyaan bagaimana use case itu berjalan dari awal sampai selesai: apa yang dilakukan aktor, apa yang ditanggapi sistem, pada langkah mana alur dapat bercabang, dan pada kondisi apa use case dinyatakan selesai. Skenario ditulis dalam bentuk tabel dua kolom, yaitu kolom Kegiatan untuk aksi aktor dan kolom Respon sistem untuk tanggapan sistem, sehingga urutan interaksi dapat dibaca dari atas ke bawah tanpa penjelasan tambahan. 

Skenario berbeda dari use case description yang dilatih pada Pertemuan 3. Use case description merangkum satu use case: tujuan, pemicu, prasyarat, alur utama secara ringkas, alur alternatif, dan pascakondisi. Skenario merinci alur tersebut menjadi langkah demi langkah yang dapat diikuti dan diuji satu per satu. Hubungan keduanya: satu use case description dapat dijabarkan menjadi satu tabel skenario, dan satu tabel skenario harus konsisten dengan use case description use case yang sama. Apabila keduanya bertentangan, salah satunya keliru dan harus diperbaiki sebelum pengumpulan. 

Skenario juga berbeda dari use case diagram. Diagram pada Pertemuan 4 menunjukkan use case apa saja yang ada dan bagaimana hubungannya, tetapi tidak menunjukkan urutan langkah. Skenario melengkapi diagram dengan urutan tersebut. Karena itu pada pertemuan ini tidak ada diagram baru: diagram acuan adalah diagram kumulatif Pertemuan 4, dan pekerjaan baru mahasiswa sepenuhnya adalah penulisan skenario dari diagram tersebut. 

### **2. Struktur tabel skenario** 

Tabel skenario pada jobsheet ini mengikuti persis struktur contoh penerapan yang dilampirkan pada tugas Pertemuan 5. Urutan penulisannya adalah sebagai berikut. 

- a. Baris Nama use case: nama use case yang diskemakan, ditulis sama persis dengan nama pada diagram. 

Praktikum Analisis dan Desain Berorientasi Objek  |  70 

Institut Teknologi Garut 

S1 Teknik Informatika 

- b. Baris Aktor: aktor utama yang menjalankan use case. Apabila aktornya adalah aktor umum, tuliskan nama aktor umum tersebut dan tambahkan catatan aktor khusus yang berlaku. 

- c. Baris Tujuan: hasil yang ingin dicapai aktor melalui use case, ditulis dalam satu kalimat. 

- d. Baris Deskripsi: penjelasan singkat tentang apa yang dilakukan aktor dan sistem pada use case ini. 

- e. Kepala kolom Kegiatan dan Respon sistem: setelah baris Deskripsi, tabel dilanjutkan dengan dua kolom. Kolom Kegiatan berisi aksi aktor, kolom Respon sistem berisi tanggapan sistem. 

- f. Bagian Skenario Normal: langkah langkah jalur utama yang terjadi apabila semua berjalan sesuai rencana. Bagian ini ditulis pertama. 

- g. Bagian Skenario Alternative: langkah langkah jalur cabang, yaitu jalur yang terjadi apabila suatu kondisi menyimpang dari jalur normal, misalnya data tidak tersedia, isian tidak lengkap, atau kondisi extend terpenuhi. Penomoran langkah pada bagian ini MELANJUTKAN penomoran Skenario Normal, tidak dimulai lagi dari nomor 1. 

- h. Baris Skenario Akhir: satu kalimat yang menyatakan kondisi selesai use case, mencakup jalur berhasil dan jalur gagal. Baris ini bukan langkah bernomor baru. 

Aturan penomoran berlanjut ini penting karena setiap cabang alternatif merujuk ke langkah tempat cabang terjadi. Apabila penomoran diulang dari 1 pada Skenario Alternative, rujukan cabang menjadi ambigu dan pemeriksa tidak dapat mengetahui cabang itu berasal dari langkah normal yang mana. 

### **3. Kaidah penulisan langkah skenario** 

- a. Satu langkah berisi satu aksi. Jangan menggabungkan dua aksi aktor atau dua tanggapan sistem ke dalam satu langkah, misalnya memilih peralatan dan mengisi tanggal pada langkah yang sama. 

- b. Kolom Kegiatan hanya berisi aksi aktor, kolom Respon sistem hanya berisi tanggapan sistem. Jangan menulis aksi aktor pada kolom Respon sistem dan jangan menulis tanggapan sistem pada kolom Kegiatan. 

Praktikum Analisis dan Desain Berorientasi Objek  |  71 

Institut Teknologi Garut 

S1 Teknik Informatika 

- c. Gunakan kalimat aktif yang singkat dan diawali kata kerja, misalnya memilih, mengisi, mengirim, menampilkan, memeriksa, menyimpan, dan menolak. 

- d. Data yang dimasukkan dan data yang ditampilkan disebut secara eksplisit: nama field, nilai, atau status. Tulis misalnya tanggal pinjam, tanggal rencana kembali, dan status Menunggu Keputusan, bukan sekadar data. 

- e. Setiap cabang pada Skenario Alternative merujuk ke langkah tempat cabang terjadi, dengan menulis frasa cabang dari langkah N di awal langkah cabang tersebut. 

- f. Penomoran langkah berlanjut dari Skenario Normal ke Skenario Alternative tanpa pengulangan nomor. 

- g. Skenario Akhir menyatakan kondisi selesai untuk jalur berhasil dan jalur gagal, bukan mengulang langkah terakhir. 

- h. Nama aktor, nama use case, ID, condition, dan extension point ditulis sama persis dengan diagram Pertemuan 4 dan jobsheet Pertemuan 4. 

### **4. Pemetaan relasi diagram ke dalam langkah skenario** 

Diagram kumulatif Pertemuan 4 memuat lima jenis relasi. Masing-masing dipetakan ke dalam skenario dengan cara yang berbeda. Tabel berikut adalah aturan pemetaan yang wajib dipakai pada seluruh tabel skenario Pertemuan 5. 

**Tabel 5 Aturan pemetaan relasi diagram ke skenario** 

|**Relasi pada**<br>**diagram**|**Cara menulisnya di dalam tabel skenario**|
|---|---|
|Include|Menjadi langkah rujukan di dalam Skenario Normal, ditulis<br>pada posisi urutan yang sesuai dengan menyebut nama<br>dan ID use case yang disertakan serta tabel skenarionya,<br>tanpa menyalin langkah use case yang disertakan. Contoh:<br>langkah 2 pada Tabel 5.1 merujuk ke Tabel skenario LAB-<br>UC04 Periksa Ketersediaan. Include tidak pernah ditulis<br>sebagai alternatif, karena perilaku yang disertakan selalu<br>terjadi.|
|Extend|Menjadi cabang bersyarat pada Skenario Alternative,<br>dilengkapi condition dan extension point, dan ditulis<br>sebagai rujukan ke tabel skenario use case tambahan<br>tanpa menyalin langkahnya. Use case dasar tetap selesai<br>tanpa cabang ini. Contoh: langkah 11 dan 12 pada Tabel|



Praktikum Analisis dan Desain Berorientasi Objek  |  72 

Institut Teknologi Garut 

S1 Teknik Informatika 

|**Relasi pada**<br>**diagram**|**Cara menulisnya di dalam tabel skenario**<br>|
|---|---|
||5.1 merujuk ke Tabel skenario LAB-UC05 Cetak Bukti<br>Pengajuan dengan condition [mahasiswa memilih cetak]<br>dan extension point Bukti pengajuan tersedia.|
|Generalization<br>aktor|Skenario ditulis satu kali atas nama aktor umum, ditambah<br>catatan aktor khusus yang berlaku. Perbedaan perilaku<br>satu aktor khusus ditulis sebagai cabang atau catatan pada<br>tabel yang sama, bukan sebagai tabel terpisah. Contoh:<br>Tabel 5.1 ditulis atas nama Peminjam dan berlaku untuk<br>Mahasiswa dan Dosen; cabang cetak bukti hanya berlaku<br>untuk mahasiswa.|
|Generalization<br>use case|Skenario use case umum ditulis sebagai perilaku bersama,<br>lalu setiap use case khusus mendapat tabel sendiri yang<br>hanya memuat perilaku pembeda dan merujuk ke skenario<br>umum untuk langkah bersama. Contoh: Tabel skenario<br>UC02 memuat pengelolaan bersama, sedangkan tabel<br>UC08, UC09, dan UC10 masing-masing memuat perilaku<br>tambah, ubah, dan hapus.|
|Collaboration<br>dan realization|Collaboration TIDAK diberi langkah kegiatan sendiri dan<br>TIDAK dibuatkan tabel skenario sendiri. Collaboration<br>cukup disebut pada keterangan tabel use case yang<br>direalisasikannya, misalnya LAB-CO01 pada tabel UC03.<br>Isi collaboration berupa peran elemen dan pertukaran<br>pesan dijabarkan pada diagram interaksi pada pertemuan<br>berikutnya.|



### **5. Contoh penerapan lengkap: LAB-UC03 Ajukan Peminjaman** 

Tabel berikut adalah contoh penerapan yang lengkap dan menjadi acuan gaya penulisan seluruh tabel pada pertemuan ini. Perhatikan tiga hal: include LAB-UC04 menjadi langkah rujukan nomor 2 pada Skenario Normal (lihat Tabel skenario LAB-UC04 pada bagian C.2, tanpa menyalin langkahnya); extend LAB-UC05 menjadi cabang nomor 11 dan 12 pada Skenario Alternative lengkap dengan condition dan extension point (lihat Tabel skenario LAB-UC05 pada bagian C.2); dan aktor ditulis sebagai Peminjam dengan catatan berlaku untuk Mahasiswa dan Dosen. Collaboration LABCO01 disebut pada keterangan di bawah tabel, tanpa langkah kegiatan sendiri. 

Praktikum Analisis dan Desain Berorientasi Objek  |  73 

Institut Teknologi Garut 

S1 Teknik Informatika 

**Tabel 5.1 Skenario Use Case LAB-UC03 Ajukan Peminjaman** 

|**Nama use case**|LAB-UC03 Ajukan Peminjaman|
|---|---|
|**Aktor**|Peminjam (berlaku untuk Mahasiswa dan<br>Dosen)|
|**Tujuan**|Pengajuan peminjaman tercatat dan dapat<br>diproses oleh petugas|
|**Deskripsi**<br>|Peminjam memilih peralatan yang tersedia,<br>mengisi data peminjaman, dan mengirim<br>pengajuan<br>|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Peminjam memilih peralatan<br>yang akan dipinjam||
||2. Sistem menjalankan Periksa Ketersediaan<br>(lihat Tabel skenario LAB-UC04)|
|3. Peminjam mengisi tanggal<br>pinjam, tanggal rencana<br>kembali, dan keperluan<br>peminjaman||
||4. Sistem memeriksa kelengkapan isian dan<br>menampilkan ringkasan pengajuan|
|5. Peminjam mengirim<br>pengajuan||
||6. Sistem menyimpan pengajuan dengan status<br>Menunggu Keputusan dan menampilkan nomor<br>pengajuan|
|**Skenario Alternative**||
|7. Peralatan yang dipilih tidak<br>tersedia (cabang dari langkah<br>2)||
||8. Sistem menampilkan pesan peralatan tidak<br>tersedia dan pengajuan tidak dilanjutkan|
|9. Isian pengajuan tidak<br>lengkap (cabang dari langkah<br>4)||
||10. Sistem menampilkan pesan isian belum<br>lengkap dan meminta peminjam melengkapi<br>isian|
|11. Peminjam memilih cetak<br>bukti, dengan condition<br>[mahasiswa memilih cetak] dan<br>extension point Bukti<br>pengajuan tersedia (extend<br>LAB-UC05 Cetak Bukti<br>Pengajuan; lihat Tabel<br>skenario LAB-UC05)||
||12. Sistem menampilkan bukti pengajuan<br>dengan nomor pengajuan sesuai Tabel<br>skenario LAB-UC05|
|**Skenario Akhir**|Use case selesai jika pengajuan tersimpan<br>dengan status Menunggu Keputusan; jika|



Praktikum Analisis dan Desain Berorientasi Objek  |  74 

Institut Teknologi Garut 

S1 Teknik Informatika 

peralatan tidak tersedia atau isian tidak lengkap, pengajuan tidak tersimpan dan peminjam kembali ke daftar peralatan atau <u>melengkapi isian.</u> 

Keterangan tabel: use case ini direalisasikan oleh collaboration LABCO01 Ajukan Peminjaman. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Periksa kembali Tabel 5.1 terhadap diagram kumulatif Pertemuan 4: asosiasi Peminjam ke LAB-UC03 menjadi dasar baris Aktor, include ke LAB-UC04 menjadi langkah rujukan nomor 2, dan extend dari LAB-UC05 menjadi langkah rujukan nomor 11 dan 12. Tidak ada langkah pada tabel ini yang tidak mempunyai dasar pada diagram atau kebutuhan LAB-R03 dan LAB-R07. 

### **6. Kesalahan umum yang harus dihindari** 

- a. Menulis dua aksi dalam satu langkah, sehingga langkah tidak dapat diuji satu per satu. 

- b. Menulis aksi aktor pada kolom Respon sistem atau tanggapan sistem pada kolom Kegiatan. 

- c. Mengulang penomoran dari 1 pada Skenario Alternative, sehingga rujukan cabang menjadi ambigu. 

- d. Menulis include sebagai alternatif atau extend tanpa condition dan tanpa extension point, padahal aturan pemetaan keduanya sudah ditetapkan pada Tabel 5.0. 

- e. Menulis Skenario Akhir sebagai langkah bernomor baru, padahal fungsinya adalah kalimat kondisi selesai. 

- f. Mengubah nama, ID, atau aktor dari diagram Pertemuan 4 pada saat menulis skenario. 

### **C. PROSEDUR DAN MEKANISME PRAKTIK** 

### **1. Workspace dan penamaan** 

Gunakan folder induk yang telah ditetapkan pada Pertemuan 1, yaitu IFRWP5149_<NIM>_LabAlat. Dokumen skenario Pertemuan 5 disimpan pada folder 01_skenario dengan nama P05_<NIM>_LAB_skenario_v01.md untuk lembar studi kasus dan P05_<NIM>_SIA_skenario_v01.drawio untuk tugas. Diagram tetap berada pada folder 04_model_analisis/P04 dan tidak dibuat folder diagram P05, karena pada pertemuan ini tidak ada diagram 

Praktikum Analisis dan Desain Berorientasi Objek  |  75 

Institut Teknologi Garut 

S1 Teknik Informatika 

baru. Berkas P04 tidak ditimpa dan tidak diubah isinya. Berkas skenario Pertemuan 4 pada folder 01_skenario tetap disimpan sebagai arsip kebutuhan dan tidak diganti oleh berkas P05. 

IFRWP5149_<NIM>_LabAlat/ 01_skenario/ P05_<NIM>_LAB_skenario_v01.md   (baru, Pertemuan 5) P05_<NIM>_SIA_skenario_v01.md  (baru, Pertemuan 5) P04_LAB_skenario_v01.md           (tetap, arsip Pertemuan 4) P04_SIA_skenario_v01.md           (tetap, arsip Pertemuan 4) 04_model_analisis/ P03/                              (tetap, jangan diubah) P04/ LAB/   P04_<NIM>_LAB_usecase_v01.drawio dan .png   (acuan, tidak diubah) SIA/   P04_<NIM>_SIA_usecase_v01.drawio dan .png   (acuan, tidak diubah) P05/ LAB/ P05_<NIM>_LAB_skenario_v01.drawio <u>SIA/ P05_<NIM>_SIA_skenario_v01.drawio</u> 

Dokumen ditulis dalam format dokumen Drawio agar tabel dan lembar skenario dapat disunting dan diperiksa pada saat review. Jangan menulis tabel skenario di dalam berkas drawio, karena berkas diagram adalah acuan yang tidak diubah pada pertemuan ini. 

### **2. Studi Kasus: Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus** 

Studi kasus ini memakai diagram kumulatif Pertemuan 4 sebagai acuan. Kebutuhan LAB-R01 sampai LAB-R11 dan spesifikasi 17 hubungan pada diagram dirujuk dari Jobsheet Pertemuan 4 (khususnya Tabel 4.5); tidak ada kebutuhan baru dan tidak ada use case baru pada pertemuan ini. Seluruh tabel skenario studi kasus dimuat lengkap pada bagian ini sebagai bahan kajian, sehingga mahasiswa tidak lagi ditugasi menulis tabel studi kasus. Pekerjaan mahasiswa pada studi kasus adalah menelaah kedua belas tabel tersebut terhadap diagram acuan. 

### **_Langkah 1: Buka kembali diagram kumulatif Pertemuan 4_** , yaitu berkas 

P04_<NIM>_LAB_usecase_v01.drawio pada folder 04_model_analisis/P04/LAB, hanya sebagai acuan. Jangan mengubah isi diagram. Periksa kembali 5 aktor, 12 use case, 2 collaboration, dan 17 hubungannya sebelum membaca tabel. 

Praktikum Analisis dan Desain Berorientasi Objek  |  76 

Institut Teknologi Garut 

S1 Teknik Informatika 

**_Langkah 2: Baca kedua belas tabel skenario menurut kelompoknya:_** peminjaman (UC01, UC03, UC04, UC05), pengelolaan data (UC02, UC08, UC09, UC10), keputusan dan laporan (UC06, UC07), dan pengembalian (UC11, UC12). Tabel UC03 adalah Tabel 5.1 pada bab teori; kesebelas tabel lainnya terdapat pada bagian ini. 

**_Langkah 3: Cocokkan setiap tabel dengan diagram._** Untuk setiap tabel, periksa tiga hal: aktor pada baris Aktor sama persis dengan aktor pada diagram; setiap langkah kunci menelusur ke satu relasi pada diagram (asosiasi, include, extend, generalization, atau realization); dan ID, nama use case, condition, serta extension point ditulis sama persis dengan diagram. 

**_Langkah 4: Periksa catatan Kepala Laboratorium._** Aktor ini hanya mempunyai satu use case, yaitu LAB-UC07 Lihat Laporan Peminjaman, dan LAB-UC07 tidak mempunyai relasi lain. Tabel skenario UC07 karena itu berdiri sendiri dan tidak memuat langkah include, extend, generalization, atau realization. 

**_Langkah 5: Isi lembar skenario dengan checklist_** pada bagian C.4 ditambah satu kolom penelusuran singkat per tabel (tabel skenario, relasi yang ditelusur, dan hasil pencocokan). Simpan lembar skenario sebagai P05_<NIM>_LAB_skenario_v01.md pada folder 01_skenario. Dokumen ini adalah deliverable studi kasus; diagram P04 tetap tidak diubah. 

Indeks berikut memuat kedua belas tabel skenario studi kasus dalam urutan kelompok. Tabel hanya memuat ID dan nama, karena uraian lengkap masing-masing tabel terdapat pada bagian ini dan pada Tabel 5.1 untuk UC03. 

**Tabel 5.2 Indeks tabel skenario studi kasus LAB** 

|**ID**|**Nama use case**|
|---|---|
|LAB-UC01|Lihat Ketersediaan Peralatan|
|LAB-UC03|Ajukan Peminjaman|
|LAB-UC04|Periksa Ketersediaan|
|LAB-UC05|Cetak Bukti Pengajuan|
|LAB-UC02|Kelola Data Peralatan|
|LAB-UC08|Tambah Data Peralatan|



Praktikum Analisis dan Desain Berorientasi Objek  |  77 

Institut Teknologi Garut 

S1 Teknik Informatika 

|**ID**|**Nama use case**|
|---|---|
|LAB-UC09|Ubah Data Peralatan|
|LAB-UC10|Hapus Data Peralatan|
|LAB-UC06|Proses Keputusan Peminjaman|
|LAB-UC07|Lihat Laporan Peminjaman|
|LAB-UC11|Catat Pengembalian Peralatan|
|LAB-UC12|Periksa Kondisi Peralatan|



Kelompok peminjaman terdiri atas UC01, UC03, UC04, dan UC05. Tabel UC03 sudah disajikan sebagai Tabel 5.1 pada bab teori; tiga tabel berikut melengkapinya. 

**Tabel 5.3 Skenario Use Case LAB-UC01 Lihat Ketersediaan Peralatan** 

|**Nama use case**|LAB-UC01 Lihat Ketersediaan Peralatan|
|---|---|
|**Aktor**|Peminjam (berlaku untuk Mahasiswa dan<br>Dosen)|
|**Tujuan**|Peminjam dapat mengetahui peralatan yang<br>tersedia sebelum mengajukan peminjaman|
|**Deskripsi**|Peminjam membuka fungsi ketersediaan dan<br>melihat daftar peralatan beserta status<br>ketersediaannya|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Peminjam membuka fungsi<br>Lihat Ketersediaan Peralatan||
||2. Sistem menampilkan daftar peralatan<br>beserta status ketersediaannya|
|**Skenario Alternative**||
|3. Tidak ada peralatan yang<br>tersedia pada daftar (cabang<br>dari langkah 2)||
||4. Sistem menampilkan pesan tidak ada<br>peralatan yang tersedia|
|**Skenario Akhir**|Use case selesai jika daftar peralatan beserta<br>status ketersediaannya ditampilkan; jika tidak<br>ada peralatan yang tersedia, use case selesai<br>dengan pesan tersebut.|



**Tabel 5.4 Skenario Use Case LAB-UC04 Periksa Ketersediaan** 

|**Nama use case**|LAB-UC04 Periksa Ketersediaan|
|---|---|
|**Aktor**|Peminjam (berjalan di dalam LAB-UC03 Ajukan<br>Peminjaman)|
|**Tujuan**|Ketersediaan peralatan yang dipilih terperiksa<br>sebelum pengajuan disimpan|
|**Deskripsi**|Sistem memeriksa jumlah dan status peralatan<br>yang dipilih peminjam dan menyampaikan<br>hasilnya kepada alur pengajuan. Use case ini<br>berjalan di dalam UC03 dan tidak mempunyai|



Praktikum Analisis dan Desain Berorientasi Objek  |  78 

Institut Teknologi Garut 

S1 Teknik Informatika 

||interaksi langsung dengan aktor|
|---|---|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Alur pengajuan memanggil<br>Periksa Ketersediaan dengan<br>peralatan yang dipilih||
||2. Sistem memeriksa jumlah dan status<br>peralatan tersebut|
|3. Sistem menyatakan<br>peralatan tersedia||
||4. Alur pengajuan melanjutkan penyimpanan<br>pengajuan|
|**Skenario Alternative**||
|5. Peralatan tidak tersedia atau<br>jumlah tidak mencukupi<br>(cabang dari langkah 2)||
||6. Sistem menyampaikan hasil tidak tersedia<br>sehingga alur pengajuan berhenti|
|**Skenario Akhir**|Use case selesai jika hasil pemeriksaan<br>tersampaikan kepada alur pengajuan; hasil<br>tersedia melanjutkan pengajuan, hasil tidak<br>tersedia menghentikan pengajuan.|



**Tabel 5.5 Skenario Use Case LAB-UC05 Cetak Bukti Pengajuan** 

|**Nama use case**|LAB-UC05 Cetak Bukti Pengajuan|
|---|---|
|**Aktor**|Mahasiswa (asosiasi khusus)|
|**Tujuan**|Bukti pengajuan tercetak sebagai tambahan<br>bersyarat pada pengajuan|
|**Deskripsi**|Mahasiswa yang memilih cetak pada<br>konfirmasi pengajuan menerima bukti<br>pengajuan dengan nomor pengajuan. Cabang<br>ini berlaku dengan condition [mahasiswa<br>memilih cetak] dan extension point Bukti<br>pengajuan tersedia pada LAB-UC03|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Mahasiswa memilih cetak<br>bukti pada konfirmasi<br>pengajuan||
||2. Sistem menampilkan bukti pengajuan<br>dengan nomor pengajuan dan status<br>Menunggu Keputusan|
|3. Mahasiswa mengonfirmasi<br>pencetakan||
||4. Sistem mencetak bukti pengajuan|
|**Skenario Alternative**||
|5. Mahasiswa tidak memilih<br>cetak (cabang dari langkah 1)||
||6. Sistem menutup konfirmasi tanpa mencetak<br>bukti dan pengajuan tetap tersimpan|
|**Skenario Akhir**|Use case selesai jika bukti pengajuan tercetak;|



Praktikum Analisis dan Desain Berorientasi Objek  |  79 

Institut Teknologi Garut 

S1 Teknik Informatika 

jika mahasiswa tidak memilih cetak, pengajuan <u>tetap selesai tanpa bukti cetak.</u> 

Kelompok pengelolaan data terdiri atas UC02 sebagai use case umum dan UC08, UC09, serta UC10 sebagai use case khusus. Tabel UC02 memuat perilaku bersama; ketiga tabel khusus hanya memuat langkah pembedanya dan merujuk ke Tabel 5.6 untuk langkah bersama. 

**Tabel 5.6 Skenario Use Case LAB-UC02 Kelola Data Peralatan** 

|**Nama use case**|LAB-UC02 Kelola Data Peralatan|
|---|---|
|**Aktor**|Petugas Laboratorium|
|**Tujuan**|Data peralatan terkelola melalui satu fungsi<br>pengelolaan bersama<br>|
|**Deskripsi**|Petugas membuka fungsi pengelolaan data<br>peralatan, memilih bentuk pengelolaan, dan<br>menyimpan perubahan. Bentuk tambah, ubah,<br>dan hapus dijabarkan pada tabel khususnya<br>masing-masing|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Petugas membuka fungsi<br>Kelola Data Peralatan||
||2. Sistem menampilkan daftar data peralatan|
|3. Petugas memilih bentuk<br>pengelolaan, yaitu tambah,<br>ubah, atau hapus||
||4. Sistem menampilkan formulir sesuai bentuk<br>pengelolaan yang dipilih|
|5. Petugas mengisi atau<br>mengonfirmasi data||
||6. Sistem memeriksa kelengkapan dan<br>keabsahan data|
|7. Petugas menyimpan<br>perubahan||
||8. Sistem menyimpan perubahan dan<br>menampilkan konfirmasi|
|**Skenario Alternative**||
|9. Data tidak lengkap atau<br>tidak sah (cabang dari langkah<br>6)||
||10. Sistem menolak penyimpanan dan<br>menampilkan pesan kesalahan data|
|**Skenario Akhir**|Use case selesai jika perubahan data peralatan<br>tersimpan; jika data tidak lengkap atau tidak<br>sah, perubahan tidak tersimpan.|



Praktikum Analisis dan Desain Berorientasi Objek  |  80 

Institut Teknologi Garut 

S1 Teknik Informatika 

**Tabel 5.7 Skenario Use Case LAB-UC08 Tambah Data Peralatan** 

|**Nama use case**|LAB-UC08 Tambah Data Peralatan|
|---|---|
|**Aktor**|Petugas Laboratorium|
|**Tujuan**|Data peralatan baru tersimpan sebagai bentuk<br>khusus dari pengelolaan data peralatan|
|**Deskripsi**|Petugas mengisi data peralatan baru dan<br>menyimpan data tersebut; langkah bersama<br>mengikuti Tabel skenario LAB-UC02|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Petugas membuka fungsi<br>Tambah Data Peralatan||
||2. Sistem menampilkan formulir data peralatan<br>baru|
|3. Petugas mengisi data<br>peralatan baru||
||4. Sistem memeriksa kelengkapan data|
|5. Petugas menyimpan data||
||6. Sistem menyimpan data peralatan baru dan<br>menampilkan konfirmasi|
|**Skenario Alternative**||
|7. Data tidak lengkap (cabang<br>dari langkah 4)||
||8. Sistem menolak penyimpanan dan meminta<br>petugas melengkapi data|
|**Skenario Akhir**|Use case selesai jika data peralatan baru<br>tersimpan; jika data tidak lengkap, data tidak<br>tersimpan.|



Keterangan: use case khusus dari LAB-UC02 Kelola Data Peralatan. 

Perilaku pembeda: data baru tersimpan. Langkah bersama mengikuti Tabel skenario LAB-UC02. 

**Tabel 5.8 Skenario Use Case LAB-UC09 Ubah Data Peralatan** 

|**Nama use case**|LAB-UC09 Ubah Data Peralatan|
|---|---|
|**Aktor**|Petugas Laboratorium|
|**Tujuan**|Data peralatan berubah sebagai bentuk khusus<br>dari pengelolaan data peralatan|
|**Deskripsi**|Petugas memilih data peralatan, mengubah<br>datanya, dan menyimpan perubahan; langkah<br>bersama mengikuti Tabel skenario LAB-UC02|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Petugas memilih data<br>peralatan yang akan diubah||
||2. Sistem menampilkan data peralatan saat ini|
|3. Petugas mengubah data<br>peralatan||



Praktikum Analisis dan Desain Berorientasi Objek  |  81 

Institut Teknologi Garut 

S1 Teknik Informatika 

||4. Sistem memeriksa perubahan data|
|---|---|
|5. Petugas menyimpan<br>perubahan||
||6. Sistem menyimpan data yang diubah dan<br>menampilkan konfirmasi|
|**Skenario Alternative**||
|7. Data peralatan tidak<br>ditemukan (cabang dari<br>langkah 2)||
||8. Sistem menampilkan pesan data peralatan<br>tidak ditemukan|
|**Skenario Akhir**|Use case selesai jika perubahan data peralatan<br>tersimpan; jika data tidak ditemukan,<br>perubahan tidak tersimpan.|



Keterangan: use case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data peralatan berubah. Langkah bersama mengikuti Tabel skenario LAB-UC02. 

**Tabel 5.9 Skenario Use Case LAB-UC10 Hapus Data Peralatan** 

|**Nama use case**|LAB-UC10 Hapus Data Peralatan|
|---|---|
|**Aktor**|Petugas Laboratorium|
|**Tujuan**|Data peralatan terhapus sebagai bentuk<br>khusus dari pengelolaan data peralatan|
|**Deskripsi**|Petugas memilih data peralatan,<br>mengonfirmasi penghapusan, dan sistem<br>menghapus data tersebut; langkah bersama<br>mengikuti Tabel skenario LAB-UC02|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Petugas memilih data<br>peralatan yang akan dihapus||
||2. Sistem memeriksa peralatan tidak sedang<br>dipinjam dan tidak memiliki pengajuan aktif|
|3. Petugas mengonfirmasi<br>penghapusan||
||4. Sistem menghapus data peralatan dan<br>menampilkan konfirmasi penghapusan|
|**Skenario Alternative**||
|5. Peralatan sedang dipinjam<br>atau memiliki pengajuan aktif<br>(cabang dari langkah 2)||
||6. Sistem menolak penghapusan dan<br>menampilkan pesan peralatan masih terpakai|
|**Skenario Akhir**|Use case selesai jika data peralatan terhapus;<br>jika peralatan sedang dipinjam atau memiliki<br>pengajuan aktif, data tidak terhapus.|
|Keterangan: use case|khusus dari LAB-UC02 Kelola Data Peralatan.|



Perilaku pembeda: data peralatan terhapus, dengan syarat peralatan tidak 

Praktikum Analisis dan Desain Berorientasi Objek  |  82 

Institut Teknologi Garut 

S1 Teknik Informatika 

sedang dipinjam dan tidak memiliki pengajuan aktif. Langkah bersama mengikuti Tabel skenario LAB-UC02. 

Kelompok keputusan dan laporan terdiri atas UC06 dan UC07. Keduanya berdiri sendiri tanpa relasi antar use case. 

**Tabel 5.10 Skenario Use Case LAB-UC06 Proses Keputusan Peminjaman** 

|**Nama use case**|LAB-UC06 Proses Keputusan Peminjaman|
|---|---|
|**Aktor**|Petugas Laboratorium|
|**Tujuan**|Pengajuan peminjaman mendapat keputusan<br>setuju atau tolak|
|**Deskripsi**|Petugas memeriksa pengajuan yang berstatus<br>Menunggu Keputusan, menetapkan<br>persetujuan atau penolakan, dan sistem<br>menyampaikan keputusan|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Petugas membuka daftar<br>pengajuan yang berstatus<br>Menunggu Keputusan||
||2. Sistem menampilkan daftar pengajuan<br>tersebut|
|3. Petugas memilih pengajuan<br>dan menetapkan persetujuan||
||4. Sistem mengubah status pengajuan menjadi<br>Disetujui dan menampilkan konfirmasi|
|**Skenario Alternative**||
|5. Petugas menetapkan<br>penolakan (cabang dari<br>langkah 4)||
||6. Sistem mengubah status pengajuan menjadi<br>Ditolak dan menampilkan konfirmasi penolakan|
|7. Pengajuan tidak ditemukan<br>atau statusnya sudah berubah<br>(cabang dari langkah 2)||
||8. Sistem menampilkan pesan pengajuan tidak<br>dapat diproses|
|**Skenario Akhir**|Use case selesai jika pengajuan berstatus<br>Disetujui atau Ditolak; jika pengajuan tidak<br>dapat diproses, status tidak berubah.|



**Tabel 5.11 Skenario Use Case LAB-UC07 Lihat Laporan Peminjaman** 

|**Nama use case**|LAB-UC07 Lihat Laporan Peminjaman|
|---|---|
|**Aktor**|Kepala Laboratorium|
|**Tujuan**|Laporan peminjaman dapat dilihat oleh kepala<br>laboratorium|
|**Deskripsi**|Kepala Laboratorium membuka fungsi laporan<br>dan melihat laporan peminjaman pada periode<br>yang dipilih|



Praktikum Analisis dan Desain Berorientasi Objek  |  83 

Institut Teknologi Garut 

S1 Teknik Informatika 

|**Kegiatan**|**Respon sistem**|
|---|---|
|**Skenario Normal**||
|1. Kepala Laboratorium<br>membuka fungsi Lihat Laporan<br>Peminjaman||
||2. Sistem menampilkan daftar periode laporan|
|3. Kepala Laboratorium<br>memilih periode||
||4. Sistem menampilkan laporan peminjaman<br>periode tersebut|
|**Skenario Alternative**||
|5. Tidak ada data peminjaman<br>pada periode yang dipilih<br>(cabang dari langkah 4)||
||6. Sistem menampilkan pesan tidak ada data<br>peminjaman pada periode tersebut|
|**Skenario Akhir**|Use case selesai jika laporan periode yang<br>dipilih ditampilkan; jika tidak ada data, use case<br>selesai dengan pesan tersebut.|



Keterangan: satu-satunya use case Kepala Laboratorium. Tabel ini berdiri sendiri dan tidak memuat langkah include, extend, generalization, atau realization. 

Kelompok pengembalian terdiri atas UC11 dan UC12. UC11 menyertakan UC12 sebagai langkah rujukan, sehingga langkah pemeriksaan kondisi tidak disalin ke dalam tabel UC11. 

**Tabel 5.12 Skenario Use Case LAB-UC11 Catat Pengembalian Peralatan** 

|**Nama use case**|LAB-UC11 Catat Pengembalian Peralatan|
|---|---|
|**Aktor**|Petugas Laboratorium|
|**Tujuan**|Pengembalian tercatat dan status peminjaman<br>serta kondisi peralatan terbarui|
|**Deskripsi**|Petugas memilih peminjaman yang akan<br>dikembalikan, mengonfirmasi alat yang<br>kembali, dan menyimpan pencatatan.<br>Prasyarat: peminjaman berstatus Dipinjam|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Petugas memilih<br>peminjaman yang akan<br>dikembalikan||
||2. Sistem menampilkan data peminjaman<br>terpilih dan statusnya|
|3. Petugas mengonfirmasi alat<br>yang kembali dan jumlahnya||
||4. Sistem menampung konfirmasi petugas|
|5. Sistem memeriksa status||



Praktikum Analisis dan Desain Berorientasi Objek  |  84 

Institut Teknologi Garut 

S1 Teknik Informatika 

|peminjaman harus Dipinjam||
|---|---|
||6. Sistem menjalankan Periksa Kondisi<br>Peralatan (lihat Tabel skenario LAB-UC12)|
|7. Petugas menyimpan<br>pencatatan pengembalian||
||8. Sistem menyimpan tanggal kembali dan<br>kondisi serta mengubah status peminjaman<br>menjadi Selesai|
|9. Petugas melihat konfirmasi||
||10. Sistem menampilkan ringkasan<br>pengembalian|
|**Skenario Alternative**||
|11. Status bukan Dipinjam<br>(cabang dari langkah 5)||
||12. Sistem menolak pencatatan dan<br>menampilkan status peminjaman saat ini|
|13. Kondisi Rusak Ringan atau<br>Rusak Berat dicatat pada<br>langkah 6 (cabang dari<br>langkah 6)||
||14. Sistem tetap menyimpan pencatatan,<br>menandai kondisi tersebut pada data peralatan,<br>dan pengembalian tetap tercatat tanpa denda|
|15. Jumlah alat yang kembali<br>tidak sesuai (cabang dari<br>langkah 3)||
||16. Sistem meminta petugas memeriksa<br>kembali isian sebelum penyimpanan|
|**Skenario Akhir**|Use case selesai jika pengembalian tercatat<br>dengan tanggal kembali dan kondisi peralatan<br>serta status peminjaman menjadi Selesai; jika<br>status bukan Dipinjam, tidak ada pengembalian<br>baru yang tercatat dan status peminjaman tidak<br>berubah.|



Keterangan: use case ini direalisasikan oleh collaboration LAB-CO02 Catat Pengembalian Peralatan, tanpa langkah kegiatan sendiri. Keterlambatan dan denda belum dimodelkan pada pertemuan ini dan tidak menimbulkan aturan tambahan pada tabel ini. 

**Tabel 5.13 Skenario Use Case LAB-UC12 Periksa Kondisi Peralatan** 

|**Nama use case**|LAB-UC12 Periksa Kondisi Peralatan|
|---|---|
|**Aktor**|Petugas Laboratorium (berjalan di dalam LAB-<br>UC11 Catat Pengembalian Peralatan)|
|**Tujuan**|Kondisi peralatan yang dikembalikan terperiksa<br>dan tercatat|
|**Deskripsi**|Sistem memeriksa kondisi peralatan yang<br>dikembalikan dan mencatat nilainya sebagai<br>bagian dari pencatatan pengembalian. Use<br>case ini berjalan di dalam UC11 dan tidak|



Praktikum Analisis dan Desain Berorientasi Objek  |  85 

Institut Teknologi Garut 

S1 Teknik Informatika 

||mempunyai interaksi langsung dengan aktor|
|---|---|
|**Kegiatan**|**Respon sistem**|
|**Skenario Normal**||
|1. Alur pengembalian<br>memanggil Periksa Kondisi<br>Peralatan dengan peralatan<br>yang dikembalikan||
||2. Sistem menampilkan pilihan kondisi, yaitu<br>Baik, Rusak Ringan, atau Rusak Berat|
|3. Petugas memilih nilai<br>kondisi peralatan||
||4. Sistem mencatat nilai kondisi pada data<br>pengembalian|
|**Skenario Alternative**||
|5. Petugas belum memilih nilai<br>kondisi (cabang dari langkah 4)||
||6. Sistem meminta petugas memilih nilai<br>kondisi sebelum pencatatan disimpan|
|**Skenario Akhir**|Use case selesai jika nilai kondisi peralatan<br>tercatat pada data pengembalian; jika nilai<br>belum dipilih, pencatatan tidak disimpan<br>sampai nilai dipilih.|



### **3. Tugas: Sistem Informasi Akademik, Layanan Hasil Studi** 

### **a. Tujuan dan cakupan** 

Tugas ini MELANJUTKAN kasus SIA Pertemuan 4, bukan kasus baru. Diagram acuannya adalah diagram SIA Pertemuan 4, dan kebutuhan acuannya adalah SIA-R07 sampai SIA-R12 (lihat Jobsheet Pertemuan 4, Tabel 4.6). Keterampilan baru pada tugas ini adalah penulisan skenario, bukan perancangan kasus baru, sehingga mahasiswa tidak menambah use case, aktor, atau kebutuhan di luar diagram SIA Pertemuan 4. Tidak ada contoh jawaban SIA di dalam jobsheet ini. 

### **Tabel 5.14 Indeks tugas skenario SIA** 

|**ID**|**Nama use**<br>**case**|**Aktor**|**Catatan pemetaan**|
|---|---|---|---|
|SIA-UC07|Lihat<br>Kalender<br>Akademik|Civitas<br>Akademika|Ditulis satu kali atas nama Civitas<br>Akademika; berlaku untuk Mahasiswa<br>dan Dosen|
|SIA-UC08|Input Nilai<br>Mata Kuliah|Dosen|Prasyarat: dosen pengampu mata<br>kuliah; alternatif: nilai di luar rentang<br>yang sah ditolak; direalisasikan SIA-<br>CO01|
|SIA-UC09|Lihat KHS|Mahasiswa|Hanya nilai yang sudah dipublikasikan<br>yang ditampilkan; direalisasikan SIA-<br>CO02|
|SIA-UC10|Kelola Data|Admin|Skenario umum pengelolaan; langkah|



Praktikum Analisis dan Desain Berorientasi Objek  |  86 

Institut Teknologi Garut 

S1 Teknik Informatika 

|**ID**|**Nama use**<br>**case**|**Aktor**|**Catatan pemetaan**|
|---|---|---|---|
||Mahasiswa|Akademik|bersama yang dirujuk UC11, UC12,<br>dan UC13|
|SIA-UC11|Tambah<br>Data<br>Mahasiswa|Admin<br>Akademik|Khusus dari UC10; perilaku pembeda:<br>data mahasiswa baru tersimpan|
|SIA-UC12|Ubah Data<br>Mahasiswa|Admin<br>Akademik|Khusus dari UC10; perilaku pembeda:<br>data mahasiswa berubah|
|SIA-UC13|Hapus Data<br>Mahasiswa|Admin<br>Akademik|Khusus dari UC10; perilaku pembeda:<br>data mahasiswa terhapus; syarat: tidak<br>ada data akademik aktif|



### **b. Langkah-langkah** 

- 1) Langkah 1: Buka kembali diagram SIA Pertemuan 4 pada folder 04_model_analisis/P04/SIA hanya sebagai acuan. Jangan mengubah isi diagram. 

- 2) Langkah 2: Baca kembali kebutuhan SIA-R07 sampai SIA-R12 dan katalog SIA-UC07 sampai SIA-UC13 pada jobsheet Pertemuan 4. Tandai generalization aktor (Mahasiswa dan Dosen ke Civitas Akademika) dan generalization use case (UC11, UC12, dan UC13 ke UC10). 

- 3) Langkah 3: Tulis tabel skenario untuk ketujuh use case pada Tabel 5.14 dengan struktur yang sama persis dengan Tabel 5.1: baris Nama use case, Aktor, Tujuan, dan Deskripsi, kolom Kegiatan dan Respon sistem, Skenario Normal, Skenario Alternative dengan penomoran berlanjut, dan Skenario Akhir. 

- 4) Langkah 4: Terapkan aturan generalization aktor pada UC07: tulis satu tabel atas nama Civitas Akademika dengan catatan berlaku untuk Mahasiswa dan Dosen. 

- 5) Langkah 5: Terapkan aturan generalization use case: tulis skenario umum UC10 sebagai perilaku bersama, lalu tulis tabel UC11, UC12, dan UC13 yang masing-masing hanya memuat perilaku pembeda dan merujuk ke skenario umum untuk langkah bersama. 

- 6) Langkah 6: Sebutkan collaboration SIA-CO01 pada keterangan tabel UC08 dan SIA-CO02 pada keterangan tabel UC09, tanpa langkah kegiatan sendiri untuk collaboration. 

Praktikum Analisis dan Desain Berorientasi Objek  |  87 

Institut Teknologi Garut 

S1 Teknik Informatika 

- 7) Langkah 7: Periksa ketujuh tabel dengan checklist pada bagian C.4, lalu simpan dalam satu dokumen LAB/ P05_<NIM>_LAB_skenario_v01.drawio  pada folder 01_skenario. 

### **c. Aturan khusus** 

- Pewarisan Civitas Akademika: Mahasiswa dan Dosen mewarisi Lihat Kalender Akademik dari Civitas Akademika; asosiasi warisan tidak digambar ulang dan skenario ditulis satu kali atas nama Civitas Akademika. 

- Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. 

- KHS hanya menampilkan nilai yang sudah dipublikasikan. 

- Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif. 

- Diagram SIA Pertemuan 4 tidak diubah; produk tugas adalah dokumen skenario, bukan diagram baru. 

### **d. Penilaian** 

Penilaian tugas SIA memakai checklist pada bagian C.4 dan rubrik praktik RPS. Checklist tersebut tidak disalin ulang pada bagian ini; periksa ketujuh tabel SIA dengan butir yang sama, termasuk kelengkapan field, penomoran berlanjut, pemisahan kolom, pemetaan include, extend, dan generalization, serta kesamaan nama, ID, dan aktor dengan diagram SIA Pertemuan 4. 

### **4. Checklist penilaian** 

Periksa setiap tabel skenario dengan checklist berikut sebelum mengunggah ke LMS. Satu tabel yang tidak memenuhi satu butir checklist harus diperbaiki, bukan dikumpulkan apa adanya. 

- ✓ Seluruh field tabel terisi: Nama use case, Aktor, Tujuan, Deskripsi, kolom Kegiatan dan Respon sistem, Skenario Normal, Skenario Alternative, dan Skenario Akhir. 

- ✓ Langkah ditulis berurutan, satu aksi per langkah, dan penomoran berlanjut dari Skenario Normal ke Skenario Alternative tanpa pengulangan nomor. 

- ✓ Kolom Kegiatan hanya berisi aksi aktor dan kolom Respon sistem hanya berisi tanggapan sistem. 

Praktikum Analisis dan Desain Berorientasi Objek  |  88 

Institut Teknologi Garut 

S1 Teknik Informatika 

- ✓ Data yang dimasukkan dan data yang ditampilkan disebut secara eksplisit, termasuk nama field, nilai, atau status. 

- ✓ Relasi include ditulis sebagai langkah rujukan pada Skenario Normal dengan nama, ID, dan tabel skenario use case yang disertakan, tanpa menyalin langkahnya. 

- ✓ Relasi extend ditulis sebagai cabang bersyarat pada Skenario Alternative lengkap dengan condition dan extension point, serta sebagai rujukan ke tabel skenario use case tambahan. 

- ✓ Generalization aktor diterapkan: skenario aktor umum ditulis satu kali ditambah catatan aktor khusus yang berlaku; tidak ada tabel ganda untuk aktor khusus yang perilakunya sama. 

- ✓ Generalization use case diterapkan: skenario umum memuat perilaku bersama, skenario khusus memuat perilaku pembeda dan merujuk ke skenario umum. 

- ✓ Collaboration disebut pada keterangan tabel use case yang direalisasikannya dan tidak diberi langkah kegiatan sendiri. 

- ✓ Setiap tabel mempunyai Skenario Alternative dan Skenario Akhir, termasuk untuk use case yang jalurnya tampak sederhana. 

- ✓ Nama, ID, aktor, condition, dan extension point sama persis dengan diagram kumulatif Pertemuan 4. 

- ✓ Catatan pemeriksaan untuk aktor Kepala Laboratorium: aktor ini hanya mempunyai satu use case, yaitu LAB-UC07 Lihat Laporan Peminjaman, dan LAB-UC07 tidak mempunyai relasi lain. Tabel skenario UC07 karena itu berdiri sendiri dan tidak memuat langkah include, extend, generalization, atau realization. 

- ✓ Berkas diagram P04 tidak diubah; dokumen skenario disimpan pada folder 01_skenario dengan nama dan versi yang benar. Lembar skenario studi kasus memuat checklist di atas ditambah satu kolom penelusuran singkat per tabel, yaitu tabel yang di cek, relasi yang ditelusur, dan hasil pencocokan terhadap diagram. Lembar yang kolom penelusurannya kosong atau hanya berisi tanda centang tanpa keterangan relasi dianggap belum lengkap. 

Praktikum Analisis dan Desain Berorientasi Objek  |  89 

Institut Teknologi Garut 

S1 Teknik Informatika 

### **5. Deliverable** 

Deliverable Pertemuan 5 adalah dua dokumen pada folder 01_skenario: P05_<NIM>_LAB_skenario_v01.md yang memuat hasil atas 12 tabel skenario studi kasus, dan P05_<NIM>_SIA_skenario_v01.drawio yang memuat 7 tabel skenario tugas. Diagram P04 tetap menjadi acuan dan tidak dikumpulkan ulang sebagai produk baru. Sertakan logbook singkat yang mencatat tabel studi kasus mana yang sudah di cek dan kemajuan penulisan tabel tugas SIA. 

### **D. REFERENSI** 

1. Object Management Group. (2017). OMG Unified Modeling Language, Version 2.5.1. Rujukan normatif untuk makna use case, include, extend, generalization, collaboration, dan realization. 

2. Institut Teknologi Garut. (2026). RPS IFRWP5149, Praktikum Analisis dan Desain Berorientasi Objek. Sumber utama untuk capaian, materi, indikator, teknik asesmen, dan bobot penilaian. 

3. Jobsheet Praktikum Pertemuan 3 IFRWP5149. Sumber diagram dasar, use case description, kebutuhan LAB-R01 sampai LAB-R06, dan kebutuhan SIA-R01 sampai SIA-R06. 

4. Jobsheet Praktikum Pertemuan 4 IFRWP5149. Sumber diagram kumulatif acuan, kebutuhan LAB-R07 sampai LAB-R11, kebutuhan SIAR07 sampai SIA-R12, katalog LAB-UC01 sampai LAB-UC12, katalog SIA-UC01 sampai SIA-UC13, dan aturan generalization serta collaboration. 

Praktikum Analisis dan Desain Berorientasi Objek  |  90 

