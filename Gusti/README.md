# Laporan Audit Final Draft Skripsi — Gusti Dimas Novarossi

**Mahasiswa:** Gusti Dimas Novarossi (NIM 2109106124)  
**Judul:** Penerapan Model Waterfall dalam Pengembangan Website Chatbot AI pada Platform Resmeku  
**Pembimbing:** Anton Prafanto, S.Kom., M.T. & Gubtha Mahendra Putra, S.Kom., M.Eng.  
**Penguji:** Masna Wati, S.Si., M.T. (I) & Andi Tejawati, M.Si. (II)  
**Dokumen:** `SKRIPSI_GUSTI DIMAS NOVAROSSI_2109106124.pdf` (95 halaman)  
**Tanggal audit:** 9 Juli 2026 (dicek ulang 2×)

---

## Untuk Pembimbing — Ringkasan Eksekutif

| Pertanyaan | Jawaban |
|------------|---------|
| Substansi layak skripsi Informatika S1? | **Ya** — implementasi + pengujian memadai |
| Layak cetak perpustakaan sekarang? | **Belum** — revisi format 3–5 hari kerja |
| Revisi sidang sudah cukup? | **Sebagian** — flowchart ✓; administratif, §2.1, hal. PDF 71 belum |
| Risiko terbesar? | Pengesahan placeholder + penguji tidak ada; rujukan gambar salah §4.4.4–4.4.6 |

---

## Untuk Mahasiswa — Baca Ini Dulu

Posisi kamu **sudah pasca sidang**. Yang perlu dilakukan sekarang bukan menulis ulang, melainkan **rapikan draft final** sebelum cetak.

**Urutan kerja:**
1. [bagian-awal.md](bagian-awal.md) — pengesahan, pernyataan, kata pengantar, abstrak
2. [bab-iv.md](bab-iv.md) — betulkan rujukan gambar + layout hal. PDF 71
3. [bab-ii.md](bab-ii.md) — rapikan §2.1 penelitian terkait (catatan Bu Masna)
4. File bab lainnya sesuai checklist di bawah

**Checklist wajib sebelum cetak:**
- [ ] Pengesahan: tanggal + tanda tangan Pembimbing I & II + **Penguji I & II** + Dekan
- [ ] Pernyataan keaslian: tanggal + materai + tanda tangan
- [ ] Kata pengantar: ganti semua *proposal* → *skripsi*; judul lengkap pakai **WEBSITE**; tahun **2026**
- [ ] ABSTRACT Inggris: *functional, particularly, response suitability, delayed response time*
- [ ] §4.4.4–4.4.6: rujukan gambar 4.11–4.13 → **4.14–4.16**
- [ ] §2.1: tiap penelitian terkait punya 1 kalimat topik di awal
- [ ] Daftar Isi: spacing rapi (catatan Pak Gubtha)
- [ ] Hapus halaman kosong di akhir PDF (hal. 95)

---

## Daftar Laporan Per Bab

| File | Bagian Skripsi |
|------|----------------|
| [bagian-awal.md](bagian-awal.md) | Cover, pengesahan, abstrak, kata pengantar, daftar |
| [bab-i.md](bab-i.md) | BAB I — Pendahuluan |
| [bab-ii.md](bab-ii.md) | BAB II — Tinjauan Pustaka |
| [bab-iii.md](bab-iii.md) | BAB III — Metodologi Penelitian |
| [bab-iv.md](bab-iv.md) | BAB IV — Hasil dan Pembahasan |
| [bab-v.md](bab-v.md) | BAB V — Kesimpulan dan Saran |
| [daftar-pustaka-lampiran.md](daftar-pustaka-lampiran.md) | Daftar Pustaka & Lampiran |

*Folder ini hanya berisi 8 file di atas — tidak ada file lain.*

---

## Penilaian Singkat

| Aspek | Status |
|-------|--------|
| Substansi penelitian | **Baik** — chatbot AI + KB + Waterfall + studi kasus Resmeku |
| Implementasi & pengujian | **Baik** — Blackbox 100%, UAT 86%, uji respons ~2 detik |
| Format & konsistensi | **Perlu perbaikan besar** — placeholder, rujukan gambar, typo |
| Sitasi & referensi | **Cukup** — sitasi utama ada di DP; Wayahdi 2023a/b duplikat |
| Kelengkapan dokumen | **Perlu perbaikan** — halaman legal template; lampiran hanya link |
| **Siap cetak perpustakaan** | **Belum — revisi wajib dulu** |

