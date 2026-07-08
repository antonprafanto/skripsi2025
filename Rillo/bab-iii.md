# Audit — BAB III: Metodologi Penelitian

**Halaman PDF:** ~28–32 (hlm dokumen 19–23)  
**Status:** Arah benar — evaluasi & artefak desain perlu dikuatkan

**Nilai kelengkapan alur:** 7/10  
**Nilai ketahanan desain eksperimen:** 5/10

---

## Ringkasan Bab

Tahapan penelitian (studi literatur → data → rancang → implementasi → uji → laporan) masuk akal. Alur query 8 langkah di 3.4 **sangat membantu** dan sudah setingkat proposal yang baik. Kelemahan: belum ada gambar, metrik jawaban generatif masih naif, dan kebijakan fallback “jawaban umum GPT” belum dikendalikan.

---

## 3.1 Tahapan Pelaksanaan Penelitian

### Yang Sudah Baik
- Urutan logis end-to-end termasuk firmware ESP32 + server VAD/STT/TTS + layanan RAG

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Tidak menyebut model proses (prototyping / waterfall / iterative) | Sebut singkat: **pengembangan prototipe iteratif** (cocok dengan perangkat + tuning RAG) |
| Disarankan | Tidak ada estimasi waktu per tahap (meski 3.7 bilang 6 bulan) | Tabel Gantt sederhana |

---

## 3.2 Pengumpulan Data

### Yang Sudah Baik
- Studi dokumentasi KB: kalender, prodi/dosen, KRS, cuti, skripsi
- Penyusunan **data uji** (Q–A acuan) — ini krusial

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Belum ada **jumlah target** soal uji | Targetkan mis. 50–100 pertanyaan, kategori: faktual, prosedural, parafrase, out-of-scope, adversarial |
| **Wajib** | Sumber dokumen institusi belum resmi disebutkan | Lampirkan daftar dokumen + versi/tanggal |
| Disarankan | Belum ada wawancara kebutuhan pengguna | Minimal 1 sesi dengan admin akademik / 5 mahasiswa untuk requirement |
| Disarankan | Etika: dokumen internal kampus | Izin penggunaan dokumen + anonymisasi jika perlu |

---

## 3.3 Perancangan Data

### Yang Sudah Baik
- Chunking + overlap, embedding OpenAI, Chroma + metadata sumber — praktik RAG yang benar
- Re-index saat update dokumen — selaras batasan Bab I

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Ukuran chunk/overlap + top-k **belum ditentukan** | Tetapkan provisional: mis. chunk 500–800 token, overlap 10–20%, top-k = 3–5 (boleh di-tune di Bab IV) |
| Disarankan | Belum ada skema metadata | Judul dokumen, jenis, tanggal versi, halaman/chunk_id |

---

## 3.4 Perancangan Proses/Algoritma

### Yang Sudah Baik
Alur: wake/tombol → audio WebSocket → VAD → Whisper STT → embed → retrieve top-k → prompt+GPT → bersihkan → TTS → speaker.

Keputusan produk penting di akhir:
- luar KB → jawaban pengetahuan umum
- data akademik tidak ada → jawab jujur “belum tersedia”

### Temuan kritis — konsistensi anti-hallucination

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Fallback “pengetahuan umum” **bertabrakan** dengan narasi anti-hallucination data kampus | Buat **router intent**: (A) akademik → wajib RAG + tolak jika retrieval lemah; (B) general → opsional; (C) refuse. Evaluasi skripsi fokus pada (A) |
| **Wajib** | Web search (dari chat WA) belum ada di sini | Masukkan sebagai modul di luar scope **atau** sub-pipeline terpisah dengan batasan ketat |
| **Wajib** | Tidak ada diagram | Gambar 3.1 Arsitektur sistem + Gambar 3.2 Activity/sequence query |
| Disarankan | Prompt template belum dilampirkan | Lampirkan system prompt: “jawab hanya dari konteks; jika tidak ada bilang tidak tahu; sebut sumber” |

---

## 3.5 Perancangan Tampilan

### Yang Sudah Baik
- Voice-first + OLED status + tombol + feedback audio untuk low-vision — konsisten dengan klaim aksesibilitas

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Belum ada mock status layar (idle / listening / processing / speaking) | Wireframe sederhana 4 state |
| Opsional | Aksesibilitas diklaim tanpa protokol uji | 1 sesi uji dengan pengguna berkacamata hitam / mata tertutup = bukti minimal |

---

## 3.6 Perancangan Pengujian — inti yang harus diperkuat

### Yang sudah ada
1. Black-box fungsional  
2. Akurasi jawaban (% benar)  
3. Relevansi retrieval  
4. Waktu respons  
5. Variasi parafrase  
6. Uji update KB (Kaprodi) — **sangat bagus**, jangan dihapus  

### Temuan

