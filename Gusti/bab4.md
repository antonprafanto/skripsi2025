# 📋 LAPORAN AUDIT SKRIPSI
## Bab IV — Hasil dan Pembahasan (Halaman 38–52)

**Nama Mahasiswa :** Gusti Dimas Novarossi
**NIM              :** 2109106124
**Dokumen          :** SEMHAS — Bab IV Hasil dan Pembahasan
**Halaman Diperiksa:** 38 – 52 (file hal. 53 – 67)
**Tanggal Audit    :** 28 April 2026
**Auditor          :** Dosen Pembimbing / Penguji

---

> [!CAUTION]
> Terdapat **3 temuan KRITIS** yang wajib diperbaiki sebelum sidang. Jika tidak diperbaiki, dokumen dianggap **belum siap defend**.

---

## 🔴 TEMUAN KRITIS (Harus Diperbaiki Sebelum Sidang)

### ❌ Temuan K-1 — Data Placeholder Belum Diisi
**Lokasi:** Halaman 51, Sub-bab 4.4.2

Pada paragraf pembuka Sub-bab 4.4.2 dan caption Tabel 4.4, terdapat huruf **`x`** (berwarna kuning) yang jelas merupakan *placeholder* yang belum diganti dengan data aktual:

> *"...dengan melibatkan **x** responden..."*
> *"...disajikan pada Tabel 4.**x**"*

**Masalah:** Ini menunjukkan bahwa data pengujian **belum selesai dikumpulkan** atau lupa dimasukkan. Dokumen yang diserahkan ke penguji harus sudah berisi data yang lengkap dan valid.

**Yang harus dilakukan:**
- [ ] Tentukan berapa jumlah responden yang sebenarnya terlibat dalam pengujian.
- [ ] Ganti semua `x` dengan angka yang nyata dan konsisten.
- [ ] Pastikan jumlah responden masuk akal (minimal 10–30 untuk uji kesesuaian dengan Likert).
- [ ] Perbarui *caption* tabel dari "Tabel 4.x" menjadi "Tabel 4.4".

---

### ❌ Temuan K-2 — Sub-bab 4.5 (Pembahasan) Tidak Ada Isinya
**Lokasi:** Halaman 52, Sub-bab 4.5

Bagian Pembahasan hanya berisi satu kalimat:

> *"Penjelasan lihat di ppt. Menjelaskan dan menjabarkan hasil-hasil percobaan hingga pengujian secara terstruktur, detail dan jelas."*

**Masalah:** Ini adalah **catatan pribadi penulis** yang tidak sengaja masuk ke dokumen final. Sub-bab Pembahasan adalah bagian **paling penting** di Bab IV karena menunjukkan kemampuan analitis mahasiswa.

**Yang harus dilakukan:**
- [ ] Hapus kalimat catatan tersebut sepenuhnya.
- [ ] Tulis pembahasan yang nyata dan substantif, mencakup:
  - Analisis mengapa Blackbox Testing 100% berhasil — apakah ada keterbatasan metode?
  - Interpretasi hasil uji kesesuaian respons 84,57% — apa artinya bagi sistem?
  - Diskusi skenario di mana chatbot **gagal** atau kurang memuaskan (kasus 5 & 6 hanya "Sesuai", bukan "Sangat Sesuai").
  - Perbandingan dengan penelitian sebelumnya yang ada di Bab II.
  - Keterbatasan sistem yang ditemukan selama pengujian.

---

### ❌ Temuan K-3 — Inkonsistensi Nama Brand/Produk
**Lokasi:** Halaman 44–47, Sub-bab 4.3

Setelah verifikasi ulang ke gambar-gambar asli, situasinya lebih serius dari yang teridentifikasi sebelumnya:

| Sumber | Nama yang Muncul | Keterangan |
|--------|-----------------|------------|
| Teks narasi (hal. 38, 44, 50, 52) | **Resmeku** | Disebut sebagai *platform* |
| Gambar 4.3 — halaman utama | **Takoni** | Nama di navbar dan tagline |
| Gambar 4.4 — form Sign Up | **"Sign Up for Takoni"** | Judul form |
| Gambar 4.5 — form Sign In | **"Sign In to Takoni"** | Judul form |
| Gambar 4.6 — manajemen organisasi | **Resmeku** | Nama *organisasi* di dalam Takoni |
| Gambar 4.7, 4.8 — chatbot | **Resbot** | Nama *chatbot* milik org Resmeku |

**Analisis kritis:** Berdasarkan bukti visual, **Takoni** adalah nama *platform SaaS* yang dibangun, sementara **Resmeku** adalah nama *organisasi klien* (tenant) yang digunakan sebagai data uji di dalam Takoni, dan **Resbot** adalah nama *chatbot* milik organisasi Resmeku. Namun seluruh teks narasi menyebut "platform Resmeku" — padahal Resmeku bukan platform, melainkan klien/tenant. Ini adalah **kesalahan konseptual** dalam penulisan, bukan sekadar inkonsistensi nama.

**Yang harus dilakukan:**
- [ ] Perbaiki narasi: ganti semua "platform Resmeku" menjadi "platform Takoni".
- [ ] Jelaskan di Sub-bab 4.3 bahwa "Resmeku" adalah organisasi demo yang digunakan saat pengujian, dan "Resbot" adalah chatbot milik organisasi tersebut.
- [ ] Pastikan penguji bisa memahami hierarki: **Takoni (platform) → Resmeku (organisasi) → Resbot (chatbot)**.

---

## 🟡 TEMUAN SEDANG (Perlu Diperbaiki, Berpengaruh pada Nilai)

### ⚠️ Temuan S-1 — Blackbox Testing Tidak Mencantumkan Detail Pengujian
**Lokasi:** Halaman 50–51, Sub-bab 4.4.1

Tabel 4.3 hanya menampilkan kolom: *Fungsionalitas Sistem*, *Hasil Yang Diharapkan*, dan *Hasil*. Seluruh 10 skenario hasilnya adalah **"Berhasil"** tanpa variasi.

**Masalah:**
- Tidak ada kolom **"Hasil Aktual"** (apa yang benar-benar terjadi saat diuji).
- Tidak ada keterangan **siapa yang menguji** dan **kapan diuji**.
- Tidak ada kolom **"Kondisi Pengujian"** (data apa yang dimasukkan, browser apa, dll.).
- Hasil 10/10 "Berhasil" tanpa satu pun catatan atau pengecualian sangat tidak realistis dan dapat memancing pertanyaan kritis dari penguji.

**Yang harus dilakukan:**
- [ ] Tambahkan kolom "Hasil Aktual" di tabel Blackbox Testing.
- [ ] Cantumkan setidaknya satu skenario negatif (misal: login dengan password salah → sistem menampilkan pesan error).
- [ ] Tambahkan informasi penguji dan tanggal pengujian.

---

### ⚠️ Temuan S-2 — Metode Uji Kesesuaian Respons Tidak Dijelaskan Cukup
**Lokasi:** Halaman 51, Sub-bab 4.4.2

Penjelasan instrumen pengujian sangat singkat. Tidak dijelaskan:
- Apa isi dari 7 skenario kasus uji tersebut secara spesifik?
- Bagaimana kuesioner dibagikan (online/offline)?
- Apa profil responden (pengguna awam? mahasiswa? karyawan?)?
- Bagaimana tabel interpretasi skor Likert yang digunakan (acuan referensi apa)?

**Yang harus dilakukan:**
- [ ] Tambahkan deskripsi singkat dari masing-masing 7 skenario kasus uji sebagai tabel atau sub-poin.
- [ ] Jelaskan profil dan cara pemilihan responden (teknik sampling).
- [ ] Cantumkan tabel/skala interpretasi persentase Likert yang digunakan beserta referensinya.

