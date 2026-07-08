# Audit — BAB IV: Hasil dan Pembahasan

**Halaman:** 80–143 (PDF ~99–163)  
**Status:** Substansi sangat kuat; **format gambar & tabel perlu perbaikan besar**

---

## Ringkasan Bab

Bab terbesar dan terkuat: data kuesioner (15 responden), 2 iterasi prototype, implementasi kode (Android + Laravel), wireframe iterasi 2, pengujian Black Box 71/71 (100%) oleh penguji eksternal. Pembahasan §4.5 komprehensif.

**Nilai substansi:** 9/10  
**Nilai format:** 4/10

---

## 4.1 Pengolahan Data

### Yang Sudah Baik
- Validasi platform Android (100% responden)
- Tabel keluhan sistem manual (Tabel 4.1)
- Grafik minat & kebutuhan fitur (Gambar 4.1–4.3)

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | **Wawancara terapis** tidak disebut sebagai sumber data di §4.1 (hanya kuesioner & observasi) | Tambahkan sub-paragraf temuan wawancara |
| Disarankan | Hasil kuesioner ditampilkan sebagai **persentase/grafik**, bukan analisis **Likert** seperti dijanjikan Bab III | Tambahkan rekapitulasi skor Likert atau revisi Bab III |

---

## 4.2 Iterasi Prototype

### Temuan Kritis — Gambar 4.20 vs 4.29

Teks §4.2.2.2 menyatakan:
> *"...penambahan Use Case Diagram baru pada **Gambar 4.20**"*

Padahal **Gambar 4.20** = *Kode Program Menyimpan Catatan Terapi pada Android*  
**Gambar 4.29** = *Use Case Diagram Iterasi 2* ✓

**Perbaikan:** Ganti referensi teks menjadi **Gambar 4.29**.

### Temuan Kritis — Kolisi Nomor Gambar 4.40 & 4.41

Nomor yang sama dipakai untuk **kode program** dan **screenshot halaman**:

| Nomor | Di Daftar Gambar | Di badan teks (kode) | Di §4.3.1 (screenshot) |
|-------|------------------|----------------------|-------------------------|
| **4.40** | Halaman Registrasi | Kode Kalkulasi Antrean Laravel | Teks merujuk 4.35, caption **4.43** |
| **4.41** | Halaman Login | Kode Lihat Antrean Back-End | Teks merujuk 4.41, caption **4.44** |

Ini menunjukkan **penomoran gambar Bab IV tidak pernah diselaraskan** setelah penambahan iterasi 2. Perlu renumber menyeluruh Bab IV.

### Temuan — Sequence Diagram Iterasi 2

§4.2.2.2: *"Gambar **3.28** menunjukkan alur sequence diagram lihat laporan"*  
→ Seharusnya **Gambar 4.30** (Sequence Diagram Lihat Laporan)

---

## 4.3 Penerapan Tampilan (Screenshot)

### Temuan Kritis — §4.3.1 Iterasi Pertama (offset teks vs caption)

Pola sistematis: **teks merujuk nomor A, caption memakai nomor A+3 s/d A+8**:

| Fitur | Teks merujuk | Caption aktual | Daftar Gambar |
|-------|--------------|----------------|---------------|
| Registrasi | 4.35 | **4.43** | 4.40 |
| Login | 4.41 | **4.44** | 4.41 |
| Beranda Pasien | 4.42 | **4.45** | 4.42 |
| Buat Janji Temu | 4.43 | **4.46** | 4.43 |
| … | … | +3 dari teks | … |
| Notifikasi | 4.67 | **4.70** | 4.67 |
| Tambah Layanan | 4.65 | **4.68** | 4.65 |
| Ubah Layanan | 4.66 | **4.69** | 4.66 |

**Tiga sistem nomor berbeda** (Daftar Gambar, teks, caption) — wajib disatukan.

### Temuan Kritis — §4.3.2 Iterasi Kedua

| Masalah | Detail |
|---------|--------|
| Offset +3 | Teks 4.68–4.77 vs caption 4.71–4.80 |
| **Gambar 4.71 duplikat** | Super Admin (hal. 128) & Detail Janji Temu+Antrean (teks hal. 129) |
| Judul caption salah | Teks item 7 = *Laporan Kinerja*, caption **4.77** = *Laporan Kegiatan* |
| Penomoran sub-item | Setelah item 8 (*Laporan Kegiatan*), muncul lagi item **7.** (*Laporan Komparatif*) |
| Campur wireframe & screenshot | §4.3.2 beralih dari rancangan ke screenshot (4.80+) tanpa subjudul jelas |

