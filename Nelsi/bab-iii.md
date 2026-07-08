# Audit — BAB III: Metodologi Penelitian

**Halaman:** 8–10 (PDF)  
**Status:** Perlu revisi wajib — kerangka ada, detail belum matang

---

## Ringkasan Bab

Bab III sudah memuat komponen standar metodologi R&D: jenis penelitian, lokasi, teknik pengumpulan data, tahapan Waterfall, alat/teknologi, dan kerangka penelitian. Namun banyak bagian masih **belum diputuskan** (teknologi "atau-atau") dan **belum dioperasionalkan** (pengukuran efisiensi & kepuasan). Gambar kerangka penelitian disebut tetapi **tidak ada**.

**Nilai substansi:** 5/10  
**Nilai kelengkapan:** 4/10

---

## 3.1 Jenis Penelitian

### Yang Sudah Baik
- Dinyatakan sebagai penelitian R&D (Research and Development)
- Mixed method (kualitatif + kuantitatif) disebutkan

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | R&D disebut tapi **tidak merujuk model R&D** (Sugiyono 10 langkah, Borg & Gall) | Tambah: *"Mengacu pada model R&D Sugiyono (2019) dengan 10 langkah, penelitian ini fokus pada langkah 3–8 (pengembangan produk)"* |
| **Wajib** | Mixed method diklaim tanpa penjelasan | Jelaskan: kualitatif = wawancara/observasi; kuantitatif = kuesioner UAT |
| Disarankan | Tidak ada diagram alur jenis penelitian | Tambah di Gambar 3.1 |

**Penjelasan untuk mahasiswa — R&D itu apa?**

R&D (Research and Development) = penelitian yang menghasilkan **produk** (dalam hal ini: sistem/aplikasi). Cocok untuk skripsi "rancang bangun". Kamu tidak hanya menulis teori, tapi **membuat sesuatu yang nyata**.

---

## 3.2 Lokasi dan Waktu Penelitian

### Yang Sudah Baik
- Lokasi jelas: Kelurahan Kampung Sambakungan
- Durasi 6 bulan disebutkan

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Tidak ada **jadwal per tahap** | Buat Tabel 3.1 Jadwal Penelitian (Gantt sederhana) |
| Disarankan | Tidak ada tanggal mulai/selesai | Tambah: bulan mulai – bulan selesai |

### Contoh Tabel 3.1 Jadwal Penelitian

| No | Tahapan | Bulan 1 | Bulan 2 | Bulan 3 | Bulan 4 | Bulan 5 | Bulan 6 |
|----|---------|---------|---------|---------|---------|---------|---------|
| 1 | Observasi & wawancara | ■ | | | | | |
| 2 | Studi literatur | ■ | ■ | | | | |
| 3 | Analisis kebutuhan | | ■ | | | | |
| 4 | Perancangan sistem (UML, ERD) | | ■ | ■ | | | |
| 5 | Implementasi (coding) | | | ■ | ■ | | |
| 6 | Pengujian (Black Box + UAT) | | | | ■ | ■ | |
| 7 | Penulisan laporan | | | | ■ | ■ | ■ |
| 8 | Sidang | | | | | | ■ |

---

## 3.3 Teknik Pengumpulan Data

### Yang Sudah Baik
- Empat teknik lengkap: observasi, wawancara, kuesioner, studi literatur
- Sesuai standar skripsi R&D

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Kuesioner §3.3 (kesiapan) vs UAT §3.4.4 (kepuasan) — **dua fungsi berbeda** belum dibedakan | Jelaskan: kuesioner pra-sistem (kesiapan) dan pasca-sistem (UAT) adalah instrumen terpisah |
| **Wajib** | Kuesioner tidak dioperasionalkan | Tambah §3.3.3: jumlah responden, sampling, instrumen |
| **Wajib** | Wawancara tidak dijelaskan (siapa, berapa orang) | Tambah: *"Wawancara dilakukan terhadap 2 petugas kelurahan dan 5 warga menggunakan pedoman wawancara semi-terstruktur"* |
| Disarankan | Observasi tidak dijelaskan | Tambah: *"Observasi dilakukan selama [X] hari kerja dengan fokus pada alur pelayanan surat"* |