---

### ⚠️ Temuan S-3 — Gambar Tidak Konsisten dengan Deskripsi Teks
**Lokasi:** Halaman 44–45, Sub-bab 4.3.1 dan 4.3.2

- Di teks Sub-bab 4.3.2, disebutkan form pendaftaran terdiri dari kolom *email*, *username*, dan *password*.
- Di Gambar 4.4, form tersebut juga menampilkan opsi **"Continue with Google"**, **"Continue with Github"**, dan checkbox **"I want to receive product updates"**. Detail-detail ini **tidak disebutkan dalam teks**.

**Yang harus dilakukan:**
- [ ] Perbarui deskripsi teks agar sesuai dengan semua elemen yang tampak di gambar (Google OAuth, GitHub OAuth, newsletter checkbox).
- [ ] Hal yang sama berlaku untuk Gambar 4.5 (Sign In) yang juga memiliki fitur OAuth yang tidak dibahas.

---

### ⚠️ Temuan S-4 — Judul Sub-bab Ada Highlight Kuning yang Tidak Seharusnya
**Lokasi:** Halaman 51 (Tabel 4.4 area)

Judul `4.4.2 Hasil Pengujian Kesesuaian Respons Chatbot` tercetak dengan **highlight kuning**, bukan format normal seperti sub-bab lainnya.

**Yang harus dilakukan:**
- [ ] Hapus highlight kuning di judul Sub-bab 4.4.2.
- [ ] Pastikan semua judul sub-bab menggunakan format yang sama dan konsisten.

---

## 🔵 TEMUAN MINOR (Perlu Diperhatikan)

### 📝 Temuan M-1 — Typo: "Repson" → "Respons"
**Lokasi:** Halaman 43, paragraf terakhir

> *"**Repson** yang diterima dari API ini nantinya..."*

**Perbaikan:** Ganti `Repson` → `Respons`.

---

### 📝 Temuan M-2 — Typo: "dashbord" → "dashboard"
**Lokasi:** Halaman 48, paragraf terakhir kalimat terakhir

> *"...Halaman **dashbord** dapat dilihat pada Gambar 4.8"*

**Perbaikan:** Ganti `dashbord` → `dashboard`.

---

### 📝 Temuan M-3 — Penulisan "identitias" → "identitas"
**Lokasi:** Halaman 38, paragraf pertama

> *"...digunakan untuk manajemen **identitias** dan hak akses pengguna."*

**Perbaikan:** Ganti `identitias` → `identitas`.

---

### 📝 Temuan M-4 — Tanda Titik Hilang di Akhir Kalimat Pengantar
**Lokasi:** Halaman 38, 40, 43, 48, 50

Beberapa kalimat pengantar sebelum tabel/gambar tidak diakhiri tanda titik.

Contoh:
> *"...disajikan pada Tabel 4.1"* ← tidak ada titik di akhir.
> *"...disajikan pada Tabel 4.2"* ← tidak ada titik di akhir.

**Perbaikan:** Tambahkan tanda titik (`.`) di akhir setiap kalimat yang mengarahkan pembaca ke tabel atau gambar.

---

### 📝 Temuan M-5 — Inkonsistensi Nilai Persentase di Halaman 52
**Lokasi:** Halaman 52, paragraf setelah rumus (4.1)

Di paragraf teks disebutkan:
> *"...rata-rata persentase kesesuaian respons chatbot mencapai **84,75%**..."*

Namun hasil di tabel dan di persamaan (4.1) menunjukkan:

> P = 296/350 × 100% = **84,57%**

**Masalah:** Ada inkonsistensi angka — **84,57%** (hasil hitung) vs **84,75%** (di teks).

**Yang harus dilakukan:**
- [ ] Periksa kembali mana yang benar secara aritmatika.
- [ ] Seragamkan semua penyebutan ke satu nilai yang sama dan konsisten.

---

