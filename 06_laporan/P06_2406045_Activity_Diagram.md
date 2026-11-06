# Laporan Praktikum Analisis dan Desain Berorientasi Objek

**Pertemuan 6: Activity Diagram: Dari Skenario ke Alur Aktivitas**

| | |
|---|---|
| Nama | Muhammad Thoriq Mustaqim |
| NIM | 2406045 |
| Program Studi | S1 Teknik Informatika, Institut Teknologi Garut |
| Mata Kuliah | Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149) |

---

## 1. Tujuan

Praktikum ini melatih penyusunan *activity diagram* UML 2.5.1 dari tabel skenario *use case* yang telah disusun pada Pertemuan 5. Mahasiswa memodelkan alur kegiatan proses bisnis yang mencakup urutan *action*, percabangan keputusan (*decision* dan *merge*), alur eksekusi paralel (*fork* dan *join*), serta pengelompokan alur berdasarkan partisipan (*swimlane*). 

Pekerjaan terbagi menjadi dua bagian utama:
1. Menyusun 7 *activity diagram* untuk studi kasus Laboratorium (LAB) dari skenario use case utama (LAB-UC01 hingga LAB-UC11).
2. Menyusun 1 *activity diagram* utuh untuk Sistem Informasi Akademik (SIA) yang memodelkan alur dari "Input Nilai Mata Kuliah" hingga "Lihat KHS" melintasi 4 *swimlane* aktor (Dosen, Sistem, Admin Akademik, Mahasiswa).

---

## 2. Kakas

Seluruh diagram dieksekusi dan digambar menggunakan aplikasi **draw.io** (`.drawio`) dengan standar notasi UML 2.5.1 (OMG). Berkas diagram disimpan sebagai kode XML `.drawio` dan diekspor ke format gambar `.png`. Berkas metadata dan laporan praktikum ini ditulis menggunakan format **Markdown** (`.md`).

---

## 3. Pelaksanaan

Pekerjaan dimulai dengan menelaah aturan pemetaan tabel skenario Pertemuan 5 ke notasi *activity diagram*:
- **Skenario Normal** dipetakan menjadi alur utama (*main flow*) dari *initial node* ke *activity final node*.
- **Kolom Kegiatan & Respon Sistem** dipetakan menjadi *action* pada *swimlane* aktor yang bersesuaian.
- **Skenario Alternative** dipetakan menjadi cabang *decision* lengkap dengan kurung siku *guard condition*.
- **Langkah Include** dipetakan sebagai *action* wajib pada alur utama, sedangkan **Langkah Extend** dipetakan sebagai cabang *decision* bersyarat.

### 3.1 Praktik Terpandu & Mandiri Studi Kasus LAB
1. **Peminjaman (LAB-UC03)**: Dibuat dengan 3 *swimlane* (Mahasiswa, Sistem, Petugas Laboratorium). Memuat *action include* `Periksa Ketersediaan (dari LAB-UC04)` dan percabangan *extend* `Cetak Bukti Pengajuan (dari LAB-UC05)`.
2. **Pengembalian (LAB-UC11)**: Ditambahkan kebutuhan proses baru `Periksa kelengkapan aksesori peralatan` yang diparalelkan dengan `Periksa Kondisi Peralatan (dari LAB-UC12)` menggunakan pasangan *fork* dan *join*.
3. **Lihat Ketersediaan Peralatan (LAB-UC01)** & **Lihat Laporan Peminjaman (LAB-UC07)**: Dibuat sebagai alur baca (*read-only*) dengan cabang penanganan kondisi data kosong.
4. **Kelola Data Peralatan (LAB-UC02, UC08, UC09, UC10)**: Mengintegrasikan 3 cabang varian pengelolaan ([tambah], [ubah], [hapus]) dalam satu *decision* bentuk pengelolaan yang bermuara ke *merge*.
5. **Cetak Bukti Pengajuan (LAB-UC05)**: Digambar utuh sebagai perilaku *extend* yang dimulai pada titik *extension point*.
6. **Proses Keputusan Peminjaman (LAB-UC06)**: Dikerjakan secara mandiri tanpa melihat berkas pembanding terlebih dahulu untuk melatih penanganan dua *decision* berurutan (`Pengajuan dapat diproses?` dan `Pengajuan disetujui?`).

