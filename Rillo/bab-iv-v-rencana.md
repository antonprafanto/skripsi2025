# Rencana BAB IV–V (Belum Ada di Proposal — Untuk Orientasi)

Proposal Rillo berhenti di Bab III. File ini menjelaskan **apa yang harus dihasilkan nanti** agar sidang akhir kuat.

---

## BAB IV — Hasil dan Pembahasan (rencana konten)

### 4.1 Implementasi Perangkat Keras
- Foto rangkaian ESP32-S3 + INMP441 + MAX98357A + OLED + speaker
- Spesifikasi & alasan pemilihan komponen
- Catatan daya, Wi-Fi, penempatan di lab/prodi

### 4.2 Implementasi Perangkat Lunak
- Arsitektur final (boleh beda minor dari proposal — dokumentasikan)
- Pipeline indexing (contoh potongan kode / konfigurasi chunk)
- System prompt & skema metadata
- Firmware WebSocket client (ringkas)

### 4.3 Knowledge Base
- Daftar dokumen + versi
- Statistik: jumlah dokumen, chunk, dimensi embedding
- Contoh retrieve untuk 2–3 query

### 4.4 Hasil Pengujian
Sesuai desain Bab III yang sudah diperbaiki:
- Tabel black-box
- Hasil retrieval (Hit@k)
- Hasil kualitas jawaban RAG vs baseline
- Latensi
- Uji update Kaprodi/dokumen
- (Opsional) uji noise / uji tangan-bebas

### 4.5 Pembahasan
- Apakah kebaruan terbukti secara empiris?
- Di mana sistem gagal (typo, slang mahasiswa, pertanyaan multi-hop)?
- Trade-off biaya API, latensi, ketergantungan cloud
- Perbandingan dengan Susilo/Neupane/Petrovych secara jujur

---

## BAB V — Kesimpulan dan Saran

### 5.1 Kesimpulan
Jawab **setiap** rumusan masalah satu per satu dengan angka/fakta dari Bab IV. Jangan kesimpulan generik.

### 5.2 Saran
Contoh arah yang masuk akal:
- Integrasi read-only ke SIAKAD (di luar skripsi ini)
- Caching / model lokal untuk menekan biaya
- Wake word lebih andal
- Evaluasi pengguna (UAT Likert) skala lebih besar
- CI pipeline re-index otomatis saat dokumen GDrive berubah

---

## Yang Jangan Ditunda Sampai Akhir

1. **Dataset uji** (Q–A) — mulai sekarang bersamaan revisi proposal  
2. **Logging** setiap query (audio path, transcript, retrieved chunks, jawaban, latency) — tanpa ini Bab IV sulit  
3. **Versi dokumen KB** — supaya uji “update Kaprodi” kredibel  

---

## Kesiapan Sidang Akhir (target)

| Kriteria | Target kasar S1 |
|----------|-----------------|
| Demo live | 3–5 pertanyaan sukses + 1 “tidak tahu” + 1 setelah update KB |
| Angka | Retrieval + jawaban + latensi tercatat |
| Reproducibility | Repo + cara index ulang terdokumentasi |
| Batasan jujur | Offline tidak didukung; SIAKAD tidak terhubung; bergantung OpenAI |