### 📝 Temuan M-6 — Field `isActive` di Kode Tidak Tercantum di Tabel Schema
**Lokasi:** Halaman 41, kode pencarian knowledge base

```javascript
const knowledges = await Knowledge.find({
  organizationId: data.organizationId,
  chatbotId: data.chatbot._id,
  isActive: true   // ← field ini tidak ada di Tabel 4.1
});
```

Tabel 4.1 (Struktur Skema Koleksi Knowledges) tidak mencantumkan field `isActive`.

**Yang harus dilakukan:**
- [ ] Tambahkan field `isActive` (tipe: Boolean) ke Tabel 4.1 beserta keterangannya, **atau**
- [ ] Tambahkan catatan dalam teks bahwa tabel hanya menampilkan field utama.

---

## 🔴 TEMUAN TAMBAHAN — TERIDENTIFIKASI SAAT RE-AUDIT

> [!IMPORTANT]
> Empat temuan berikut terlewat dalam audit pertama setelah verifikasi ulang ke gambar asli.

### ❌ Temuan T-1 — Caption Gambar 4.1 Tidak Sesuai Isi Gambar
**Lokasi:** Halaman 41, Sub-bab 4.2.2

Gambar 4.1 diberi caption **"Gambar 4.1 Pengiriman Pertanyaan Pengguna"**, tetapi yang ditampilkan adalah widget chatbot dalam keadaan **kosong (idle)** — belum ada pertanyaan yang dikirim. Sub-bab 4.2.2 membahas "Proses Pengiriman Pertanyaan", namun gambar yang dipilih tidak mengilustrasikan proses tersebut.

**Yang harus dilakukan:**
- [ ] Ganti caption menjadi lebih akurat, misal: **"Gambar 4.1 Tampilan Awal Widget Chatbot"**.
- [ ] Atau ganti gambar dengan screenshot yang benar-benar menampilkan pengguna sedang mengetik/mengirim pesan.

---

### ❌ Temuan T-2 — Format Caption "Gambar 4. 2" Ada Spasi Berlebih
**Lokasi:** Halaman 44, caption di bawah Gambar 4.2

Caption tertulis **"Gambar 4. 2 Penampilan Respons Chatbot"** dengan spasi antara "4." dan "2". Seluruh gambar lain (4.1, 4.3 dst.) tidak memiliki spasi ini.

**Yang harus dilakukan:**
- [ ] Perbaiki menjadi **"Gambar 4.2 Penampilan Respons Chatbot"** (tanpa spasi).

---

### ⚠️ Temuan T-3 — Parameter API AI Bermasalah Secara Teknis
**Lokasi:** Halaman 43, kode di Sub-bab 4.2.5

Kode mengirim parameter berikut secara bersamaan ke API Qwen:
```
model: qwen3.5-flash,
temperature: 0.1,
max_tokens: 512,
top_p: 0.8,
enable_thinking: false
```

Terdapat **dua masalah teknis** yang perlu diklarifikasi:

1. **`temperature` dan `top_p` digunakan bersamaan.** Praktik umum AI: gunakan salah satu, tidak keduanya. Kombinasi ini dapat menghasilkan perilaku decoding yang tidak terduga dan tidak didokumentasikan dengan jelas.
2. **`max_tokens: 512` sangat terbatas** untuk chatbot layanan pelanggan. Jika respons AI dipotong di tengah, kualitas jawaban akan buruk — ini bisa menjelaskan mengapa Kasus 5 (76%) dan Kasus 6 (78%) hanya mendapat skor "Sesuai".
3. **`model: qwen3.5-flash`** — Verifikasi kebenaran nama model ini. Model Qwen yang terdokumentasi adalah `qwen2.5`, `qwen-plus`, `qwen-turbo`, dsb. Nama `qwen3.5-flash` belum terdokumentasi secara publik saat penelitian dilakukan.

