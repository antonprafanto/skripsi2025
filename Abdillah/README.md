# Laporan Audit Final Draft Skripsi

**Mahasiswa:** Muhammad Abdillah (2209106065)  
**Judul:** Pengembangan Aplikasi Layanan Berbasis Android Menggunakan Metode Prototype (Studi Kasus: Rumah Sehat Manna wa Salwa)  
**Pembimbing:** Ir. Indah Fitri Astuti, S.Kom., M.Cs. & Anton Prafanto, S.Kom., M.T.  
**Dokumen:** Skripsi_MuhammadAbdillah_2209106065_afterSidang2.pdf (175 halaman)  
**Tanggal audit:** 8 Juli 2026

---

## Daftar Laporan Per Bab

| File | Bagian Skripsi |
|------|----------------|
| [bagian-awal.md](bagian-awal.md) | Cover, pengesahan, abstrak, kata pengantar, daftar |
| [bab-i.md](bab-i.md) | BAB I — Pendahuluan |
| [bab-ii.md](bab-ii.md) | BAB II — Tinjauan Pustaka |
| [bab-iii.md](bab-iii.md) | BAB III — Metodologi Penelitian |
| [bab-iv.md](bab-iv.md) | BAB IV — Hasil dan Pembahasan |
| [bab-v.md](bab-v.md) | BAB V — Kesimpulan dan Saran |
| [daftar-pustaka-lampiran.md](daftar-pustaka-lampiran.md) | Daftar Pustaka & Lampiran |

---

## Penilaian Singkat

| Aspek | Status |
|-------|--------|
| Substansi penelitian | **Baik** — scope besar, 2 iterasi prototype, implementasi lengkap |
| Implementasi & pengujian | **Baik** — Black Box 71 skenario, 100% |
| Format & konsistensi | **Perlu perbaikan besar** — penomoran bab/gambar bermasalah |
| Sitasi & referensi | **Perlu perbaikan** — 2 referensi hilang, Primin/Permana≠Wibowo, BPS tahun, DOI rusak |
| Kelengkapan dokumen | **Kritis** — **lampiran 1–6 kosong** (hanya judul); placeholder tanggal/materai |
| **Siap cetak perpustakaan** | **Belum — revisi wajib dulu** |

Estimasi waktu revisi: **7–10 hari kerja** (renumber gambar Bab IV menyeluruh adalah pekerjaan terbesar).

---

## 12 Temuan Paling Kritis (Prioritas Tertinggi)

1. **BAB I bernomor 4.1.1.1–4.1.1.6** — seharusnya 1.1–1.6 (salah copy-paste/template)
2. **Pernyataan keaslian:** typo **BEBASIS**, tanggal **"Tgl bln thn"**, materai kosong
3. **Halaman pengesahan TIDAK memuat Penguji I & II** — kata pengantar berterima kasih ke Addy Suyatno & Medi Taruk, tetapi blok penguji absen
4. **Kata pengantar** masih **"proposal skripsi"** (4 kali)
5. **Kolisi nomor Gambar 4.40 & 4.41** — dipakai untuk kode Laravel DAN screenshot halaman (nomor bentrok)
6. **§4.3.1 Iterasi 1** — teks merujuk 4.35–4.67, caption 4.43–4.70 (+3 s/d +8 dari teks)
7. **§4.3.2 Iterasi 2** — teks vs caption offset +3; **Gambar 4.71** dipakai 2× untuk konten berbeda
8. **§3.5 Bab III** — offset +1 teks vs caption; **Gambar 3.41** duplikat; **Gambar 3.35** judul ganda di daftar
9. **Tabel 2.2–2.5, 3.8 (Lanjutan), 4.3–4.6** ada di teks tapi **tidak/tidak lengkap di Daftar Tabel**
10. **Sitasi (Hermawan & Paramita, 2021)** dan **(Merdekawati et al., 2024)** tidak ada di Daftar Pustaka
11. **Likert** disebut di metodologi, **hasil tidak ditampilkan** di Bab IV; **wawancara** tidak dirangkum di Bab IV
12. **Gambar 4.20** (teks) vs **4.29** (caption) untuk Use Case iterasi 2; **Gambar 4 39** (spasi, bukan titik)
13. **Lampiran 1–6 kosong** — hanya judul, tanpa wawancara/kuesioner/surat/dokumen uji 27 hal.

---

## Temuan Lintas Bab

