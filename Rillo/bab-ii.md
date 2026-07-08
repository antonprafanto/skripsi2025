# Audit — BAB II: Tinjauan Pustaka

**Halaman PDF:** ~18–27 (hlm dokumen 9–18)  
**Status:** Konten kuat — **cacat administrasi sitasi kritis**

**Nilai substansi:** 8/10  
**Nilai ketelitian sitasi:** 4/10

---

## Ringkasan Bab

Bab II adalah **salah satu bagian terbaik** proposal ini: 10 penelitian terkait + paragraf “Perbedaan dengan Penelitian Sebelumnya” yang mampu mengartikulasikan kebaruan (voice + ESP32 + RAG akademik vs text-only RAG atau ESP32 tutor tanpa RAG). Teori pendukung singkat tapi cukup untuk S1.

Masalah utamanya: **banyak karya yang dibahas tidak muncul di Daftar Pustaka.**

---

## 2.1 Penelitian Terkait

### Yang Sudah Baik
- Mix lokal + internasional
- Ada pembanding metode: RAG, Dialogflow, ESP32+LLM tutor, RAGAS, optimasi retriever, fine-tune vs RAG, STT Indonesia
- Narasi kesenjangan jelas di akhir

### Inventarisasi: apakah ada di Daftar Pustaka?

| # | Karya (sebagaimana di teks) | Ada di DP? | Catatan |
|---|----------------------------|------------|---------|
| 1 | Susilo et al., 2026 | Ya (#18) | Verifikasi status jurnal 2026 |
| 2 | Afandi, 2025 | Ya (#2) | OK |
| 3 | Petrovych et al., 2026 | Ya (#15) | Verifikasi proceeding/DOI |
| 4 | Neupane et al., 2024 (BARKPLUG V.2) | **Tidak** | **Wajib tambah** |
| 5 | Afzal et al., 2024 | **Tidak** | **Wajib tambah** |
| 6 | Hartono et al., 2025 | **Tidak** | **Wajib tambah** |
| 7 | Alan et al., 2024 (MufassirQAS) | **Tidak** | **Wajib tambah** |
| 8 | Dan et al., 2023 (EduChat) | **Tidak** | **Wajib tambah** |
| 9 | Pratama & Amrullah, 2024 | **Tidak** | **Wajib tambah** |
| 10 | Adila et al., 2024 | **Tidak** | **Wajib tambah** |

**Ini temuan #1 audit keseluruhan.** Penguji yang teliti bisa menjatuhkan kredibilitas proposal hanya dari tabel ini.

### Temuan lain 2.1

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Format daftar 1–10 panjang & sulit dibandingkan | Ubah ke **Tabel 2.1** (lihat `template-penelitian-terdahulu.md`) |
| **Wajib** | Typo: “Dari perbandingan **tersbut**” | “tersebut” |
| Disarankan | Susilo/Petrovych bertahun **2026** — sempat dicurigai di audit awal | **Sudah terverifikasi** DOI-nya; simpan PDF, jangan dihapus hanya karena tahun 2026 |
| Disarankan | Beberapa ringkasan terkait terlalu panjang (hampir seperti abstrak) | Padatkan: metode, objek, hasil kunci, keterbatasan, beda dengan penelitian ini |

---

## 2.2 Teori Pendukung

### Yang Sudah Baik
| Subbab | Penilaian |
|--------|-----------|
| 2.2.1 Chatbot | Cukup, sitasi Adamopoulou & Pérez/Kuhail |
| 2.2.2 LLM & GPT | Transformer + Brown + batasan hallucination |
| 2.2.3 RAG | Lewis + Gao; tiga tahap indexing–retrieval–generation |
| 2.2.4 Embedding & Vector DB | Sentence-BERT + similarity search; sebut Chroma & text-embedding-3-small |
| 2.2.5 STT | Whisper + OpenAI transcription — konsisten |
| 2.2.6 TTS | Edge TTS id-ID — spesifik |
| 2.2.7 IoT & ESP32 | Jujur: ESP32-S3 + INMP441 + MAX98357A + WebSocket |
| 2.2.8 VUI | Hoy — cukup |

**Catatan hardware:** KS5026 adalah kit DIY “Xiao Zhi AI Chatbot” (OLED + mic + amp siap). Itu **sah** untuk prototipe S1, tetapi di kontribusi/Bab III harus ditegaskan yang baru adalah **pipeline RAG akademik + evaluasi**, bukan perakitan kit.

### Temuan teori

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Belum ada teori singkat **evaluasi RAG** (faithfulness, context precision, human eval) | Tambah ½–1 halaman — ini menopang Bab III |
| Disarankan | Belum bahas **Voice Activity Detection** padahal dipakai di Bab III | Tambah subbab kecil VAD atau masukkan di STT |
| Disarankan | **Microsoft Edge TTS** bersifat tidak resmi untuk banyak use-case produksi | Di batasan: “TTS Edge untuk prototipe”; siapkan opsi Google/Azure/OpenAI TTS jika diminta penguji |
| Opsional | Johnson et al. 2021 (FAISS/GPU) vs Chroma | Boleh; sebut Chroma sebagai *store* aplikatif |

---

## Kebaruan (Novelty) — Verdict

**Klaim kebaruan cukup masuk akal untuk S1**, *jika* diformulasikan hati-hati:

| Komponen | Sudah banyak diteliti? | Di proposal ini |
|----------|------------------------|-----------------|
| Chatbot akademik teks + RAG | Ya | Digunakan |
| ESP32 + STT/TTS + LLM (tutor) | Ada (Petrovych) | Diadaptasi |
| RAG + voice + ESP32 **untuk layanan akademik institusional (ID)** | Relatif jarang di literatur yang kamu kutip | **Titik kebaruan** |

Jangan klaim “belum pernah ada sama sekali di dunia”. Klaim yang aman:

> Penelitian ini mengintegrasikan antarmuka suara berbasis ESP32 dengan pipeline RAG pada knowledge base akademik berbahasa Indonesia untuk layanan informasi institusional, yang pada penelitian terkait masih terpisah antara sistem RAG berbasis teks dan sistem embedded voice tanpa grounding dokumen lokal.

---

## Checklist Revisi Bab II
```
[ ] Tambah 7+ referensi hilang ke Daftar Pustaka
[ ] Buat Tabel 2.1 + subbab Kesenjangan Penelitian (ringkas)
[ ] Perbaiki typo "tersbut"
[ ] Tambah landasan evaluasi RAG + VAD
[ ] Soften klaim kebaruan sesuai tabel di atas
```

**Estimasi:** 2–4 hari (terutama berburu & memverifikasi PDF referensi).