**Yang harus dilakukan:**
- [ ] Tambahkan penjelasan dalam teks mengapa memilih `temperature: 0.1` (jawaban deterministik).
- [ ] Verifikasi dan cantumkan nama model secara tepat dan sesuai dokumentasi resmi Qwen.
- [ ] Pertimbangkan menaikkan `max_tokens` dan jelaskan alasan pemilihan nilai ini.

---

### ⚠️ Temuan T-4 — Teknologi UI (Tailwind & shadcn/ui) Baru Disebutkan di Bab IV
**Lokasi:** Halaman 44, paragraf pembuka Sub-bab 4.3

Paragraf berisi:
> *"...Seluruh halaman dirancang dengan pendekatan sederhana, intuitif, dan responsif sehingga memudahkan **Tailwind CSS dan komponen shadcn/ui**..."*

**Masalah:** Ini adalah **pertama kalinya** Tailwind CSS dan shadcn/ui disebutkan dalam dokumen. Seharusnya kedua teknologi ini sudah diperkenalkan dan dijustifikasi di **Bab III (Metodologi/Teknologi yang Digunakan)**. Penguji dapat mempertanyakan mengapa justifikasi tidak ada di Bab III.

**Yang harus dilakukan:**
- [ ] Pastikan Tailwind CSS dan shadcn/ui sudah tercantum di Bab III (Tabel teknologi atau sub-bab stack teknologi).
- [ ] Di Bab IV, cukup menyebut "sesuai yang telah dijelaskan di Bab III" tanpa perlu mengenalkan ulang.

---

## 📊 RINGKASAN TEMUAN

| Kode | Kategori | Judul Temuan | Prioritas |
|------|----------|--------------|-----------|
| K-1 | 🔴 Kritis | Data placeholder `x` belum diisi | Sebelum Sidang |
| K-2 | 🔴 Kritis | Sub-bab 4.5 tidak berisi pembahasan | Sebelum Sidang |
| K-3 | 🔴 Kritis | Kesalahan konseptual nama brand (Takoni vs Resmeku vs Resbot) | Sebelum Sidang |
| S-1 | 🟡 Sedang | Blackbox Testing kurang detail | Sebelum Sidang |
| S-2 | 🟡 Sedang | Metode uji Likert tidak dijelaskan cukup | Sebelum Sidang |
| S-3 | 🟡 Sedang | Gambar tidak sesuai deskripsi teks (OAuth tidak disebutkan) | Sebelum Sidang |
| S-4 | 🟡 Sedang | Highlight kuning di judul sub-bab 4.4.2 | Segera |
| T-3 | 🟡 Sedang | *(Baru)* Parameter API AI bermasalah secara teknis | Sebelum Sidang |
| T-4 | 🟡 Sedang | *(Baru)* Tailwind/shadcn pertama disebut di Bab IV, bukan Bab III | Segera |
| M-1 | 🔵 Minor | Typo "Repson" | Segera |
| M-2 | 🔵 Minor | Typo "dashbord" | Segera |
| M-3 | 🔵 Minor | Typo "identitias" | Segera |
| M-4 | 🔵 Minor | Tanda titik hilang di akhir kalimat pengantar | Segera |
| M-5 | 🔵 Minor | Inkonsistensi angka 84,57% vs 84,75% | Segera |
| M-6 | 🔵 Minor | Field `isActive` tidak ada di Tabel 4.1 | Segera |
| T-1 | 🔵 Minor | *(Baru)* Caption Gambar 4.1 tidak sesuai isi | Segera |
| T-2 | 🔵 Minor | *(Baru)* Spasi berlebih di caption "Gambar 4. 2" | Segera |

**Total: 3 Kritis | 6 Sedang | 8 Minor = 17 Temuan**

> [!NOTE]
> Re-audit memperbaiki framing K-3 (dari sekadar inkonsitensi nama menjadi kesalahan konseptual hierarki produk) dan menambahkan 4 temuan baru (T-1 s/d T-4) yang terlewat di audit pertama.

---

