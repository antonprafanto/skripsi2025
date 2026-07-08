# Laporan Audit Draft Skripsi — NELSI

**Mahasiswa:** Nelsi (NIM 2309106120)  
**Judul:** Rancang Bangun Sistem Layanan Surat Administrasi Kelurahan Kampung Sambakungan Berbasis WhatsApp untuk Meningkatkan Efisiensi Pelayanan Publik  
**Program Studi:** Informatika, Fakultas Teknik, Universitas Mulawarman  
**Dokumen:** `SKRIPSI_NELSI.pdf` (14 halaman — draft proposal awal)  
**Tanggal audit:** 8 Juli 2026  
**Tahap dokumen:** Proposal awal (hanya Bab I–III + Daftar Pustaka)

---

## Untuk Mahasiswa — Baca Ini Dulu

Skripsi itu **bukan sekadar menulis**. Urutan kerja yang benar:

```
1. Cari masalah nyata di lapangan (observasi + wawancara)
2. Baca penelitian orang lain (minimal 5–8 jurnal/skripsi serupa)
3. Tulis proposal (Bab I–III) dengan bukti dan sitasi
4. Setujui dengan pembimbing → sidang proposal
5. Bangun sistem (koding + database + integrasi WhatsApp)
6. Uji sistem → tulis Bab IV
7. Tulis kesimpulan → sidang akhir
```

**Posisi draft kamu sekarang:** Kamu baru di langkah awal langkah 3. Topiknya **boleh dilanjutkan**, tetapi isinya **belum cukup** untuk sidang proposal. Jangan panik — semua mahasiswa baru melewati tahap ini. Ikuti file audit per bab di bawah ini satu per satu.

---

## Daftar Laporan Per Bab

| File | Isi | Mulai dari sini jika… |
|------|-----|------------------------|
| [panduan-mahasiswa.md](panduan-mahasiswa.md) | **Panduan lengkap untuk mahasiswa baru** | Kamu bingung harus mulai dari mana |
| [bagian-awal.md](bagian-awal.md) | Cover, abstrak, daftar isi | Kamu mau lengkapi format dokumen |
| [bab-i.md](bab-i.md) | BAB I — Pendahuluan | Kamu mau perbaiki latar belakang & rumusan masalah |
| [bab-ii.md](bab-ii.md) | BAB II — Tinjauan Pustaka | **PRIORITAS UTAMA** — bab paling lemah |
| [bab-iii.md](bab-iii.md) | BAB III — Metodologi | Kamu mau tentukan teknologi & metode uji |
| [bab-iv-v-rencana.md](bab-iv-v-rencana.md) | Rencana Bab IV–V (belum ditulis) | Kamu mau tahu apa yang harus dikerjakan nanti |
| [daftar-pustaka-lampiran.md](daftar-pustaka-lampiran.md) | Daftar Pustaka & referensi | Kamu mau perbaiki sitasi |
| [template-penelitian-terdahulu.md](template-penelitian-terdahulu.md) | Template siap pakai Tabel 2.1 | Kamu mau langsung isi Bab II |

---

## Penilaian Singkat

| Aspek | Status | Penjelasan singkat |
|-------|--------|-------------------|
| **Topik penelitian** | Layak dengan syarat | Banyak skripsi serupa, tapi masih diterima di prodi Informatika jika ada implementasi kuat |
| **Substansi masalah** | Belum cukup | Belum ada data nyata dari Kelurahan Kampung Sambakungan |
| **Tinjauan pustaka** | Belum memadai | Penelitian terdahulu hampir kosong; sitasi dalam teks = nol |
| **Metodologi** | Belum matang | Teknologi masih "PHP/Python atau Node.js" — belum diputuskan |
| **Implementasi** | Belum ada | Normal untuk tahap proposal, tapi rencananya harus jelas |
| **Sitasi & referensi** | Perlu perbaikan besar | Banyak referensi tidak dipakai; sebagian perlu diverifikasi |
| **Kelengkapan dokumen** | Belum lengkap | Abstrak, Bab IV–V, lampiran belum ada |
| **Siap sidang proposal** | **Belum** | Estimasi revisi: **2–3 minggu** kerja fokus |

