# Audit — BAB V: Kesimpulan dan Saran

**Halaman:** 47–48  
**Status:** Perlu revisi minor

---

## Ringkasan Bab

Bab V ringkas dengan 3 kesimpulan + 3 saran. Struktur sudah sesuai standar. Revisi pada konsistensi angka dengan Bab IV, argumen pemilihan broker, dan keselarasan dengan rumusan masalah.

### Temuan Struktur

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | **Kesimpulan tidak paralel** dengan rumusan masalah (2 pertanyaan: rancang/bangun + pengujian) | Susun kesimpulan #1 = fungsionalitas sistem, #2 = hasil pengujian QoS/broker — selaras dengan Bab I §1.2 |
| Disarankan | Kesimpulan **tidak menyebut keterbatasan** (prototipe, durasi uji broker tidak setara, belum uji jadwal jika masih diklaim) | Tambahkan 1 kalimat keterbatasan di akhir §5.1 |

**Nilai substansi:** 7/10  
**Nilai konsistensi dengan Bab IV:** 6/10

---

## 5.1 Kesimpulan

### Kesimpulan 1 — Fungsionalitas Sistem

> *"Sistem otomatisasi kandang ayam kontes berbasis IoT ... berhasil diimplementasikan dan seluruh komponen dapat berfungsi sesuai perancangan."*

**Penilaian:** Sesuai Tabel 4.4 (semua VALID).

**Catatan:** Jika klaim "jadwal otomatis" dihapus/diperbaiki di Bab IV, sesuaikan juga kesimpulan ini agar tidak menyebut fitur yang tidak terbukti.

**Saran minor:** Tambahkan *"dashboard monitoring berbasis web"*.

---

### Kesimpulan 2 — Performa Broker

> *"EMQX ... throughput 3.298,49 bps, delay 246,65 ms. HiveMQ ... 2.882,55 bps, delay 307,37 ms. Packet loss HiveMQ 0% vs EMQX 0,11%."*

**Penilaian:** Angka selaras dengan Tabel 4.5, **tetapi**:

| Masalah | Tindakan |
|---------|----------|
| Satuan throughput bps vs Kbps bergantian dengan Bab IV | Seragamkan setelah revisi Bab IV |
| Angka delay bisa berubah jika metode perhitungan diperbaiki | Update setelah revisi Bab IV |
| Perbandingan broker didasarkan durasi capture tidak setara | Sebutkan keterbatasan atau perbaiki data dulu |

---

### Kesimpulan 3 — Broker Terbaik

> *"Broker EMQX dapat dianggap sebagai broker yang paling baik ... throughput lebih tinggi, delay lebih rendah, packet loss masih sangat baik (0,11%)."*

**Penilaian:** Argumen cukup, tapi perlu nuance — HiveMQ **0% packet loss** vs EMQX **0,11%** (1 paket hilang). Untuk perintah kendali atap, keandalan pengiriman bisa lebih kritis daripada throughput.

**Teks perbaikan yang disarankan:**

> Pemilihan broker bergantung pada prioritas sistem. Jika prioritas **kecepatan transmisi**, EMQX unggul (throughput lebih tinggi, delay lebih rendah). Jika prioritas **keandalan tanpa kehilangan paket**, HiveMQ unggul (packet loss 0%). Untuk prototipe monitoring kandang ini, EMQX dapat direkomendasikan dengan catatan packet loss 0,11% masih sangat rendah.

---

## 5.2 Saran

### Yang Sudah Baik
- Panel surya — relevan
- Sensor suhu & kelembaban — selaras gap penelitian
- Uji skala lebih besar — standar untuk prototipe

### Saran Tambahan

| Prioritas | Saran | Alasan |
|-----------|-------|--------|
| Disarankan | **UPS / battery backup** untuk ESP32 & router | Wawancara (Lampiran 1): listrik sering padam |
| Disarankan | **Autentikasi MQTT** (TLS/username) | Broker publik saat ini tanpa keamanan |
| Disarankan | Uji **QoS Level 1 atau 2** | Bandingkan trade-off keandalan vs performa |
| Opsional | Notifikasi Telegram/WhatsApp saat pakan habis/hujan | Meningkatkan utilitas praktis |
| Opsional | Pengujian jangka panjang 24–48 jam | Uji stabilitas koneksi MQTT |
| Opsional | Aplikasi mobile native sebagai pelengkap dashboard web | Selaras batasan saat ini (web only) |

---

## Konsistensi dengan Bab Sebelumnya

| Aspek | Status | Catatan |
|-------|--------|---------|
| Komponen sistem | Baik | ESP32, HC-SR04, water sensor, servo, MQTT |
| Parameter QoS | Baik | Delay, throughput, packet loss |
| Angka hasil | Perlu cek | Update setelah revisi Bab IV |
| Klaim jadwal otomatis | Perlu cek | Selaraskan dengan Bab III & IV |
| Klaim broker terbaik | Perlu diperkuat | Tambah nuance EMQX vs HiveMQ |

---

## Checklist Revisi Bab V

```
[ ] Selaraskan kesimpulan dengan perbaikan klaim "jadwal otomatis" di Bab IV
[ ] Susun kesimpulan paralel dengan rumusan masalah (§1.2)
[ ] Tambahkan kalimat keterbatasan penelitian
[ ] Seragamkan satuan throughput dengan Bab IV
[ ] Update angka jika perhitungan delay/throughput diperbaiki
[ ] Perkuat kesimpulan #3 dengan argumen trade-off EMQX vs HiveMQ
[ ] Tambahkan saran UPS/battery (listrik padam dari wawancara)
[ ] Tambahkan saran keamanan MQTT
[ ] Pastikan tidak ada poin baru yang tidak dibahas di Bab IV
```

**Estimasi waktu revisi:** 1–2 jam