| No | Temuan | File terkait |
|----|--------|--------------|
| 1 | Penomoran subbab Bab I salah | `bab-i.md` |
| 2 | Konsistensi gambar Bab III & IV | `bab-iii.md`, `bab-iv.md` |
| 3 | Super Admin di luar batasan Bab I | `bab-i.md`, `bab-iv.md` |
| 4 | XAMPP di teori, tidak dipakai di implementasi | `bab-ii.md`, `bab-iii.md` |
| 5 | EP/BVA di teori, tidak dilabeli di uji | `bab-ii.md`, `bab-iv.md` |
| 6 | Kuesioner n=15 tanpa instrumen di lampiran | `bab-iii.md`, `bab-iv.md`, `daftar-pustaka-lampiran.md` |
| 7 | Gelar M.T. / MT. tidak konsisten | `bagian-awal.md` |
| 8 | Penguji tidak ada di halaman pengesahan | `bagian-awal.md` |
| 9 | Kolisi penomoran gambar kode vs screenshot (4.40+) | `bab-iv.md` |
| 10 | Judul gambar duplikat/salah (4.24–4.25, 4.35–4.36, 4.75) | `bab-iv.md`, `bagian-awal.md` |
| 11 | Back-end / Back-End tidak konsisten | `bab-ii.md`, `bab-iv.md` |
| 12 | Manna **wa** Salwa vs Manna **Wa** Salwa | `bagian-awal.md`, `bab-i.md` |
| 13 | Penomoran sub-item §4.3.2 terduplikasi (7, 8, lalu 7 lagi) | `bab-iv.md` |
| 14 | **Lampiran 1–6 kosong** (hanya judul) | `daftar-pustaka-lampiran.md` |
| 15 | Sitasi Primin & Permana ≠ Primin & Wibowo | `bab-i.md`, `daftar-pustaka-lampiran.md` |
| 16 | BPS (2024) vs (2025) dalam paragraf sama | `bab-i.md` |
| 17 | Kebutuhan nonfungsional tidak diuji | `bab-iii.md`, `bab-iv.md` |

---

## Temuan Baru — Pass Ketiga (8 Juli 2026)

| No | Temuan | Prioritas |
|----|--------|-----------|
| 14 | **Gambar 2.2** (Tahapan Prototype) ada di Bab II, **tidak ada di Daftar Gambar** | Wajib |
| 15 | **Figma** dijelaskan §2.13, tetapi perancangan memakai **wireframe** — bukan Figma | Disarankan |
| 16 | **Firebase** inti autentikasi, **tidak ada subbab teori Bab II** (hanya Daftar Istilah) | Disarankan |
| 17 | **Tidak ada diagram ERD** — struktur DB hanya Tabel 3.1–3.7 | Disarankan |
| 18 | **Evolutionary Prototyping** dipakai di Bab IV, **tidak dideklarasikan eksplisit di Bab III §3.1** | Disarankan |
| 19 | **Gambar 4.40** dirujuk **2× untuk kode berbeda** dalam satu subbab (antrean + API detail) | Wajib |
| 20 | **DOI rusak berulang** — `https://doi.org/https://doi.org/...` (min. 3 entri) | Wajib |
| 21 | Paragraf **kebaruan §2.1** menyebut aktor **admin**, belum **Super Admin** (iterasi 2) | Disarankan |
| 22 | **Kata kunci** tidak menyertakan **Firebase** / **REST API** padahal inti sistem | Opsional |
| 23 | Label rumus: **(2.1)** di Bab II vs **Persamaan 2.1** di Bab IV — tidak konsisten | Opsional |

---

## Temuan Baru — Pass Keempat (8 Juli 2026)

| No | Temuan | Prioritas |
|----|--------|-----------|
| 24 | **Lampiran 1–6 hanya judul, tanpa isi** — Bab III janjikan dokumen uji **27 halaman** | **Kritis** |
| 25 | Sitasi **Primin & Permana (2023)** ≠ referensi **Primin & Wibowo (2023)** | Wajib |
| 26 | **BPS (2024)** vs **BPS (2025)** dalam paragraf yang sama | Wajib |
| 27 | **Kebutuhan nonfungsional** tidak diuji di Bab IV | Disarankan |
| 28 | Koreksi audit: rumusan & kesimpulan **2 poin** (bukan 3) — **sudah selaras** | — |

Ekstraksi: `extracted_abdillah/full_text.txt`, `page_173.txt`–`page_175.txt`
