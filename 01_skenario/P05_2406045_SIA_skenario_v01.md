# Lembar Skenario SIA – Layanan Hasil Studi

Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149) – Pertemuan 5  
NIM: 2406045  
Diagram acuan: diagram SIA Pertemuan 4 (tidak diubah). Kebutuhan acuan: SIA-R07 sampai SIA-R12.

## Indeks tabel

| ID | Nama use case | Aktor | Catatan pemetaan |
|---|---|---|---|
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | Ditulis satu kali atas nama Civitas Akademika; berlaku untuk Mahasiswa dan Dosen |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | Prasyarat dosen pengampu; alternatif nilai di luar rentang ditolak; direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS | Mahasiswa | Hanya nilai yang sudah dipublikasikan yang ditampilkan; direalisasikan SIA-CO02 |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | Skenario umum pengelolaan; langkah bersama dirujuk UC11, UC12, dan UC13 |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | Khusus dari UC10; perilaku pembeda: data mahasiswa baru tersimpan |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | Khusus dari UC10; perilaku pembeda: data mahasiswa berubah |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | Khusus dari UC10; perilaku pembeda: data mahasiswa terhapus; syarat: tidak ada data akademik aktif |

## Tabel 5.14 Skenario Use Case SIA-UC07 Lihat Kalender Akademik

| | |
|---|---|
| **Nama use case** | SIA-UC07 Lihat Kalender Akademik |
| **Aktor** | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen) |
| **Tujuan** | Civitas akademika dapat mengetahui jadwal kegiatan akademik pada periode akademik yang dipilih |
| **Deskripsi** | Civitas Akademika membuka fungsi kalender akademik, memilih periode akademik, dan melihat daftar kegiatan akademik beserta tanggalnya |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik |  |
|  | 2. Sistem menampilkan daftar periode akademik |
| 3. Civitas Akademika memilih periode akademik |  |
|  | 4. Sistem menampilkan kalender akademik periode tersebut berisi nama kegiatan, tanggal mulai, dan tanggal selesai |
| **Skenario Alternative** | |
| 5. Kalender akademik belum tersedia pada periode yang dipilih (cabang dari langkah 4) |  |
|  | 6. Sistem menampilkan pesan kalender akademik belum tersedia untuk periode tersebut |
| **Skenario Akhir** | Use case selesai jika kalender akademik periode yang dipilih ditampilkan; jika kalender belum tersedia, use case selesai dengan pesan tersebut. |

**Keterangan tabel:** skenario ditulis satu kali atas nama Civitas Akademika (generalization aktor); berlaku untuk Mahasiswa dan Dosen sehingga tidak ada tabel terpisah untuk masing-masing aktor khusus. Tabel ini tidak memuat langkah include, extend, generalization use case, atau realization.

## Tabel 5.15 Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah

| | |
|---|---|
| **Nama use case** | SIA-UC08 Input Nilai Mata Kuliah |
| **Aktor** | Dosen |
| **Tujuan** | Nilai mahasiswa pada mata kuliah yang diampu tersimpan |
| **Deskripsi** | Dosen pengampu memilih mata kuliah yang diampu, mengisi nilai setiap mahasiswa, dan menyimpan nilai. Prasyarat: dosen adalah dosen pengampu mata kuliah tersebut |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Dosen membuka fungsi Input Nilai Mata Kuliah |  |
|  | 2. Sistem menampilkan daftar mata kuliah yang diampu dosen tersebut |
| 3. Dosen memilih mata kuliah |  |
|  | 4. Sistem menampilkan daftar mahasiswa peserta mata kuliah beserta kolom nilai |
| 5. Dosen mengisi nilai mahasiswa |  |
|  | 6. Sistem memeriksa nilai berada dalam rentang yang sah |
| 7. Dosen menyimpan nilai |  |
|  | 8. Sistem menyimpan nilai dan menampilkan konfirmasi penyimpanan nilai |
| **Skenario Alternative** | |
| 9. Nilai di luar rentang yang sah (cabang dari langkah 6) |  |
|  | 10. Sistem menolak penyimpanan, menampilkan pesan nilai di luar rentang, dan meminta dosen memperbaiki nilai |
| 11. Dosen tidak mengampu mata kuliah apa pun (cabang dari langkah 2) |  |
|  | 12. Sistem menampilkan pesan tidak ada mata kuliah yang dapat diinput nilainya |
| **Skenario Akhir** | Use case selesai jika nilai mata kuliah tersimpan; jika nilai di luar rentang yang sah, nilai tidak tersimpan sampai diperbaiki; jika dosen tidak mengampu mata kuliah, use case selesai dengan pesan tersebut. |

