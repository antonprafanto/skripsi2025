# Audit — BAB I: Pendahuluan

**Halaman PDF:** ~10–17 (hlm dokumen 1–8)  
**Status:** Substansi baik — revisi wajib pada rumusan, bukti lokal, dan title framing

**Nilai substansi:** 7/10  
**Nilai penulisan akademik:** 7/10

---

## Ringkasan Bab

Bab I sudah punya alur ilmiah yang baik: AI di pendidikan → chatbot → kelemahan rule-based & hallucination LLM → RAG → peluang voice + ESP32 sebagai edge → kesenjangan penelitian → tujuan. Tingkat tulisannya **jauh di atas** tipikal proposal “baru mulai”.

Kelemahan utama: masalah lokal belum terbukti, rumusan terlalu padat, dan sebagian tujuan/manfaat saling tumpang tindih.

---

## 1.1 Latar Belakang

### Yang Sudah Baik
- Sitasi relevan (Kuleto, Pérez, UNESCO, Adamopoulou, Chuang, Lewis, Kuhail, Zawacki-Richter)
- Penjelasan jujur: ESP32 **tidak** menjalankan GPT penuh — hanya antarmuka
- Kesenjangan: jarang kombinasi **voice + LLM + RAG + embedded** untuk layanan akademik (bukan hanya learning)
- Justifikasi inklusi/aksesibilitas disebut (meski klaimnya perlu di-soften)

### Temuan

| Prioritas | Temuan | Kenapa masalah? | Perbaikan |
|-----------|--------|-----------------|-----------|
| **Wajib** | Masalah masih **generik** “banyak PT di Indonesia” | Penguji tanya: “Di UNMUL/Informatika, datanya apa?” | Tambah 1 paragraf observasi/studi kasus lokal + jenis dokumen KB |
| **Wajib** | Pertanyaan penelitian di akhir 1.1 **menggandakan** seluruh 1.2 | Redundan & terlalu kompleks sebagai “satu pertanyaan” | Ringkas di 1.1; detail di 1.2 yang sudah dipecah |
| Disarankan | Klaim 87% orang dengan gangguan penglihatan (UNESCO) dipindahkan ke justifikasi produk tanpa rencana uji | Overclaim | Soften: “berpotensi mendukung akses…” atau rencanakan uji aksesibilitas di Bab III |
| Disarankan | Justifikasi RAG ala chat WA (tanpa RAG mengarang Kaprodi) belum ditulis | Argumen paling mudah dipahami penguji | Masukkan 1 ilustrasi konkret “tanpa RAG vs dengan RAG” |
| **Wajib** | Spek teknis menyebut ESP32 **Xtensa LX6 / SRAM ~520 KB** | Perangkat aktual = kit **KS5026 (ESP32-S3)**; spek LX6 milik ESP32 klasik → terlihat copy-paste salah | Ganti ke spek ESP32-S3 (LX7, flash/PSRAM sesuai modul N16R8) dan sebut KS5026 sebagai kit |
| **Wajib** | Tidak ada pembahasan **privasi/keamanan**: rekaman suara & dokumen kampus dikirim ke API pihak ketiga | Penguji AI+cloud biasanya menanyakan ini | Tambah batasan etika + praktik: izin dokumen, retensi audio, API key di server |
| Opsional | Beberapa sitasi format inkonsisten (`et al` tanpa titik; `Pérez` encoding rusak di ekstraksi) | Kerapian | Cek ulang PDF |

### Paragraf lokal yang perlu ditambahkan (contoh kerangka)

> Berdasarkan pengumpulan dokumen dan koordinasi dengan [staf akademik / Kaprodi / admin] Program Studi Informatika Universitas Mulawarman, informasi layanan akademik mahasiswa masih tersebar pada [portal / PDF panduan / grup pesan]. Pertanyaan berulang yang sering muncul meliputi [KRS, kalender, dosen wali, prosedur skripsi]. Dokumen resmi yang akan menjadi basis pengetahuan penelitian ini meliputi [sebutkan 4–6 jenis dokumen]. Kondisi tersebut menjadi landasan pengembangan asisten suara berbasis RAG agar jawaban merujuk pada dokumen institusi, bukan pengetahuan parametrik model semata.

---

## 1.2 Rumusan Masalah

### Kondisi sekarang
Satu kalimat majemuk yang mencampur: **implementasi sistem** + **peningkatan aksesibilitas/responsivitas** + **efektivitas memahami keragaman pertanyaan**.

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Sulit diuji & dijawab di kesimpulan | Pecah menjadi 3–4 rumusan |
| **Wajib** | “Meningkatkan aksesibilitas dan responsivitas” belum terdefinisi | Definisikan indikator (latensi, keberhasilan task, skor UAT) di Bab III dan rujuk di sini |

### Rumusan yang disarankan

