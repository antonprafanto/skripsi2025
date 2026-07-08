# Panduan Revisi Proposal — untuk Muhammad Rillo Pambudi

Halo Rillo. Draft kamu **sudah di jalur yang benar** — lebih lengkap dari tipikal proposal awal. Yang diminta pembimbing sekarang bukan “ganti topik”, melainkan **rapikan agar lolos sidang proposal dan mudah diuji di Bab IV**.

---

## 1. Verdict singkat

| Pertanyaan | Jawaban |
|------------|---------|
| Topik layak skripsi Informatika? | **Ya** |
| Proposal siap sidang hari ini? | **Belum — revisi 1–2 minggu** |
| Boleh lanjut bangun hardware/software? | **Ya**, paralel dengan perbaikan proposal |

---

## 2. Apa yang sudah kamu lakukan dengan baik

- Alasan pakai **RAG** (akurasi lokal, update dokumen, tanpa retrain) sudah jelas — pertahankan di proposal.
- Peran **ESP32 sebagai edge interface** (bukan menjalankan GPT offline) sudah jujur secara teknis.
- Ada **10 penelitian terkait** + paragraf kebaruan (voice + ESP32 + RAG akademik).
- Teori pendukung (LLM, RAG, embedding, STT/TTS, ESP32, VUI) cukup untuk S1.
- Stack teknis spesifik: Whisper/OpenAI STT, Chroma, text-embedding-3-small, GPT API, Edge TTS, WebSocket, INMP441, MAX98357A.

---

## 3. Lima pekerjaan wajib sebelum sidang proposal

### Wajib 1 — Lengkapi Daftar Pustaka
Di Bab II kamu membahas Neupane, Afzal, Hartono, Alan, Dan, Pratama & Amrullah, Adila, dll.  
**Sebagian besar belum ada di Daftar Pustaka (hanya 22 entri).**  
Aturan: setiap nama+(tahun) di teks **wajib** ada di DP.

### Wajib 2 — Pecah rumusan masalah
Sekarang rumusanmu **satu kalimat panjang**. Ubah menjadi 3–4 pertanyaan yang masing-masing punya cara uji di Bab III.

Contoh arah:

1. Bagaimana merancang arsitektur chatbot suara (ESP32 + STT + RAG + GPT + TTS) untuk layanan akademik Prodi Informatika UNMUL?
2. Sejauh mana kualitas *retrieval* dokumen relevan terhadap pertanyaan uji (precision/recall atau hit@k)?
3. Sejauh mana kualitas jawaban (faithfulness / relevansi / skor rubrik manusia) dibanding baseline tanpa RAG?
4. Berapa latensi end-to-end (ujung ucapan → mulai audio jawaban)?

### Wajib 3 — Perbaiki cara ukur “akurasi”
Jawaban LLM jarang dinilai benar/salah biner. Pakai salah satu:
- **Rubrik manusia** (1–5) oleh 2–3 penilai + contoh skor
- **RAGAS** / metrik sejenis (sesuai Neupane/Hartono yang kamu sitir)
- Minimal: ketepatan fakta terhadap dokumen sumber (groundedness) + relevansi

### Wajib 4 — Selaraskan dengan prototipe kamu
Di chat kamu bilang sistem sudah:
- jawab info akademik (RAG)
- jawab pengetahuan umum (GPT)
- **web search** harga/berita
- anti-hallucination data kampus via RAG

**Tulis di proposal:** mode mana yang masuk ruang lingkup skripsi.  
Saran pembimbing tipikal: skripsi fokus **mode akademik RAG**; mode umum/web search boleh ada tapi **dibatasi** dan diuji terpisah (atau dikeluarkan).

### Wajib 5 — Tambah gambar arsitektur + tegaskan kontribusi di atas kit
Satu diagram di Bab III menghemat banyak pertanyaan penguji.  
Kit KS5026 (Xiao Zhi) sah dipakai, tetapi tulis jelas: skripsi ini **bukan** tutorial rakitan chatbot generik — kontribusinya RAG KB akademik + evaluasi.

### Wajib 6 — Abstrak + privasi + spek chip yang benar
- Tulis **Abstrak** (saat ini belum ada sama sekali).
- Seragamkan hardware ke **ESP32-S3 / kit KS5026**; hapus spek LX6 di Latar Belakang.
- Tambah batasan etika: rekaman suara, dokumen kampus, data ke API OpenAI.

### Wajib 7 — Kunci detail implementasi yang masih mengambang
- Stack server (mis. Python FastAPI) + model proses (**prototipe iteratif**)
- Versi model GPT + parameter
- **Tombol** push-to-talk (lebih aman daripada wake word yang belum didesain)
- Rencana UAT singkat agar klaim manfaat punya bukti
- Catat Edge TTS sebagai pilihan prototipe (bukan layanan resmi produksi)

---

## 4. Tentang judul

Judul sekarang mudah dibaca seolah GPT berjalan *di dalam* ESP32.

Opsi penyesuaian (diskusikan dengan pembimbing):

> Implementasi Chatbot Layanan Akademik Berbasis Interaksi Suara dengan ESP32, GPT, dan Retrieval-Augmented Generation (RAG)

atau

> Rancang Bangun Asisten Suara Layanan Akademik Berbasis ESP32 dengan Pipeline RAG dan Model GPT

Intinya: ESP32 = perangkat antarmuka; GPT+RAG = sisi server.

---

## 5. Bukti masalah lokal (jangan ditunda)

Tambahkan di Latar Belakang 1 paragraf tentang konteks **UNMUL / Prodi Informatika**, misalnya:
- dokumen resmi yang jadi KB (panduan akademik, SOP KRS, daftar dosen)
- observasi singkat: pertanyaan berulang ke admin/dosen wali
- kenapa perangkat fisik di ruang prodi/lab dianggap berguna (hands-free, antrian counter)

Tidak perlu survei besar untuk proposal — cukup **bukti minimal yang kredibel**.

---

## 6. Checklist 14 hari

### Hari 1–3
- [ ] Kumpulkan PDF semua paper yang kamu sebut di 2.1
- [ ] Update Daftar Pustaka
- [ ] Buat Tabel 2.1
- [ ] Tulis Abstrak; perbaiki spek ESP32-S3

### Hari 4–7
- [ ] Revisi rumusan masalah + tujuan + kontribusi agar selaras
- [ ] Tulis kebijakan mode: RAG / general / “tidak tahu” (/ web search jika dipakai)
- [ ] Diagram arsitektur + alur indexing
- [ ] Paragraf etika & privasi data

### Hari 8–14
- [ ] Perbaiki desain pengujian (metrik + jumlah soal uji + baseline + UAT ringan)
- [ ] Kunci stack server, versi GPT, tombol vs wake word
- [ ] Rapikan Kata Pengantar & daftar singkatan
- [ ] Kirim ke pembimbing; siapkan demo singkat prototipe

---

## 7. Yang tidak perlu kamu lakukan sekarang

- Tidak perlu ganti topik.
- Tidak perlu menulis Bab IV penuh sebelum Sidang Proposal (kecuali diminta).
- Tidak perlu fine-tune LLM sendiri (sudah tepat dibatasi).

Kerja keras kamu di RAG + perangkat sudah jadi modal. Sekarang rapikan agar **dapat diuji dan dapat dipertanggungjawabkan secara ilmiah**.
