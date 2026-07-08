# Template Tabel 2.1 — Penelitian Terdahulu (isi oleh Rillo)

Ganti ringkasan bernomor panjang di subbab 2.1 dengan tabel seperti ini. Setelah tabel, tulis 1–2 paragraf **Kesenjangan Penelitian** (sudah ada draft-nya — padatkan).

---

## Tabel 2.1 Penelitian Terdahulu

| No | Peneliti (Tahun) | Objek / Domain | Metode / Teknologi | Hasil kunci | Keterbatasan | Perbedaan dengan penelitian ini |
|----|------------------|----------------|--------------------|-------------|--------------|----------------------------------|
| 1 | Susilo et al. (2026) | Layanan akademik (UT) | RAG + LLM (teks/web) | Akurasi ~92%; respons ~5 dtk | Belum voice; kesulitan slang | Penelitian ini menambah **voice + ESP32** |
| 2 | Afandi (2025) | Layanan akademik | Dialogflow + Telegram | Respons otomatis; preferensi user ~70% | Bukan LLM/RAG modern; lemah pada typo | Penelitian ini memakai **GPT + RAG** |
| 3 | Petrovych et al. (2026) | Tutor belajar (STEM) | ESP32 + STT + LLM + TTS | Latensi ~0,5–1 dtk | Fokus **pembelajaran**, bukan admin akademik; tanpa RAG KB institusi; Bahasa Inggris | Penelitian ini: **layanan akademik + RAG KB lokal + Bahasa Indonesia** |
| 4 | Neupane et al. (2024) | Info kampus (MSU) | RAG + RAGAS (teks) | Arsitektur retriever–generator | Teks only; bukan embedded voice | + **antarmuka suara ESP32** |
| 5 | Afzal et al. (2024) | Data akademik univ. teknik | Optimasi RAG (Multi-Query dll.) | Multi-Query meningkatkan performa | Teks only | Penelitian ini fokus **integrasi sistem voice-edge**, bukan hanya tuning retriever |
| 6 | Hartono et al. (2025) | Chatbot kampus | RAG vs fine-tune (Gemma2) | RAG unggul overall RAGAS 0,72 | Teks; bukan IoT voice | + **STT/TTS + ESP32** |
| 7 | Alan et al. (2024) | Domain keagamaan | RAG + vector DB | Turunkan hallucination; sertakan sumber | Bukan akademik kampus/voice | Ambil pelajaran **grounding + sitasi sumber** untuk KB akademik |
| 8 | Dan et al. (2023) | EduChat | Pretrain + fine-tune korpus pendidikan | Fitur edukasi luas | Mahal train ulang; update pengetahuan kurang fleksibel | Penelitian ini pilih **RAG** agar update dokumen murah |
| 9 | Pratama & Amrullah (2024) | ASR Jawa | Fine-tune Whisper PEFT | WER 13,77% vs 89,40% | Hanya komponen STT | Penelitian ini **mengintegrasikan STT** ke layanan akademik utuh |
| 10 | Adila et al. (2024) | ASR Indonesia | Evaluasi MMS vs Whisper | Acuan pilih model STT ID | Hanya evaluasi ASR | STT sebagai **modul** dalam sistem lengkap |

> **Catatan:** Kolom “Hasil kunci” harus kamu sesuaikan ulang setelah membaca paper aslinya — jangan menyalin angka jika belum verifikasi.

---

## Paragraf kesenjangan (contoh revisi singkat)

> Ringkasan penelitian terkait menunjukkan dua jalur yang masih terpisah. Jalur pertama mengembangkan chatbot akademik berbasis teks dengan RAG dan evaluasi kuantitatif, namun belum menghadirkan antarmuka suara maupun perangkat tepi. Jalur kedua menghadirkan tutor suara berbasis ESP32 dan LLM, namun berorientasi pada pembelajaran adaptif tanpa grounding dokumen layanan akademik institusional melalui RAG. Selain itu, kajian pengenalan ucapan berbahasa Indonesia umumnya berhenti pada evaluasi komponen STT. Oleh karena itu, penelitian ini menempatkan kontribusinya pada integrasi antarmuka suara berbasis ESP32 dengan pipeline RAG dan model GPT untuk layanan informasi akademik berbahasa Indonesia pada studi kasus Program Studi Informatika Universitas Mulawarman.

---

## Checklist setelah mengisi tabel
```
[ ] Setiap baris punya entri lengkap di Daftar Pustaka
[ ] Angka hasil sudah dicek dari paper PDF
[ ] Paragraf kesenjangan tidak mengklaim “belum ada sama sekali di dunia”
[ ] Kebaruan terfokus: voice + ESP32 + RAG KB akademik ID
```