1. Bagaimana merancang dan mengimplementasikan chatbot layanan akademik berbasis interaksi suara yang mengintegrasikan ESP32 sebagai antarmuka tepi, Speech-to-Text, pipeline RAG, model GPT, dan Text-to-Speech?
2. Bagaimana kinerja *retrieval* dokumen pada pipeline RAG terhadap pertanyaan uji layanan akademik Prodi Informatika UNMUL?
3. Bagaimana kualitas jawaban sistem (ketepatan terhadap dokumen sumber dan relevansi) dibandingkan baseline tanpa konteks RAG?
4. Berapa waktu respons end-to-end sistem, dan bagaimana hasil pengujian fungsional black-box pada rangkaian perangkat keras–perangkat lunak?

---

## 1.3 Batasan Masalah

### Yang Sudah Baik — ini kekuatan proposalmu
1. ESP32 = antarmuka; AI di server  
2. GPT via API; butuh internet; tidak offline  
3. KB dari dokumen akademik; **bukan** integrasi SIAKAD langsung  
4. KB **statis**, update manual + re-index (contoh ganti Kaprodi) — selaras chat WA  
5. Bahasa Indonesia  
6. Fokus evaluasi fungsi; tidak train LLM baru  

### Temuan tambahan yang wajib ditambahkan

| Prioritas | Temuan | Saran teks batasan |
|-----------|--------|-------------------|
| **Wajib** | Prototipe punya **web search** & mode umum | “Fitur pencarian web / jawaban pengetahuan umum di luar dokumen akademik **tidak termasuk / termasuk terbatas** dalam ruang lingkup evaluasi skripsi.” — pilih salah satu secara eksplisit |
| **Wajib** | Domain institusi belum disebut | Batasi: Prodi Informatika FT UNMUL (atau kampus X) |
| Disarankan | Ketergantungan vendor API | Sebut batasan: biaya token, ketersediaan layanan pihak ketiga, bahasa Indonesia STT/TTS |
| Disarankan | Lingkungan uji suara | Sebut kondisi: ruangan semi-terkontrol / jarak mikrofon / satu pembicara |
| Disarankan | Memori percakapan multi-turn | Batasi: single-turn atau window N giliran saja |
| **Wajib** | Etika data: suara pengguna + KB institusi ke cloud | Tambah poin batasan/etika eksplisit |

---

## 1.4 Tujuan Penelitian

### Yang Sudah Baik
- Tujuan 1 (implementasi), 3 (terapkan RAG), 4 (uji akurasi/relevansi/waktu) selaras skripsi Informatics

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Tujuan 2 (“Mempermudah mahasiswa…”) adalah **manfaat**, bukan tujuan penelitian | Pindahkan ke 1.5; ganti tujuan 2 menjadi misalnya “Membangun knowledge base akademik lokal dan mekanisme pembaruan indeks RAG” |
| Disarankan | Selaraskan jumlah tujuan dengan jumlah rumusan | 1–1 mapping |

---

## 1.5 Manfaat Penelitian

Sudah memadai (mahasiswa, institusi, pengembang).  
**Catatan:** klaim inklusi visual oke sebagai manfaat yang diharapkan, jangan dijual sebagai hasil terbukti sebelum ada uji.

---

## 1.6 Kontribusi Penelitian

### Yang Sudah Baik
- Integrasi voice + embedded untuk layanan akademik  
- RAG KB lokal bahasa Indonesia + mekanisme update  
- Evaluasi kemampuan sistem  

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | Poin 3 klaim “kebaruan menggabungkan GPT, RAG, STT, TTS **dalam satu perangkat ESP32**” | Hati-hati: pemrosesan AI **bukan** di ESP32. Tulis: “menggabungkan … dengan **antarmuka** perangkat ESP32” |
| **Wajib** | Hardware memakai kit konsumen KS5026 (Xiao Zhi) | Penguji bisa bilang “ini hanya ikut tutorial kit”. Tegaskan diferensiasi: knowledge base akademik UNMUL, pipeline RAG, metrik evaluasi, bukan sekadar voice chat generik |
| Opsional | Bedakan kontribusi *engineering* vs *evaluasi empiris* | Agar penguji tidak menilai ini “hanya perakitan API” |

---

## Checklist Revisi Bab I
```
[ ] Tambah bukti/konteks lokal UNMUL (1 paragraf)
[ ] Pecah rumusan masalah 3–4 butir terukur
[ ] Rapikan tujuan (pisahkan manfaat)
[ ] Tambah batasan: institusi, mode web/general, kondisi uji audio, etika/privasi
[ ] Soften klaim disabilitas ATAU rencanakan uji
[ ] Masukkan ilustrasi tanpa-RAG vs RAG (dari chat)
[ ] Perbaiki frasa kontribusi “GPT pada ESP32”
[ ] Perbaiki spek mikrokontroler → ESP32-S3 / KS5026 (hapus LX6)
[ ] Tegaskan kontribusi di atas kit KS5026 (bukan tutorial rakitan generik)
```
**Estimasi:** 3–5 hari menulis (termasuk observasi singkat).
