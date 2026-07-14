# Catatan Revisi Proposal Skripsi

**Mahasiswa:** Nelsi (2309106120)  
**Judul:** Implementasi Algoritma Priority Scheduling pada Sistem Informasi Pelayanan Surat Administrasi Kelurahan Kampung Sambakungan Berbasis Web  
**Status:** Belum siap seminar proposal — perlu revisi dulu  
**Target revisi:** 1–2 minggu (fokus pada poin wajib)

---

## Baca ini dulu

Proposal kamu **secara arah topik sudah bagus** untuk S1 Informatika, karena ada algoritma (Priority Scheduling), bukan hanya bikin website.

Tapi draft sekarang masih terbaca sebagai:

> “Sistem informasi kelurahan + sedikit formula prioritas”

Padahal yang diharapkan penguji:

> “Penelitian algoritma penjadwalan yang dibuktikan lebih baik dari antrean biasa (FIFO), dan diwujudkan dalam sistem informasi”

Jadi: **topiknya dipertahankan**, isinya yang harus diperkuat.

### Aturan kerja selama revisi

1. Kerjakan **poin wajib** dulu. Jangan loncat ke fitur baru.
2. Semua bagian proposal harus **saling nyambung**: rumusan ↔ tujuan ↔ batasan ↔ kontribusi ↔ pengujian.
3. Kalau bingung, tanya ke pembimbing dengan pertanyaan spesifik (ada contoh di akhir file ini).

---

## Yang TIDAK perlu dikerjakan dulu

Supaya tidak melebar, **jangan** menambah ini sebelum seminar proposal:

- aplikasi mobile / Flutter / Android
- chatbot / WhatsApp gateway baru (kecuali memang sudah sangat dulu direncanakan dan disetujui)
- menambah banyak jenis surat di luar 4 jenis yang sudah ada
- fitur laporan statistik yang rumit
- redesign UI yang berlebihan

Fokus revisi proposal sekarang: **algoritma + cara membuktikan + konsistensi dokumen**.

---

## Bagian yang sudah baik

- Judul sudah mengaitkan **algoritma** dengan masalah nyata di kelurahan.
- Teknologi yang dipilih (Laravel + MySQL) masuk akal untuk dikerjakan mahasiswa S1.
- Susunan BAB I–III sudah mengikuti format proposal.
- Masalah antrean FIFO vs kebutuhan mendesak mudah dipahami.

Simpan bagian ini. Jangan buang topiknya.

---

## Poin wajib (harus selesai sebelum seminar)

Kerjakan urut dari No. 1. Ini yang paling menentukan lolos/tidaknya proposal.

### 1. Perjelas algoritma Priority Scheduling kamu

Sekarang formula sudah ada:

```text
P(i) = w1 × JenisSurat + w2 × Urgensi + w3 × StatusPemohon
```

Tapi belum lengkap. Tambahkan di proposal:

| Yang harus ditulis | Contoh arah jawaban |
|---|---|
| Nilai bobot `w1`, `w2`, `w3` | Misalnya 0.3, 0.5, 0.2 (jumlah = 1) |
| Alasan kenapa bobot itu dipilih | Hasil wawancara petugas / urgensi dianggap lebih penting |
| Skala skor tiap variabel | Urgensi: Tinggi=5, Sedang=3, Rendah=1 |
| Skala status pemohon | Lansia=5, Disabilitas=4, Umum=1 |
| Skala jenis surat | Misalnya SKTM=4, Domisili=2, dst. |
| Jika skor sama, siapa didahulukan? | Misal: waktu pengajuan lebih awal |
| Preemptive atau non-preemptive? | Untuk pelayanan surat, biasanya **non-preemptive** (sekali petugas mulai proses, tidak digeser) |
| Langkah algoritma / pseudocode singkat | Input data → hitung skor → urutkan descending → petugas proses dari atas |
| Contoh hitung 2–3 permohonan | Tunjukkan angka → skor → urutan antrean |