Contoh offset iterasi 2:

| Teks merujuk | Caption | Isi |
|--------------|---------|-----|
| 4.68 (Super Admin) | **4.71** | Kelola Pengguna Super Admin |
| 4.69 (Detail Admin) | **4.72** | Detail Admin |
| 4.70 (Reset Password) | **4.73** | Reset Password |
| 4.71 (Detail+Antrean) | **4.74** | Detail Janji Temu Antrean |
| 4.72 (Laporan Keuangan) | **4.75** | Laporan Keuangan |

### Temuan — Judul Gambar Duplikat (Kode)

| Nomor | Masalah |
|-------|---------|
| **4.24 & 4.25** | Judul identik: *API Mengambil Detail Catatan Terapi pada Android* |
| **4.35 & 4.36** | Judul identik: *API Mengunduh File PDF Laporan pada Android* |
| **4 39** | Spasi bukan titik — di Daftar Gambar & caption |

### Temuan Kritis — Gambar 4.40 Dirujuk Dua Kali (Kode Berbeda)

Dalam subbab implementasi antrean (§4.2 iterasi 2), **Gambar 4.40** dipakai untuk **dua cuplikan kode berbeda**:

1. *"Gambar 4.40 menunjukkan fungsi show pada BookingController.php"* — kalkulasi antrean dinamis  
2. *"Gambar 4.40 menunjukkan pemanggilan API detail janji temu"* — sisi Android

Ini **duplikasi nomor dalam satu alur pembahasan** — salah satu harus renomori.

---

## 4.4 Pengujian

### Yang Sudah Baik
- Cuplikan kode Android (Kotlin/Compose) & Laravel terstruktur per fitur
- 7 modul pengujian (M-01 s/d M-07) jelas
- **71 skenario**, **100%** keberhasilan, penguji eksternal (objektivitas)
- Persamaan persentase keberhasilan diterapkan benar: 71/71 × 100% = 100%

### Temuan Wajib — Tabel 4.3–4.6

Tabel hasil pengujian Black Box (lanjutan) **ada di badan teks** tetapi **tidak tercantum di Daftar Tabel**:
- Tabel 4.3, 4.4, 4.5, 4.6 — *Hasil Pengujian Oleh Penguji Eksternal (Black Box) (Lanjutan)*

### Temuan Disarankan

| **"didalam"** (satu kata) di §4.1 — *"hadir didalam aplikasi"* | Standar: **di dalam** |
| Super Admin tidak ada di batasan Bab I | Jelaskan di §4.5 sebagai evolusi iterasi 2 |
| **Kebutuhan nonfungsional** (5 poin §3.2.2) tidak diuji/dibahas | Pembahasan singkat atau batasi klaim |
| EP/BVA tidak dilabeli pada skenario uji | Kolom "Teknik" atau contoh di pembahasan |
| Tabel 4.1 baris "1 ." — spasi aneh | Koreksi menjadi "1." |

---

## 4.5 Pembahasan

### Yang Sudah Baik
- Menghubungkan masalah → prototype 2 iterasi → arsitektur REST → pengujian
- Modul M-01 s/d M-07 dijelaskan dengan baik
- Objektivitas penguji eksternal disebutkan

### Saran Opsional
- Sebutkan keterbatasan: belum uji beban (load test), belum uji keamanan penetrasi
- Integrasi hasil kuesioner kualitatif dengan fitur yang diimplementasikan

---

## Checklist Revisi Bab IV

```
[ ] URGENT: Renumber menyeluruh gambar Bab IV (kode vs screenshot bentrok)
[ ] URGENT: Gambar 4.40 duplikat (2 kode berbeda) — renomori salah satu
[ ] URGENT: Gambar 4.20 → 4.29 (Use Case iterasi 2)
[ ] URGENT: §4.3.1 — selaraskan teks, caption, & Daftar Gambar (offset +3 s/d +8)
[ ] URGENT: §4.3.2 — offset +3, duplikat 4.71, perbaiki penomoran sub-item 7/8
[ ] URGENT: Gambar 3.28 → 4.30 (sequence lihat laporan)
[ ] Koreksi judul ganda 4.24–4.25, 4.35–4.36, 4.75, Gambar 4 39
[ ] Tambahkan Tabel 4.3–4.6 ke Daftar Tabel
[ ] Ringkaskan wawancara + tampilkan Likert atau revisi Bab III
[ ] Selaraskan Super Admin dengan Bab I
```

**Estimasi waktu:** 8–12 jam (renumber gambar Bab IV menyeluruh — pekerjaan terbesar)
