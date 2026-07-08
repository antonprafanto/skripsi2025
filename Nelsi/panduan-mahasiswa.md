# Panduan Skripsi untuk Mahasiswa Baru — NELSI

Halo Nelsi! Dokumen ini ditulis khusus untuk kamu yang **baru mulai skripsi**. Bahasanya sengaja dibuat mudah dipahami. Baca sampai selesai sebelum mulai revisi.

---

## 1. Apa Itu Skripsi? (Singkatnya)

Skripsi = tugas akhir S1 yang membuktikan kamu bisa:
1. **Mengidentifikasi masalah** di dunia nyata
2. **Mencari solusi** berbasis teknologi informasi
3. **Membangun solusi** (aplikasi/sistem)
4. **Menguji** apakah solusi itu berfungsi
5. **Menulis laporan** ilmiah dengan aturan akademik

Judul kamu: *Rancang Bangun Sistem Layanan Surat Administrasi Kelurahan Kampung Sambakungan Berbasis WhatsApp.*

Artinya kamu harus **benar-benar membuat sistem**, bukan hanya menulis tentang WhatsApp.

---

## 2. Di Mana Posisimu Sekarang?

```
[✓] Punya ide topik
[✓] Punya draft Bab I, II, III (14 halaman)
[✗] Belum ada data lapangan
[✗] Belum ada penelitian terdahulu yang proper
[✗] Belum ada sitasi dalam teks
[✗] Belum tentukan teknologi pasti
[✗] Belum buat sistem (koding)
[✗] Belum ada Bab IV & V
```

**Kesimpulan:** Kamu baru di **tahap proposal awal**. Itu wajar untuk mahasiswa baru. Tapi jangan kirim draft ini ke sidang proposal — belum siap.

---

## 3. Struktur Skripsi Lengkap (Yang Harus Kamu Capai)

| Bab | Isi | Status kamu |
|-----|-----|-------------|
| Bagian awal | Cover, abstrak, kata pengantar, daftar isi | Belum ada |
| **Bab I** | Masalah, tujuan, batasan | Ada, perlu revisi |
| **Bab II** | Teori + penelitian orang lain | Ada, **harus ditulis ulang** |
| **Bab III** | Cara penelitian & metode | Ada, perlu dilengkapi |
| **Bab IV** | Hasil: rancangan, koding, pengujian | **Belum ada** |
| **Bab V** | Kesimpulan & saran | **Belum ada** |
| Lampiran | Kuesioner, screenshot, kode, wawancara | Belum ada |

---

## 4. Lima Kesalahan Terbesar di Draft Kamu

### Kesalahan 1: Menulis dulu, riset kemudian

Draft kamu terasa seperti **template umum** — bisa dipakai untuk kelurahan mana saja. Penguji akan bertanya:

> "Berapa lama warga nunggu surat di Kampung Sambakungan? Berapa permohonan per bulan? Apa kata petugas kelurahan?"

**Solusi:** Pergi ke kelurahan. Observasi. Wawancara. Catat angka dan kutipan.

---

### Kesalahan 2: Daftar pustaka panjang, tapi tidak dipakai

Kamu punya 35+ referensi, tapi **tidak ada satu pun sitasi** di Bab I, II, atau III.

**Aturan emas sitasi:**
- Setiap paragraf yang berisi **fakta/klaim** → wajib ada `(Nama, Tahun)`
- Setiap referensi di daftar pustaka → wajib muncul minimal 1× di teks
- Setiap penelitian terdahulu di tabel → wajib ada di daftar pustaka

**Contoh salah:**
> WhatsApp sangat populer di Indonesia.

**Contoh benar:**
> WhatsApp sangat populer di Indonesia, dengan lebih dari 100 juta pengguna aktif (We Are Social & Hootsuite, 2023).

---

### Kesalahan 3: Penelitian terdahulu hanya 2 paragraf kosong

Ini **masalah terbesar**. Bab II §2.1 kamu hanya menulis:
- "Beberapa penelitian terdahulu..."
- "Penelitian oleh berbagai akademisi..."

**Tanpa menyebut siapa, tahun berapa, apa hasilnya, apa bedanya dengan penelitianmu.**

Penguji **pasti menolak** proposal seperti ini.

**Solusi:** Buat tabel (lihat `template-penelitian-terdahulu.md`).

---

### Kesalahan 4: Teknologi masih "atau-atau"

Di Bab III kamu tulis:
- PHP/Python **atau** Node.js
- MySQL **atau** PostgreSQL
- WhatsApp Business API **atau** Baileys

Di skripsi Informatika, kamu **harus sudah memutuskan** sebelum proposal. Penguji akan tanya: "Kamu pakai yang mana? Kenapa?"