**Kenapa wajib?**  
Tanpa ini, penguji bisa bilang: “Ini bukan algoritma, hanya sorting biasa.”

> **Catatan aging:** kalau kamu ingin memakai mekanisme aging (skor naik setelah menunggu lama) sebagai pembeda dari penelitian sebelumnya, tulis juga di bagian ini. Jangan hanya disebut enteng di BAB II.

---

### 2. Ubah cara pengujian: bandingkan dengan FIFO

Ini poin yang paling sering bikin proposal ditolak di sidang.

#### Masalah di draft sekarang

- Kamu bilang sistem akan **mengoptimalkan** / memperbaiki efisiensi waktu.
- Tapi pengujiannya hanya **Black Box** (cek fungsi jalan atau tidak).

Black Box **tidak bisa** membuktikan sistem lebih cepat/lebih adil.

#### Yang harus kamu rencanakan

Buat 2 skenario:

1. **FIFO** → siapa datang lebih dulu, diproses lebih dulu  
2. **Priority Scheduling** → siapa skor prioritasnya lebih tinggi, diproses lebih dulu

Lalu bandingkan, misalnya:

- rata-rata waktu tunggu
- waktu selesai permohonan
- apakah kasus mendesak (lansia / sangat urgent) lebih cepat terlayani

#### Cara mengukur waktu (wajib dijelaskan di metodologi)

Pilih dan tulis salah satu pendekatan (boleh digabung):

1. **Data uji buatan (disarankan untuk proposal/skripsi):** buat 20–30 data permohonan contoh dengan variasi urgensi/status/jenis surat, jalankan dengan FIFO dan Priority Scheduling, bandingkan hasilnya.
2. **Timestamp di sistem:** catat waktu pengajuan dan waktu mulai diproses petugas, lalu hitung selisihnya.

Jangan biarkan kalimat “mengukur efisiensi” tanpa menjelaskan **cara mengukur**.

#### Tentang SUS

Keputusan bimbingan:

- Kalau kapasitas terbatas, **prioritaskan uji FIFO vs Priority Scheduling + Black Box**.
- SUS **boleh dipakai sebagai pendukung**, bukan sebagai bukti utama optimasi.
- Jika SUS dipakai, harus muncul di rumusan/tujuan/batasan.
- Jika tidak dipakai, hapus dari pengumpulan data dan lampiran agar tidak menggantung.

---

### 3. Bedakan research kamu dari Rohmah (2023)

Paper Rohmah sudah memakai:

- Priority Scheduling
- SI administrasi kependudukan
- Waterfall
- Black Box
- SUS

Kalau bedanya hanya:

> “Di Kampung Sambakungan belum ada”

maka kontribusi kamu terlalu tipis.

#### Tulis perbedaan yang bersifat ilmiah/teknis, misalnya:

- rubrik skor prioritas yang berbeda
- cara menentukan bobot yang berbeda
- ada mekanisme **aging** (agar yang prioritas rendah tidak menunggu selamanya)
- evaluasi **FIFO vs Priority Scheduling** (bukan hanya Black Box)

Buat tabel “Perbedaan dengan Penelitian Terdahulu” yang jelas.

#### Perbaiki juga bagian 1.6 Kontribusi Penelitian

Sekarang kontribusimu masih berbunyi “baru di lokasi ini”.  
Ubah menjadi kontribusi yang lebih ilmiah, misalnya:

- perancangan rubrik prioritas untuk pelayanan surat kelurahan
- implementasi dan evaluasi Priority Scheduling dibanding FIFO
- (opsional) penerapan aging untuk mengurangi starvation

---

### 4. Rapikan agar rumusan, tujuan, batasan, variabel, dan pengujian selaras

Semua bagian harus “nyambung”.

| Jika kamu klaim... | Maka harus ada di... |
|---|---|
| Optimasi antrean | Tujuan + pengujian komparatif FIFO vs Priority |
| Black Box | Tujuan pengujian fungsional |
| SUS | Rumusan/tujuan/batasan (jangan hanya di lampiran) |
| Efisiensi waktu | Tabel variabel + cara pengukuran waktu |
| Aging | Batasan masalah + penjelasan algoritma + pengujian |