### Tambahkan §3.3.3 Desain Kuesioner UAT

| Aspek | Detail yang harus ditulis |
|-------|--------------------------|
| Populasi | Masyarakat yang pernah/sedang mengurus surat di kelurahan |
| Sampel | Minimal 15 responden (purposive sampling) |
| Instrumen | Kuesioner Likert 1–5, adaptasi dari Yusuf et al. (2022) |
| Aspek penilaian | Kemudahan, kecepatan, kegunaan, kepuasan keseluruhan |
| Analisis | Skor rata-rata per aspek; kategori: Sangat Baik (4,01–5), Baik (3,01–4), Cukup (2,01–3), Kurang (≤2) |

---

## 3.4 Metode Pengembangan Sistem (Waterfall)

### Yang Sudah Baik
- Lima tahapan Waterfall diuraikan: analisis, perancangan, implementasi, pengujian, pemeliharaan
- Black Box Testing dan UAT disebutkan di tahap pengujian
- UML disebutkan untuk perancangan

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Tidak ada **Gambar 3.2** Tahapan Waterfall | Tambahkan diagram |
| Disarankan | Pemeliharaan dijelaskan panjang padahal skripsi S1 jarang implementasi maintenance | Boleh dipendekkan; fokus ke 4 tahap pertama |
| Disarankan | UML disebut tapi tidak detail jenis diagramnya | Sebutkan: Use Case, Activity, Sequence, ERD |

---

## 3.5 Alat dan Teknologi — KRITIS

### Isi saat ini (masalah!)

```
1. Bahasa Pemrograman: PHP/Python atau Node.js
2. Database: MySQL atau PostgreSQL
3. WhatsApp API: WhatsApp Business API atau library Baileys
4. Web Server: Apache atau Nginx
5. Tools Perancangan: Draw.io atau Lucidchart
```

### Kenapa ini masalah?

Di skripsi Informatika, Bab III harus **spesifik**. Penguji akan bertanya: *"Kamu pakai yang mana? Kenapa?"* Jawaban "atau" = belum siap.

### Keputusan teknologi yang disarankan

| Komponen | Pilihan | Alasan |
|----------|---------|--------|
| Backend | **Laravel 10 (PHP)** | Mudah CRUD, banyak tutorial, cocok untuk admin panel |
| Database | **MySQL 8** | Standar, mudah di XAMPP/Laragon |
| Frontend admin | **Blade (Laravel)** atau **React** | Blade lebih simpel untuk pemula |
| WhatsApp | **WhatsApp Cloud API (Meta)** | Resmi, ada free tier, aman |
| Web server | **Apache (XAMPP/Laragon)** | Mudah setup di Windows |
| Diagram | **Draw.io** | Gratis, online |
| Version control | **Git + GitHub** | Dokumentasi pengembangan |

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Semua teknologi masih "atau" | Tentukan satu pilihan |
| **Wajib** | **Baileys** disebut sebagai opsi | **Hapus.** Tidak resmi, melanggar ToS WhatsApp, akun bisa banned |
| **Wajib** | Tidak ada penjelasan **kenapa** memilih teknologi tersebut | Tambah 1 paragraf justifikasi per komponen |
| Disarankan | Tidak ada spesifikasi perangkat keras | Tambah: laptop, OS, RAM minimum |
| Disarankan | Tidak ada editor kode | Tambah: VS Code |

### Paragraf justifikasi contoh

> Laravel dipilih sebagai framework backend karena menyediakan fitur autentikasi, ORM (Eloquent), dan routing yang memudahkan pengembangan sistem CRUD untuk pengelolaan permohonan surat (Supriadi et al., 2021). MySQL dipilih sebagai database karena kompatibel dengan Laravel dan mudah di-deploy di lingkungan lokal menggunakan XAMPP. WhatsApp Cloud API dipilih karena merupakan layanan resmi dari Meta yang menyediakan free tier dan mendukung pengiriman pesan otomatis untuk notifikasi status surat (Dewi & Nurlaela, 2022).

