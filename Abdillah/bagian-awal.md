# Audit — Bagian Awal (Pra-Bab)

**Halaman:** i–xviii  
**Status:** Perlu revisi wajib sebelum cetak

---

## Ringkasan

Bagian awal memuat komponen lengkap (termasuk halaman persembahan). Namun ada **placeholder dan typo kritis** di pernyataan keaslian, serta sisa bahasa proposal di kata pengantar.

---

## 1. Halaman Judul & Pengesahan

### Yang Sudah Baik
- Judul konsisten (BERBASIS) di cover dan pengesahan
- NIM, nama, pembimbing, dekan, tanggal sidang (30 Juni 2026) dan pengesahan (07 Juli 2026) sudah benar
- Halaman persembahan ada (lebih lengkap dari draft minimal)

### Temuan Wajib — Penguji Tidak Ada di Pengesahan

Halaman pengesahan (PDF hal. iv) hanya memuat:
- Pembimbing I & II
- Dekan Fakultas Teknik

**Tidak ada blok Penguji I dan Penguji II**, padahal kata pengantar berterima kasih kepada:
- **Ir. Addy Suyatno, S.Kom., M.Kom.** (Penguji I)
- **Medi Taruk, S.Kom., M.Cs.** (Penguji II)

**Perbaikan:** Tambahkan blok penguji + tanda tangan sesuai template skripsi prodi.

### Temuan Lainnya

| Prioritas | Temuan | Perbaikan |
|-----------|--------|-----------|
| Disarankan | Gelar pembimbing II: **M.T.** (pengesahan) vs **MT.** (abstrak) | Seragamkan **M.T.** |
| Disarankan | **M.Cs..** — titik ganda pada Pembimbing I (abstrak) | Koreksi **M.Cs.** |
| Disarankan | Nama dekan: **"H. Tamrin"** (pengesahan) vs **"Tamrin"** tanpa H. (kata pengantar) | Samakan |
| Disarankan | **ASEAN Eng.** vs **ASEAN.Eng.** | Samakan format gelar |
| Disarankan | Kapitalisasi: **Manna wa Salwa** vs **Manna Wa Salwa** (kata pengantar baris judul) | Seragamkan |

---

## 2. Pernyataan Keaslian

### Temuan Wajib

| No | Temuan | Perbaikan |
|----|--------|-----------|
| 1 | **"LAYANAN BEBASIS ANDROID"** — typo | **BERBASIS** |
| 2 | Tanggal: **"Samarinda, Tgl bln thn"** — placeholder | Isi tanggal lengkap, mis. **07 Juli 2026** |
| 3 | **Materai** — kotak kosong | Tempel materai & tanda tangan |
| 4 | **"gelar kesarjanaan"** | **gelar kesarjanaan** (jika memang standar prodi; cek template) |

---

## 3. Abstrak (Indonesia & Inggris)

### Yang Sudah Baik
- Abstrak lengkap: latar, tujuan, metode prototype, teknologi (Jetpack Compose, Laravel, Firebase), hasil pengujian Black Box
- Abstract Inggris paralel dan berkualitas baik

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Kata kunci: **"Larave"** (huruf l hilang); tidak ada **Firebase** padahal inti autentikasi | **Laravel**; pertimbangkan **Firebase** |
| Disarankan | Keywords EN: **"Laravel Prototype Method"** — kurang koma | **"Laravel, Prototype Method"** atau pisah kata kunci |
| Opsional | Abstrak bisa menyebut hasil kuantitatif: 71 skenario, 100%, 15 responden | 1 kalimat tambahan |

---

## 4. Kata Pengantar

### Temuan Wajib

| No | Temuan | Perbaikan |
|----|--------|-----------|
| 1 | **"proposal skripsi"** muncul **4 kali** | Ganti semua menjadi **"skripsi"** |
| 2 | *"Proposal ini disusun sebagai salah satu tahapan..."* | *"Skripsi ini disusun sebagai salah satu syarat..."* |
| 3 | Karakter rusak pada judul (tanda **)** di teks ekstrak) | Periksa encoding di Word sebelum cetak PDF |

### Yang Sudah Baik
- Ucapan terima kasih lengkap termasuk penguji (Addy Suyatno, Medi Taruk)

---

## 5. Daftar Isi, Tabel, Gambar, Lampiran

### Temuan Wajib

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | **Tabel 2.2–2.5** (simbol UML & kelayakan) ada di Bab II tetapi **tidak di Daftar Tabel** | Tambahkan ke Daftar Tabel |
| Wajib | **Tabel 3.8 (Lanjutan)** — 4+ halaman lanjutan pengujian Black Box **tidak di Daftar Tabel** | Tambahkan entri lanjutan |
| Wajib | **Tabel 4.3, 4.4, 4.5, 4.6** ada di Bab IV tetapi **tidak tercantum di Daftar Tabel** | Tambahkan ke Daftar Tabel |
| Wajib | **Gambar 4.39** tertulis **"Gambar 4 39"** (spasi) di Daftar Gambar & caption | Koreksi menjadi **Gambar 4.39** |
| Wajib | **Gambar 4.75** — judul duplikat (*Laporan Kegiatan* 2×); salah satu seharusnya **Laporan Kinerja** | Koreksi judul |
| Disarankan | **Duplikasi judul gambar** lain: **4.24 & 4.25** (judul identik), **4.35 & 4.36** (judul identik), **3.35** (2×) | Bedakan judul atau renomori |
| Disarankan | **Gambar 2.2** (Tahapan Prototype) ada di Bab II, tidak di Daftar Gambar | Tambahkan |
| Disarankan | Tidak ada **Daftar Rumus** (Persamaan 2.1 dirujuk di Bab III & IV) | Tambahkan jika diwajibkan prodi |

---

## Checklist Revisi — Bagian Awal

```
[ ] Tambahkan Penguji I & II di halaman pengesahan + tanda tangan
[ ] Koreksi BEBASIS → BERBASIS di pernyataan keaslian
[ ] Isi tanggal lengkap + materai + tanda tangan
[ ] Ganti semua "proposal skripsi" → "skripsi"
[ ] Koreksi Larave, M.Cs.., MT./M.T., Manna wa/Wa Salwa
[ ] Tambahkan Tabel 2.2–2.5, 3.8 (Lanjutan), 4.3–4.6 ke Daftar Tabel
[ ] Tambahkan Gambar 2.2 ke Daftar Gambar
[ ] Perbaiki Daftar Gambar (4 39, duplikat 3.35/4.75, judul ganda 4.24–4.36)
[ ] (Opsional) Daftar Rumus, perkaya abstrak dengan angka hasil
```

**Estimasi waktu:** 2–3 jam (+ waktu renumber gambar jika menyentuh daftar)
