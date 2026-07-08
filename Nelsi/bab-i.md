# Audit — BAB I: Pendahuluan

**Halaman:** 3–5 (PDF)  
**Status:** Perlu revisi wajib

---

## Ringkasan Bab

Bab I sudah memuat komponen standar (latar belakang, rumusan masalah, tujuan, manfaat, batasan) dengan bahasa yang cukup rapi. Namun isinya masih **generik** — bisa dipakai untuk kelurahan mana saja. Belum ada bukti lapangan, sitasi, atau kebaruan penelitian.

**Nilai substansi:** 5/10  
**Nilai penulisan akademik:** 4/10 (tanpa sitasi)

---

## 1.1 Latar Belakang

### Yang Sudah Baik
- Alur logis: perkembangan TI → pelayanan manual → masalah antrean → WhatsApp familiar → solusi
- Objek penelitian jelas: Kelurahan Kampung Sambakungan
- Manfaat untuk masyarakat dan petugas kelurahan dijelaskan

### Temuan

| Prioritas | Temuan | Kenapa ini masalah? | Cara memperbaiki |
|-----------|--------|---------------------|------------------|
| **Wajib** | Tidak ada **data spesifik** kelurahan (jumlah permohonan, waktu tunggu, jumlah petugas) | Penguji akan bilang: "Masalahnya di mana buktinya?" | Observasi + wawancara; masukkan angka |
| **Wajib** | Tidak ada **sitasi** sama sekali | Setiap klaim faktual harus ada referensi | Sitasi UU 25/2009, Permen PANRB, We Are Social 2023 |
| **Wajib** | Tidak ada **hasil wawancara/observasi** | Skripsi harus berbasis masalah nyata | Tambah 1 paragraf bukti lapangan |
| Disarankan | Paragraf 1–2 sangat **umum** (template) | Terkesan copy-paste | Personalisasi dengan kondisi Kampung Sambakungan |
| Disarankan | Klaim "WhatsApp dapat dimanfaatkan" tanpa data penetrasi lokal | Lemah secara argumentasi | Tambah: "Berdasarkan wawancara, X dari Y warga aktif menggunakan WhatsApp" |

### Contoh paragraf yang HARUS kamu tambahkan

Setelah observasi ke kelurahan, tulis paragraf seperti ini (sesuaikan angkanya dengan hasil lapanganmu):

> Berdasarkan hasil observasi dan wawancara di Kelurahan Kampung Sambakungan pada bulan [bulan] 2026, diketahui bahwa pelayanan surat administrasi masih dilakukan secara manual. Petugas melayani rata-rata [X] permohonan surat per minggu, dengan jenis terbanyak adalah surat domisili dan surat pengantar. Masyarakat umumnya harus datang langsung ke kantor kelurahan dan menunggu antrean selama [X] menit hingga [X] jam. Selain itu, [X] dari [Y] responden warga menyatakan pernah menanyakan status surat melalui WhatsApp secara informal karena tidak ada sistem resmi. Kondisi ini menunjukkan perlunya sistem layanan terintegrasi yang memanfaatkan WhatsApp sebagai kanal komunikasi resmi (Wahyudi et al., 2022).

**Catatan:** Angka dalam [kurung] harus kamu isi sendiri dari hasil lapangan. Jangan bikin angka fiktif.

---

## 1.2 Rumusan Masalah

### Yang Sudah Baik
- Ada 3 pertanyaan penelitian
- Mencakup perancangan, efisiensi, dan kepuasan

### Temuan

| Prioritas | Temuan | Saran perbaikan |
|-----------|--------|-----------------|
| **Wajib** | Pertanyaan 2 (*efisiensi*) tidak terukur | Ubah atau tambahkan indikator di Bab III |
| **Wajib** | Pertanyaan 3 (*kepuasan*) tidak ada instrumen | Rujuk ke UAT + kuesioner Likert di Bab III |
| Disarankan | Pertanyaan 1 terlalu luas | Spesifikkan: "…terintegrasi panel admin web…" |

### Rumusan masalah yang disarankan