---

## Skor Penilaian

| Dimensi | Skor | Artinya |
|---------|------|---------|
| Substansi masalah | 5/10 | Masalah umum, belum terbukti di lapangan |
| Kebaruan (novelty) | 3/10 | Banyak penelitian serupa; belum dijelaskan bedanya |
| Kedalaman teknis Informatika | 4/10 | Stack & arsitektur belum jelas |
| Metodologi | 5/10 | Kerangka ada, detail belum |
| Tinjauan pustaka | 2/10 | Bab terlemah |
| Penulisan akademik | 4/10 | Bahasa cukup rapi, tapi tanpa sitasi |
| Kelengkapan dokumen | 2/10 | Baru 3 bab dari ±6 bab |
| **Rata-rata** | **3,6/10** | Masih tahap awal — bisa ditingkatkan |

---

## 12 Temuan Paling Penting (Urutkan Perbaikannya!)

| No | Temuan | Mengapa penting? | File panduan |
|----|--------|------------------|--------------|
| 1 | **Penelitian terdahulu hampir kosong** — hanya 2 paragraf umum | Penguji pasti menolak proposal tanpa ini | `bab-ii.md`, `template-penelitian-terdahulu.md` |
| 2 | **Tidak ada sitasi dalam teks** meski daftar pustaka sudah 35+ entri | Melanggar aturan penulisan ilmiah | `daftar-pustaka-lampiran.md` |
| 3 | **Belum ada bukti lapangan** dari Kelurahan Kampung Sambakungan | Masalah penelitian belum terbukti nyata | `bab-i.md`, `panduan-mahasiswa.md` |
| **4** | **Lokasi penelitian di Berau, kampus di Samarinda** — jarak ±500 km, belum dijustifikasi | Observasi berulang sulit; penguji akan menanyakan | `bab-i.md` |
| 5 | **Teknologi belum diputuskan** (PHP/Python/Node.js, API/Baileys) | Skripsi Informatika harus spesifik teknis | `bab-iii.md` |
| 6 | **Baileys disebut sebagai opsi** | Library tidak resmi, melanggar aturan WhatsApp, berisiko banned | `bab-iii.md` |
| 7 | **Judul menyebut "efisiensi" tapi belum terukur** di rumusan/tujuan | Judul dan isi harus selaras | `bab-i.md` |
| 8 | **Beberapa referensi perlu diverifikasi** — perkiraan 8–12 entri | Risiko dianggap referensi fiktif | `daftar-pustaka-lampiran.md` |
| 9 | **Tujuan penelitian poin 2–3 lebih mirip manfaat** | Tidak selaras dengan rumusan masalah | `bab-i.md` |
| 10 | **Kerangka penelitian disebut tapi tidak ada gambarnya** | Bab III tidak lengkap tanpa diagram | `bab-iii.md` |
| 11 | **Topik sangat mirip penelitian lain** (Sipuas, SIPANDHA, dll.) | Harus jelaskan apa bedanya penelitianmu | `bab-ii.md` |
| **12** | **Keamanan data warga & etika penelitian belum dibahas** | Sistem mengelola data pribadi (NIK, dll.) | `bab-iii.md` |

---

## Rencana Kerja 3 Minggu (Saran untuk Nelsi)

### Minggu 1 — Lapangan & Literatur
- [ ] Kunjungi Kelurahan Kampung Sambakungan (observasi + wawancara petugas & 3–5 warga)
- [ ] Catat: jenis surat, alur manual, waktu tunggu, keluhan
- [ ] Baca & download 5–8 jurnal/skripsi serupa (lihat `template-penelitian-terdahulu.md`)
- [ ] Verifikasi referensi di daftar pustaka — hapus yang tidak ditemukan

