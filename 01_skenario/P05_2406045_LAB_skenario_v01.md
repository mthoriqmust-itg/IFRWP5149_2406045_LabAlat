# Lembar Skenario Studi Kasus LAB – Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus

Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149) – Pertemuan 5  
NIM: 2406045  
Diagram acuan: diagram kumulatif Pertemuan 4 (`04_model_analisis/P04/LAB/P04_2406045_LAB_usecase_v01.drawio`), hanya sebagai acuan dan tidak diubah.  
Kebutuhan acuan: LAB-R01 sampai LAB-R11 (Jobsheet Pertemuan 4, Tabel 4.5).

## 1. Pemeriksaan awal diagram acuan

| Unsur | Jumlah | Keterangan |
|---|---|---|
| Aktor | 5 | Peminjam (umum), Mahasiswa, Dosen, Petugas Laboratorium, Kepala Laboratorium |
| Use case | 12 | LAB-UC01 sampai LAB-UC12 |
| Collaboration | 2 | LAB-CO01 Ajukan Peminjaman, LAB-CO02 Catat Pengembalian Peralatan |
| Hubungan | 17 | Asosiasi, include, extend, generalization, dan realization (Tabel 4.5) |

## 2. Lembar penelusuran 12 tabel skenario

Kolom "Konfirmasi diagram P04" diberi tanda ✓ setelah relasi dicocokkan langsung pada berkas diagram.

| No | Tabel skenario | Relasi yang ditelusur | Hasil pencocokan | Konfirmasi diagram P04 |
|---|---|---|---|---|
| 1 | Tabel 5.3 – LAB-UC01 Lihat Ketersediaan Peralatan | Asosiasi Peminjam ke LAB-UC01; generalization aktor Mahasiswa dan Dosen ke Peminjam | Aktor tertulis Peminjam (berlaku untuk Mahasiswa dan Dosen), ditulis satu kali tanpa tabel ganda. Tidak ada include, extend, atau realization pada tabel. Nama dan ID sama dengan Tabel 5.2. | ☐ |
| 2 | Tabel 5.1 – LAB-UC03 Ajukan Peminjaman | Asosiasi Peminjam ke LAB-UC03; include LAB-UC04; extend dari LAB-UC05; realization LAB-CO01; kebutuhan LAB-R03 dan LAB-R07 | Include LAB-UC04 menjadi langkah rujukan 2 pada Skenario Normal tanpa menyalin langkah. Extend LAB-UC05 menjadi langkah 11 dan 12 pada Skenario Alternative dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia. LAB-CO01 hanya disebut pada keterangan tabel. | ☐ |
| 3 | Tabel 5.4 – LAB-UC04 Periksa Ketersediaan | Include dari LAB-UC03 ke LAB-UC04 | Aktor Peminjam berjalan di dalam LAB-UC03 dan tidak ada interaksi langsung dengan aktor. Langkah dirujuk dari langkah 2 Tabel 5.1. Include tidak ditulis sebagai alternatif. | ☐ |
| 4 | Tabel 5.5 – LAB-UC05 Cetak Bukti Pengajuan | Extend dari LAB-UC05 ke LAB-UC03; asosiasi khusus Mahasiswa ke LAB-UC05 | Aktor Mahasiswa (asosiasi khusus). Condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia sama dengan Tabel 5.1. Use case dasar tetap selesai tanpa cabang ini. | ☐ |
| 5 | Tabel 5.6 – LAB-UC02 Kelola Data Peralatan | Asosiasi Petugas Laboratorium ke LAB-UC02; generalization LAB-UC08, LAB-UC09, LAB-UC10 ke LAB-UC02 | Skenario memuat perilaku bersama (membuka, memilih bentuk pengelolaan, mengisi, memeriksa, menyimpan). Bentuk tambah, ubah, dan hapus diserahkan ke tabel khusus. | ☐ |
| 6 | Tabel 5.7 – LAB-UC08 Tambah Data Peralatan | Generalization LAB-UC08 ke LAB-UC02 | Hanya memuat perilaku pembeda (data baru tersimpan) dan merujuk Tabel LAB-UC02 untuk langkah bersama. Aktor Petugas Laboratorium. | ☐ |
| 7 | Tabel 5.8 – LAB-UC09 Ubah Data Peralatan | Generalization LAB-UC09 ke LAB-UC02 | Hanya memuat perilaku pembeda (data peralatan berubah) dan merujuk Tabel LAB-UC02. Aktor Petugas Laboratorium. | ☐ |
| 8 | Tabel 5.9 – LAB-UC10 Hapus Data Peralatan | Generalization LAB-UC10 ke LAB-UC02 | Hanya memuat perilaku pembeda (data terhapus, syarat tidak sedang dipinjam dan tidak ada pengajuan aktif) dan merujuk Tabel LAB-UC02. | ☐ |
| 9 | Tabel 5.10 – LAB-UC06 Proses Keputusan Peminjaman | Asosiasi Petugas Laboratorium ke LAB-UC06 | Berdiri sendiri tanpa relasi antar use case. Status Disetujui dan Ditolak disebut eksplisit. | ☐ |
| 10 | Tabel 5.11 – LAB-UC07 Lihat Laporan Peminjaman | Asosiasi Kepala Laboratorium ke LAB-UC07 (satu-satunya use case aktor ini) | Tidak memuat langkah include, extend, generalization, atau realization. Aktor Kepala Laboratorium sama dengan diagram. | ☐ |
| 11 | Tabel 5.12 – LAB-UC11 Catat Pengembalian Peralatan | Asosiasi Petugas Laboratorium ke LAB-UC11; include LAB-UC12; realization LAB-CO02 | Include LAB-UC12 menjadi langkah rujukan 6 pada Skenario Normal tanpa menyalin langkah. LAB-CO02 hanya disebut pada keterangan tabel. Keterlambatan dan denda tidak dimodelkan. | ☐ |
| 12 | Tabel 5.13 – LAB-UC12 Periksa Kondisi Peralatan | Include dari LAB-UC11 ke LAB-UC12 | Aktor Petugas Laboratorium berjalan di dalam LAB-UC11, tanpa interaksi langsung dengan aktor. Langkah dirujuk dari langkah 6 Tabel 5.12. | ☐ |

