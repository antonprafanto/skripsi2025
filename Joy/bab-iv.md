# Audit — BAB IV: Hasil dan Pembahasan

**Halaman:** 30–46  
**Status:** Perlu revisi besar (teknis & format)

---

## Ringkasan Bab

Bab IV adalah inti empiris skripsi. Substansi penelitian sudah memadai, tetapi bab ini memiliki **temuan terbanyak**: penomoran gambar, referensi silang, perhitungan QoS, dan klaim yang tidak selalu didukung bukti uji.

**Nilai substansi:** 7,5/10  
**Nilai presentasi & keakuratan teknis:** 5,5/10

---

## 4.1 – 4.2 Implementasi Prototipe & Perangkat Keras

### Yang Sudah Baik
- Dimensi prototipe (40×40×50 cm) spesifik
- Gambar 4.1 jelas; Tabel 4.1 pin GPIO ada

### Temuan Tambahan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | **§4.1 tidak ada gambar** prototipe miniatur kandang — hanya deskripsi teks | Tambahkan foto prototipe sebagai Gambar 4.x |
| Disarankan | **Threshold pakan** (berapa cm = status habis/aman) **tidak didefinisikan** — dashboard menampilkan cm tanpa batas | Cantumkan nilai threshold di metodologi atau tabel spesifikasi |
| Disarankan | Nama **"Smart Chicken Coop"** muncul tanpa perkenalan di Bab III | Sebutkan sekali saat perancangan tampilan |
| Disarankan | **Teknologi dashboard** (HTML/CSS/JS, library MQTT client, hosting) tidak dijelaskan | Tambahkan 1 paragraf di §4.4 |
| Disarankan | Caption Gambar 4.9: **"WaterSensor"** (satu kata) | Ubah **"Water Sensor"** konsisten dengan istilah lain |

### Temuan

| Prioritas | Temuan | Perbaikan |
|-----------|--------|-----------|
| Disarankan | Nama sensor **"SR-HC04"** | Standarkan **"HC-SR04"** |
| Disarankan | Tabel 4.1: **"5 v"**, **"3.3 v"** | **"5V"**, **"3.3V"** |
| Wajib | *"dihubungkan melalui pin 3V"* — tidak akurat | Ganti **"3,3V"** + sebutkan pin: Echo 4, Trig 5, Water 34 |
| Opsional | Tidak ada diagram wiring | Tambahkan di lampiran |

---

## 4.3 Implementasi Broker

### Yang Sudah Baik
- Kode EMQX & HiveMQ disertakan; mekanisme publish/subscribe/reconnect jelas

### Temuan Wajib

| No | Temuan | Saran |
|----|--------|-------|
| 1 | Kode di **Tabel 4.2 & 4.3 terpotong** — kurung `}` tidak lengkap | Lengkapi atau pindah ke Lampiran |
| 2 | Kode di label **"Tabel"** — seharusnya **Listing Program** | Sesuaikan format prodi |
| 3 | Komentar kode: **"HIVEMQ"** | **"HiveMQ"** |
| 4 | Topik publish data sensor tidak ditampilkan di kode | Dokumentasikan di teks/lampiran |
| Disarankan | Kalimat **"Pada tabel 4.2 menunjukkan..."** / **"Pada tabel 4.3 menunjukkan..."** — tidak baku | Ganti: **"Tabel 4.2 menunjukkan..."** |
| Disarankan | Broker publik tanpa autentikasi | Catat di batasan/metodologi |

---

## 4.4 Implementasi Tampilan

### Temuan Wajib
| Temuan | Perbaikan |
|--------|-----------|
| Teks: *"disajikan pada Gambar 4.4"* — padahal gambar tampilan adalah **Gambar 4.2** | Koreksi referensi silang |

### Yang Sudah Baik
- Penjelasan indikator dashboard (Atap, Hujan, Pakan) lengkap

---

## 4.5 Implementasi Wireshark

| Prioritas | Temuan | Perbaikan |
|-----------|--------|-----------|
| Wajib | **Paragraf duplikat** (2 paragraf identik) | Hapus salah satu |
| Wajib | Teks: *"gambar 4.6 dan 4.7"* untuk packet capture — seharusnya **Gambar 4.4 dan 4.5** | Koreksi semua referensi silang |
| Wajib | Klaim *"kondisi pengujian yang sama"* — padahal durasi capture berbeda | Hapus klaim atau perbaiki pengujian |
| Disarankan | *"memfilter paket MQTT"* — kalimat terpotong | Lengkapi kalimat |
| Disarankan | **Cara menghitung Paket Dikirim/Diterima** di Wireshark tidak dijelaskan | Tambahkan langkah filter MQTT + metode penghitungan paket |

---

## 4.6 Hasil Pengujian

### 4.6.1 Hasil Uji Fungsionalitas Komponen

#### Yang Sudah Baik
- Format Tabel 4.4 standar; semua komponen VALID

#### Temuan Wajib

| No | Temuan | Saran |
|----|--------|-------|
| 1 | **Baris duplikat** uji HC-SR04 (2 kali identik) | Hapus duplikat; ganti dengan uji lain (mis. dashboard real-time) |
| 2 | Uji servo atap *"sesuai jam"* — **tidak ada penjelasan jadwal** di Bab III | Jelaskan jadwal, atau ubah skenario uji |
| 3 | Klaim servo pakan *"sesuai jadwal"* di pembahasan — **tidak ada baris uji jadwal** di Tabel 4.4 | Tambahkan uji jadwal ATAU hapus klaim di §4.7.1 |
| 4 | Kolom "Hasil Pengujian" hanya "berhasil" — **tanpa data kuantitatif** | Tambahkan contoh: jarak cm, waktu trigger, dll. |

### 4.6.2 Hasil Perbandingan Performa Broker

