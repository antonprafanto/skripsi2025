# Audit — BAB IV: Hasil dan Pembahasan

**Halaman isi:** 46–71 (PDF hal. 62–87)  
**Catatan:** *"PDF hal. 71"* = halaman fisik PDF; *"isi hal. 55"* = nomor di footer Bab IV  
**Status:** **Substansi baik — revisi wajib pada rujukan gambar & layout**

---

## Ringkasan Bab

Bab IV komprehensif: implementasi MongoDB/KB, alur proses chatbot (dengan cuplikan kode), integrasi widget Resmeku, screenshot 9 halaman UI, hasil Blackbox 100%, UAT 86%, uji non-fungsional, dan pembahasan metodologi. Ini **bab terkuat** secara teknis.

**Nilai substansi:** 8,5/10  
**Nilai format & konsistensi:** 6/10

---

## 4.1 Penerapan Data Sistem

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Tabel 4.1 schema `knowledges` detail | — |
| OK | 15/15 dokumen KB terimplementasi (Tabel 4.2) | — |
| Sedang | *"identitias"* → **identitas** | §4.1 opening |

---

## 4.2 Implementasi Proses dan Logika Sistem

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Alur widget → REST → KB filter → prompt → Qwen API → tampil | — |
| Sedang | Pencarian KB = **filter MongoDB** (orgId, chatbotId), bukan semantic retrieval | Jujur di teks: *"pencarian berbasis filter dokumen aktif, bukan embedding"* — hindari istilah RAG jika tidak dipakai |
| Sedang | *"dikirimkan kelayanan API AI"* → **ke layanan** | §4.2.4 |
| Sedang | *"direspons"* → **diproses** / **ditangani** | §4.2.6 — bahasa Indonesia baku |
| Sedang | Hal. 66 (§4.2.2–4.2.3): konsistensi **titik/koma** dalam enumerasi | Catatan Bu Masna — cek daftar atribut (*"nama dan alamat email jika tersedia"*) |

### Cuplikan kode (Gambar 4.4–4.6)

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | Syntax highlight tidak seragam (JSON vs plain) | Opsional: format monospace konsisten |
| OK | Model `qwen3.5-flash`, max_tokens, top_p didokumentasikan | — |

---

## 4.3 Integrasi Widget Resmeku

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | 3 tahap: konfigurasi → kode skrip → embed `<head>` | — |
| OK | URL `takoni.vercel.app/.../widget.js` — bukti integrasi nyata | — |

### §4.3.4 & Hal. 71 — Catatan Penguji I

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | **Gambar 4.10** kecil, ada label merah *"Widget Chatbot"* + panah manual | Ganti screenshot resolusi lebih besar; hilangkan anotasi merah (tidak standar skripsi) |
| **Wajib** | Teks §4.3.4 **terpotong**: caption Gambar 4.10 di hal. 71, penjelasan lanjutan di hal. 72 | Satukan gambar + paragraf penjelas dalam **satu halaman** |
| Sedang | §4.3.3 & 4.3.4 — dua blok kode HTML berurutan (Gambar 4.8 & 4.9) mirip | OK; pastikan spacing antar gambar cukup |

---

## 4.4 Penerapan Antarmuka Pengguna — **Temuan Kritis**

### Rujukan gambar salah

| Subbab | Teks merujuk | Caption benar | Status |
|--------|--------------|---------------|--------|
| 4.4.4 Manajemen Organisasi | Gambar **4.11** | Gambar **4.14** | **SALAH** |
| 4.4.5 Pemilihan Chatbot | Gambar **4.12** | Gambar **4.15** | **SALAH** |
| 4.4.6 Dashboard Chatbot | Gambar **4.13** | Gambar **4.16** | **SALAH** |

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Offset −3 pada tiga subbab di atas | Koreksi semua rujukan teks |
| Sedang | *"dashbord"* → **dashboard** | §4.4.6 |
| Sedang | §4.4.1–4.4.3 rujukan gambar **benar** (4.11–4.13) | — |
| OK | Screenshot UI modern, konsisten desain | — |

---

## 4.5 Hasil Pengujian Sistem

### 4.5.1 Blackbox

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | 10/10 Berhasil — selaras Tabel 3.5 | — |

### 4.5.2 UAT

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | Skenario 1: Tabel 4.4 hitung **92,6%**, Tabel 4.5 tulis **93%** | Bukan error hitung — pembulatan. Pilih satu format (92,6% atau 93%) di seluruh naskah, atau tambah catatan *"dibulatkan"* |
| OK | Rata-rata 86% = Sangat Sesuai | — |
| OK | Analisis skenario terendah (#7 75%, #10 77%) — jujur | — |
| Sedang | Aspek akurasi terendah (4,02) — sudah dibahas §4.6.3 | — |

### 4.5.3 Pengujian Non-Fungsional

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Rata-rata respons **2,03 detik** < 3 detik | — |
| OK | Kompatibilitas MacBook, Android, iPhone — Tabel 4.8 | — |
| Sedang | *"Kompatilbitas"* → **Kompatibilitas** | Judul tabel |
| **Wajib** | Kontradiksi dengan batasan §1.3 | Lihat `bab-i.md` — selaraskan |

---

## 4.6 Pembahasan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | §4.6.1 evaluasi Waterfall jujur (kendala kategori KB) | — |
| OK | §4.6.2 integrasi embed script — portabilitas | — |
| OK | §4.6.3 akurasi vs relevansi/efektivitas — analisis kritis | — |
| Sedang | Efektivitas rata-rata: teks §4.5.2 sebut **4,37**, §4.6.3 sebut **4,37** — konsisten ✓ | — |

---

## Kesimpulan Bab IV

Ini bab yang **paling banyak pekerjaan revisi format**:

1. Betulkan rujukan Gambar 4.14–4.16  
2. Rapikan hal. 71 (Gambar 4.10)  
3. Selaraskan angka UAT & batasan performa  
4. Proofread hal. 66 (titik/koma)

Substansi implementasi **tidak perlu diubah**.
