# Rencana BAB IV & V — Belum Ditulis

**Status:** Belum ada di draft  
**Ini normal** untuk tahap proposal — tapi kamu harus **tahu apa yang akan ditulis** nanti

---

## Untuk Mahasiswa — Baca Ini Agar Tidak Kaget Nanti

Bab IV adalah **bab terbesar** skripsi kamu (biasanya 30–50 halaman). Di sinilah kamu membuktikan bahwa kamu benar-benar **membangun sistem**, bukan hanya menulis konsep. Bab V singkat (2–3 halaman) — jawaban dari rumusan masalah.

---

## BAB IV — Hasil dan Pembahasan (Rencana)

### Struktur yang disarankan

```
BAB IV HASIL DAN PEMBAHASAN
  4.1 Hasil Pengumpulan Data
      4.1.1 Hasil Observasi
      4.1.2 Hasil Wawancara
      4.1.3 Hasil Kuesioner Kesiapan
  4.2 Analisis Kebutuhan Sistem
      4.2.1 Kebutuhan Fungsional
      4.2.2 Kebutuhan Non-Fungsional
  4.3 Perancangan Sistem
      4.3.1 Arsitektur Sistem
      4.3.2 Use Case Diagram
      4.3.3 Activity Diagram
      4.3.4 Sequence Diagram
      4.3.5 Entity Relationship Diagram (ERD)
      4.3.6 Perancangan Database
      4.3.7 Perancangan Antarmuka (Wireframe/UI)
  4.4 Implementasi Sistem
      4.4.1 Implementasi Backend
      4.4.2 Implementasi Database
      4.4.3 Implementasi Integrasi WhatsApp
      4.4.4 Implementasi Panel Admin Web
      4.4.5 Implementasi Chatbot WhatsApp
  4.5 Pengujian Sistem
      4.5.1 Pengujian Black Box Testing
      4.5.2 Pengujian User Acceptance Testing (UAT)
      4.5.3 Pengujian Efisiensi Waktu Layanan
  4.6 Pembahasan Hasil
```

---

## Penjelasan per bagian — Apa yang harus kamu kerjakan

### 4.1 Hasil Pengumpulan Data

**Ini hasil dari kunjungan lapangan yang kamu lakukan sekarang.**

| Subbab | Isi | Contoh output |
|--------|-----|---------------|
| Observasi | Apa yang kamu lihat di kelurahan | "Alur pengajuan surat dimulai dari…" |
| Wawancara | Ringkasan jawaban petugas & warga | Tabel: pertanyaan + jawaban |
| Kuesioner | (Opsional di proposal) Kesiapan warga pakai WhatsApp | "80% responden setuju" |

**Tips:** Simpan catatan wawancara asli untuk **Lampiran**.

---

### 4.2 Analisis Kebutuhan Sistem

Ubah hasil observasi/wawancara menjadi **daftar fitur sistem**.

**Contoh kebutuhan fungsional:**

| No | Kebutuhan | Aktor |
|----|-----------|-------|
| F1 | Masyarakat dapat mengajukan surat via WhatsApp | Masyarakat |
| F2 | Sistem mengirim notifikasi status surat | Sistem |
| F3 | Petugas dapat melihat daftar permohonan | Petugas |
| F4 | Petugas dapat verifikasi & proses surat | Petugas |
| F5 | Petugas dapat mengubah status permohonan | Petugas |
| F6 | Masyarakat dapat cek status via WhatsApp | Masyarakat |
| F7 | Admin dapat login ke panel web | Admin |
| F8 | Sistem mencatat log waktu pengajuan-selesai | Sistem |

**Contoh kebutuhan non-fungsional:**

| No | Kebutuhan |
|----|-----------|
| NF1 | Sistem dapat diakses 24 jam |
| NF2 | Response time < 3 detik |
| NF3 | Data tersimpan aman di database |
| NF4 | Antarmuka WhatsApp mudah dipahami |

---

### 4.3 Perancangan Sistem — Ini inti skripsi Informatika

**Diagram yang wajib kamu buat:**

| Diagram | Tools | Gambar |
|---------|-------|--------|
| Arsitektur sistem | Draw.io | Gambar 4.1 |
| Use Case Diagram | Draw.io | Gambar 4.2 |
| Activity Diagram (alur pengajuan surat) | Draw.io | Gambar 4.3 |
| Sequence Diagram (integrasi WhatsApp) | Draw.io | Gambar 4.4 |
| ERD | Draw.io / dbdiagram.io | Gambar 4.5 |
| Wireframe UI admin | Figma / Draw.io | Gambar 4.6–4.x |

**Tabel database (contoh):**

| Tabel | Isi |
|-------|-----|
| users | Data petugas kelurahan |
| permohonan | Data pengajuan surat |
| jenis_surat | Jenis-jenis surat |
| log_notifikasi | Riwayat notifikasi WhatsApp |
| warga | Data masyarakat pemohon |

---

### 4.4 Implementasi Sistem — Bukti kamu bisa coding

**Yang harus ada di bab ini:**

1. **Screenshot** setiap halaman/fitur sistem
2. **Cuplikan kode** penting (bukan seluruh kode — pilih yang relevan)
3. **Penjelasan** cara kerja setiap modul

**Modul yang harus diimplementasi:**

| Modul | Bukti di skripsi |
|-------|------------------|
| Login admin | Screenshot + cuplikan kode autentikasi |
| Dashboard permohonan | Screenshot daftar permohonan |
| Form pengajuan (via WhatsApp) | Screenshot alur chat bot |
| Verifikasi petugas | Screenshot halaman verifikasi |
| Notifikasi status | Screenshot pesan WhatsApp otomatis |
| Database | Screenshot phpMyAdmin / tabel |