**Keterangan tabel:** use case ini direalisasikan oleh collaboration SIA-CO01. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut.

## Tabel 5.16 Skenario Use Case SIA-UC09 Lihat KHS

| | |
|---|---|
| **Nama use case** | SIA-UC09 Lihat KHS |
| **Aktor** | Mahasiswa |
| **Tujuan** | Mahasiswa dapat mengetahui hasil studi yang sudah dipublikasikan |
| **Deskripsi** | Mahasiswa membuka fungsi KHS, memilih semester, dan melihat nilai mata kuliah yang sudah dipublikasikan |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Mahasiswa membuka fungsi Lihat KHS |  |
|  | 2. Sistem menampilkan daftar semester milik mahasiswa tersebut |
| 3. Mahasiswa memilih semester |  |
|  | 4. Sistem menampilkan KHS semester tersebut berisi mata kuliah beserta nilai yang berstatus dipublikasikan |
| **Skenario Alternative** | |
| 5. Tidak ada nilai yang dipublikasikan pada semester yang dipilih (cabang dari langkah 4) |  |
|  | 6. Sistem menampilkan pesan belum ada nilai yang dipublikasikan pada semester tersebut |
| **Skenario Akhir** | Use case selesai jika KHS berisi nilai yang sudah dipublikasikan ditampilkan; jika belum ada nilai yang dipublikasikan, use case selesai dengan pesan tersebut. |

**Keterangan tabel:** use case ini direalisasikan oleh collaboration SIA-CO02. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. KHS hanya menampilkan nilai yang sudah dipublikasikan; nilai yang belum dipublikasikan tidak ditampilkan.

## Tabel 5.17 Skenario Use Case SIA-UC10 Kelola Data Mahasiswa

| | |
|---|---|
| **Nama use case** | SIA-UC10 Kelola Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terkelola melalui satu fungsi pengelolaan bersama |
| **Deskripsi** | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa |  |
|  | 2. Sistem menampilkan daftar data mahasiswa |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus |  |
|  | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih |
| 5. Admin Akademik mengisi atau mengonfirmasi data |  |
|  | 6. Sistem memeriksa kelengkapan dan keabsahan data |
| 7. Admin Akademik menyimpan perubahan |  |
|  | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6) |  |
|  | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

**Keterangan tabel:** skenario umum (use case umum pada generalization use case) yang memuat perilaku bersama. Use case khusus SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa masing-masing mempunyai tabel sendiri yang hanya memuat perilaku pembeda dan merujuk ke tabel ini untuk langkah bersama.

## Tabel 5.18 Skenario Use Case SIA-UC11 Tambah Data Mahasiswa

| | |
|---|---|
| **Nama use case** | SIA-UC11 Tambah Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa baru tersimpan sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik mengisi data mahasiswa baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Tambah Data Mahasiswa |  |
|  | 2. Sistem menampilkan formulir data mahasiswa baru |
| 3. Admin Akademik mengisi data mahasiswa baru |  |
|  | 4. Sistem memeriksa kelengkapan data |
| 5. Admin Akademik menyimpan data |  |
|  | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data tidak lengkap (cabang dari langkah 4) |  |
|  | 8. Sistem menolak penyimpanan dan meminta Admin Akademik melengkapi data |
| **Skenario Akhir** | Use case selesai jika data mahasiswa baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

**Keterangan tabel:** use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa baru tersimpan. Langkah bersama mengikuti Tabel skenario SIA-UC10.

## Tabel 5.19 Skenario Use Case SIA-UC12 Ubah Data Mahasiswa