### 3.2 Tugas Akademik SIA
Tugas mandiri menyusun satu diagram aktivitas utuh melintasi 4 *swimlane* berdasarkan skenario SIA-UC08 dan SIA-UC09:
- **Dosen**: Memasukkan nilai dan melengkapi nilai bila belum lengkap.
- **Sistem**: Menyimpan nilai, memvalidasi kelengkapan nilai, menyiapkan publikasi hasil studi, serta mengeksekusi dua alur paralel (*Menerbitkan KHS* dan *Mengirim pemberitahuan*).
- **Admin Akademik**: Memeriksa dan mengesahkan nilai.
- **Mahasiswa**: Melihat KHS pada portal akademik.

Seluruh hasil diagram diselaraskan dengan checklist penilaian Bagian C.4 Jobsheet Pertemuan 6.

---

## 4. Hasil

### 4.1 Studi Kasus Laboratorium (LAB)

Telah dihasilkan 7 berkas diagram dan 7 berkas ekspor PNG untuk studi kasus laboratorium:

| ID Diagram | Nama Activity Diagram | Swimlane yang Terlibat | Unsur Khusus |
|---|---|---|---|
| `lihat_ketersediaan` | Activity Lihat Ketersediaan Peralatan | Peminjam, Sistem | Decision ketersediaan data |
| `kelola_data` | Activity Kelola Data Peralatan | Petugas Laboratorium, Sistem | 3 Cabang varian (tambah, ubah, hapus), Merge, 3 Guard validasi |
| `peminjaman` | Activity Peminjaman | Mahasiswa, Sistem, Petugas Laboratorium | Action Include (LAB-UC04), Cabang Extend (LAB-UC05) |
| `cetak_bukti` | Activity Cetak Bukti Pengajuan | Mahasiswa, Sistem | Extension point context, Decision cetak |
| `keputusan` | Activity Proses Keputusan Peminjaman | Petugas Laboratorium, Sistem | Decision kelayakan proses, Decision penetapan persetujuan |
| `pengembalian` | Activity Pengembalian | Mahasiswa, Sistem, Petugas Laboratorium | Action Include (LAB-UC12), Pasangan Fork & Join (Proses Paralel) |
| `laporan` | Activity Lihat Laporan Peminjaman | Kepala Laboratorium, Sistem | Decision ada/tidaknya data periode |

### 4.2 Tugas Akademik SIA

Telah dihasilkan diagram aktivitas SIA utuh (`P06_2406045_SIA_activity_v01.drawio`) yang memenuhi seluruh kriteria wajib:

| Unsur Wajib | Penerapan pada Diagram SIA |
|---|---|
| **Cakupan Alur** | Berjalan dari *Input Nilai Mata Kuliah* (Dosen) hingga *Melihat KHS* (Mahasiswa). |
| **Swimlane (4 Aktor)** | **Dosen**, **Sistem**, **Admin Akademik**, **Mahasiswa**. |
| **Decision & Guard** | Decision `Nilai sudah lengkap?` dengan guard `[lengkap]` (lanjut ke Admin) dan `[belum lengkap]` (kembali ke Dosen untuk melengkapi nilai via *Merge*). |
| **Fork & Join** | Sepasang *Fork* dan *Join* pada swimlane **Sistem** untuk menjalankan *Menerbitkan KHS pada portal akademik* dan *Mengirim pemberitahuan hasil studi kepada mahasiswa* secara paralel. |
| **Awal & Akhir** | Tepat 1 *Initial Node* di swimlane Dosen dan 1 *Activity Final Node* di swimlane Mahasiswa. |

---

## 5. Pembahasan

Transisi dari skenario *use case* ke *activity diagram* memvisualisasikan bagaimana alur kontrol dan tanggung jawab berpindah antar partisipan secara kronologis. Beberapa poin penting dalam penerapan notasi UML 2.5.1 pada praktikum ini:

1. **Pengelompokan Swimlane**: Menempatkan *action* pada *swimlane* yang tepat memastikan kejelasan tanggung jawab. *Action* respon sistem (seperti menyimpan data, mengubah status, menerbitkan KHS) dipisahkan secara tegas ke dalam *swimlane* **Sistem**, tidak disatukan di *swimlane* aktor manusia.
2. **Penggunaan Fork dan Join vs. Decision dan Merge**:
   - *Decision* dan *Merge* digunakan untuk percabangan logis (kondisi saling lepas/alternatif), di mana hanya satu jalur yang dieksekusi berdasarkan *guard condition*.
   - *Fork* dan *Join* digunakan untuk mengeksekusi dua atau lebih aktivitas bersamaan (*concurrency*). Alur baru dapat dilanjutkan melewati *Join* hanya jika **semua** cabang paralel pada *Fork* telah selesai dikerjakan. Penggabungan alur paralel menggunakan *Merge* adalah kesalahan notasi karena *Merge* tidak menanti proses lain selesai.