Perbaiki juga:

- Di tabel skenario Black Box, hapus status “Sesuai harapan” (proposal belum diuji).
- Ganti menjadi “Direncanakan” / “Akan diuji”.
- Update **Tabel 3.2 Variabel Penelitian** agar variabel terikat benar-benar diukur.
- Update **Batasan Masalah** jika ada penambahan aging / uji banding FIFO / keputusan pakai atau tidaknya SUS.

---

### 5. Fokuskan masalah penelitian di latar belakang

Di draft sekarang ada **dua masalah sekaligus**:

1. antrean FIFO tidak memperhatikan urgensi → ini inti algoritma  
2. pencatatan masih berkas fisik → ini masalah digitalisasi SI

Keduanya boleh disebut, tetapi ingat:

> **Kontribusi ilmiah utama kamu adalah poin 1 (algoritma prioritas).**  
> Poin 2 adalah alasan membuat sistem, bukan novelty utama.

Jangan sampai skripsi terlihat seperti “bikin website kelurahan”, lalu algoritma hanya tempelan.

Kalau bisa, tambahkan data observasi singkat:

- perkiraan jumlah permohonan per minggu
- jenis surat yang sering diajukan
- gambaran waktu tunggu
- SOP singkat pelayanan

---

### 6. Lengkapi bagian yang masih kosong / rapihkan formal

- [ ] Tabel 2.1 Matriks Penelitian Terkait
- [ ] Perbaiki daftar penelitian terkait di BAB II (jangan hanya metode; cantumkan judul/fokus paper)
- [ ] Gambar 3.1 Kerangka Penelitian
- [ ] Gambar 3.2 Use Case Diagram
- [ ] Gambar 3.3 Activity Diagram
- [ ] Gambar 3.4 ERD
- [ ] Gambar 3.5–3.6 Rancangan antarmuka
- [ ] Nama pembimbing / pejabat di kata pengantar & pengesahan
- [ ] Rapikan redaksi Halaman Pengesahan (ini proposal, jangan memakai kalimat seolah sudah “dinyatakan sebagai skripsi”)

---

## Poin penguat (sangat disarankan)

Kerjakan setelah poin wajib, biar sidang lebih kuat.

### 7. Bahas starvation (+ aging jika dipakai)

Priority Scheduling punya risiko:

> orang dengan prioritas rendah bisa menunggu terus (starvation)

Tunjukkan kamu paham masalah ini.

Kalau memakai aging, jelaskan singkat:

> semakin lama menunggu, skor prioritas naik bertahap

Jika aging jadi pembeda utama dari Rohmah, anggap ini bagian dari poin wajib No.1 dan No.3 — jangan ditunda.

### 8. Jelaskan asal-usul bobot prioritas

Jangan ambil bobot secara sembarangan.  
Dasarkan pada wawancara petugas/lurah, lalu tulis di metodologi.

Kalau wawancara dipakai untuk menentukan bobot, sesuaikan juga **pedoman wawancara** di lampiran (tanya soal prioritas pelayanan, bukan hanya soal umum SI).

### 9. Pisahkan 2 jenis pengujian

1. **Uji algoritma** → apakah skor dan urutan antrean benar  
2. **Uji sistem (Black Box)** → apakah form, login, status, email, dll. berjalan  

Lalu **uji banding FIFO vs Priority Scheduling** sebagai bukti kinerja.

### 10. Cek ulang daftar pustaka

Pastikan paper yang kamu sebut “pakai scheduling” memang benar membahas scheduling.  
Jangan klaim berlebihan.

Contoh yang perlu dicek ulang: jika paper hanya membahas SI administrasi desa secara umum, jangan ditulis seolah paper itu menjadi rujukan utama arsitektur algoritma penjadwalan.

### 11. Sesuaikan jadwal jika pengujian bertambah

