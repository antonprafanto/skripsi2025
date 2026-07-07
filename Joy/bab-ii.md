# Audit — BAB II: Tinjauan Pustaka

**Halaman:** 5–20  
**Status:** Perlu revisi sedang

---

## Ringkasan Bab

Bab II mencakup landasan teori yang relevan untuk skripsi IoT. Cakupan materi cukup lengkap. Revisi utama pada format penelitian terkait, sitasi, dan pemindahan konten metodologi dari §2.8.

**Nilai substansi:** 7/10  
**Nilai penulisan & sitasi:** 6/10

---

## 2.1 Penelitian Terkait

### Yang Sudah Baik
- 10 penelitian terkait — jumlah memadai
- Masing-masing diikuti penjelasan relevansi
- Variasi topik: monitoring, pakan otomatis, enkripsi MQTT, QoS, ventilasi

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Format **bukan tabel standar** | Ubah ke **Tabel 2.1**: No, Peneliti/Tahun, Metode, Temuan, Relevansi |
| Wajib | Penelitian #5 menyebut **Blynk** — implementasi skripsi pakai **dashboard web HTML/CSS** | Hapus referensi Blynk |
| Disarankan | Penelitian #7: *"subsistem kontrol lingkungan skripsi ini"* — batasan hanya atap + pakan | Ubah: diadaptasi melalui mekanisme atap otomatis |
| Disarankan | Typo **"Atandard"** → **"Standard"** (penelitian #3) | Koreksi |
| Disarankan | Typo **"Ayam Boiler"** → **"Broiler"** (penelitian #10) | Koreksi |
| Disarankan | Typo ganda titik **"2022).."** (penelitian #10) | Hapus satu titik |
| Disarankan | Typo sitasi **"Hadyanto."** dan **"Randily."** (titik setelah nama) | Koreksi format sitasi |
| Wajib | Sitasi **(Usman, 2021)** dan **(Hermansyah et al., 2025)** tidak ada di Daftar Pustaka | Tambahkan |
| Opsional | Beberapa ringkasan terlalu panjang | Ringkas 3–5 kalimat per penelitian |

---

## 2.2 Smart Farming dan Otomatisasi Kandang Ternak

### Yang Sudah Baik
- Definisi smart farming (4 kebutuhan utama) dan hubungan suhu → produktivitas

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Sitasi **(Rohman & Isnaini, 2024)** tidak ada di Daftar Pustaka | Tambahkan atau ganti |
| Disarankan | Paragraf cenderung umum (broiler), kurang spesifik ayam kontes | Tambah transisi ke §2.3 |

---

## 2.3 Ayam Kontes & 2.4 Kandang Ayam

### Yang Sudah Baik
- Definisi ayam kontes jelas; Gambar 2.1 ada

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | **(Rohman, G. A., 2025)** — judul referensinya tentang ayam potong, bukan ayam kontes | Verifikasi relevansi |
| Disarankan | Gambar 2.1 — tambah sumber jika bukan foto sendiri | *"Sumber: dokumentasi penulis, 2026"* |

---

## 2.5 Internet of Things (IoT)

### Yang Sudah Baik
- Definisi IoT standar, koneksi ke peternakan

### Saran Opsional
- Tambahkan 1 kalimat arsitektur 3 lapis IoT (perception, network, application)

---

## 2.6 Prototipe

### Yang Sudah Baik
- Penjelasan metode prototipe sesuai pendekatan penelitian

---

## 2.7 Message Queuing Telemetry Transport (MQTT)

### Yang Sudah Baik
- Sejarah MQTT, arsitektur publish/subscribe, Gambar 2.2, Tabel 2.1 jenis pesan

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | Sitasi **(Abilovani, 2018)** tidak ada di Daftar Pustaka | Tambahkan (cek entri #11 "bilovani" — kemungkinan typo) |
| Disarankan | Kapitalisasi **"telemetry"** di Daftar Isi | Seragamkan **"Telemetry"** |
| Disarankan | Caption Gambar 2.2: **"Message Queue"** — teks bab memakai **"Message Queuing"** | Seragamkan istilah MQTT |
| Opsional | Tabel 2.1 terpecah antar halaman (CONNACK terpisah) | Pastikan tidak terpotong di versi cetak |
| Opsional | Jika penelitian terkait diubah ke tabel, **jangan bentrok** dengan Tabel 2.1 (jenis pesan MQTT) | Gunakan nomor tabel berikutnya atau format naratif |

---

## 2.8 Quality of Service (QoS)

### Yang Sudah Baik
- Tiga level QoS dijelaskan; rumus 2.1–2.3 ada

### Temuan Wajib

| No | Temuan | Saran |
|----|--------|-------|
| 1 | Paragraf terakhir §2.8 membahas rencana penelitian (*"analisis difokuskan pada perbandingan broker..."*) | **Pindahkan ke Bab III** — tinjauan pustaka cukup definisi & rumus |
| 2 | Rumus delay (2.1): jika "Total Delay" = durasi capture Wireshark, pembagian dengan jumlah paket **bukan delay valid** | Perjelas definisi; sesuaikan perhitungan di Bab IV |

**Definisi delay yang benar:**
```
delay_i = waktu_terima_paket_i - waktu_kirim_paket_i
DELAY_rata = Σ delay_i / n
```

---

## 2.9 – 2.14 Komponen Hardware & Wireshark

### Yang Sudah Baik
- Motor servo, broker, HC-SR04, ESP32, water sensor, Wireshark — dijelaskan dengan gambar

### Temuan
| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Water sensor = deteksi hujan di sini, tapi "level air" di Bab III | Seragamkan seluruh dokumen |
| Disarankan | Caption Gambar 2.3: **"MOTOR SERVO"** | Ubah **"Motor Servo"** |

---

## Sitasi Bab II — Cek Daftar Pustaka

| Sitasi | Status |
|--------|--------|
| Usman, 2021 | Tidak ada |
| Hermansyah et al., 2025 | Tidak ada |
| Rohman & Isnaini, 2024 | Tidak ada |
| Abilovani, 2018 | Tidak ada (ada "bilovani") |

---

## Checklist Revisi Bab II

```
[ ] Ubah penelitian terkait ke format tabel (perhatikan nomor Tabel 2.1 yang sudah dipakai)
[ ] Hapus referensi Blynk
[ ] Koreksi typo: Atandard, Boiler, 2022).., Hadyanto., Randily.
[ ] Seragamkan "Message Queuing" vs "Message Queue" (Gambar 2.2)
[ ] Pindahkan paragraf metodologi QoS dari §2.8 ke Bab III
[ ] Perjelas definisi rumus delay
[ ] Lengkapi 4 referensi yang hilang
[ ] Verifikasi relevansi Rohman 2025 (ayam potong vs kontes)
```

**Estimasi waktu revisi:** 4–6 jam
