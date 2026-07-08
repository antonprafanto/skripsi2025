# Audit — BAB II: Tinjauan Pustaka

**Halaman:** 6–7 (PDF)  
**Status:** Perlu ditulis ulang — ini prioritas utama

---

## Ringkasan Bab

Bab II adalah **kelemahan terbesar** draft ini. Penelitian terdahulu hanya 2 paragraf kosong tanpa menyebut peneliti mana pun. Landasan teori ada tetapi dangkal dan tanpa sitasi. Padahal di Daftar Pustaka sudah ada 35+ referensi — **tidak satu pun dipakai di teks**.

**Nilai substansi:** 2/10  
**Nilai penulisan akademik:** 1/10 (tanpa sitasi, tanpa tabel)

> **Untuk Nelsi:** Bab inilah yang harus kamu kerjakan pertama. Sisihkan 5–7 hari hanya untuk Bab II. Gunakan `template-penelitian-terdahulu.md` sebagai panduan.

---

## 2.1 Penelitian Terdahulu — KRITIS

### Isi saat ini (hanya ini!)

```
Beberapa penelitian terdahulu yang relevan dengan penelitian ini antara lain 
penelitian mengenai pemanfaatan teknologi informasi dalam pelayanan publik...

Penelitian oleh berbagai akademisi menunjukkan bahwa pemanfaatan WhatsApp 
sebagai media komunikasi dalam layanan publik dapat meningkatkan efisiensi...
```

### Kenapa ini ditolak penguji?

| Masalah | Penjelasan |
|---------|------------|
| Tidak menyebut **nama peneliti** | Siapa "berbagai akademisi"? |
| Tidak menyebut **tahun** | Kapan penelitiannya? |
| Tidak menyebut **hasil** | Apa temuannya? |
| Tidak ada **perbandingan** | Sama atau beda dengan penelitianmu? |
| Tidak ada **research gap** | Apa yang belum diteliti? |
| Tidak ada **tabel** | Standar minimum skripsi Informatika |

### Yang harus ada di §2.1

1. **Tabel 2.1 — Penelitian Terdahulu** (minimal 5 baris) → lihat `template-penelitian-terdahulu.md`
2. **Paragraf analisis** setelah tabel — pola, kelebihan, kekurangan penelitian sebelumnya
3. **Paragraf kesenjangan penelitian (research gap)** — apa yang belum dilakukan dan akan kamu lakukan
4. **Paragraf posisi penelitian ini** — kebaruan penelitianmu

### Contoh paragraf kesenjangan (sesuaikan setelah isi tabel)

> Berdasarkan Tabel 2.1, penelitian-penelitian sebelumnya telah berhasil mengintegrasikan WhatsApp dalam pelayanan surat administrasi, namun belum ada penelitian yang secara khusus menerapkan sistem terintegrasi web admin dan chatbot WhatsApp di Kelurahan Kampung Sambakungan. Penelitian Sipuas (JITED UNY, 2024) dan SIPANDHA (JAG, 2024) menerapkan integrasi web dan WhatsApp di tingkat desa, sedangkan Puspita et al. (2023) menggunakan WhatsApp Gateway di tingkat kecamatan. Oleh karena itu, penelitian ini mengisi kesenjangan tersebut dengan merancang sistem yang menggabungkan panel admin web dan chatbot WhatsApp Cloud API, serta mengukur peningkatan efisiensi waktu layanan di Kelurahan Kampung Sambakungan.

**Catatan:** Jangan menyitasi referensi yang belum diverifikasi (mis. Purnama 2020, Hidayat 2022, Aldila 2022) — gunakan hanya referensi yang bisa dibuka PDF-nya.

---

## 2.2 Landasan Teori

### Yang Sudah Baik
- Subbab lengkap: Sistem Informasi, WhatsApp, Pelayanan Kelurahan, Chatbot, Waterfall
- Urutan logis dari konsep umum ke spesifik