Ganti rumusan masalah kamu dengan versi ini (sesuaikan dengan pembimbing). **Penting:** Judul skripsi kamu menyebut *"efisiensi"* — jangan hilangkan dari rumusan masalah.

**Opsi A — 3 pertanyaan (selaras judul):**

1. Bagaimana merancang dan membangun sistem layanan surat administrasi berbasis WhatsApp terintegrasi panel admin web di Kelurahan Kampung Sambakungan?
2. Bagaimana menguji kelayakan fungsional sistem menggunakan metode Black Box Testing?
3. Bagaimana tingkat kepuasan pengguna dan **peningkatan efisiensi waktu layanan** berdasarkan User Acceptance Testing (UAT) dan perbandingan waktu layanan sebelum-sesudah implementasi?

**Opsi B — 4 pertanyaan (lebih lengkap):**

1. Bagaimana merancang dan membangun sistem layanan surat administrasi berbasis WhatsApp terintegrasi panel admin web di Kelurahan Kampung Sambakungan?
2. Bagaimana menguji kelayakan fungsional sistem menggunakan metode Black Box Testing?
3. Bagaimana **tingkat efisiensi** pelayanan surat sebelum dan sesudah implementasi sistem?
4. Bagaimana tingkat kepuasan pengguna terhadap sistem berdasarkan User Acceptance Testing (UAT)?

**Kenapa diubah?**
- Pertanyaan 1 → fokus pada **rancang bangun** (sesuai skripsi Informatika)
- Pertanyaan 2 → bisa dijawab dengan **tabel pengujian** (ya/tidak, berhasil/gagal)
- Pertanyaan 3–4 → menjawab **efisiensi** (ada di judul!) dan **kepuasan** dengan angka

---

## TEMUAN KRITIS — Lokasi Penelitian

| Aspek | Fakta |
|-------|-------|
| Kampus | Universitas Mulawarman, **Samarinda** |
| Lokasi penelitian | Kelurahan Kampung Sambakungan, Kec. Gunung Tabur, **Kab. Berau** |
| Jarak | Berau ↔ Samarinda ≈ **500+ km** |

**Ini belum dijelaskan di draft.** Penguji pasti bertanya: *"Kenapa mitra penelitian di Berau padahal kuliah di Samarinda?"*

**Yang harus kamu lakukan (pilih salah satu):**
- **Jelaskan alasan** di latar belakang (misalnya: asal/domisili Berau, sudah ada izin kelurahan, ada kerabat di sana)
- **Atau ganti lokasi** ke kelurahan di Samarinda agar observasi lebih mudah
- **Atau** dokumentasikan rencana kunjungan (frekuensi, biaya, mode observasi)

---

## 1.3 Tujuan Penelitian

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Poin 2 & 3 adalah **manfaat**, bukan tujuan penelitian | Pisahkan: tujuan = apa yang kamu lakukan; manfaat = apa dampaknya |
| **Wajib** | Tidak selaras dengan rumusan masalah | Setiap rumusan masalah harus punya tujuan pasangan |

### Tujuan penelitian yang disarankan

1. Merancang dan membangun sistem layanan surat administrasi berbasis WhatsApp terintegrasi panel admin web di Kelurahan Kampung Sambakungan.
2. Menguji kelayakan fungsional sistem menggunakan metode Black Box Testing.
3. Mengukur tingkat kepuasan pengguna terhadap sistem berdasarkan User Acceptance Testing (UAT).

### Perbedaan tujuan vs manfaat (penting!)

| Tujuan (apa yang kamu kerjakan) | Manfaat (dampak untuk orang lain) |
|----------------------------------|-----------------------------------|
| Membangun sistem | Masyarakat jadi mudah mengurus surat |
| Menguji fungsionalitas | Petugas punya alat kerja digital |
| Mengukur kepuasan | Peneliti dapat pengalaman |

Manfaat sudah kamu tulis dengan baik di §1.4 — jangan dicampur ke tujuan.

---

## 1.4 Manfaat Penelitian

### Yang Sudah Baik
- Dibagi manfaat teoritis dan praktis
- Mencakup masyarakat, kelurahan, dan peneliti
- Bahasa jelas

