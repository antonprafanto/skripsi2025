# Audit — BAB I: Pendahuluan

**Halaman isi:** 1–4 (PDF hal. 17–20)  
**Status:** Cukup baik — revisi minor

---

## Ringkasan Bab

Bab I membangun argumen dengan runtut: layanan pelanggan digital → chatbot AI → masalah Resmeku → relevansi Waterfall → ruang lingkup penelitian. Rumusan masalah, tujuan, batasan, manfaat, dan kontribusi **selaras** dengan implementasi di Bab IV.

**Nilai substansi:** 8/10  
**Nilai format:** 7,5/10

---

## 1.1 Latar Belakang

### Yang sudah baik
- Sitasi mutakhir (2022–2025) mendukung argumen layanan pelanggan & chatbot
- Transisi ke **Platform Resmeku** spesifik dan masuk akal (respons lambat, FAQ berulang)
- Justifikasi **Waterfall** untuk kebutuhan terdefinisi — konsisten dengan §4.6.1

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | Klaim masalah Resmeku (Kejor & Purwanti, 2025) — pastikan referensi benar-benar membahas Resmeku | Jika referensi generik Node.js, ganti dengan bukti observasi sendiri atau sitasi Resmeku (2026) |
| Sedang | Tidak ada **angka kuantitatif lokal** (mis. rata-rata waktu balas email) | 1 kalimat data observasi memperkuat latar |

---

## 1.2 Rumusan Masalah

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Satu pertanyaan komprehensif — acceptable untuk skripsi final | Opsional: pecah menjadi sub-pertanyaan implisit di tujuan |
| Sedang | Spasi ganda *"chatbot AI  berbasis"* | Hapus spasi extra |

---

## 1.3 Batasan Masalah

### Yang sudah baik
- Model **qwen3.5-flash** Alibaba Cloud disebut eksplisit
- Tidak fine-tune / tidak audit keamanan mendalam — jujur
- Blackbox + UAT sebagai metode uji — jelas

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Poin 3: *"Pengujian tidak mencakup pengujian performa teknis seperti beban sistem"* | **Kontradiksi** dengan §4.5.3 (uji kecepatan respons). Tambahkan pengecualian: *"tidak termasuk load/stress testing; pengujian waktu respons tunggal diperbolehkan"* |
| Sedang | Tidak membahas privasi data percakapan / API pihak ketiga | 1 kalimat etika singkat memperkuat batasan |

---

## 1.4 Tujuan Penelitian

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | 4 tujuan operasional, selaras rumusan & Bab IV | — |
| OK | Tujuan 4 (uji fungsionalitas + kesesuaian respons) terukur | — |

---

## 1.5 Manfaat Penelitian

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Penulis, mahasiswa, pengguna Resmeku — struktur jelas | — |
| Sedang | Manfaat mahasiswa agak generik | Boleh tambah 1 contoh konkret (referensi arsitektur widget embed) |

---

## 1.6 Kontribusi Penelitian

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| OK | Kontribusi: sistem chatbot multi-platform + KB + dokumentasi Waterfall | — |
| Sedang | Klaim *"dapat digunakan berbagai platform website"* — sudah dibuktikan 1 studi kasus | OK untuk S1; cukup sebutkan kode embed sebagai mekanisme portabilitas |

---

## Kesimpulan Bab I

Bab I **tidak perlu ditulis ulang**. Fokus revisi: **selaraskan batasan dengan uji non-fungsional** dan perkuat bukti masalah Resmeku jika masih ada waktu.
