# Laporan Audit Draft Proposal Skripsi — RILLO

**Mahasiswa:** Muhammad Rillo Pambudi (NIM 2009106128)  
**Judul:** Implementasi Chatbot AI Berbasis Interaksi Suara Menggunakan Model GPT pada ESP32 untuk Layanan Akademik Menggunakan Metode Retrieval-Augmented Generation (RAG)  
**Program Studi:** Informatika, Fakultas Teknik, Universitas Mulawarman  
**Dokumen:** `PROPOSAL SKRIPSI Muhammad_Rillo_Pambudi.pdf` (35 halaman — Bab I–III + Daftar Pustaka)  
**Tanggal audit:** 8 Juli 2026 (dicek ulang 2×; isi sudah digabung di README ini)  
**Tahap dokumen:** Proposal (siap menuju sidang proposal setelah revisi menengah)  
**Konteks tambahan:** Chat WhatsApp mahasiswa (justifikasi RAG + status prototipe: jawaban akademik RAG, GPT umum, web search)

---

## Untuk Pembimbing — Ringkasan Eksekutif

| Pertanyaan | Jawaban |
|------------|---------|
| Apakah topik **layak** untuk skripsi Informatika? | **Ya.** Kombinasi ESP32 (edge), STT/TTS, GPT API, dan RAG pada domain akademik lokal punya kedalaman teknis yang memadai. |
| Apakah draft **layak sidang proposal** sekarang? | **Hampir.** Lebih matang dari tipikal proposal awal. Perlu revisi **menengah** (bukan tulis ulang total). |
| Bolehkah mahasiswa dilanjutkan? | **Ya.** Arahkan ke: (1) lengkapi sitasi penelitian terkait di Daftar Pustaka, (2) pecah rumusan masalah + metrik evaluasi, (3) selaraskan scope dengan prototipe (web search), (4) Abstrak + etika data + spek chip. |
| Risiko terbesar? | Sitasi Bab II ≠ DP; metrik “akurasi % benar”; judul “GPT pada ESP32”; scope creep web search; Abstrak/privasi hilang; spek LX6 vs ESP32-S3; kit KS5026 (Xiao Zhi) bisa dianggap rakitan siap pakai jika kontribusi tidak ditegaskan. |

**Kesimpulan satu kalimat:** Topik **layak**; draft **boleh dilanjutkan menuju sidang proposal setelah revisi 1–2 minggu**, bukan ditolak.

---

## Untuk Mahasiswa — Baca Ini Dulu

Posisi kamu **jauh lebih maju** dari banyak proposal baru: teori ada, terkait ada, arsitektur cukup jelas, batasan teknis sudah berpikir (ESP32 = antarmuka, bukan menjalankan GPT offline).

Yang belum cukup: **ketelitian akademik** (sitasi hilang di DP), **operasionalisasi evaluasi**, dan **selaraskan apa yang sudah kamu bangun** dengan apa yang ditulis di proposal.

```
1. Masalah layanan akademik + peluang teknis (sudah ada secara umum)
2. Baca & bandingkan penelitian terkait (sudah — 10 karya + kebaruan)
3. Tulis proposal Bab I–III (sudah — perlu rapikan)
4. Setujui pembimbing → sidang proposal  ← kamu di sini
5. Bangun/sempurnakan sistem hardware+software
6. Uji metrik → Bab IV
7. Kesimpulan → sidang akhir
```

---

## Daftar Laporan Per Bab

| File | Isi | Prioritas |
|------|-----|-----------|
| [panduan-mahasiswa.md](panduan-mahasiswa.md) | Panduan perbaikan untuk Rillo | Baca dulu |
| [bagian-awal.md](bagian-awal.md) | Cover, pengesahan, kata pengantar, daftar isi | Sedang |
| [bab-i.md](bab-i.md) | Pendahuluan | Tinggi |
| [bab-ii.md](bab-ii.md) | Tinjauan pustaka + penelitian terkait | **Tinggi (sitasi)** |
| [bab-iii.md](bab-iii.md) | Metodologi & pengujian | Tinggi |
| [bab-iv-v-rencana.md](bab-iv-v-rencana.md) | Apa yang harus ada di Bab IV–V nanti | Sedang |
| [daftar-pustaka-lampiran.md](daftar-pustaka-lampiran.md) | DP & verifikasi referensi | **Prioritas #1** |
| [template-penelitian-terdahulu.md](template-penelitian-terdahulu.md) | Template Tabel 2.1 siap isi | Pakai saat revisi |

*Catatan: ringkasan lengkap untuk pembimbing ada di README ini; detail perbaikan per bab di file di atas.*

---

## Penilaian Singkat

