# Audit — Bagian Awal (Pra-Bab)

**Halaman:** i–xvi (cover s/d daftar singkatan)  
**Status:** Perlu revisi sebelum cetak

---

## Ringkasan

Bagian awal sudah memuat komponen standar skripsi. Revisi terutama pada kata pengantar, kelengkapan halaman pengesahan, dan konsistensi daftar gambar.

---

## 1. Halaman Judul & Pengesahan

### Yang Sudah Baik
- Judul konsisten di seluruh halaman awal
- NIM, nama, fakultas, dan tahun sudah benar
- Pernyataan keaslian sudah ada (tanggal 07 Juli 2026, nama & NIM benar)
- Halaman pengesahan memuat pembimbing I & II, dekan, tanggal sidang (30 Juni 2026)

### Temuan & Perbaikan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | **"07 juli 2026"** — huruf kecil | Ubah menjadi **"07 Juli 2026"** |
| Wajib | Halaman pengesahan **belum memuat Penguji I & II** (Medi Taruk, Reza Wardhana), padahal disebut di Kata Pengantar | Sesuaikan template UNMUL: tambah lembar/kolom pengesahan sidang penguji |
| Wajib | **Tanda tangan & materai masih kosong** (hal. ii–iii) | Lengkapi sebelum cetak final |
| Disarankan | Gelar pembimbing II: **"M.T."** vs **"MT"** (abstrak) | Seragamkan **"M.T."** di seluruh dokumen |
| Disarankan | Gelar Dekan tidak konsisten: Pengesahan punya **ASEAN Eng., APEC Eng.** — Kata Pengantar hanya **APEC Eng.** | Samakan gelar di semua halaman |

---

## 2. Abstrak (Indonesia & Inggris)

### Yang Sudah Baik
- Abstrak mencakup latar, tujuan, metode, komponen, pengujian, dan hasil
- Terjemahan Inggris secara umum sudah baik

### Temuan & Perbaikan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Hasil perbandingan broker tidak dirinci di abstrak | Tambahkan 1 kalimat hasil singkat (throughput, delay, packet loss) |
| Disarankan | Satuan throughput belum disebut jika angka ditambahkan | Gunakan satu satuan konsisten (bps atau Kbps) |
| Opsional | Kata kunci bisa ditambah **"prototipe"** atau **"smart farming"** | Sesuai kebijakan prodi |
| Opsional | Abstrak ID & EN: istilah **performa/performance** vs **performansi** di badan teks | Selaraskan setelah revisi istilah di seluruh skripsi |

---

## 3. Kata Pengantar

### Temuan Wajib

| No | Temuan | Perbaikan |
|----|--------|-----------|
| 1 | Masih tertulis **"proposal skripsi"** (2 kali) | Ganti menjadi **"skripsi"** |
| 2 | Kalimat *"disusun sebagai salah satu tahapan dalam menyelesaikan skripsi"* | Ganti: *"disusun sebagai salah satu syarat untuk menyelesaikan pendidikan..."* |
| 3 | Pronomina **"kami"** vs **"saya"** tidak konsisten | Skripsi individu → gunakan **"saya"** di seluruh kata pengantar |
| 4 | Penutup hanya **"Penulis"** tanpa nama | Tambahkan **Joy Disanto Nupa** |

**Contoh paragraf pembuka:**
> Puji syukur kepada Tuhan Yang Maha Esa sehingga dapat menyelesaikan skripsi dengan judul "PERANCANGAN SISTEM OTOMATISASI KANDANG AYAM KONTES TERINTEGRASI DENGAN PROTOKOL MQTT". Skripsi ini disusun sebagai salah satu syarat untuk menyelesaikan pendidikan pada Program Studi S1 Informatika, Fakultas Teknik, Universitas Mulawarman.

### Yang Sudah Baik
- Ucapan terima kasih lengkap (orang tua, dekan, koordinator, pembimbing, penguji, dosen, teman)

---

## 4. Daftar Isi, Tabel, Gambar, Lampiran

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | **Gambar 5.0, 5.1, 5.2** di Daftar Gambar padahal isinya di **Bab IV** | Renomori menjadi **Gambar 4.10, 4.11, 4.12** |
| Disarankan | Judul Gambar 3.2 di Daftar Isi: *"Arsitektur Sistem Kandang"* vs teks: *"...Otomatisasi Kandang"* | Seragamkan judul |
| Disarankan | Format subbab Bab IV tidak rapi (spasi leader dots) | Rapikan di Word |
| Disarankan | Halaman Bab II di daftar isi: **"...5'"** — karakter aneh | Periksa, pastikan hanya angka **"5"** |
| Opsional | Tidak ada **Daftar Rumus** (padahal ada persamaan 2.1–2.3) | Tambahkan jika diwajibkan prodi |

---

## 5. Daftar Istilah & Daftar Singkatan

### Yang Sudah Baik
- Istilah teknis utama sudah tercakup (MQTT, broker, ESP32, QoS, dll.)

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | **RTC** tercantum di Daftar Singkatan, tetapi **tidak dipakai** di implementasi | Hapus RTC, atau jelaskan & implementasikan jika memang dipakai |
| Disarankan | Penulisan **"Water Sensor"** vs **"water sensor"** tidak konsisten | Pilih satu gaya |
| Opsional | Tambahkan istilah **Dashboard**, **Publish/Subscribe** | Jika sering dipakai di Bab IV |

---

## Checklist Revisi — Bagian Awal

```
[ ] Ganti "proposal skripsi" → "skripsi"
[ ] Konsistenkan pronomina "saya"
[ ] Tambahkan nama penulis di penutup kata pengantar
[ ] Koreksi "07 juli" → "07 Juli"
[ ] Lengkapi pengesahan penguji sidang + tanda tangan + materai
[ ] Seragamkan gelar M.T. dan gelar Dekan
[ ] Perbaiki penomoran gambar di Daftar Gambar (5.x → 4.x)
[ ] (Opsional) Tambah Daftar Rumus dan perkaya abstrak
```

**Estimasi waktu revisi:** 1–2 jam