### Temuan per subbab

#### 2.2.1 Sistem Informasi

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Definisi tanpa sitasi | Tambah (Laudon & Laudon, 2020) atau (Jogiyanto, 2017) |
| Disarankan | Tidak dihubungkan ke sistem yang akan dibangun | Akhiri paragraf: *"Dalam penelitian ini, sistem informasi dibangun dengan komponen…"* |

#### 2.2.2 WhatsApp sebagai Media Komunikasi

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Tidak menjelaskan perbedaan jenis WhatsApp | Tambah sub-sub: WhatsApp Messenger vs Business App vs Cloud API |
| Wajib | Tanpa sitasi | (Dewi & Nurlaela, 2022), (We Are Social & Hootsuite, 2023) |
| Disarankan | Tidak ada gambar arsitektur integrasi | Tambah Gambar 2.1: Arsitektur WhatsApp Cloud API |

**Penjelasan untuk mahasiswa — jenis WhatsApp:**

| Jenis | Untuk siapa | Cocok untuk skripsi? |
|-------|-------------|-------------------|
| WhatsApp biasa | Personal | ✗ Tidak bisa diotomasi |
| WhatsApp Business App | UMKM kecil | ✗ Terbatas, manual |
| WhatsApp Business API / Cloud API | Bisnis & organisasi | ✓ **Ini yang harus kamu pakai** |
| Baileys (library tidak resmi) | Developer hobi | ✗ **Jangan pakai** — melanggar ToS |

#### 2.2.3 Pelayanan Administrasi Kelurahan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Tidak merujuk regulasi | Sitasi UU No. 25/2009 dan Permen PANRB No. 15/2014 (sudah ada di daftar pustaka!) |
| Disarankan | Tidak ada standar pelayanan | Jelaskan 5 dimensi kualitas pelayanan (Hardiansyah, 2018) |

#### 2.2.4 Chatbot

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Tidak ada jenis chatbot | Bedakan: rule-based (menu pilihan) vs AI/NLP |
| Disarankan | Tanpa sitasi | (Agus & Wahyuni, 2021), (Mustika et al., 2023) — **verifikasi dulu** |
| Disarankan | Tidak dijelaskan chatbot yang akan kamu buat | *"Penelitian ini menggunakan chatbot rule-based berbasis menu interaktif"* |

#### 2.2.5 Metode Waterfall

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Hanya definisi, tanpa sitasi | (Pressman & Maxim, 2019), (Sommerville, 2016) |
| Disarankan | Tidak ada gambar tahapan | Tambah Gambar 2.2: Tahapan Waterfall |
| Disarankan | Tidak ada alasan pemilihan | Tambah paragraf: kenapa Waterfall, bukan Prototype/Agile |
| Disarankan | R&D disebut di Bab III tapi tidak di teori | Tambah §2.2.6 Metode Penelitian R&D (Sugiyono, 2019) |

**Contoh alasan memilih Waterfall:**
> Metode Waterfall dipilih karena kebutuhan sistem sudah jelas setelah observasi di kelurahan, alur pelayanan surat sudah baku, dan perubahan kebutuhan selama pengembangan diperkirakan minimal (Dian et al., 2021).

---

## Subbab yang Harus Ditambahkan

| Subbab baru | Isi |
|-------------|-----|
| **2.2.6 Metode Penelitian R&D** | Definisi R&D menurut Sugiyono; posisi dalam penelitian ini |
| **2.2.7 Black Box Testing** | Definisi, tujuan, cara pengujian (Kurniawan & Santoso, 2021) |
| **2.2.8 User Acceptance Testing (UAT)** | Definisi, indikator kepuasan (Yusuf et al., 2022) |
| **2.3 Kerangka Pemikaran** | Diagram hubungan: masalah → sistem → efisiensi & kepuasan |

### Contoh Kerangka Pemikaran (Gambar 2.3)