| Aspek | Status | Penjelasan singkat |
|-------|--------|-------------------|
| **Topik penelitian** | Layak | IoT edge + RAG + voice + domain institusional = skripsi Informatika yang solid |
| **Substansi masalah** | Cukup, perlu dikuatkan | Masalah masih generik perguruan tinggi; belum ada data UNMUL/prodi |
| **Tinjauan pustaka** | Baik, cacat teknis | Narasi & kebaruan bagus; **7 karya terkait tidak ada di DP** |
| **Metodologi** | Baik, belum matang evaluasi | Alur sistem jelas; metrik “akurasi % benar” belum cocok untuk jawaban generatif |
| **Implementasi** | Di luar proposal | Dari chat: RAG akademik + GPT umum + web search sudah berjalan — **masukkan ke batasan/metodologi** |
| **Sitasi & referensi** | Perlu perbaikan wajib | Inkonsistensi teks ↔ DP berbahaya di sidang |
| **Kelengkapan dokumen** | Belum lengkap | **Abstrak hilang**; template kata pengantar; daftar istilah/singkatan/gambar kosong |
| **Etika & privasi data** | Belum dibahas | Suara mahasiswa + dokumen kampus ke API pihak ketiga |
| **Siap sidang proposal** | **Hampir** | Estimasi revisi: **1–2 minggu** kerja fokus |

---

## Skor Penilaian

| Dimensi | Skor | Artinya |
|---------|------|---------|
| Substansi masalah | 6/10 | Argumen kuat secara global, bukti lokal lemah |
| Kebaruan (novelty) | 7/10 | Kombinasi voice+ESP32+RAG akademik cukup jelas bedanya |
| Kedalaman teknis Informatika | 7,5/10 | Komponen spesifik; spek LX6 keliru; server stack & wake word menggantung |
| Metodologi | 5,5/10 | Alur ada; kurang UAT, etika data, parameter model terkunci |
| Tinjauan pustaka | 7/10 | Konten kuat, administrasi sitasi bermasalah |
| Penulisan akademik | 7/10 | Rapi; ada typo & template tersisa |
| Kelengkapan dokumen | 5/10 | Abstrak hilang; bagian depan template |
| **Rata-rata** | **≈ 6,4/10** | Layak lanjut — revisi menengah |

*(Bandingkan: proposal tipikal “baru mulai” sering di bawah 4/10. Rillo sudah di jalur yang benar.)*

---

## Temuan Paling Penting (Urutkan Perbaikannya)

| No | Temuan | Mengapa penting? | File |
|----|--------|------------------|------|
| 1 | **Penelitian terkait #4–#10 banyak tidak masuk Daftar Pustaka** (Neupane, Afzal, Hartono, Alan, Dan, Pratama, Adila, dll.) | Penguji anggap sitasi fiktif/asal | `daftar-pustaka-lampiran.md` |
| 2 | **Rumusan masalah satu kalimat majemuk** — sulit diuji | Sidang butuh pertanyaan yang terjawab tiap satu metrik | `bab-i.md` |
| 3 | **Metrik “akurasi = % jawaban benar”** terlalu kasar untuk LLM+RAG | Hasil Bab IV bisa diragukan ilmiahnya | `bab-iii.md` |
| 4 | **Judul: “Model GPT pada ESP32”** mudah disalahartikan | ESP32 hanya edge I/O; AI di server — harus eksplisit di judul/abstrak | `bab-i.md`, `bagian-awal.md` |
| 5 | **Chat: web search + GPT umum** vs proposal batasan KB statis | Scope tidak selaras; risiko hallucination di “mode umum” | `bab-i.md`, `bab-iii.md` |
| 6 | **Belum ada bukti masalah lokal UNMUL** (antrian layanan, FAQ berulang, waktu respons staf) | Latar masih “bisa dipakai kampus mana saja” | `bab-i.md` |
| 7 | **Tujuan ke-2 mirip manfaat**, bukan tujuan ilmiah | Selaraskan tujuan dengan rumusan | `bab-i.md` |
| 8 | **Diagram arsitektur/alur belum ada** di proposal | Bab III berat teks; penguji butuh gambar | `bab-iii.md` |
| 9 | **Ketergantungan OpenAI API + biaya + offline** belum dibahas sebagai keterbatasan | Risiko operasional & keberlanjutan sistem | `bab-i.md`, `bab-iii.md` |
| 10 | **Kata Pengantar & daftar istilah masih template**; **Abstrak tidak ada** | Format proposal belump lengkap | `bagian-awal.md` |
| 11 | **Klaim inklusi disabilitas visual** tanpa rencana uji pengguna / UAT | Soften atau rencanakan uji aksesibilitas + UAT | `bab-i.md`, `bab-iii.md` |
| 12 | **Daftar Isi: 2.2** loncat ke 2.2.1; daftar istilah/gambar kosong | Format baku prodi | `bagian-awal.md`, `bab-ii.md` |
| 13 | **Privasi/keamanan**: suara mahasiswa + dokumen kampus ke API OpenAI belum dibahas | Risiko etika & pertanyaan penguji | `bab-i.md`, `bab-iii.md` |
| 14 | **Spek Latar Belakang = ESP32 LX6 / 520 KB**, perangkat aktual = **ESP32-S3 / kit KS5026** | Copy-paste spek chip salah (KS5026 sendiri konsisten dengan S3) | `bab-i.md` |
| 15 | **Wake word** tanpa desain; **stack server**, **versi GPT**, parameter RAG belum dikunci | Replikasi eksperimen lemah | `bab-iii.md` |
| 16 | **Metode pengembangan sistem tidak disebut** (prototype / waterfall / iteratif) | Bab III hanya daftar tahap generik | `bab-iii.md` |
| 17 | **Kit KS5026 = DIY “Xiao Zhi AI Chatbot”** siap suara | Novelty hardware lemah jika hanya merakit kit; kontribusi harus di **RAG akademik + evaluasi**, bukan rakitan | `bab-i.md`, `bab-iii.md` |
| 18 | **Microsoft Edge TTS** (unofficial) sebagai TTS produksi | Risiko ToS/keberlanjutan; sebut alternatif atau justifikasi prototipe | `bab-iii.md` |