Estimasi revisi: **3–5 hari kerja**.

---

## 12 Temuan Paling Kritis

1. **Pengesahan (PDF hal. iv):** tanggal placeholder; **Penguji I & II tidak ada** (Kata Pengantar sudah berterima kasih ke mereka)
2. **Pernyataan keaslian:** *"Tgl bln thn"* + materai kosong
3. **Kata pengantar:** *proposal/proposal skripsi* muncul **3 kali**; judul tanpa **WEBSITE**; tahun **2025**
4. **§4.4.4–4.4.6:** teks merujuk Gambar **4.11–4.13**, caption benar **4.14–4.16** — **diverifikasi ulang ✓**
5. **Tabel 4.4 vs 4.5 Skenario 1:** hitung **92,6%**, rekapitulasi **93%** — selaraskan (bulatkan + catatan jika perlu)
6. **§2.1 Penelitian Terkait (isi hal. 5):** belum ada penjelasan topik di awal tiap poin — catatan Bu Masna
7. **ABSTRACT Inggris:** *funtional, particulary, response sustainability, delayed responses time*
8. **PDF hal. 71 (isi hal. 55):** Gambar 4.10 layout kurang rapi, teks lanjut di hal. berikutnya
9. **§3.4.4 UAT:** peneliti mengoreksi jawaban sebelum responden menilai — risiko bias, perlu diklarifikasi
10. **§1.3 vs §4.5.3:** batasan mengecualikan uji performa, tapi ada uji kecepatan respons
11. **§5.2 saran RAG:** frame sebagai pengembangan lanjutan (bukan koreksi bahwa KB belum ada)
12. **PDF hal. 95 kosong** — hapus sebelum export final

---

## Status Revisi Penguji

| Penguji | Catatan | Hasil cek ulang |
|---------|---------|-----------------|
| Bu Masna | Titik/koma hal. 66 | Minor — proofread §4.2.2 |
| Bu Masna | Flowchart proses sebelum End | **Sudah ✓** (Gambar 3.2) |
| Bu Masna | Kerapian hal. 71 | **Belum ✓** |
| Bu Masna | Penomoran romawi | **Sudah ii–xvi**; cover tanpa nomor — cek template prodi |
| Bu Masna | Penelitian terkait hal. 5 | **Belum ✓** |
| Bu Andi | — | — |
| Pak Gubtha | Spacing daftar isi | **Belum ✓** |

---

## Temuan Lintas Bab

| No | Temuan | File |
|----|--------|------|
| 1 | Judul resmi *WEBSITE*; kata pengantar tidak | `bagian-awal.md` |
| 2 | Penguji di KP, absen di pengesahan | `bagian-awal.md` |
| 3 | Batasan vs uji kecepatan respons | `bab-i.md`, `bab-iv.md` |
| 4 | KB filter vs saran RAG Bab V | `bab-v.md` |
| 5 | Abstrak ↔ Bab IV ↔ Bab V konsisten (100%, 86%) | OK |
| 6 | Wayahdi 2023a = 2023b duplikat | `daftar-pustaka-lampiran.md` |

---

## Hasil Audit Ulang (9 Juli 2026)

| Aspek audit sebelumnya | Verdict cek ulang |
|------------------------|-------------------|
| Rujukan gambar §4.4.4–4.4.6 salah | **Tetap valid** — teks 4.11/4.12/4.13, caption 4.14/4.15/4.16 |
| Flowchart sudah diperbaiki | **Tetap valid** |
| Kata pengantar *proposal* 2× | **Dikoreksi** → **3×** (*proposal skripsi* 2× + *Proposal ini* 1×) |
| Typo *kompilbitas* di daftar temuan | **Dikoreksi** → *Kompatilbitas* |
| Skor & substansi penelitian | **Tetap valid** — tidak perlu ubah verdict |
| Folder `extracted/` untuk mahasiswa | **Dihapus** — hanya 8 file inti yang disisakan |

---

*Audit final draft pasca sidang. Mahasiswa cukup buka README ini lalu file per bab sesuai urutan di atas.*