Jika sekarang ada uji banding FIFO vs Priority Scheduling, pastikan di jadwal ada cukup waktu untuk:

- menyusun data uji
- menjalankan perbandingan
- menganalisis hasil

Jangan biarkan semua pengujian menumpuk hanya 1 minggu tanpa rincian.

---

## Contoh yang bisa kamu tiru

### A. Contoh rubrik skor (versi awal — silakan revisi setelah wawancara)

**Bobot (contoh):**
- `w1` Jenis surat = 0.3
- `w2` Urgensi = 0.5
- `w3` Status pemohon = 0.2

**Skala (contoh):**

| Variabel | Kategori | Skor |
|---|---|---|
| Jenis surat | Surat keterangan tidak mampu | 5 |
| Jenis surat | Surat keterangan usaha | 3 |
| Jenis surat | Surat domisili | 2 |
| Jenis surat | Surat pengantar | 2 |
| Urgensi | Tinggi | 5 |
| Urgensi | Sedang | 3 |
| Urgensi | Rendah | 1 |
| Status pemohon | Lansia | 5 |
| Status pemohon | Disabilitas | 4 |
| Status pemohon | Umum | 1 |

**Contoh hitung:**
- Pemohon A: SKTM (5), Urgensi Tinggi (5), Lansia (5)  
  `P = 0.3(5) + 0.5(5) + 0.2(5) = 5.0`
- Pemohon B: Domisili (2), Urgensi Rendah (1), Umum (1)  
  `P = 0.3(2) + 0.5(1) + 0.2(1) = 1.3`

Maka antrean: **A lebih dulu dari B**.

> Bobot di atas hanya contoh. Finalnya harus kamu justifikasi (wawancara petugas).

### B. Contoh struktur Tabel 2.1 Matriks Penelitian Terkait

| No | Peneliti (tahun) | Fokus penelitian | Metode | Algoritma scheduling? | Pengujian | Persamaan | Perbedaan dengan penelitian ini |
|---|---|---|---|---|---|---|---|
| 1 | Rohmah (2023) | SI administrasi + Priority Scheduling | Waterfall | Ya | Black Box + SUS | Sama-sama Priority Scheduling | Penelitian ini menambah uji banding FIFO + rubrik/aging yang berbeda |
| 2 | Aldila dkk. (2022) | SI surat kelurahan | Waterfall | Tidak | - | Sama domain surat | Belum memakai Priority Scheduling |
| 3 | ... | ... | ... | ... | ... | ... | ... |

### C. Contoh skenario uji FIFO vs Priority Scheduling

Buat minimal 10–20 data uji. Contoh kecil:

| ID | Jenis surat | Urgensi | Status | Datang urutan ke- |
|---|---|---|---|---|
| 1 | Domisili | Rendah | Umum | 1 |
| 2 | SKTM | Tinggi | Lansia | 2 |
| 3 | Pengantar | Sedang | Umum | 3 |

Lalu tunjukkan:

- Urutan FIFO: 1 → 2 → 3
- Urutan Priority Scheduling: 2 → ... (sesuai skor)
- Bandingkan: siapa yang lebih dulu terlayani untuk kasus mendesak?

### D. Contoh rumusan masalah

1. Bagaimana merancang mekanisme penentuan prioritas permohonan surat berdasarkan jenis surat, tingkat urgensi, dan status pemohon pada sistem informasi pelayanan surat di Kelurahan Kampung Sambakungan?
2. Bagaimana kinerja algoritma Priority Scheduling dibandingkan FIFO dalam mengatur urutan pemrosesan permohonan surat berdasarkan metrik waktu tunggu dan ketepatan prioritas?
3. Bagaimana hasil pengujian fungsional sistem yang dibangun (dan pengujian usability, jika memang digunakan)?

### E. Contoh tujuan penelitian (harus selaras dengan rumusan)

