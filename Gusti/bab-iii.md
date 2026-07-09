# Audit — BAB III: Metodologi Penelitian

**Halaman isi:** 25–45 (PDF hal. 41–61)  
**Status:** Baik — revisi sedang pada prosedur UAT & persamaan

---

## Ringkasan Bab

Bab III terstruktur jelas: tahapan penelitian (Gambar 3.1), pengumpulan data, perancangan data (KB 15 dokumen / 5 kategori), perancangan proses (Waterfall: analisis–pemeliharaan), desain UI, dan perancangan pengujian (Blackbox + UAT + Likert). Diagram flowchart, use case, dan sequence **memadai** untuk skripsi S1.

**Nilai substansi:** 8/10  
**Nilai format:** 7/10

---

## 3.1 Tahapan Pelaksanaan Penelitian

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | 6 tahap (identifikasi → laporan) selaras Waterfall | — |
| OK | Gambar 3.1 ada | — |

---

## 3.2 Pengumpulan Data

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Studi pustaka + observasi platform Resmeku | — |
| Sedang | Observasi tidak menyebut durasi / tanggal | Opsional: 1 kalimat periode observasi |

---

## 3.3 Perancangan Data

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Tabel 3.1 & 3.2 — 15 dokumen, 5 kategori | — |
| Sedang | *"Penggunaa"* → **Pengguna** | Tabel 3.2 |

---

## 3.4 Perancangan Proses

### 3.4.1 Analisis Kebutuhan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Kebutuhan fungsional a–d & non-fungsional a–d jelas | — |

### 3.4.2 Desain

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Flowchart (Gambar 3.2), Use Case (3.3), Sequence (3.4) | Flowchart sudah revisi sidang ✓ |
| Sedang | Disebut **OOP** tetapi tidak ada class diagram | Hapus klaim OOP atau tambahkan diagram kelas singkat |
| Sedang | *"lansgung"* → **langsung** | §Use case explanation |

### 3.4.3 Pengkodean

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Tabel 3.3 teknologi lengkap (Next.js, MongoDB, shadcn/ui, API AI) | — |
| OK | Tabel 3.4 risk assessment — relevan operasional | — |

### 3.4.4 Pengujian — **Temuan Penting**

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | *"Sebelum responden memberikan penilaian, peneliti berperan sebagai verifikator yang mengklarifikasi kebenaran respons… apabila terdapat ketidaksesuaian, peneliti menjelaskan jawaban yang seharusnya"* | **Risiko bias UAT.** Pilih salah satu: (a) jelaskan bahwa klarifikasi hanya untuk skenario instruksional, bukan mempengaruhi skor; (b) ubah prosedur menjadi responden menilai tanpa koreksi; (c) pisahkan skor *pre-koreksi* vs *post-koreksi* |
| OK | 10 responden, 10 skenario, Likert 1–5, 3 aspek | — |

### 3.4.5 Pemeliharaan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Standar Waterfall | — |

---

## 3.5 Perancangan Tampilan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Mockup hal. 3.5–3.10 selaras screenshot Bab IV | — |
| Sedang | *"strutkur"* → **struktur** | §Manajemen Chatbot |
| Sedang | *"Resmeku yang menjadi"* — spasi sebelum titik | §Manajemen Organisasi |

---

## 3.6 Perancangan Pengujian

### 3.6.1 Blackbox

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Tabel 3.5 — 10 skenario fungsional | Dieksekusi di Bab IV ✓ |

### 3.6.2 UAT

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Tabel 3.6 — 10 kasus uji terhubung KB | — |
| OK | Tabel 3.7 contoh pertanyaan ilustratif | — |
| Sedang | Tabel 3.6 terpotong antar halaman | Pastikan header tidak duplikat |

### 3.6.3 Likert

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | Persamaan (3.1)–(3.3) **render rusak** di PDF (*𝑋"*, subscript aneh) | Perbaiki equation editor Word; gunakan X̄ notasi sederhana |
| OK | Tabel 3.8–3.9 bobot & interpretasi 81–100% = Sangat Sesuai | — |

---

## Kesimpulan Bab III

Metodologi **sudah memadai**. Prioritas revisi: **klarifikasi prosedur UAT** (bias verifikator) dan perbaikan **persamaan matematika** + typo.