| Prioritas | Temuan | Kenapa | Perbaikan konkret |
|-----------|--------|--------|-------------------|
| **Wajib** | “Akurasi = % jawaban benar” untuk teks generatif | Dua jawaban bisa sama-sama benar dengan wording berbeda; atau benar-salah abu-abu | Gunakan: (1) **groundedness** terhadap sumber, (2) rubrik 1–5, (3) opsional RAGAS faithfulness/answer relevancy |
| **Wajib** | Relevansi retrieval belum punya rumus | Tidak reproducible | Precision@k / Recall@k / Hit@k pada chunk yang diannotasi |
| **Wajib** | Belum ada **baseline** | Tidak bisa klaim RAG berguna | Bandingkan: GPT tanpa konteks vs GPT+RAG pada set soal yang sama |
| **Wajib** | Ambang keberhasilan belum ada | Tidak tahu lulus/tidak | Mis. groundedness rata-rata ≥ 4/5; Hit@3 ≥ 0.8; latensi median ≤ X detik |
| Disarankan | Black-box belum berwujud tabel kasus uji | Buat minimal 20 test case device-to-answer | |
| Disarankan | Uji lingkungan suara (noise) | Realistis kampus | 2 kondisi: sunyi & berisik ringan |
| Disarankan | Uji biaya/latensi API | Keberlanjutan | Catat token usage per query |
| **Wajib** | Tidak ada **UAT / task success** pengguna | Klaim manfaat di Bab I tidak punya jalur bukti | Likert 10–20 orang ATAU 5 skenario tugas (berhasil/gagal + waktu) |
| **Wajib** | Aktivasi “wake word atau tombol” tanpa desain wake word | Fitur menggantung | Untuk S1: **push-to-talk saja**; wake word opsional di saran |
| **Wajib** | Bahasa/framework **server** belum dipilih | Sulit estimasi kerja & reproduksi | Tetapkan provisional (mis. Python FastAPI) |
| **Wajib** | Versi model GPT & parameter generasi belum dikunci | Eksperimen tidak reproducible | Sebut model (mis. gpt-4o-mini), temperature, max tokens, top-k |
| Disarankan | TTS memakai **Microsoft Edge TTS** (sering tidak resmi untuk produksi) | Risiko ToS / bisa putus | Catat sebagai pilihan prototipe; siapkan fallback resmi jika diminta |
| Disarankan | Kit KS5026 sudah bundel mic/amp/OLED | Jangan jual sebagai “rancang hardware dari nol” | Dokumentasikan sebagai platform perangkat; kontribusi di firmware client + server RAG |

### Desain eksperimen minimal yang disarankan untuk Sidang Proposal

| Eksperimen | Input | Ukuran | Output yang dilaporkan |
|------------|-------|--------|------------------------|
| E1 Retrieval | 50 pertanyaan + chunk emas | Hit@k, Precision@k | Tabel + rata-rata |
| E2 Jawaban | 50 pertanyaan | Skor rubrik 2 penilai (atau RAGAS) | RAG vs no-RAG |
| E3 Latensi | 30 query | Detik end-to-end | mean/median/p95 |
| E4 Update KB | 5 fakta yang diubah | Jawaban sebelum/sesudah re-index | Lulus/gagal |
| E5 Fungsional HW | Checklist jalur suara | Pass/fail | Tabel black-box |
| E6 UAT ringan | 10–20 mahasiswa/staf | Likert / task success | Rata-rata skor + temuan kualitatif |

---

## 3.7 Waktu dan Tempat

- Lokasi: Prodi Informatika FT UNMUL — **bagus** (berbeda dengan kasus mitra jauh)
- Durasi 6 bulan 2026 — wajar

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Breakdown bulan tidak ada | Tambah jadwal 6 baris sesuai 3.1 |

---

## Checklist Revisi Bab III
```
[ ] Gambar arsitektur + alur indexing/query
[ ] Parameter chunk/overlap/top-k (provisional)
[ ] Kebijakan routing RAG vs general vs refuse (+ web search jika ada)
[ ] Ganti metrik akurasi biner → groundedness/rubrik/RAGAS
[ ] Baseline tanpa RAG
[ ] Target jumlah & kategori soal uji
[ ] Ambang keberhasilan provisional
[ ] System prompt di lampiran
[ ] Daftar dokumen KB + izin penggunaan
[ ] Tetapkan stack server + versi model GPT + parameter
[ ] Putuskan tombol vs wake word (disarankan tombol)
[ ] Tambah rencana UAT / task success
[ ] Paragraf etika: audio, dokumen, API key, retensi log
[ ] Batasan single-user / semi-terkontrol
[ ] Sebut model proses: prototipe iteratif
[ ] Justifikasi kit KS5026 + batasan Edge TTS
```
**Estimasi:** 4–6 hari (termasuk gambar & desain soal uji).
