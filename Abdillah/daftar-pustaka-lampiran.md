# Audit — Daftar Pustaka & Lampiran

**Halaman:** 147–156 (PDF ~166–175)  
**Status:** Daftar Pustaka cukup lengkap; sitasi & lampiran perlu perbaikan

---

## Daftar Pustaka

### Yang Sudah Baik
- Jumlah referensi besar (~50+ entri) — sesuai skripsi implementasi
- Format umumnya mengikuti gaya APA
- Referensi teknologi (Android, Laravel, Firebase) memadai

### Temuan Wajib — Tabel Hilang dari Daftar Tabel

| Tabel | Lokasi | Status di Daftar Tabel |
|-------|--------|------------------------|
| **2.2** | Simbol Use Case | **Tidak ada** |
| **2.3** | Simbol Sequence Diagram | **Tidak ada** |
| **2.4** | Simbol Class Diagram | **Tidak ada** |
| **2.5** | Kategori Kelayakan (Dewi et al.) | **Tidak ada** |
| **3.8 (Lanjutan)** | Skenario Black Box (4+ halaman) | Hanya 3.8 utama |
| **4.3–4.6** | Hasil pengujian eksternal | **Tidak ada** |

### Temuan Kritis — Lampiran Kosong (Hanya Judul)

Verifikasi per halaman cetak (PDF hal. 173–175 = hal. 154–156):

| Lampiran | Yang dijanjikan | Yang ada di PDF |
|----------|-----------------|-----------------|
| 1 | Wawancara terapis | **Hanya judul** |
| 2 | Responden kuesioner | **Hanya judul** |
| 3 | Surat pernyataan mitra | **Hanya judul** |
| 4 | Surat pernyataan penguji eksternal | **Hanya judul** |
| 5 | File APK | **Hanya judul** |
| 6 | Dokumen uji Black Box (**27 halaman** menurut Bab III) | **Hanya judul** |

**Enam lampiran berbagi 3 halaman fisik tanpa konten.** Kemungkinan scan/gambar tidak ter-embed di PDF, atau belum dilampirkan sama sekali. Ini **blokir cetak** — wajib dilengkapi sebelum perpustakaan.

### Temuan Wajib — Sitasi Tidak Selaras dengan Daftar Pustaka

| Sitasi di teks | Entri Daftar Pustaka | Masalah |
|----------------|----------------------|---------|
| **(Hermawan & Paramita, 2021)** | Tidak ada | Referensi hilang |
| **(Merdekawati et al., 2024)** | Tidak ada | Referensi hilang |
| **(Primin & Permana, 2023)** | **Primin, B., & Wibowo, A. P. (2023)** | **Penulis kedua tidak cocok** |
| **BPS (2024)** (Bab I) | **Badan Pusat Statistik (2025)** | **Tahun tidak cocok** — dalam paragraf yang sama dengan sitasi (2025) |

### Temuan Disarankan — Format Referensi

| Temuan | Contoh perbaikan |
|--------|------------------|
| URL DOI rusak (spasi/karakter) | `https://doi.org/10.29062/...` tanpa spasi |
| **DOI ganda** — prefix `https://doi.org/` diulang | Contoh rusak: entri **Alfauzain et al. (2025)**, **jyk**, **jkms** — hapus duplikasi prefix |
| Inkonsistensi penulis (nama depan/ belakang) | Seragamkan gaya APA |
| Beberapa entri web tanpa tanggal akses | Tambahkan *diakses tanggal* jika diwajibkan prodi |

---

## Lampiran

### Daftar Lampiran (di Daftar Isi)

| No | Judul | Hal. |
|----|-------|------|
| 1 | Wawancara kepada Terapis | 154 |
| 2 | Responden Kuesioner (Pasien) | 154 |
| 3 | Surat Pernyataan Aplikasi oleh Mitra | 155 |
| 4 | Surat Pernyataan Pengujian oleh Penguji Eksternal | 155 |
| 5 | File APK | 156 |
| 6 | Dokumen Uji Black Box Testing | 156 |

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| ~~Wajib~~ | ~~Ekstraksi teks hanya judul~~ | **Dikonfirmasi pass 4: lampiran benar-benar kosong** (bukan masalah ekstraksi) |
| **Kritis** | **Lampiran 1–6 tanpa isi** — 3 halaman untuk 6 lampiran; Lampiran 6 seharusnya ~27 hal. | Lampirkan scan/PDF lengkap: wawancara, kuesioner, surat mitra & penguji, info APK, skenario uji |
| Wajib | **Formulir kuesioner** tidak ada | Lampirkan instrumen Likert |
| Wajib | **Primin & Permana** vs **Primin & Wibowo** di Daftar Pustaka | Seragamkan sitasi & referensi |
| Disarankan | Lampiran 5 (APK) — tidak ada QR/link/file | Sertakan link unduhan atau petunjuk instalasi |

### Halaman Persembahan

Halaman persembahan (PDF hal. 5) berisi teks penuh — **sudah baik**, tidak kosong.

---

## Checklist Revisi

```
[ ] KRITIS: Lengkapi isi Lampiran 1–6 (saat ini hanya judul)
[ ] Koreksi sitasi Primin & Permana / Wibowo; BPS 2024 vs 2025
[ ] Tambahkan Tabel 2.2–2.5, 3.8 (Lanjutan), 4.3–4.6 ke Daftar Tabel
[ ] Tambahkan Hermawan & Paramita (2021), Merdekawati et al. (2024)
[ ] Perbaiki DOI/URL rusak
[ ] Lampirkan instrumen kuesioner Likert + dokumen uji 71 skenario
```

**Estimasi waktu:** 1–2 hari (lampiran) + 2–3 jam (sitasi)