3. **Looping/Perulangan via Merge**: Pada diagram SIA, jika nilai dinyatakan `[belum lengkap]`, alur mengarah ke *action* melengkapi nilai oleh Dosen, lalu kembali masuk ke alur utama melalui *Merge* sebelum menuju pemeriksaan Admin Akademik. Hal ini mencegah terciptanya *unbounded loop* atau *deadlock*.

---

## 6. Kendala dan Penyelesaian

- **Kendala 1 (Kerapian Alur & Cross-Swimlane Arrows)**: Garis *control flow* yang melintasi 4 *swimlane* pada diagram SIA rawan saling bersilangan (*overlap*) sehingga membingungkan dibaca.
  - *Penyelesaian*: Mengurutkan posisi swimlane secara logis dari kiri ke kanan (Dosen -> Sistem -> Admin Akademik -> Mahasiswa) serta mengatur *exit/entry points* pada *draw.io* menggunakan *orthogonal edge style* agar lintasan panah tetap siku dan rapi.
- **Kendala 2 (Penggunaan Notasi Paralel vs Percabangan)**: Kebingungan membedakan kapan harus menyatukan alur dengan *Merge* atau *Join*.
  - *Penyelesaian*: Mempelajari kembali Notasi OMG UML 2.5.1 pada Jobsheet Tabel 6.1. Alur percabangan *decision* disatukan kembali oleh *Merge*, sedangkan alur cabang yang berasal dari *Fork* wajib disatukan oleh *Join*.

---

## 7. Kesimpulan

Praktikum Pertemuan 6 berhasil menyusun *activity diagram* yang selaras dan terkonfirmasi keterlacakannya terhadap tabel skenario Pertemuan 5. Tujuh *activity diagram* untuk studi kasus Laboratorium dan satu *activity diagram* empat *swimlane* untuk Sistem Informasi Akademik telah selesai digambar menggunakan notasi UML 2.5.1 yang benar. 

Aturan pemetaan relasi (*include* sebagai *action* wajib, *extend* sebagai cabang bersyarat, percabangan *decision-merge*, eksekusi paralel *fork-join*, serta partisipasi *swimlane*) telah diterapkan secara konsisten tanpa memutus alur dari *initial node* hingga *activity final node*.

---

## Lampiran: Daftar Berkas

Seluruh berkas tersimpan pada direktori `04_model_analisis/P06/`:

| Berkas | Jenis Berkas | Keterangan / Content |
|---|---|---|
| `P06_2406045_LAB_activity_lihat_ketersediaan_v01.drawio` | Source Diagram | Activity Diagram Lihat Ketersediaan (LAB-UC01) |
| `P06_2406045_LAB_activity_kelola_data_v01.drawio` | Source Diagram | Activity Diagram Kelola Data Peralatan (LAB-UC02,08,09,10) |
| `P06_2406045_LAB_activity_peminjaman_v01.drawio` | Source Diagram | Activity Diagram Peminjaman (LAB-UC03) |
| `P06_2406045_LAB_activity_cetak_bukti_v01.drawio` | Source Diagram | Activity Diagram Cetak Bukti Pengajuan (LAB-UC05) |
| `P06_2406045_LAB_activity_keputusan_v01.drawio` | Source Diagram | Activity Diagram Proses Keputusan Peminjaman (LAB-UC06) |
| `P06_2406045_LAB_activity_pengembalian_v01.drawio` | Source Diagram | Activity Diagram Pengembalian Peralatan (LAB-UC11) |
| `P06_2406045_LAB_activity_laporan_v01.drawio` | Source Diagram | Activity Diagram Lihat Laporan Peminjaman (LAB-UC07) |
| `P06_2406045_SIA_activity_v01.drawio` | Source Diagram | Activity Diagram Tugas SIA (Input Nilai s/d Lihat KHS) |
| `P06_2406045_SIA_activity_v01.png` | Export Image | Hasil Ekspor Gambar Activity Diagram SIA |
| `P06_2406045_metadata_activity_v01.md` | Document | Metadata Artefak Pertemuan 6 |
| `Laporan_P06_2406045_Activity_Diagram.md` | Document | Laporan Praktikum Pertemuan 6 |
```