| | |
|---|---|
| **Nama use case** | SIA-UC12 Ubah Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa berubah sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan diubah |  |
|  | 2. Sistem menampilkan data mahasiswa saat ini |
| 3. Admin Akademik mengubah data mahasiswa |  |
|  | 4. Sistem memeriksa perubahan data |
| 5. Admin Akademik menyimpan perubahan |  |
|  | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data mahasiswa tidak ditemukan (cabang dari langkah 2) |  |
|  | 8. Sistem menampilkan pesan data mahasiswa tidak ditemukan |
| 9. Data hasil perubahan tidak lengkap atau tidak sah (cabang dari langkah 4) |  |
|  | 10. Sistem menolak penyimpanan dan meminta Admin Akademik memperbaiki data |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan atau data hasil perubahan tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

**Keterangan tabel:** use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa berubah. Langkah bersama mengikuti Tabel skenario SIA-UC10.

## Tabel 5.20 Skenario Use Case SIA-UC13 Hapus Data Mahasiswa

| | |
|---|---|
| **Nama use case** | SIA-UC13 Hapus Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terhapus sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik memilih data mahasiswa, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan dihapus |  |
|  | 2. Sistem memeriksa mahasiswa tidak memiliki data akademik aktif |
| 3. Admin Akademik mengonfirmasi penghapusan |  |
|  | 4. Sistem menghapus data mahasiswa dan menampilkan konfirmasi penghapusan |
| **Skenario Alternative** | |
| 5. Mahasiswa memiliki data akademik aktif (cabang dari langkah 2) |  |
|  | 6. Sistem menolak penghapusan dan menampilkan pesan data mahasiswa masih memiliki data akademik aktif |
| **Skenario Akhir** | Use case selesai jika data mahasiswa terhapus; jika mahasiswa memiliki data akademik aktif, data tidak terhapus. |

**Keterangan tabel:** use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa terhapus, dengan syarat mahasiswa tidak memiliki data akademik aktif. Langkah bersama mengikuti Tabel skenario SIA-UC10.

## Pemeriksaan dengan checklist (bagian C.4)

| Butir checklist | Hasil |
|---|---|
| Seluruh field terisi (Nama use case, Aktor, Tujuan, Deskripsi, Kegiatan, Respon sistem, Skenario Normal, Skenario Alternative, Skenario Akhir) | Terpenuhi pada 7 tabel |
| Satu aksi per langkah; penomoran berlanjut dari Normal ke Alternative | Terpenuhi pada 7 tabel |
| Kolom Kegiatan hanya aksi aktor; kolom Respon sistem hanya tanggapan sistem | Terpenuhi pada 7 tabel |
| Data dan status disebut eksplisit (nama field, nilai, status) | Terpenuhi |
| Generalization aktor: satu tabel atas nama Civitas Akademika | SIA-UC07 |
| Generalization use case: UC10 umum, UC11/UC12/UC13 hanya perilaku pembeda dan merujuk ke UC10 | SIA-UC10 s.d. SIA-UC13 |
| Collaboration disebut pada keterangan tabel, tanpa langkah sendiri | SIA-CO01 pada UC08, SIA-CO02 pada UC09 |
| Setiap tabel punya Skenario Alternative dan Skenario Akhir | Terpenuhi pada 7 tabel |
| Nama, ID, aktor sama dengan diagram SIA Pertemuan 4 | Dicocokkan dengan Tabel 5.14 jobsheet; cocokkan ulang dengan diagram P04 |
| Diagram P04 tidak diubah | Terpenuhi |

## Logbook singkat

| No | Kegiatan | Status |
|---|---|---|
| 1 | Membuka diagram SIA Pertemuan 4 sebagai acuan | Selesai |
| 2 | Membaca kebutuhan SIA-R07 sampai SIA-R12 dan katalog SIA-UC07 sampai SIA-UC13 | Selesai |
| 3 | Menulis tabel SIA-UC07 sampai SIA-UC13 | Selesai |
| 4 | Memeriksa ketujuh tabel dengan checklist C.4 | Selesai |