# Audit — BAB II: Tinjauan Pustaka

**Halaman isi:** 5–24 (PDF hal. 21–40)  
**Status:** Substansi baik — **format §2.1 perlu perbaikan** (catatan penguji)

---

## Ringkasan Bab

Bab II lengkap: 10 penelitian terkait, analisis kompetitor, teori chatbot/AI/website, stack teknologi (Next.js, Tailwind, MongoDB, Mongoose, REST), metode Waterfall, pengujian, UML, flowchart. Paragraf **Perbedaan dengan Penelitian Sebelumnya** cukup kuat menjelaskan kebaruan.

**Nilai substansi:** 7,5/10  
**Nilai format §2.1:** 5/10

---

## 2.1 Penelitian Terkait — Temuan Utama (Hal. 5)

### Catatan Penguji I (Bu Masna)

> *"Kurang penjelasan penelitian terkait apa (halaman 5)"*

**Diagnosis:** Setiap poin langsung ke *"Metode yang digunakan"* dan *"Temuan penelitian"* tanpa **1–2 kalimat pembuka** yang menjelaskan **topik/fokus** penelitian terdahulu. Pembaca harus membaca paragraf panjang baru paham konteksnya.

### Contoh perbaikan (poin #1)

**Sekarang:**
> Metode yang digunakan: R&D … Temuan penelitian: Penelitian ini membahas tentang rancang bangun chatbot…

**Usulan:**
> **1. Chatbot asisten virtual karyawan bank syariah (Rahmaya et al., 2026).**  
> Penelitian ini mengembangkan chatbot internal untuk efisiensi pencarian SOP dan dokumen operasional.  
> Metode: R&D + Waterfall.  
> Temuan: …

### Temuan lain §2.1

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Format 10 poin = **dinding teks** (~6 halaman) | Buat **Tabel 2.1 Penelitian Terdahulu** (Peneliti \| Tahun \| Topik \| Metode \| Hasil \| Gap) + ringkas narasi |
| Sedang | **#4 Nugroho (2024)** — performa Next.js vs Bootstrap; relevansi chatbot **lemah** | Pertahankan jika jadi landasan pemilihan Next.js; jelaskan 1 kalimat relevansi |
| Sedang | **#8 Ramadani (2023)** — sistem keuangan sekolah; **relevansi sangat lemah** | Ganti dengan penelitian chatbot/KB lebih dekat, atau jelaskan hanya sebagai contoh Waterfall |
| Sedang | Typo: *"kayawan"*, *"Understandin"*, *"dan, User Interface"* (koma salah) | Proofread |
| Sedang | *"kompelksitas"* → **kompleksitas** | Perbaiki |
| OK | Semua 10 sitasi ada di Daftar Pustaka | — |

---

## 2.2–2.3 Platform Resmeku & Kompetitor

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Tabel 2.1 analisis kompetitor (Chatfuel, ManyChat, DialogFlow) — kuat | — |
| OK | Sitasi web Chatfuel/ManyChat/Google Cloud (2026) | Pastikan URL masih aktif saat cetak |

---

## 2.4–2.7 Teori Chatbot, AI, Website

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | *"dendorongpemanfaatannya"* — spasi hilang | **dorong pemanfaatannya** |
| Sedang | *"kecerdasan buatan"* di §2.6 seharusnya *"kecerdasan manusia"* | Perbaiki frasa AI |
| Sedang | *"saran penyampaian"* → **sarana** | §2.7 |
| OK | Teori kecepatan respons (<3 detik) dipakai di Bab IV | — |

---

## 2.8–2.12 Teknologi

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Next.js, Tailwind, MongoDB, Mongoose, REST — selaras implementasi | — |
| Sedang | *"dlama"* → **dalam**; *"protkol"* → **protokol** | §2.10, 2.12 |
| Sedang | *"next.js"* vs *"Next.js"* — kapitalisasi tidak konsisten | Seragamkan |

---

## 2.9 Waterfall

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | *"menyeluruh menyeluruh"* duplikasi | Hapus salah satu |
| Sedang | *"persepektif"* → **perspektif** | Beberapa subbab |
| OK | Gambar 2.1 ada | — |

---

## 2.14–2.17 Pengujian & Likert

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Blackbox, UAT, kriteria akurasi/relevansi/efektivitas — dipakai konsisten | — |
| Sedang | *"intepretasi"* → **interpretasi** | §3.6.3 / Tabel 3.9 |

---

## 2.18 Flowchart

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Tabel 2.2 simbol flowchart | — |
| OK | Revisi sidang: **Gambar 3.2** sudah punya proses sebelum *End* | Sudah sesuai catatan penguji |

---

## 2.19 UML

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | Tabel 2.2 header **duplikat** di hal. 22–23 | Hapus header tabel yang terulang |
| OK | Use case & sequence diagram di Bab III selaras | — |

---

## Kesimpulan Bab II

- **Jangan kurangi** 10 penelitian terkait — sudah bagus.  
- **Ubah cara penyajian §2.1** agar memenuhi catatan penguji.  
- Proofread typo dan evaluasi relevansi penelitian #4 & #8.