## ✅ CHECKLIST REVISI MAHASISWA

```
BAB IV — CHECKLIST REVISI SEBELUM SIDANG (v2 — setelah re-audit)

KRITIS (wajib selesai sebelum kumpul dokumen):
[ ] K-1: Isi jumlah responden yang sebenarnya (ganti semua 'x')
       → Dari kalkulasi tabel: Skor Maks=50, Likert max=5, jadi responden=10.
         Pastikan angka ini memang benar, lalu masukkan ke teks.
[ ] K-2: Tulis sub-bab 4.5 Pembahasan secara lengkap dan substantif
[ ] K-3: Perbaiki kesalahan konseptual nama — platform=Takoni, klien=Resmeku, chatbot=Resbot
       → Ganti semua "platform Resmeku" di teks menjadi "platform Takoni"
       → Tambahkan penjelasan hierarki: Takoni > Resmeku (org) > Resbot (chatbot)

SEDANG (berpengaruh signifikan pada nilai):
[ ] S-1: Lengkapi tabel Blackbox Testing (kolom hasil aktual, kondisi uji, tanggal/penguji)
[ ] S-2: Jelaskan profil responden, cara sampling, dan tabel skala Likert + referensi
[ ] S-3: Sesuaikan deskripsi teks: sebut fitur Google OAuth & GitHub OAuth yang terlihat di gambar
[ ] S-4: Hapus highlight kuning di judul Sub-bab 4.4.2
[ ] T-3: Klarifikasi parameter API — verifikasi nama model & justifikasi temperature/top_p/max_tokens
[ ] T-4: Pastikan Tailwind CSS dan shadcn/ui sudah disebutkan di Bab III

MINOR (penyempurnaan):
[ ] M-1: Perbaiki typo "Repson" -> "Respons" (hal. 43)
[ ] M-2: Perbaiki typo "dashbord" -> "dashboard" (hal. 48)
[ ] M-3: Perbaiki typo "identitias" -> "identitas" (hal. 38)
[ ] M-4: Tambahkan tanda titik di akhir kalimat pengantar tabel/gambar (cek hal. 38,40,43,48,50)
[ ] M-5: Seragamkan nilai persentase: gunakan 84,57% (hasil hitung benar) di semua tempat
[ ] M-6: Tambahkan field 'isActive' (Boolean) ke Tabel 4.1
[ ] T-1: Ganti caption Gambar 4.1 agar sesuai isi gambar (widget kosong, bukan proses kirim)
[ ] T-2: Hapus spasi di "Gambar 4. 2" -> "Gambar 4.2"
```

---

## 💡 SARAN UMUM UNTUK MAHASISWA

> [!TIP]
> **Untuk Sub-bab 4.5 Pembahasan**, fokuslah menjawab pertanyaan berikut dalam tulisan kamu:
> 1. "Mengapa sistem ini bisa berfungsi dengan baik?" (kaitan dengan desain di Bab III)
> 2. "Apa yang membuat 2 kasus uji hanya mendapat skor 'Sesuai' (76% dan 78%) dan bukan 'Sangat Sesuai'?" — ini justru temuan menarik yang perlu dibahas!
> 3. "Apa keterbatasan sistem yang saya bangun?" (jujur mengakui keterbatasan adalah nilai plus di mata penguji)
> 4. "Bagaimana hasil ini dibandingkan dengan penelitian terdahulu di Bab II?"

> [!NOTE]
> **Tentang inkonsistensi nama brand**: Sebelum sidang, pastikan kamu bisa menjawab pertanyaan penguji seperti: *"Di sini tertulis Resmeku, tapi di gambar tertulis Takoni, ini platform yang sama atau berbeda?"* Penguji **pasti** akan menanyakan ini.

> [!WARNING]
> **Jangan membawa dokumen dengan placeholder `x` ke sidang.** Penguji akan langsung mempermasalahkan ini dan bisa menjadi dasar untuk menunda kelulusan sidang.