---

## 3.6 Kerangka Penelitian — KRITIS

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Kerangka penelitian **dijelaskan dengan teks** tetapi **tidak ada gambar** | Wajib tambah **Gambar 3.1** |
| **Wajib** | Gambar 3.1 = halaman kosong saat ini | Buat flowchart |

### Gambar 3.1 yang harus kamu buat (flowchart)

```
[Identifikasi Masalah] → [Studi Literatur] → [Observasi & Wawancara]
        ↓
[Analisis Kebutuhan Sistem]
        ↓
[Perancangan Sistem (UML, ERD, UI)]
        ↓
[Implementasi (Coding)]
        ↓
[Pengujian Black Box] → [Pengujian UAT]
        ↓
[Kesimpulan & Saran]
```

Buat di Draw.io, export sebagai gambar, masukkan ke dokumen.

---

## Yang Harus Ditambahkan di Bab III

| Subbab baru | Isi |
|-------------|-----|
| **3.7 Prosedur Pengujian Black Box** | Tabel format uji: ID, fitur, input, output diharapkan, hasil |
| **3.8 Prosedur Pengujian UAT** | Instrumen kuesioner, skala Likert, cara analisis |
| **3.9 Metrik Efisiensi** | Cara mengukur waktu layanan sebelum & sesudah |
| **3.10 Keamanan Data & Etika** | Autentikasi admin, proteksi data warga, surat izin penelitian, UU PDP |

### Contoh §3.9 Metrik Efisiensi

> Efisiensi pelayanan diukur dengan membandingkan rata-rata waktu pengurusan surat sebelum dan sesudah implementasi sistem. Data waktu sebelum sistem diperoleh dari wawancara petugas dan dokumentasi kelurahan. Data waktu sesudah sistem diperoleh dari log timestamp di database sistem (waktu pengajuan → waktu selesai). Selain itu, dihitung persentase permohonan yang dilakukan tanpa kunjungan fisik ke kelurahan.

---

## Checklist Revisi Bab III

```
[ ] Tentukan stack final (hapus semua "atau")
[ ] Hapus Baileys dari dokumen
[ ] Tambah justifikasi pemilihan teknologi
[ ] Tambah model R&D (Sugiyono)
[ ] Jelaskan mixed method (kualitatif + kuantitatif)
[ ] Operasionalkan kuesioner (responden, instrumen, analisis)
[ ] Operasionalkan wawancara (jumlah narasumber)
[ ] Buat Gambar 3.1 Kerangka Penelitian
[ ] Buat Gambar 3.2 Tahapan Waterfall
[ ] Buat Tabel 3.1 Jadwal Penelitian
[ ] Tambah §3.7 Pengujian Black Box
[ ] Tambah §3.8 Pengujian UAT
[ ] Tambah §3.9 Metrik Efisiensi
```

**Estimasi waktu:** 3–5 hari

---

## Pertanyaan Penguji yang Sering Muncul di Bab III

| Pertanyaan | Jawaban yang harus kamu siapkan |
|------------|--------------------------------|
| "Kenapa Waterfall, bukan Prototype?" | Kebutuhan jelas, alur surat baku, perubahan minimal |
| "Kenapa Laravel?" | Fitur CRUD, autentikasi, kompatibel MySQL |
| "Bagaimana integrasi WhatsApp-nya?" | WhatsApp Cloud API → webhook → backend Laravel |
| "Berapa responden kuesioner?" | 15 responden, purposive sampling |
| "Black Box Testing-nya apa saja?" | Sebutkan fitur: login, pengajuan, tracking, notifikasi |
| "Bagaimana mengukur efisiensi?" | Bandingkan waktu layanan sebelum-sesudah |