**Rekomendasi untuk kamu (bisa didiskusikan dengan pembimbing):**

| Komponen | Pilihan yang disarankan | Alasan |
|----------|------------------------|--------|
| Backend | **Laravel (PHP)** atau **Node.js (Express)** | Banyak tutorial, cocok untuk CRUD surat |
| Database | **MySQL** | Umum dipakai, mudah di hosting lokal |
| Frontend admin | **Web (Blade/React)** | Petugas kelurahan kelola permohonan |
| WhatsApp | **WhatsApp Cloud API** (Meta) | Resmi, aman untuk layanan pemerintahan |
| Diagram | **Draw.io** | Gratis, mudah |
| Metode | **Waterfall** | Sudah kamu pilih, cocok untuk kebutuhan jelas |

**Jangan pakai Baileys** — itu library tidak resmi, akun WhatsApp bisa diblokir, tidak pantas untuk layanan kelurahan.

---

### Kesalahan 5: Rumusan masalah tidak bisa dijawab dengan angka

Kamu bertanya: *"Bagaimana sistem dapat meningkatkan efisiensi?"*

Tapi tidak menjelaskan **efisiensi diukur bagaimana**.

**Perbaikan — tentukan indikator sejak proposal:**

| Variabel | Indikator | Cara ukur |
|----------|-----------|-----------|
| Efisiensi waktu | Rata-rata waktu pengurusan surat | Bandingkan sebelum & sesudah sistem (hari) |
| Efisiensi kunjungan | Jumlah kunjungan fisik ke kelurahan | Hitung permohonan online vs datang langsung |
| Kepuasan | Skor kepuasan pengguna | Kuesioner Likert 1–5, metode UAT |
| Fungsionalitas | Persentase fitur berjalan benar | Black Box Testing |

---

## 5. Langkah Praktis — Mulai dari Mana?

### Langkah 1: Kunjungan lapangan (1–2 hari)

**Siapa yang diwawancarai:**
- 1–2 petugas kelurahan (administrasi)
- 3–5 warga yang pernah mengurus surat

**Pertanyaan untuk petugas:**
1. Surat apa saja yang paling sering diajukan?
2. Bagaimana alur pengajuan saat ini (step by step)?
3. Berapa lama rata-rata waktu selesai?
4. Apa kendala terbesar dalam pelayanan?
5. Apakah warga sudah pernah tanya via WhatsApp? Bagaimana ditangani?

**Pertanyaan untuk warga:**
1. Pernah mengurus surat di kelurahan? Berapa kali datang?
2. Berapa lama nunggu?
3. Apakah pakai WhatsApp sehari-hari?
4. Mau tidak kalau pengajuan surat lewat WhatsApp?

**Catat semua jawaban.** Nanti masukkan ke latar belakang Bab I.

---

### Langkah 2: Baca jurnal serupa (3–5 hari)

Cari di Google Scholar dengan kata kunci:
- `sistem informasi surat kelurahan whatsapp`
- `chatbot whatsapp pelayanan publik`
- `pengajuan surat online kelurahan`

**Minimal baca 5 penelitian** dan isi tabel di `template-penelitian-terdahulu.md`.

Penelitian yang **valid dan bisa dipakai** (sudah diverifikasi):

| Penelitian | Lokasi | Teknologi | Yang bisa kamu pelajari |
|------------|--------|-----------|------------------------|
| Sipuas (JITED UNY, 2024) | Desa Pondokrejo | Next.js + NestJS + WhatsApp Cloud API | Arsitektur web + bot, pengujian ISO 25010 |
| SIPANDHA (JAG, 2024) | Desa Cepoko | Web + notifikasi WhatsApp | Pengukuran waktu layanan sebelum-sesudah |
| Puspita et al. (G-Tech, 2023) | Kecamatan Jangkar | Web + WhatsApp Gateway | Waterfall, tracking kode surat |

---

### Langkah 3: Tentukan apa yang membedakan penelitianmu

Karena topikmu **sudah banyak diteliti orang**, kamu harus punya alasan kenapa penelitianmu tetap penting:

**Contoh kebaruan yang bisa kamu pakai:**
> "Penelitian ini berbeda karena: (1) fokus pada Kelurahan Kampung Sambakungan yang belum memiliki sistem digital; (2) mengintegrasikan panel admin web dengan chatbot WhatsApp untuk 4 jenis surat spesifik setempat; (3) mengukur peningkatan efisiensi waktu layanan sebelum dan sesudah implementasi."

Tulis paragraf seperti ini di akhir Bab II §2.1.

---

### Langkah 4: Tulis ulang Bab I–III (1–2 minggu)

