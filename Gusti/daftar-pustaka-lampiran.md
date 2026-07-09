# Audit — Daftar Pustaka & Lampiran

**Halaman:** 74–78 (PDF hal. 90–94)  
**Status:** Cukup — revisi minor

---

## Daftar Pustaka

### Yang sudah baik

- **42 entri** — mencakup seluruh sitasi utama di Bab I–III
- Penelitian terkait #1–#10 **semua ada** (Rahmaya, Pirmansyah, Mulyawan, Nugroho, Prasetyawan, Aryabimo, Budiman, Ramadani, Isma, Sanjaya)
- Referensi teknologi web (Vercel, Chatfuel, Google Cloud, Resmeku.xyz)

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | **Wayahdi & Ruziq (2023a)** dan **(2023b)** — **paper identik** (judul & halaman sama) | Satukan jadi satu entri; gunakan (2023a/2023b) hanya jika memang 2 bagian berbeda |
| Sedang | **Aulia & Wijirahayu (2022)** — entri **tanpa nama jurnal** | Lengkapi venue publikasi |
| Sedang | **Aryabimo et al. (2024)** — *"12(3)"* tanpa halaman artikel | Lengkapi page range jika ada |
| Sedang | Format penulis **ManyChat (2026)** — line break aneh di PDF | Rapikan satu baris |
| Sedang | **Google Cloud (2026)** — URL terpotong multi-baris | Pastikan URL utuh & dapat diakses |
| OK | DOI tidak wajib untuk semua — mayoritas ada URL | — |

### Verifikasi sitasi teks ↔ DP

| Sitasi di teks | Ada di DP? |
|---------------|------------|
| Wardhana, 2024 | ✓ |
| Sugianto et al., 2022 | ✓ |
| Lantana et al., 2023 | ✓ |
| Satyafebrianti et al., 2025 | ✓ |
| Kejor & Purwanti, 2025 | ✓ |
| Maulana, 2025 | ✓ |
| Rahmaya et al., 2026 | ✓ |
| Resmeku, 2026 | ✓ |
| Semua teori Bab II | ✓ (spot check) |

**Tidak ditemukan** sitasi orphan yang jelas (sitasi tanpa DP) pada audit ini.

---

## Lampiran

| Lampiran | Isi | Evaluasi |
|----------|-----|----------|
| **1** | Source code GitHub (`github.com/npmdms/takoni`) | ✓ QR + URL — baik untuk reproducibility |
| **2** | Rekapitulasi UAT (`lampiran.vercel.app`) | ⚠ URL generik |
| **3** | Kuesioner UAT, formulir, log (`lampiran.vercel.app`) | ⚠ **URL sama** dengan Lampiran 2 |

### Temuan lampiran

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Lampiran 2 & 3 **URL identik** — tidak jelas pemisahan konten | Bedakan path: `/uat-rekap`, `/kuesioner` atau gabung jadi satu lampiran |
| Sedang | Kuesioner UAT **tidak tercetak** di naskah — hanya link | Untuk arsip perpustakaan: lampirkan PDF kuesioner + contoh log (min. 2–3 halaman) |
| Sedang | QR code tidak terbaca jelas di PDF render | Uji scan sebelum cetak |
| OK | Lampiran 1 GitHub — kontribusi teknis jelas | — |

---

## Rekomendasi Arsip Perpustakaan

Sebelum bind final, mahasiswa sebaiknya menyiapkan:

1. **PDF lampiran terpisah** (kuesioner UAT, tabel rekap mentah R1–R10, 1–2 log percakapan anonim)
2. **Screenshot** halaman GitHub (commit hash / release tag) sebagai bukti versi kode yang diuji
3. **Surat izin** Resmeku (jika ada) — tidak terlihat di naskah; opsional tergantung kebijakan prodi

---

## Checklist

- [ ] Gabung/fix duplikat Wayahdi 2023a/b
- [ ] Lengkapi entri jurnal tanpa venue
- [ ] Bedakan URL Lampiran 2 vs 3
- [ ] Siapkan PDF lampiran UAT untuk arsip
- [ ] Tes QR code dari print preview