```
Masalah: Pelayanan manual, antrean, tidak terstruktur
    ↓
Solusi: Sistem layanan surat berbasis WhatsApp + Web Admin
    ↓
Variabel terikat: Efisiensi waktu layanan ↑, Kepuasan pengguna ↑
    ↓
Pengujian: Black Box Testing + UAT
```

---

## Masalah Referensi di Bab II

| Prioritas | Temuan |
|-----------|--------|
| **Wajib** | 35+ referensi di daftar pustaka, **0 sitasi** di Bab I–III |
| **Wajib** | Beberapa referensi **tidak terverifikasi** — lihat `daftar-pustaka-lampiran.md` |
| **Wajib** | Penelitian terdahulu di daftar pustaka (Purnama 2020, Hidayat 2022, dll.) **tidak dibahas** di §2.1 |

---

## Struktur Bab II yang Disarankan (setelah revisi)

```
BAB II TINJAUAN PUSTAKA
  2.1 Penelitian Terdahulu
      Tabel 2.1 Penelitian Terdahulu
      Analisis penelitian terdahulu
      Kesenjangan penelitian
      Posisi penelitian ini
  2.2 Landasan Teori
      2.2.1 Sistem Informasi
      2.2.2 WhatsApp sebagai Media Komunikasi
      2.2.3 Pelayanan Administrasi Kelurahan
      2.2.4 Chatbot
      2.2.5 Metode Waterfall
      2.2.6 Metode Penelitian R&D
      2.2.7 Black Box Testing
      2.2.8 User Acceptance Testing (UAT)
  2.3 Kerangka Pemikaran
```

---

## Checklist Revisi Bab II

```
[ ] Buat Tabel 2.1 Penelitian Terdahulu (min. 5 baris, referensi terverifikasi)
[ ] Tulis paragraf analisis setelah tabel
[ ] Tulis paragraf kesenjangan penelitian (research gap)
[ ] Tulis paragraf posisi/kebaruan penelitian ini
[ ] Tambahkan sitasi di SETIAP subbab landasan teori
[ ] Tambah penjelasan jenis WhatsApp (Cloud API)
[ ] Tambah sitasi UU 25/2009 dan Permen PANRB
[ ] Tambah subbab R&D, Black Box, UAT
[ ] Buat Gambar 2.2 (Waterfall) dan Gambar 2.3 (Kerangka Pemikaran)
[ ] Verifikasi semua referensi yang disitasi
[ ] Hapus referensi fiktif/tidak ditemukan dari daftar pustaka
```

**Estimasi waktu:** 5–7 hari kerja

---

## Tips Mencari Referensi yang Valid

1. Buka **Google Scholar** → scholar.google.com
2. Ketik: `sistem informasi surat kelurahan whatsapp`
3. Pilih artikel yang punya **tahun**, **nama jurnal**, dan bisa dibuka PDF-nya
4. Prioritaskan yang punya **DOI** (nomor unik artikel)
5. Jangan pakai referensi dari ChatGPT tanpa buka link-nya — banyak yang fiktif

**Referensi valid yang sudah diverifikasi untuk topik kamu:**

| Referensi | DOI/Link | Status |
|-----------|----------|--------|
| Sipuas — JITED UNY (2024) | doi.org/10.21831/jited.v3i1.1044 | ✓ Valid |
| SIPANDHA — JAG (2024) | doi.org/10.30869/jag.v8i2.1516 | ✓ Valid |
| Puspita et al. — G-Tech (2023) | doi.org/10.33379/gtech.v7i3.2680 | ✓ Valid |
| Fitriansyah & Budiarto (2020) | Cek di Google Scholar | Perlu verifikasi |
| Purnama & Sukardi (2020) | Tidak ditemukan | ⚠ Ganti referensi lain |
| Hidayat et al. (2022) | Tidak ditemukan | ⚠ Ganti referensi lain |