1. Merancang mekanisme perhitungan prioritas permohonan surat berdasarkan jenis surat, urgensi, dan status pemohon.
2. Mengimplementasikan algoritma Priority Scheduling dan membandingkan kinerjanya dengan FIFO berdasarkan metrik yang telah ditentukan.
3. Menguji fungsionalitas sistem menggunakan Black Box Testing (dan SUS jika dipakai).

Intinya: pertanyaan/tujuan harus bisa dijawab dengan **bukti**, bukan hanya “sistem berhasil dibuat”.

---

## Rencana kerja 2 minggu (disarankan)

### Minggu 1
- [ ] Finalkan rubrik skor + contoh perhitungan + pseudocode
- [ ] Putuskan: aging dipakai atau tidak
- [ ] Putuskan: SUS dipakai atau tidak
- [ ] Susun ulang rumusan, tujuan, batasan, kontribusi
- [ ] Buat Tabel 2.1 matriks penelitian terkait

### Minggu 2
- [ ] Tulis desain uji FIFO vs Priority Scheduling + cara ukur waktu
- [ ] Update Tabel 3.2 variabel penelitian
- [ ] Lengkapi gambar (kerangka, use case, activity, ERD, UI)
- [ ] Rapikan formal (nama pejabat, pengesahan, status uji “direncanakan”)
- [ ] Cek daftar pustaka (hindari overclaim)
- [ ] Baca ulang: apakah semua bagian sudah nyambung?

---

## Checklist sebelum kirim ulang proposal

Centang semua ini sebelum submit ke pembimbing:

- [ ] Rubrik skor prioritas lengkap (bobot + skala + contoh hitung)
- [ ] Ada penjelasan non-preemptive/preemptive
- [ ] Ada pseudocode / langkah algoritma singkat
- [ ] Ada rencana uji banding **FIFO vs Priority Scheduling**
- [ ] Ada penjelasan cara mengukur waktu tunggu
- [ ] Bagian kontribusi (1.6) sudah bukan hanya “baru di lokasi”
- [ ] Perbedaan dengan Rohmah (2023) sudah jelas dan bersifat teknis
- [ ] Rumusan, tujuan, batasan, variabel, dan pengujian sudah selaras
- [ ] Latar belakang menekankan masalah antrean/prioritas sebagai inti penelitian
- [ ] SUS masuk tujuan/rumusan **atau** dihapus dari proposal
- [ ] Tabel matriks penelitian terkait sudah ada
- [ ] Semua gambar (kerangka, UML, ERD, UI) sudah dilampirkan
- [ ] Nama pejabat/pembimbing sudah diisi
- [ ] Redaksi pengesahan sudah sesuai untuk proposal
- [ ] Tidak ada status pengujian “Sesuai harapan” di tahap proposal
- [ ] Tidak menambah fitur di luar ruang lingkup revisi

---

## Ringkasan satu kalimat

> Jangan menambah fitur dulu. Perkuat dulu: **spesifikasi algoritma**, **perbandingan dengan FIFO**, dan **beda jelas dari penelitian sebelumnya**.

Kalau 3 hal itu sudah rapi, proposal kamu jauh lebih siap untuk seminar.

---

## Apa yang dikirim saat revisi selesai?

Kirim ulang ke pembimbing:

1. Proposal PDF yang sudah direvisi  
2. Lampiran singkat 1–2 halaman: rubrik skor prioritas + contoh perhitungan + contoh urutan FIFO vs Priority

Jika ada yang bingung, tanyakan dengan pertanyaan spesifik, misalnya:

> “Pak/Bu, apakah bobot urgensi 0.5 dan status pemohon 0.2 sudah masuk akal untuk wawancara petugas?”

atau

> “Pak/Bu, untuk proposal ini apakah aging wajib dimasukkan sebagai pembeda dari Rohmah, atau cukup uji banding FIFO dulu?”

Jangan tanya terlalu umum seperti “bagaimana lanjutnya?”.

---

**Catatan pembimbing:** Topik dipertahankan. Seminar belum diizinkan sampai poin wajib selesai.  
**Estimasi pengerjaan revisi substansi:** 1–2 minggu jika fokus.