### Saran minor
- Manfaat teoritis bisa lebih spesifik: *"…khususnya integrasi WhatsApp Cloud API dengan sistem informasi pelayanan publik di tingkat kelurahan"*

---

## 1.5 Batasan Masalah

### Yang Sudah Baik
- Lokasi spesifik (Kampung Sambakungan)
- Jenis surat disebutkan (domisili, pengantar, keterangan usaha)
- Platform WhatsApp disebutkan

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Poin 2: "WhatsApp Business API **atau** Chatbot" — belum diputuskan | Tentukan satu. Disarankan: *"WhatsApp Cloud API sebagai kanal notifikasi dan chatbot" |
| **Wajib** | Poin 4: "pendekatan pengembangan yang sesuai" — terlalu kabur | Tulis: *"Metode Waterfall"* |
| **Wajib** | Opsi **Baileys** (di Bab III) harus dihapus dari batasan | Tidak pantas untuk layanan pemerintahan |
| Disarankan | "Surat administrasi lainnya" terlalu luas | Batasi: sebutkan 3–4 jenis surat spesifik setelah observasi |
| Disarankan | Tidak ada batasan teknologi | Tambah: *"Backend menggunakan Laravel, database MySQL, web server Apache"* |
| Disarankan | Tidak ada batasan pengujian | Tambah: *"Pengujian fungsional menggunakan Black Box Testing; pengujian kepuasan menggunakan UAT dengan minimum 15 responden"* |

### Contoh batasan masalah yang lengkap

1. Sistem hanya mencakup layanan surat administrasi di Kelurahan Kampung Sambakungan.
2. Jenis surat yang diproses: surat pengantar, surat domisili, surat keterangan usaha, dan surat keterangan tidak mampu.
3. Platform komunikasi masyarakat menggunakan WhatsApp Cloud API; petugas kelurahan mengelola permohonan melalui panel admin berbasis web.
4. Sistem dikembangkan menggunakan metode Waterfall.
5. Bahasa pemrograman backend Laravel (PHP), database MySQL, web server Apache.
6. Pengujian fungsional menggunakan Black Box Testing; pengujian kepuasan menggunakan UAT.

---

## Yang Belum Ada di Bab I (Tambahkan)

| Subbab | Perlu? | Keterangan |
|--------|--------|------------|
| 1.6 Sistematika Penulisan | Disarankan | 1 paragraf per bab — umum di UNMUL |
| Kebaruan penelitian | Wajib (bisa di akhir 1.1 atau di Bab II) | Jelaskan apa bedanya dengan penelitian lain |

---

## Checklist Revisi Bab I

```
[ ] Kunjungi kelurahan & catat data lapangan
[ ] Tambahkan paragraf bukti observasi/wawancara (min. 1 paragraf)
[ ] Tambahkan sitasi di setiap paragraf (min. 5 sitasi di Bab I)
[ ] Perbaiki rumusan masalah (3 pertanyaan yang terukur)
[ ] Perbaiki tujuan penelitian (pisahkan dari manfaat)
[ ] Perjelas batasan masalah (teknologi, metode, jenis surat)
[ ] Hapus opsi "atau" di batasan
[ ] Tambahkan subbab sistematika penulisan (opsional)
```

**Estimasi waktu:** 3–5 hari (termasuk kunjungan lapangan)

---

## Pertanyaan yang Mungkin Ditanyakan Penguji

| Pertanyaan penguji | Kamu harus bisa jawab |
|--------------------|----------------------|
| "Apa masalah spesifik di Kampung Sambakungan?" | Data observasi + wawancara |
| "Kenapa pakai WhatsApp, bukan aplikasi mobile?" | Familiaritas warga, biaya rendah, tidak perlu install app baru |
| "Apa bedanya dengan skripsi surat kelurahan lain?" | Kebaruan: lokasi, fitur, integrasi spesifik |
| "Efisiensi diukur bagaimana?" | Perbandingan waktu layanan sebelum-sesudah |
| "Berapa responden kuesioner?" | Min. 15 (sebutkan di batasan) |
