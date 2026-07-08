# Audit — BAB III: Metodologi Penelitian

**Halaman:** 31–79 (PDF ~50–98)  
**Status:** Substansi kuat; **referensi silang gambar §3.5 perlu perbaikan besar**

---

## Ringkasan Bab

Metodologi lengkap: observasi, wawancara, kuesioner, analisis kebutuhan, perancangan UML, wireframe, implementasi 2 iterasi, pengujian Black Box. Ini bab terpanjang dan paling detail — sesuai untuk skripsi implementasi.

**Nilai substansi:** 9/10  
**Nilai format (gambar):** 4/10

---

## Yang Sudah Baik

- Alur metode prototype (Evolutionary) jelas: iterasi 1 → evaluasi → iterasi 2
- Analisis kebutuhan fungsional & non-fungsional terstruktur
- Use Case, Sequence, Class Diagram lengkap
- Deskripsi struktur database (Tabel 3.1–3.7) detail
- Wireframe per aktor (Pasien, Terapis, Admin) sangat detail
- Rencana pengujian 71 skenario / 7 modul sudah dirancang di Bab III

---

## Temuan Kritis — §3.5 Perancangan Tampilan (Referensi Gambar)

Pada §3.5, **nomor gambar di teks tidak cocok dengan caption** — pola offset **+1** (teks lebih besar dari caption):

| Teks merujuk | Caption aktual | Isi seharusnya |
|--------------|----------------|----------------|
| Gambar **3.30** (registrasi) | Gambar **3.29** | Registrasi Pasien |
| Gambar **3.31** (login) | Gambar **3.30** | Login |
| Gambar **3.32** (beranda) | Gambar **3.31** | Beranda Pasien |
| Gambar **3.33** (buat janji) | Gambar **3.32** | Buat Janji Temu |
| … | … | Pola berlanjut ke gambar berikutnya |

**Dampak:** Pembaca yang mengikuti "lihat Gambar 3.33" akan membuka gambar yang salah.

### Temuan Tambahan Daftar Gambar

| Prioritas | Temuan |
|-----------|--------|
| Wajib | **Gambar 3.41** — **nomor duplikat** untuk 2 wireframe berbeda (Akan Datang Terapis & Riwayat Terapis) | Renomori salah satu |
| Wajib | **Gambar 3.35** — judul duplikat (*Jadwal Janji Temu Akan Datang* 2×); item 7 seharusnya **Riwayat** | Koreksi judul caption |
| Disarankan | Lompat nomor halaman (mis. 3.50 → 3.51 di hal. 72) — periksa urutan |

---

## Temuan — Metodologi vs Hasil

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Wajib | **Skala Likert** disebut untuk kuesioner (§3.x), tetapi Bab IV **tidak menampilkan** analisis Likert (mean, distribusi skor) | Tambahkan tabel/grafik Likert di Bab IV ATAU ubah redaksi metodologi |
| Disarankan | **15 responden** kuesioner — instrumen/kuesioner **tidak terlihat** di Lampiran (hanya judul) | Lampirkan formulir kuesioner lengkap |
| Wajib | **Wawancara terapis** dilakukan (§3.2.1) tetapi **tidak dirangkum** di Bab IV §4.1 — hanya kuesioner & observasi yang tampak | Tambahkan ringkasan temuan wawancara |
| Disarankan | Struktur database dijelaskan via **Tabel 3.1–3.7**, tanpa **diagram ERD** visual | Tambahkan ERD jika diwajibkan prodi |
| Disarankan | **Evolutionary Prototyping** baru eksplisit di Bab IV §4.5, tidak di §3.1 | Tambahkan deklarasi jenis prototype di §3.1 |
| Disarankan | **Kebutuhan fungsional §3.2.2** — poin reset password admin tidak bernomor **f.** | Perbaiki format list |
| Disarankan | **Kebutuhan nonfungsional** (§3.2.2) tidak dibahas/diuji di Bab IV | Tambahkan validasi atau batasi klaim |

---

## Temuan — Wireframe vs Figma

Metodologi §3.5 memakai **wireframe** low-fidelity. Bab II §2.13 menjelaskan **Figma** panjang, tetapi **tidak disebut** bahwa Figma dipakai dalam penelitian ini. Jika tidak dipakai, §2.13 perlu dipendekkan atau dihubungkan dengan alasan memilih wireframe.

---

## Temuan — Sequence Diagram (Minor)

Beberapa paragraf di §3.4 merujuk nomor gambar yang perlu diverifikasi silang dengan caption (mirip masalah §3.5). Contoh yang perlu dicek manual:
- Gambar 3.28 di Bab IV §4.2.2.2 merujuk **Sequence Lihat Laporan** — padahal di Bab III Gambar 3.28 adalah **Class Diagram**

---

## Checklist Revisi Bab III

```
[ ] URGENT: Perbaiki seluruh referensi silang §3.5 (teks ↔ caption)
[ ] Koreksi duplikat Gambar 3.35 & 3.41
[ ] Ringkaskan wawancara terapis di Bab IV
[ ] Tampilkan hasil Likert di Bab IV atau revisi metodologi
[ ] Lampirkan instrumen kuesioner
[ ] Perbaiki format list kebutuhan fungsional (poin f.)
[ ] Deklarasikan Evolutionary Prototyping di §3.1
[ ] (Opsional) Tambahkan diagram ERD
```

**Estimasi waktu:** 4–6 jam (tergantung jumlah gambar yang perlu renumber)
