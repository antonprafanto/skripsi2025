# Audit — BAB III: Metodologi Penelitian

**Halaman:** 21–29  
**Status:** Perlu revisi sedang

---

## Ringkasan Bab

Bab III menguraikan tahapan penelitian dengan diagram yang memadai. Revisi utama pada konsistensi dengan implementasi (web vs mobile, water sensor), kelengkapan Gambar 3.2, integrasi wawancara, dan penjelasan mekanisme penjadwalan.

**Nilai substansi:** 7,5/10  
**Nilai konsistensi dengan implementasi:** 6/10

---

## 3.1 Tahap Pelaksanaan Penelitian

### Yang Sudah Baik
- Gambar 3.1 alur penelitian jelas
- 6 tahap dijelaskan dengan baik

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Tahap 5 menyebut **"aplikasi mobile"** — implementasi adalah **dashboard web** | Ganti: *"dashboard monitoring berbasis web"* |
| Disarankan | *"melakukan melakukan pengumpulan data"* — kata ganda | Hapus salah satu |

---

## 3.2 Pengumpulan Data

### Yang Sudah Baik
- Tiga metode: studi literatur, observasi, wawancara
- Lokasi spesifik: **AR Farm Simpang Pasir**

### Temuan Wajib

| No | Temuan | Saran |
|----|--------|-------|
| 1 | Hasil wawancara **tidak dirangkum** — padahal Lampiran 1 memuat data penting | Tambahkan paragraf ringkasan + rujuk Lampiran 1 |
| 2 | Tanggal wawancara (**7 Oktober 2025**) tidak disebut | Cantumkan di metodologi |

**Data wawancara yang perlu dimasukkan:**
- 20 kandang, pengelolaan manual penutupan atap tiap 2–3 jam
- Saat hujan, penutupan satu per satu sangat repot
- Wi-Fi tersedia, **listrik sering padam mendadak**
- Peternak mendukung otomatisasi pakan & atap

### Saran Tambahan
- Rinci parameter observasi: ketersediaan pakan, kondisi hujan, kebutuhan monitoring jarak jauh

---

## 3.3 Perancangan Data

### Yang Sudah Baik
- Alur sensor → ESP32 → aktuator → MQTT → dashboard jelas

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | *"sensor lainnya"* — tidak spesifik | Sebutkan: HC-SR04 + water sensor saja |
| Wajib | Topik MQTT **publish** tidak didokumentasikan (hanya subscribe di kode) | Tambahkan tabel topik publish & subscribe |

**Contoh tabel topik MQTT:**

| Arah | Topik | Keterangan |
|------|-------|------------|
| Publish | `joeybiosolarindustri/kandang/sensor/...` | Data sensor ke broker |
| Subscribe | `joeybiosolarindustri/kandang/control/atap` | Perintah atap |
| Subscribe | `joeybiosolarindustri/kandang/control/pakan` | Perintah pakan |

---

## 3.4 Perancangan Proses

### Temuan Wajib

| No | Temuan | Perbaikan |
|----|--------|-----------|
| 1 | **"penelitian Anda"** — sisa template | Ganti *"penelitian ini"* |
| 2 | **"Gambar 15"** | Ganti **"Gambar 3.3"** |
| 3 | Water sensor = **"level air"** | Ganti *"deteksi air/hujan"* |
| 4 | **"servo kandang"** untuk dispenser pakan | Ganti **"servo pakan"** |
| 5 | Typo **"manejemen"** | **"manajemen"** |
| 6 | **Gambar 3.2 tidak memuat water sensor** — padahal disebut di teks | Redesain diagram, tambahkan water sensor |
| 7 | Gambar 3.2 ada **titik seleksi biru** (artifact editor Canva) | Hapus sebelum cetak |
| 8 | Gambar 3.2 menunjukkan **2 dashboard terpisah** — tidak dijelaskan di teks | Jelaskan: 1 dashboard atau 2 halaman terpisah |

