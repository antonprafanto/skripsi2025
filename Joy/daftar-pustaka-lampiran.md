# Audit — Daftar Pustaka & Lampiran

**Halaman:** 49–55  
**Status:** Perlu revisi besar (Daftar Pustaka)

---

## Ringkasan

Daftar Pustaka memuat 39 entri — jumlah cukup, tetapi **banyak sitasi di badan teks tidak ada di daftar**. Lampiran perlu dilengkapi format dan isi (terutama source code).

---

## Daftar Pustaka

### Yang Sudah Baik
- Format umum mendekati standar (penulis, tahun, judul, sumber)
- Campuran jurnal, web, konferensi — wajar untuk topik IoT
- Beberapa referensi memiliki DOI

---

### Temuan Wajib — Sitasi di Teks Tidak Ada di Daftar Pustaka

| No | Sitasi di Teks | Bab | Tindakan |
|----|----------------|-----|----------|
| 1 | Rohman, 2021 | I | Tambahkan referensi lengkap |
| 2 | Angriawan, 2020 | I | Tambahkan (atau ganti dengan Angriawan 2024) |
| 3 | Kasim, 2020 | I | Tambahkan (atau ganti dengan Kasim 2023) |
| 4 | Asyari, 2021 | I | Tambahkan (atau ganti dengan Asyari 2024) |
| 5 | Purnamasari et al., 2021 | I | Tambahkan |
| 6 | Sitinjak & Suwita, 2020 | I | Tambahkan |
| 7 | Amirudin et al., 2021 | I | Tambahkan |
| 8 | Suryanto & Ariefin, 2022 | I | Tambahkan atau seragamkan dengan entri 2024 |
| 9 | Usman, 2021 | II | Tambahkan |
| 10 | Hermansyah et al., 2025 | II | Tambahkan |
| 11 | Rohman & Isnaini, 2024 | II | Tambahkan |
| 12 | Abilovani, 2018 | II | Tambahkan (cek entri #11 "bilovani" — kemungkinan typo) |

> **Temuan terbesar di seluruh skripsi.** Referensi yang disitasi di teks wajib ada di Daftar Pustaka sebelum dicetak.

---

### Temuan Format & Typo

| Prioritas | Temuan | Perbaikan |
|-----------|--------|-----------|
| Wajib | #11: **"bilovani, Z. B."** — kemungkinan **"Abilovani"** | Verifikasi & koreksi |
| Wajib | #38: **"Ayam Boiler"** → **"Ayam Broiler"** | Koreksi typo |
| Disarankan | #21–22: *"Diakses pada 05 Juni 2026, pada website"* — kata "pada" ganda | Rapikan |
| Disarankan | Format tidak seragam (DOI, URL, tanpa keduanya) | Seragamkan gaya prodi |
| Disarankan | Beberapa URL pendek/tidak lengkap (#1, #5, #6) | Pastikan dapat diakses |
| Disarankan | #33 Rohman 2025 — judul ayam **potong**, disitasi untuk ayam **kontes** | Verifikasi relevansi |

---

### Referensi di Daftar Pustaka yang Mungkin Tidak Disitasi

| No | Referensi | Saran |
|----|-----------|-------|
| 4 | Andini et al., 2020 | Cek & sitasi atau hapus |
| 7 | Atzori et al., 2010 | Referensi klasik IoT — sebaiknya disitasi di §2.5 |
| 8 | Aulia, 2021 | Cek |
| 9 | Babbar, 2021 | Cek |
| 10 | Basori, 2023 | Cek |
| 12 | Cardi & Najmurrokhman, 2021 | Cek |
| 16 | Ervianto et al., 2026 | Verifikasi validitas |

**Aturan:** Setiap entri daftar pustaka harus disitasi di teks; setiap sitasi di teks harus ada di daftar.

---

### Cara Memperbaiki

1. Gunakan Find di Word, cari semua pola `(Nama, Tahun)`
2. Buat checklist: Sitasi di Teks | Ada di Daftar Pustaka?
3. Lengkapi yang belum ada; hapus entri yang tidak pernah disitasi
4. Urutkan sesuai aturan prodi (abjad atau urutan kemunculan)

---

## Lampiran

### Yang Ada

| Lampiran | Halaman | Konten |
|----------|---------|--------|
| Lampiran 1 | 54 | Hasil Wawancara (transkrip 5 pertanyaan) |
| Lampiran 2 | 55 | Dokumentasi Bersama Peternak (foto) |
| Lampiran 3 | 55 | Kumpulan File Terkait (QR Bitly) |

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | **Hasil wawancara tidak dirangkum** di Bab I & III — padahal isinya penting | Ringkas di narasi utama; rujuk Lampiran 1 |
| Disarankan | Judul **"LAMPIRAN 1"** muncul di **bawah** isi (hal. 54), bukan di atas | Pindahkan judul ke awal halaman |
| Disarankan | Tanggal wawancara **7 Oktober 2025** tidak disebut di metodologi | Cantumkan di Bab III §3.2 |
| Wajib | **Kode program lengkap tidak ada** — kode di Bab IV terpotong | Tambah Lampiran: source code ESP32 & dashboard |
| Disarankan | Lampiran 3 hanya QR Bitly **tanpa daftar file** | Tambahkan daftar isi link; verifikasi QR masih aktif |
| Disarankan | Wawancara sebut **listrik sering padam** — tidak dibahas di skripsi | Bahas di Bab V saran (UPS) |

### Isi Lampiran yang Disarankan

```
Lampiran 1  — Hasil Wawancara (transkrip)
Lampiran 2  — Dokumentasi Kegiatan di AR Farm Simpang Pasir
Lampiran 3  — Daftar File Proyek + QR/link
Lampiran 4  — Source Code Program ESP32 (lengkap)
Lampiran 5  — Source Code Dashboard Web (HTML/CSS/JS)
Lampiran 6  — Export Wireshark .pcapng (opsional)
```

---

## Checklist Revisi — Daftar Pustaka & Lampiran

```
[ ] Tambahkan 12 referensi yang hilang / tidak cocok
[ ] Koreksi typo: bilovani, Boiler
[ ] Seragamkan format sitasi
[ ] Verifikasi semua URL masih aktif
[ ] Pastikan setiap entri disitasi & setiap sitasi ada entri
[ ] Perbaiki format Lampiran 1 (judul di atas)
[ ] Lengkapi lampiran source code
[ ] Tambahkan daftar file di Lampiran 3
[ ] Verifikasi QR Bitly masih aktif
```

**Estimasi waktu revisi:** 4–6 jam