**Tabel 4.5:**

| Parameter | EMQX | HiveMQ |
|-----------|------|--------|
| Jumlah Byte | 90.001 | 98.348 |
| Time Span | 218,284 s | 272,947 s |
| Paket Dikirim | 886 | 888 |
| Paket Diterima | 885 | 888 |
| Throughput | 3.298,49 bps | 2.882,55 bps |
| Packet Loss | 0,11% | 0% |
| Delay | 246,65 ms | 307,37 ms |

#### Temuan Wajib — Validitas Perbandingan

| No | Temuan | Saran |
|----|--------|-------|
| 1 | **Durasi capture tidak setara** (~218 s vs ~273 s, selisih ~25%) | Ulangi dengan durasi identik ATAU jelaskan keterbatasan di §4.7.2 |
| 2 | **Jumlah byte berbeda** — tidak dijelaskan | Jelaskan penyebab perbedaan |

#### Temuan Wajib — Metodologi Perhitungan

**1. Delay — kemungkinan salah**

Perhitungan saat ini:
```
DELAY = Time Span / Paket Diterima = 218,284 / 885 = 246,65 ms
```

Time Span = **total durasi capture Wireshark**, bukan total waktu tunggu paket. Metode ini **bukan definisi delay jaringan yang standar**.

**Perbaikan:** Hitung dari timestamp per-paket di Wireshark, lalu rata-rata.

**2. Satuan throughput — perlu konsistensi**

Tabel memakai **bps**, perhitungan §4.7.2 memakai **Kbps**. Dengan format angka Indonesia, nilai bisa selaras (~3298 bps ≈ 3,298 Kbps), tetapi **penggunaan satuan bergantian membingungkan**. Pilih satu satuan di tabel, perhitungan, pembahasan, dan kesimpulan.

**3. Packet Loss HiveMQ — typo langkah perhitungan**

Teks: `(888-888)/888 = (1/888) × 100%` — **"(1/888)" salah**, seharusnya **(0/888)**. Hasil 0% tetap benar.

---

## 4.7 Pembahasan

### 4.7.1 Pembahasan Hasil Uji Fungsionalitas

#### Temuan Wajib — Penomoran Gambar

Referensi silang gambar **saling bentrok** antara bagian Wireshark dan bagian fungsional:

| Isi sebenarnya | Nomor saat ini | Masalah |
|----------------|----------------|---------|
| Packet capture EMQX/HiveMQ | 4.4, 4.5 | §4.5 salah merujuk 4.6, 4.7 |
| Atap terbuka, dashboard, servo pakan | 4.6–4.9, **5.0–5.2** | Gambar 5.x seharusnya lanjutan 4.x |

**Renomori yang disarankan:**

| Urutan | Isi | Nomor |
|--------|-----|-------|
| 1 | Implementasi hardware | 4.1 |
| 2 | Implementasi tampilan | 4.2 |
| 3 | Implementasi Wireshark | 4.3 |
| 4 | Packet capture EMQX | 4.4 |
| 5 | Packet capture HiveMQ | 4.5 |
| 6 | Atap terbuka | 4.6 |
| 7 | Dashboard atap buka | 4.7 |
| 8 | Atap tertutup | 4.8 |
| 9 | Dashboard atap tutup | 4.9 |
| 10 | Servo pakan | 4.10 |
| 11 | Tombol kontrol pakan | 4.11 |
| 12 | Dashboard stok pakan | 4.12 |

#### Yang Sudah Baik
- Narif pembahasan mudah diikuti; foto & screenshot mendukung klaim

### 4.7.2 Pembahasan Performa Broker

#### Yang Sudah Baik
- Perhitungan ditunjukkan langkah demi langkah; 3 parameter dibahas

#### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Wireshark dirujuk ke Gambar 4.6 & 4.7 — seharusnya **4.4 & 4.5** | Koreksi |
| Wajib | Time Span & byte count berbeda — belum dibahas | Tambahkan penjelasan/keterbatasan |
| Disarankan | Kesimpulan pro-EMQX tanpa nuance packet loss HiveMQ 0% | Seimbangkan argumen |
| Opsional | Tidak ada grafik perbandingan visual | Tambah bar chart |

### Format Penulisan
- Beberapa paragraf di §4.6–4.7 diawali **spasi/indent berlebih** — rapikan format Word sebelum cetak

---

## Checklist Revisi Bab IV

```
[ ] Standarkan HC-SR04; koreksi "pin 3V" → 3,3V
[ ] Renomori SEMUA gambar Bab IV + perbaiki Daftar Gambar
[ ] Koreksi SEMUA referensi silang gambar di teks
[ ] Hapus paragraf duplikat §4.5
[ ] Lengkapi kode broker / pindah ke lampiran; koreksi "HIVEMQ"
[ ] Hapus baris duplikat Tabel 4.4
[ ] Selesaikan klaim "jadwal otomatis" (bukti uji atau hapus klaim)
[ ] Tambahkan data kuantitatif di hasil uji
[ ] Setarakan durasi capture broker ATAU jelaskan keterbatasan
[ ] Perbaiki perhitungan delay (timestamp per-paket)
[ ] Seragamkan satuan throughput
[ ] Koreksi langkah perhitungan packet loss HiveMQ: (0/888)
[ ] Hapus klaim "kondisi pengujian yang sama" jika durasi berbeda
[ ] Koreksi "Pada tabel 4.x menunjukkan" → "Tabel 4.x menunjukkan"
[ ] Tambahkan foto prototipe §4.1, threshold pakan (cm), teknologi dashboard
[ ] Jelaskan cara hitung paket di Wireshark
[ ] Rapikan spasi/indent §4.6–4.7
```

**Estimasi waktu revisi:** 6–8 jam