### Temuan Penting — Penjadwalan Otomatis

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Bab IV menyebut servo beroperasi **"sesuai jadwal"**, tetapi Bab III **tidak menjelaskan** mekanisme jadwal (RTC, timer, dsb.) | Jelaskan mekanisme penjadwalan di sini |
| Wajib | **RTC** ada di Daftar Singkatan tapi tidak dipakai | Hapus RTC dari daftar singkatan, ATAU implementasikan & jelaskan |

### Yang Sudah Baik
- Penjelasan publish/subscribe, QoS Level 0, parameter Wireshark

### Saran Tambahan
- Spesifikasi pengujian: durasi capture, interval publish ESP32
- Alasan memilih QoS 0
- Perangkat lunak: Arduino IDE, PubSubClient, browser
- **Prosedur uji broker:** jelaskan apakah EMQX dan HiveMQ diuji **bergantian** (satu per satu) atau simultan — saat ini tidak dijelaskan
- **Client ID** `ESP32_KandangAyam` sama untuk kedua broker — jelaskan bahwa uji dilakukan sesi terpisah agar tidak bentrok koneksi
- **Lingkungan uji:** sebutkan kondisi Wi-Fi (SSID, jarak router, perangkat uji) agar pengujian QoS dapat direplikasi

---

## 3.5 Perancangan Tampilan

### Yang Sudah Baik
- Gambar 3.4 mockup dashboard; fitur atap, hujan, pakan, kontrol manual

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Teks menyebut **"aplikasi mobile"** | Ganti **"web"* |
| Disarankan | Teknologi frontend tidak disebut | Tambahkan HTML, CSS, JavaScript MQTT client |

---

## 3.6 Perancangan Pengujian

### Yang Sudah Baik
- Dua jenis pengujian: fungsionalitas + performa broker

### Saran — Tambahkan Tabel 3.1 Rencana Pengujian

| No | Jenis Uji | Komponen | Metode | Kriteria Lulus |
|----|-----------|----------|--------|----------------|
| 1 | Fungsional | Servo atap | Trigger water sensor | Atap tertutup saat air terdeteksi |
| 2 | Fungsional | Servo pakan | Tombol dashboard | Servo berputar sesuai perintah |
| 3 | Fungsional | HC-SR04 | Ukur jarak pakan | Nilai tampil di dashboard |
| 4 | Fungsional | Jadwal otomatis | (jika ada) | Servo berjalan sesuai waktu program |
| 5 | Performa | EMQX vs HiveMQ | Wireshark, durasi **sama** | Hitung delay, throughput, packet loss |

---

## Diagram & Gambar

| Gambar | Status | Catatan |
|--------|--------|---------|
| 3.1 Tahap Penelitian | Baik | — |
| 3.2 Arsitektur Sistem | **Perlu perbaikan** | Tambah water sensor, hapus artifact editor, jelaskan dashboard |
| 3.3 Perangkat Keras | Baik | Perbaiki referensi "Gambar 15" |
| 3.4 Rancangan Tampilan | Baik | — |

---

## Checklist Revisi Bab III

```
[ ] Ganti "penelitian Anda" → "penelitian ini"
[ ] Ganti "Gambar 15" → "Gambar 3.3"
[ ] Koreksi "level air", "servo kandang", "manejemen"
[ ] Ganti semua "mobile" → "web"
[ ] Hapus kata ganda "melakukan melakukan"
[ ] Ringkas hasil wawancara + tanggal pengumpulan data
[ ] Perbaiki Gambar 3.2 (water sensor, artifact editor, dashboard)
[ ] Jelaskan mekanisme penjadwalan ATAU koordinasi dengan Bab IV untuk hapus klaim jadwal
[ ] Tambahkan tabel topik MQTT (publish & subscribe)
[ ] Tambahkan Tabel 3.1 rencana pengujian dengan durasi capture setara
```

**Estimasi waktu revisi:** 4–5 jam
