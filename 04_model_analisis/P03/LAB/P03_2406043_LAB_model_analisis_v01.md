# P03 LAB - Model Analisis

Diagram: `P03_2406043_LAB_usecase_v02.drawio` (v01 dipertahankan; v02 menambah aktor Kepala Laboratorium dan menyatukan label aktor).

| Sumber | Hubungan | Tujuan |
|---|---|---|
| Mahasiswa | Asosiasi | LAB-UC01 |
| Mahasiswa | Asosiasi | LAB-UC03 |
| Mahasiswa | Asosiasi | LAB-UC05 |
| Petugas laboratorium | Asosiasi | LAB-UC02 |
| Petugas laboratorium | Asosiasi | LAB-UC06 |
| Kepala laboratorium | Asosiasi | LAB-UC07 |
| LAB-UC03 | «include» | LAB-UC04 |
| LAB-UC05 | «extend» | LAB-UC03 |