## 3. Catatan pemeriksaan aktor Kepala Laboratorium

Kepala Laboratorium hanya mempunyai satu use case, yaitu LAB-UC07 Lihat Laporan Peminjaman, dan LAB-UC07 tidak mempunyai relasi lain. Tabel skenario LAB-UC07 karena itu berdiri sendiri dan tidak memuat langkah include, extend, generalization, atau realization.

## 4. Checklist penilaian (bagian C.4)

| Butir checklist | Hasil |
|---|---|
| Seluruh field tabel terisi (Nama use case, Aktor, Tujuan, Deskripsi, Kegiatan, Respon sistem, Skenario Normal, Skenario Alternative, Skenario Akhir) | ✓ 12 tabel |
| Langkah berurutan, satu aksi per langkah, penomoran berlanjut dari Normal ke Alternative | ✓ 12 tabel |
| Kolom Kegiatan hanya aksi aktor, kolom Respon sistem hanya tanggapan sistem | ✓ 12 tabel |
| Data yang dimasukkan dan ditampilkan disebut eksplisit (nama field, nilai, status) | ✓ misalnya tanggal pinjam, tanggal rencana kembali, status Menunggu Keputusan |
| Include ditulis sebagai langkah rujukan pada Skenario Normal | ✓ UC03 langkah 2 (ke UC04), UC11 langkah 6 (ke UC12) |
| Extend ditulis sebagai cabang bersyarat dengan condition dan extension point | ✓ UC03 langkah 11 dan 12 (dari UC05) |
| Generalization aktor: satu tabel atas nama aktor umum | ✓ Peminjam pada UC01 dan UC03 |
| Generalization use case: umum memuat perilaku bersama, khusus memuat perilaku pembeda | ✓ UC02 dengan UC08, UC09, UC10 |
| Collaboration disebut pada keterangan tabel, tanpa langkah sendiri | ✓ LAB-CO01 pada UC03, LAB-CO02 pada UC11 |
| Setiap tabel mempunyai Skenario Alternative dan Skenario Akhir | ✓ 12 tabel |
| Nama, ID, aktor, condition, dan extension point sama dengan diagram Pertemuan 4 | ✓ terhadap Tabel 5.2 jobsheet; konfirmasi terhadap berkas diagram pada kolom terakhir bagian 2 |
| Catatan Kepala Laboratorium dipenuhi | ✓ lihat bagian 3 |
| Diagram P04 tidak diubah; dokumen disimpan di `01_skenario` dengan nama dan versi benar | ✓ |

## 5. Logbook singkat

| No | Kegiatan | Status |
|---|---|---|
| 1 | Membuka diagram kumulatif P04 LAB sebagai acuan (5 aktor, 12 use case, 2 collaboration, 17 hubungan) | Selesai |
| 2 | Membaca 12 tabel skenario menurut kelompok: peminjaman, pengelolaan data, keputusan dan laporan, pengembalian | Selesai |
| 3 | Mencocokkan tiap tabel dengan diagram (aktor, relasi, ID, nama, condition, extension point) | Selesai |
| 4 | Memeriksa catatan Kepala Laboratorium (UC07 berdiri sendiri) | Selesai |
| 5 | Mengisi lembar skenario dan menyimpan sebagai P05_2406045_LAB_skenario_v01.md | Selesai |
| 6 | Menulis 7 tabel tugas SIA (SIA-UC07 sampai SIA-UC13) | Selesai |