**Tips:** Simpan source code di GitHub — lampirkan link di lampiran.

---

### 4.5 Pengujian Sistem

#### 4.5.1 Black Box Testing

Buat tabel seperti ini:

| ID | Fitur | Input | Output Diharapkan | Hasil | Status |
|----|-------|-------|-------------------|-------|--------|
| T01 | Login admin | username & password benar | Masuk dashboard | Sesuai | ✓ |
| T02 | Login admin | password salah | Pesan error | Sesuai | ✓ |
| T03 | Pengajuan surat via WA | Data lengkap | Konfirmasi terima | Sesuai | ✓ |
| T04 | Pengajuan surat via WA | Data kosong | Pesan lengkapi data | Sesuai | ✓ |
| T05 | Notifikasi status | Status diubah petugas | WA terkirim ke warga | Sesuai | ✓ |
| … | … | … | … | … | … |

**Target:** Minimal 20 skenario uji, 100% berhasil.

#### 4.5.2 UAT (Kuesioner)

| Aspek | Rata-rata Skor | Kategori |
|-------|---------------|----------|
| Kemudahan penggunaan | 4,2 | Sangat Baik |
| Kecepatan layanan | 4,0 | Sangat Baik |
| Kemanfaatan sistem | 4,3 | Sangat Baik |
| Kepuasan keseluruhan | 4,1 | Sangat Baik |

#### 4.5.3 Efisiensi Waktu

| Metrik | Sebelum Sistem | Sesudah Sistem | Peningkatan |
|--------|---------------|----------------|-------------|
| Rata-rata waktu pengurusan | 2 hari | 1 hari | 50% |
| Kunjungan fisik per permohonan | 2× | 1× (ambil surat) | 50% |

*Angka contoh — kamu isi dengan data nyata.*

---

### 4.6 Pembahasan Hasil

Jawab rumusan masalah dengan data dari 4.5:

1. Sistem berhasil dibangun dengan fitur A, B, C → bukti screenshot
2. Black Box Testing: X skenario, Y% berhasil → bukti tabel
3. UAT: skor rata-rata Z → bukti kuesioner

---

## BAB V — Kesimpulan dan Saran (Rencana)

### Struktur singkat

```
BAB V KESIMPULAN DAN SARAN
  5.1 Kesimpulan (jawab setiap rumusan masalah)
  5.2 Saran (untuk kelurahan, peneliti selanjutnya)
```

### Contoh kesimpulan

> 1. Sistem layanan surat administrasi berbasis WhatsApp terintegrasi panel admin web telah berhasil dirancang dan dibangun di Kelurahan Kampung Sambakungan dengan 8 fitur utama.
> 2. Pengujian Black Box Testing menunjukkan 25 skenario uji dengan tingkat keberhasilan 100%.
> 3. Pengujian UAT terhadap 15 responden menghasilkan skor kepuasan rata-rata 4,15 dengan kategori Sangat Baik.

### Contoh saran

> 1. Kelurahan Kampung Sambakungan disarankan untuk mengadopsi sistem ini secara resmi dan melatih petugas.
> 2. Peneliti selanjutnya dapat menambahkan fitur tanda tangan digital dan integrasi Dukcapil.

---

## Estimasi Halaman Bab IV–V

| Bab | Estimasi halaman |
|-----|-----------------|
| Bab IV | 35–50 halaman |
| Bab V | 2–3 halaman |
| Lampiran | 10–20 halaman |

---

## Timeline Pengerjaan Bab IV–V

| Tahap | Durasi | Kapan |
|-------|--------|-------|
| Analisis kebutuhan + UML | 2 minggu | Setelah proposal disetujui |
| Coding & integrasi WhatsApp | 4–6 minggu | Inti pengerjaan |
| Pengujian Black Box + UAT | 1–2 minggu | Setelah sistem jadi |
| Penulisan Bab IV | 2 minggu | Paralel dengan coding |
| Penulisan Bab V + Abstrak | 3 hari | Setelah semua data terkumpul |

---

## Checklist — Persiapan Bab IV (mulai pikirkan dari sekarang)

```
[ ] Simpan semua catatan observasi & wawancara (untuk §4.1)
[ ] Saat coding, screenshot setiap fitur
[ ] Simpan source code di GitHub
[ ] Rancang database di awal (jangan ubah-ubah terus)
[ ] Buat skenario Black Box Testing sejak perancangan fitur
[ ] Siapkan formulir kuesioner UAT sebelum pengujian
[ ] Catat waktu layanan sebelum sistem (baseline) SEKARANG
```

**Penting:** Data "sebelum sistem" harus kamu kumpulkan **sekarang** saat observasi. Kalau sistem sudah jadi baru tanya "dulu berapa lama?" — jawabannya tidak akurat.

---

## Fitur Minimum yang Harus Ada di Sistem

Agar skripsi Informatika dianggap layak, sistem kamu **minimal** harus punya:

| No | Fitur | Wajib? |
|----|-------|--------|
| 1 | Login/logout petugas admin | ✓ Wajib |
| 2 | Dashboard ringkasan permohonan | ✓ Wajib |
| 3 | Input/pengajuan permohonan surat | ✓ Wajib |
| 4 | Verifikasi & proses oleh petugas | ✓ Wajib |
| 5 | Notifikasi status via WhatsApp | ✓ Wajib |
| 6 | Cek status permohonan | ✓ Wajib |
| 7 | Cetak/generate surat (PDF) | Disarankan |
| 8 | Riwayat & log permohonan | Disarankan |
| 9 | Chatbot menu interaktif di WhatsApp | ✓ Wajib |
| 10 | Manajemen jenis surat | Opsional |

Jika fitur di atas tidak ada, penguji akan mempertanyakan kedalaman implementasi.
