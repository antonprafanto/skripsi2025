# Audit — Daftar Pustaka & Lampiran

**Halaman PDF:** 33–35 (hlm dokumen 24–26)  
**Status:** Ada 22 entri — **tidak lengkap terhadap sitasi Bab II**

---

## Ringkasan

Daftar Pustaka yang ada berkualitas relatif baik (banyak DOI/arXiv resmi: Lewis, Brown, Vaswani, Radford, Gao, UNESCO, dll.). Masalahnya bukan “referensi jelek”, melainkan **ketidaklengkapan** terhadap karya yang sudah dibahas di teks.

---

## Entri yang sudah ada (22) — catatan singkat

| No | Entri | Catatan audit |
|----|-------|---------------|
| 1 | Adamopoulou & Moussiades (2020) | OK |
| 2 | Afandi (2025) | OK; jurnal relatif baru — simpan PDF |
| 3 | Atzori et al. (2010) | OK |
| 4 | Babiuch et al. (2019) | OK |
| 5 | Brown et al. (2020) | OK |
| 6 | Chuang et al. (2024) | OK |
| 7 | Espressif ESP32-S3 datasheet | OK untuk teknis hardware |
| 8 | Gao et al. (2023) RAG survey | OK |
| 9 | Hoy (2018) | OK |
| 10 | Johnson et al. (2021) | OK (FAISS); related ke vector search |
| 11 | Kuhail et al. (2023) | OK |
| 12 | Kuleto et al. (2021) | OK |
| 13 | Lewis et al. (2020) | OK — paper fondasi RAG |
| 14 | Pérez et al. (2020) | OK |
| 15 | Petrovych et al. (2026) | **Terverifikasi** ICAIIT 2026 DOI `10.25673/123941` — tetap simpan PDF |
| 16 | Radford et al. (2023) Whisper | OK |
| 17 | Reimers & Gurevych (2019) | OK |
| 18 | Susilo et al. (2026) | **Terverifikasi** JITP 13(1) 2026 DOI `10.21831/jitp.v13i1.83632` — tetap simpan PDF |
| 19 | Tan et al. (2021) TTS survey | OK |
| 20 | UNESCO (2023) | OK |
| 21 | Vaswani et al. (2017) | OK |
| 22 | Zawacki-Richter et al. (2019) | OK |

---

## Entri yang WAJIB ditambahkan (disebut di Bab II, absen di DP)

Lengkapi metadata resmi (penulis, tahun, judul, venue, DOI/URL). Di bawah ini **nama karya sesuai teks proposal** — mahasiswa wajib cari bibliografi pasti:

1. **Neupane et al. (2024)** — BARKPLUG V.2 / campus RAG / RAGAS (Mississippi State University)
2. **Afzal et al. (2024)** — RAG optimization + RAG Confusion Matrix (technical university in Germany)
3. **Hartono et al. (2025)** — RAG vs fine-tuning Gemma2 untuk chatbot kampus (skor RAGAS 0,72)
4. **Alan et al. (2024)** — MufassirQAS
5. **Dan et al. (2023)** — EduChat
6. **Pratama & Amrullah (2024)** — fine-tune Whisper untuk bahasa Jawa / low-resource
7. **Adila et al. (2024)** — evaluasi MMS & Whisper untuk bahasa Indonesia

Jika salah satu paper **tidak ditemukan** setelah pencarian sungguh-sungguh: **hapus dari Bab II**, jangan biarkan sitasi menggantung.

---

## Kemungkinan referensi teknis yang baik ditambahkan (opsional tapi berguna)

| Topik | Mengapa |
|-------|---------|
| Dokumentasi OpenAI Embeddings / Chat Completions | Menopang pilihan text-embedding-3-small & GPT |
| Paper/dokumen RAGAS (Es et al., atau dokumen resmi) | Karena kamu mengutip evaluasi bergaya RAGAS |
| Edge TTS / implementasinya | Klaim TTS Indonesia |
| WebSocket / desain edge-cloud | Arsitektur ESP32 |

---

## Aturan sitasi yang harus ditegakkan

1. Setiap `(Nama, Tahun)` di Bab I–III → ada di DP  
2. Setiap entri DP → dipakai minimal 1× di teks (hindari “pajangan”)  
3. Format seragam (APA) — titik pada `et al.`, nama jurnal miring sesuai panduan prodi  
4. Simpan PDF semua referensi di folder lokal sebelum sidang  

---

## Lampiran yang sebaiknya disiapkan (proposal / skripsi)

Untuk **revisi proposal** (disarankan):
- Lampiran A: daftar dokumen KB (judul, sumber, tanggal)
- Lampiran B: contoh 20 item dataset uji (pertanyaan + jawaban acuan + dokumen sumber)
- Lampiran C: diagram arsitektur
- Lampiran D: system prompt

Untuk **skripsi lengkap** nanti:
- Screenshot/log retrieve
- Skema rangkaian / foto hardware
- Tabel lengkap uji
- (Opsional) cuplikan kode penting — bukan full dump tanpa arahan

---

## Checklist
```
[ ] Tambah 7 referensi wajib di atas (metadata lengkap)
[ ] Simpan PDF Susilo 2026 & Petrovych 2026 (sudah terverifikasi DOI-nya)
[ ] Cek silang semua sitasi teks ↔ DP
[ ] Siapkan folder PDF referensi
[ ] Hapus sitasi yang tidak bisa diverifikasi
```

**Estimasi:** 1–2 hari fokus bibliografi.