Ikuti checklist di masing-masing file:
- `bab-i.md`
- `bab-ii.md`
- `bab-iii.md`

---

### Langkah 5: Konsultasi pembimbing

Baru setelah Bab I–III direvisi, bawa ke pembimbing. Jangan konsultasi dengan draft yang sekarang — pembimbing akan banyak komentar dasar yang bisa kamu selesaikan sendiri dulu.

---

## 6. Gambaran Sistem yang Akan Kamu Bangun

Agar kamu paham **arah teknisnya**, ini arsitektur yang disarankan:

```
┌─────────────┐         ┌──────────────────┐         ┌─────────────┐
│  Masyarakat │ ◄─────► │  WhatsApp Bot    │ ◄─────► │   Backend   │
│  (WhatsApp) │  chat   │  (Cloud API)     │  API    │  (Laravel)  │
└─────────────┘         └──────────────────┘         └──────┬──────┘
                                                            │
                       ┌──────────────────┐         ┌──────▼──────┐
                       │  Petugas         │ ◄─────► │   MySQL     │
                       │  Kelurahan       │  web    │   Database  │
                       │  (Web Admin)     │         └─────────────┘
                       └──────────────────┘
```

**Alur singkat:**
1. Warga kirim pesan ke WhatsApp kelurahan → bot memandu isi data
2. Data masuk ke database → petugas lihat di web admin
3. Petugas verifikasi & proses surat
4. Sistem kirim notifikasi status ke WhatsApp warga

Ini yang nanti kamu gambarkan di Bab IV (UML, ERD, screenshot).

---

## 7. FAQ — Pertanyaan yang Sering Ditanyakan Mahasiswa Baru

### "Apakah topik saya ditolak karena sudah banyak yang riset?"

**Tidak otomatis ditolak.** Banyak skripsi Informatika dengan topik serupa tetap lulus. Yang penting:
- Ada **implementasi nyata** (bukan hanya konsep)
- Ada **perbedaan** dengan penelitian sebelumnya
- Ada **pengujian** yang jelas

### "Haruskah pakai WhatsApp Business API? Kan berbayar?"

Ada **free tier** dari Meta (WhatsApp Cloud API). Atau bisa pakai **gateway resmi** seperti Fonnte (ada biaya bulanan, lebih murah). Hindari Baileys.

### "Berapa lama menyelesaikan skripsi?"

Dengan draft sekarang + revisi proposal (3 minggu) + implementasi (2–3 bulan) + penulisan Bab IV–V (1 bulan) = **±4–5 bulan** total. Kamu sudah rencanakan 6 bulan — masih realistis jika mulai serius sekarang.

### "Bolehkah pakai ChatGPT untuk menulis?"

Boleh untuk **bantuan**, tapi:
- **Jangan copy-paste** tanpa edit — draft kamu terasa seperti template AI
- **Verifikasi semua referensi** — AI sering membuat referensi fiktif
- **Tulis ulang dengan data lapangan kamu sendiri**

### "Apa yang harus saya kerjakan minggu ini?"

1. Kunjungi Kelurahan Kampung Sambakungan
2. Baca 3 jurnal dari `template-penelitian-terdahulu.md`
3. Mulai isi Tabel 2.1 Penelitian Terdahulu
4. Tentukan stack teknologi (diskusi dengan pembimbing)

---

## 8. Checklist Cepat — Apakah Proposal Sudah Siap?

Centang semua ini sebelum ajukan sidang proposal:

```
[ ] Latar belakang ada data angka dari kelurahan
[ ] Ada kutipan hasil wawancara/observasi
[ ] Tabel penelitian terdahulu min. 5 baris
[ ] Ada paragraf kesenjangan penelitian (research gap)
[ ] Setiap bab ada sitasi dalam teks
[ ] Teknologi sudah diputuskan (bukan "atau")
[ ] Ada gambar kerangka penelitian
[ ] Rumusan masalah bisa dijawab dengan pengujian
[ ] Instrumen kuesioner sudah dirancang
[ ] Semua referensi diverifikasi (bisa dibuka/dicari)
[ ] Sudah dikonsultasikan ke pembimbing
```

Jika belum semua tercentang → **belum siap sidang**.

---

**Semangat, Nelsi! Skripsi itu marathon, bukan sprint. Mulai dari observasi lapangan — itu fondasi semuanya.**

Kalau bingung, baca file audit per bab atau tanya pembimbing dengan pertanyaan spesifik, misalnya: *"Pak/Bu, untuk integrasi WhatsApp saya rencana pakai Cloud API, apakah feasible?"* — bukan *"Gimana cara nulis skripsi?"*