---

## Rencana Kerja 2 Minggu (Saran untuk Rillo)

### Minggu 1 — Rapatkan akademik
- [ ] Masukkan **semua** karya di bagian Penelitian Terkait ke Daftar Pustaka (dengan DOI/URL yang benar)
- [ ] Buat **Tabel 2.1** Penelitian Terdahulu (lihat template)
- [ ] Pecah rumusan masalah jadi 3–4 pertanyaan terukur
- [ ] Tulis 1 paragraf bukti lokal (wawancara staf akademik / observasi FAQ prodi) **atau** batasi klaim ke “studi kasus Prodi Informatika UNMUL berdasarkan dokumen X”
- [ ] Tulis **Abstrak**; rapikan spek **ESP32-S3 / KS5026** (hapus LX6 yang salah)
- [ ] Tambah paragraf **etika & privasi** (rekaman suara, dokumen kampus, API pihak ketiga)

### Minggu 2 — Metodologi & scope
- [ ] Tambah **Gambar arsitektur** (ESP32 ↔ WebSocket ↔ VAD/STT ↔ RAG/Chroma ↔ GPT ↔ TTS)
- [ ] Perbaiki desain pengujian: skor retrieval + skor jawaban (lihat Bab III) — pertimbangkan RAGAS atau rubrik manusia
- [ ] Putuskan: **web search** masuk batasan atau dikeluarkan dari skripsi
- [ ] Kunci **stack server**, **versi model GPT**, parameter RAG; pilih **tombol** vs wake word (disarankan tombol)
- [ ] Tambah rencana **UAT/task success** singkat + lampiran 10–20 soal uji
- [ ] Tegaskan kontribusi di atas kit KS5026 (RAG KB UNMUL + evaluasi); sebut Edge TTS sebagai pilihan prototipe
- [ ] Rapikan Kata Pengantar, daftar singkatan (RAG, STT, TTS, VAD, LLM, VUI)
- [ ] Konsultasi ke Pak pembimbing dengan draft revisi

---

## Temuan Lintas Bab

| No | Temuan | File terkait |
|----|--------|--------------|
| 1 | Karya terkait disitasi di Bab II tetapi absen di DP | `bab-ii`, `daftar-pustaka` |
| 2 | “Aksesibilitas & responsivitas” di rumusan belum punya indikator | `bab-i`, `bab-iii` |
| 3 | Mode fallback “pengetahuan umum GPT” bertentangan dengan anti-hallucination | `bab-i`, `bab-iii` |
| 4 | Prototipe (chat WA) lebih luas dari proposal tertulis | seluruh bab + batasan |
| 5 | Susilo & Petrovych (2026) **DOI terverifikasi**; tetap simpan PDF | `daftar-pustaka` |
| 6 | Spek LX6 di Bab I vs ESP32-S3 di Bab II | `bab-i`, `bab-ii` |
| 7 | Privasi suara/dokumen vs manfaat “layanan di luar jam kerja” | `bab-i`, `bab-iii` |
| 8 | Tidak ada Abstrak / Daftar Gambar / model proses pengembangan | `bagian-awal`, `bab-iii` |
| 9 | Hardware berbasis kit konsumen (KS5026/Xiao Zhi) vs klaim kebaruan embedded | `bab-i`, `bab-ii`, `bab-iii` |

---

## Catatan dari Chat WhatsApp Mahasiswa

Mahasiswa sudah menjelaskan justifikasi RAG dengan benar:
1. Akurasi jawaban berbasis dokumen lokal  
2. Informasi dinamis (contoh ganti Kaprodi) lewat update dokumen  
3. Maintenance tanpa fine-tune ulang model  

Perbandingan “tanpa RAG vs dengan RAG” **bagus** — seharusnya masuk Bab I atau Bab II sebagai 1 paragraf ilustrasi.

**Yang perlu diwaspadai pembimbing:** mahasiswa juga mengklaim **web search real-time** dan jawaban pengetahuan umum. Itu **bukan inti skripsi RAG akademik** dan bisa melemahkan klaim “tidak mengarang data kampus” jika routing antar-mode tidak ketat. Minta mahasiswa menuliskan **kebijakan routing** di Bab III (kapan RAG / kapan general / kapan web / kapan “tidak tahu”).

---

*Audit ini dibuat agar pembimbing punya verdict cepat, dan mahasiswa punya daftar kerja yang jelas.*