### Minggu 2 — Tulis Ulang Bab I & II
- [ ] Tulis ulang latar belakang dengan data lapangan
- [ ] Buat Tabel 2.1 Penelitian Terdahulu (min. 5 penelitian)
- [ ] Tulis subbab Kesenjangan Penelitian
- [ ] Tambahkan sitasi di setiap paragraf Bab I & II

### Minggu 3 — Matangkan Bab III & Konsultasi
- [ ] Tentukan stack final (disarankan: Laravel + MySQL + WhatsApp Cloud API)
- [ ] Buat Gambar Kerangka Penelitian
- [ ] Rancang instrumen kuesioner UAT
- [ ] Konsultasi ke pembimbing dengan draft revisi

---

## Temuan Lintas Bab

| No | Temuan | File terkait |
|----|--------|--------------|
| 1 | Sitasi teks = 0, daftar pustaka = 35+ | `bab-i`, `bab-ii`, `bab-iii`, `daftar-pustaka-lampiran` |
| 2 | Rumusan masalah ↔ tujuan ↔ metode tidak selaras | `bab-i`, `bab-iii` |
| 3 | Waterfall dipilih tapi R&D disebut tanpa model R&D | `bab-ii`, `bab-iii` |
| 4 | Mixed method diklaim tanpa penjelasan | `bab-iii` |
| 5 | Efisiensi & kepuasan tidak dioperasionalkan | `bab-i`, `bab-iii`, `bab-iv-v-rencana` |
| 6 | WhatsApp API vs Baileys belum diputuskan | `bab-i`, `bab-iii` |
| 7 | Kebaruan tidak dijelaskan | `bab-i`, `bab-ii` |
| 8 | Lokasi Berau vs kampus Samarinda | `bab-i` |
| 9 | Dua kuesioner (kesiapan vs UAT) belum dibedakan | `bab-iii` |
| 10 | Keamanan data & UU PDP belum dibahas | `bab-iii` |

---

## Temuan Kritis — Lokasi Penelitian (Berau vs Samarinda)

Kelurahan Kampung Sambakungan **bukan di Samarinda**. Lokasi resmi: Kec. Gunung Tabur, **Kab. Berau**, Kaltim (Kode Kemendagri 64.03.06.2006). Jarak ke kampus UNMUL Samarinda ≈ **500+ km**.

| Risiko | Dampak |
|--------|--------|
| Akses lapangan | Observasi berulang mahal & jarang |
| Kredibilitas | Penguji akan tanya kenapa mitra di Berau |
| Koordinasi | Perlu surat izin lintas kabupaten |

**Yang harus Nelsi lakukan (pilih salah satu):**
- **Opsi A:** Jelaskan alasan pilih Berau (asal/domisili, ada izin kelurahan) + rencana kunjungan di Bab III
- **Opsi B:** Ganti lokasi ke kelurahan di Samarinda agar observasi feasible
- **Opsi C:** Dokumentasikan keterbatasan jika penelitian jarak jauh

Detail & saran rumusan masalah: lihat [`bab-i.md`](bab-i.md).

---

## Kesimpulan untuk Pembimbing

| Pertanyaan | Jawaban |
|------------|---------|
| Apakah topik layak untuk skripsi Informatika? | **Ya**, dengan syarat implementasi teknis kuat dan ada diferensiasi |
| Apakah draft saat ini layak sidang proposal? | **Belum** — perlu revisi besar terutama Bab II |
| Apakah mahasiswa boleh melanjutkan? | **Ya**, arahkan ke observasi lapangan + penulisan ulang Bab II |
| Risiko terbesar? | Lokasi Berau vs Samarinda + duplikasi topik + referensi tidak terverifikasi |

---

*Audit ini dibuat untuk membantu mahasiswa baru memahami apa yang harus diperbaiki dan bagaimana caranya. Baca `panduan-mahasiswa.md` terlebih dahulu jika bingung.*
