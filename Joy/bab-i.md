# Audit — BAB I: Pendahuluan

**Halaman:** 1–4  
**Status:** Perlu revisi minor–sedang

---

## Ringkasan Bab

Bab I sudah memuat komponen standar dengan alur argumentasi yang logis (masalah peternakan → IoT → MQTT → QoS → prototipe). Revisi utama pada typo, sitasi, dan integrasi bukti lapangan dari wawancara.

**Nilai substansi:** 7,5/10  
**Nilai penulisan akademik:** 6,5/10

---

## 1.1 Latar Belakang

### Yang Sudah Baik
- Konteks ayam kontes vs ayam komersial sudah dijelaskan
- Hubungan manajemen manual → masalah → solusi IoT → MQTT jelas
- Sitasi mendukung argumen

### Temuan

| Prioritas | Temuan | Saran Perbaikan |
|-----------|--------|-----------------|
| Wajib | Sitasi **(Rohman, 2021)**, **(Angriawan, 2020)**, **(Asyari, 2021)**, **(Purnamasari et al., 2021)**, **(Sitinjak & Suwita, 2020)**, **(Amirudin et al., 2021)** tidak ada di Daftar Pustaka | Tambahkan referensi lengkap ATAU ganti dengan referensi yang sudah ada |
| Wajib | Sitasi **(Suryanto & Ariefin, 2022)** — di Daftar Pustaka hanya ada **(2024)** | Verifikasi tahun yang benar, seragamkan |
| Wajib | **Hasil wawancara** (Lampiran 1) tidak dipakai di latar belakang | Tambahkan 1 paragraf bukti lapangan: 20 kandang, penutupan manual tiap 2–3 jam, repot saat hujan, peternak mendukung otomatisasi. Rujuk Lampiran 1 |
| Disarankan | **Tujuan penelitian** sudah diuraikan di latar belakang (*"Tujuan utama dari penelitian ini..."*) | Ringkas; detail tujuan hanya di §1.4 |
| Disarankan | **Metode Prototipe** dijelaskan di latar belakang | Singkatkan; detail ada di Bab III |
| Opsional | Klaim heat stress ↔ pemberian pakan — hubungan kausal perlu hati-hati | Redaksi: *"ketidakstabilan pakan dapat memperburuk kondisi stres termal"* |

**Contoh paragraf tambahan dari wawancara:**
> Berdasarkan wawancara dengan peternak di AR Farm Simpang Pasir (Lampiran 1), pengelolaan kandang masih dilakukan secara manual, termasuk penutupan atap setiap 2–3 jam dan penanganan hujan yang memakan waktu karena jumlah kandang yang banyak.

---

## 1.2 Rumusan Masalah

### Yang Sudah Baik
- Mencakup perancangan + pengujian, selaras dengan tujuan

### Saran (Opsional)
Pertimbangkan dipecah menjadi dua pertanyaan penelitian agar lebih jelas:
1. Bagaimana merancang dan membangun prototipe sistem otomatisasi kandang ayam kontes terintegrasi protokol MQTT?
2. Bagaimana menguji fungsionalitas sistem serta membandingkan performa broker HiveMQ dan EMQX?

---

## 1.3 Batasan Masalah

### Temuan Wajib

| Temuan | Perbaikan |
|--------|-----------|
| Typo **"kendang"** | **"kandang"** |
| Typo **"Telemetry Transfer"** | **"Telemetry Transport"** |

### Yang Sudah Baik
- Batasan prototipe, dua fungsi utama (atap + pakan), dua broker, tiga parameter QoS — jelas

### Saran Tambahan
- Tambahkan: *"Pengujian QoS dilakukan pada QoS Level 0"*
- Tambahkan: *"Dashboard berbasis web (HTML/CSS), bukan aplikasi mobile native"*
- Tambahkan: *"Menggunakan broker MQTT publik untuk keperluan prototipe"*

---

## 1.4 Tujuan Penelitian

### Yang Sudah Baik
- Spesifik, terukur, selaras dengan rumusan masalah

### Saran Opsional
Pecah menjadi 2 poin bernomor agar lebih mudah dibaca.

---

## Catatan Konsistensi Istilah (Lintas Bab)

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Istilah **"performansi"**, **"performa"**, dan **"kinerja"** dipakai bergantian di Bab I–V | Pilih satu istilah dominan (mis. **"performa"**) dan konsistenkan |
| Opsional | Judul **"PERANCANGAN"** vs teks **"membangun/implementasi"** | Boleh tetap (rancang bangun); pastikan selaras di abstrak & kesimpulan |

---

## 1.5 Manfaat Penelitian

### Yang Sudah Baik
- Struktur penulis / mahasiswa / peternak sudah baik

### Saran
- Bagian mahasiswa agak umum — tambahkan contoh konkret (referensi praktikum IoT)
- Hindari klaim berlebihan: *"kepastian data terkelola akurat"* → *"membantu meningkatkan akurasi pengelolaan data"*
- Poin **"2. Mahasiswa"** jarang dipakai di skripsi individu — pertimbangkan digabung ke manfaat teoretis/praktis atau ubah redaksi *"bagi akademisi/mahasiswa Informatika"*

---

## 1.6 Kontribusi Penelitian

### Yang Sudah Baik
- Diferensiasi: otomatisasi + evaluasi broker MQTT

### Saran
- Tambahkan hasil kuantitatif singkat (EMQX vs HiveMQ)
- Tambahkan kontribusi praktis: prototipe miniatur 40×40×50 cm

---

## Sitasi Bab I — Cek Daftar Pustaka

| Sitasi di teks | Ada di Daftar Pustaka? |
|----------------|------------------------|
| Rohman, 2021 | Tidak |
| Angriawan, 2020 | Tidak (ada 2024) |
| Rohmah, 2023 | Ya |
| Kasim, 2020 | Tidak (ada 2023) |
| Asyari, 2021 | Tidak (ada 2024) |
| Purnamasari et al., 2021 | Tidak |
| Sitinjak & Suwita, 2020 | Tidak |
| Amirudin et al., 2021 | Tidak |
| Suryanto & Ariefin, 2022 | Tidak (ada 2024) |

---

## Checklist Revisi Bab I

```
[ ] Koreksi typo "kendang" dan "Telemetry Transfer"
[ ] Integrasikan ringkasan wawancara (Lampiran 1) ke §1.1
[ ] Lengkapi 9 referensi yang belum ada / tidak cocok di Daftar Pustaka
[ ] Singkat tujuan & metode di latar belakang
[ ] Tambahkan batasan QoS 0, dashboard web, broker publik
[ ] (Opsional) Pecah rumusan masalah menjadi 2 pertanyaan
```

**Estimasi waktu revisi:** 2–3 jam
