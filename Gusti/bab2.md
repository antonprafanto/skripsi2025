# LAPORAN AUDIT DRAFT SKRIPSI

**Nama Mahasiswa:** Gusti Dimas Novarossi  
**NIM:** 2109106124  
**Dokumen:** Draft Skripsi – BAB II (Tinjauan Pustaka)  
**Halaman yang Diaudit:** 5 – 22 (Halaman 5 s/d 22 berdasarkan nomor halaman pada dokumen)  
**Tanggal Audit:** 27 April 2026  
**Auditor:** Dosen Informatika

---

## RINGKASAN EKSEKUTIF

Draft BAB II skripsi ini membahas Tinjauan Pustaka yang cukup komprehensif mencakup 16 sub-bab (2.1 hingga 2.16). Topik yang dibahas meliputi penelitian terkait, analisis kompetitor chatbot, konsep AI, Chatbot, Website, teknologi pengembangan (Next.js, Tailwind CSS), metode Waterfall, MongoDB, Mongoose, REST API, Risk Assessment, Blackbox Testing, Uji Kesesuaian Respons Chatbot, Skala Likert, Flowchart, UML (Use Case Diagram & Sequence Diagram). Secara umum, tulisan cukup baik, namun terdapat beberapa catatan penting yang perlu direvisi.

---

## TEMUAN AUDIT PER ASPEK

### 1. Kelengkapan dan Kedalaman Konten

#### ✅ Hal Positif:
- Tinjauan pustaka mencakup topik yang sangat relevan dengan penelitian chatbot berbasis AI.
- Setiap sub-bab memiliki definisi yang cukup jelas dan disertai referensi.
- Terdapat analisis kompetitor (Tabel 2.1) yang menunjukkan posisi sistem yang dibangun.
- Tabel simbol untuk Flowchart, Use Case Diagram, dan Sequence Diagram disajikan dengan baik.

#### ⚠️ Catatan & Saran Revisi:
- **Sub-bab 2.4: Typo pada judul** → ditulis *"Artifical Intelligence"* (salah), seharusnya **"Artificial Intelligence"**. Harap diperbaiki.
- **Sub-bab 2.1 (Penelitian Terkait):** Penelitian terkait sudah 10 item, namun tidak ada tabel rangkuman perbandingan. **Saran:** Tambahkan tabel matriks perbandingan penelitian terkait yang memuat kolom: No, Peneliti/Tahun, Judul/Topik, Metode, Teknologi, Hasil, Perbedaan dengan penelitian ini. Ini akan mempermudah pembaca memahami posisi penelitian.
- **Sub-bab 2.2 (Analisis Kompetitor):** Tabel 2.1 sudah ada namun fitur yang dibandingkan masih terbatas. **Saran:** Tambahkan fitur seperti "Harga/Biaya", "API Availability", dan "Keamanan Data" untuk memperkuat argumen keunggulan sistem yang dikembangkan.

---

### 2. Penggunaan Referensi & Sitasi

#### ✅ Hal Positif:
- Setiap paragraf umumnya sudah disertai sitasi.
- Format sitasi konsisten menggunakan gaya (Penulis, Tahun).

#### ⚠️ Catatan & Saran Revisi:
- **Sub-bab 2.10 (REST API):** Referensi menggunakan *"(GeeksForGeeks, 2025)"*. Sumber dari situs seperti GeeksForGeeks, W3Schools, atau Medium **tidak direkomendasikan** sebagai referensi ilmiah dalam skripsi. **Saran:** Ganti dengan jurnal atau buku akademik yang membahas REST API, misalnya buku karya Fielding (2000) atau jurnal yang terindeks.
- **Beberapa sub-bab** hanya memiliki satu referensi tunggal untuk seluruh paragraf panjang. **Saran:** Perkaya dengan minimal 2 referensi per konsep utama untuk memperkuat landasan teori.
- **Tahun referensi:** Terdapat referensi tahun 2026 (Rahmaya et al., 2026) yang perlu diverifikasi apakah sudah benar-benar terbit dan dapat diakses — pastikan referensi valid dan dapat dilacak.

---

### 3. Struktur Penulisan & Format

#### ✅ Hal Positif:
- Hierarki sub-bab jelas dan terurut dengan baik (2.1, 2.2, ..., 2.16.1, 2.16.2).
- Penomoran halaman konsisten.
- Penggunaan cetak miring (*italic*) untuk istilah asing sudah dilakukan dengan cukup konsisten.

#### ⚠️ Catatan & Saran Revisi:
- **Penomoran sub-bab tidak konsisten:** Sub-bab mulai dari 2.1 hingga 2.16, namun loncat dari 2.9 (Mongoose) langsung ke 2.10 (REST API) kemudian 2.11, dst — ini perlu dicek ulang apakah ada sub-bab yang terlewat atau urutannya logis dalam konteks penelitian.
- **Gambar 2.1 (Tahapan Metode Waterfall):** Gambar sudah ada namun kualitas diagram perlu ditingkatkan. Caption gambar sudah ada (**Gambar 2.1 Tahapan Metode Waterfall**) — pastikan penomoran gambar konsisten dengan referensi dalam teks.
- **Tabel-tabel simbol (Tabel 2.2, 2.3, 2.4):** Secara umum baik, namun pastikan setiap tabel direferensikan secara eksplisit dalam teks sebelum tabel muncul. Contoh yang perlu diperbaiki: pada halaman 21, kalimat pengantar menuju Tabel 2.4 terpotong tanpa tanda baca yang tepat — *"...dapat dilihat pada Tabel 2.4"* sebaiknya diakhiri dengan tanda titik (**.**), bukan tanpa tanda baca.
- **Penggunaan istilah Bahasa Inggris:** Sudah cukup konsisten dicetak miring. Namun ada beberapa tempat yang tidak konsisten, seperti kata "database" kadang dicetak miring, kadang tidak. **Saran:** Tetapkan aturan yang konsisten — semua istilah asing/teknis yang belum diserap ke Bahasa Indonesia dicetak miring.

---

### 4. Relevansi dengan Topik Penelitian

#### ✅ Hal Positif:
- Topik-topik yang dibahas sangat relevan untuk penelitian pengembangan sistem chatbot berbasis AI pada platform website.
- Pemilihan teknologi (Next.js, Tailwind CSS, MongoDB, Mongoose, REST API) sesuai dengan stack yang umum digunakan.

#### ⚠️ Catatan & Saran Revisi:
- **Sub-bab mengenai teknologi AI/LLM kurang mendalam:** Sub-bab 2.4 (AI) menyebutkan LLM secara singkat namun tidak ada sub-bab khusus yang membahas teknologi LLM/GPT/OpenAI API yang digunakan dalam sistem. **Saran:** Tambahkan sub-bab khusus tentang **OpenAI API / ChatGPT API** atau **teknologi LLM yang digunakan** mengingat dari penelitian terkait jelas sistem mengintegrasikan API ChatGPT.
- **Sub-bab 2.11 (Risk Assessment):** Konsep risk assessment disebutkan, tetapi hubungannya dengan sistem chatbot yang dikembangkan kurang dijelaskan. **Saran:** Tambahkan kalimat penghubung yang menjelaskan mengapa risk assessment relevan dalam konteks penelitian ini.
- **Natural Language Processing (NLP):** NLP disebutkan berulang kali di penelitian terkait dan sub-bab chatbot, namun tidak ada sub-bab tersendiri yang membahas NLP secara teori. **Saran:** Pertimbangkan menambahkan sub-bab NLP sebagai landasan teori tersendiri.

---

### 5. Tata Bahasa & Ejaan

#### ✅ Hal Positif:
- Secara umum kalimat sudah formal dan akademis.
- Penggunaan paragraf cukup terstruktur.

#### ⚠️ Catatan & Saran Revisi:
- **Typo teridentifikasi:**
  - Hal. 12: *"Artifical Intelligence"* → seharusnya **"Artificial Intelligence"**
  - Hal. 15: *"sturktur"* → seharusnya **"struktur"**
  - Hal. 15: *"disimpan dlama format"* → seharusnya **"disimpan dalam format"**
- **Kalimat terlalu panjang:** Beberapa paragraf mengandung kalimat yang sangat panjang (lebih dari 3 klausa) sehingga sulit dipahami. **Saran:** Pecah kalimat panjang menjadi beberapa kalimat yang lebih pendek dan jelas.
- **Pengulangan kata:** Beberapa sub-bab mengulang kata yang sama di awal kalimat berturut-turut. Variasikan struktur kalimat untuk meningkatkan keterbacaan.

---

## TABEL REKAPITULASI TEMUAN

| No | Aspek | Status | Prioritas Revisi |
|----|-------|--------|-----------------|
| 1 | Typo "Artifical" pada judul sub-bab 2.4 | ❌ Perlu Diperbaiki | **Tinggi** |
| 2 | Typo "sturktur" dan "dlama" di hal. 15 | ❌ Perlu Diperbaiki | **Tinggi** |
| 3 | Referensi GeeksForGeeks tidak akademis | ❌ Perlu Diperbaiki | **Tinggi** |
| 4 | Tidak ada tabel matriks penelitian terkait | ⚠️ Perlu Ditambahkan | **Tinggi** |
| 5 | Sub-bab OpenAI API/LLM tidak ada | ⚠️ Perlu Ditambahkan | **Tinggi** |
| 6 | Kalimat pengantar Tabel 2.4 tanpa tanda titik | ❌ Perlu Diperbaiki | **Sedang** |
| 7 | Referensi tahun 2026 perlu diverifikasi | ⚠️ Perlu Dicek | **Sedang** |
| 8 | Penggunaan cetak miring tidak konsisten | ⚠️ Perlu Diseragamkan | **Sedang** |
| 9 | Sub-bab NLP tidak ada | ⚠️ Pertimbangkan Tambah | **Sedang** |
| 10 | Analisis kompetitor kurang lengkap | ⚠️ Perlu Diperlengkap | **Rendah** |
| 11 | Relevansi Risk Assessment kurang dijelaskan | ⚠️ Perlu Klarifikasi | **Rendah** |
| 12 | Kalimat terlalu panjang di beberapa bagian | ⚠️ Perlu Diperbaiki | **Rendah** |

---

## SARAN PERBAIKAN UTAMA (PRIORITAS TINGGI)

1. **Segera perbaiki typo** pada judul sub-bab 2.4 dan kata-kata di halaman 15.
2. **Ganti referensi GeeksForGeeks** dengan sumber akademik yang valid (jurnal/buku).
3. **Tambahkan tabel matriks perbandingan** penelitian terkait untuk memudahkan pembaca melihat posisi penelitian ini.
4. **Tambahkan sub-bab tentang OpenAI API / ChatGPT API** sebagai landasan teori teknologi utama yang digunakan dalam sistem.
5. **Periksa kembali semua tanda baca** terutama pada kalimat penutup sebelum tabel/gambar.

---

## KESIMPULAN UMUM

BAB II skripsi ini sudah memiliki fondasi yang baik dengan cakupan topik yang cukup luas dan relevan. Dengan melakukan perbaikan pada typo, penguatan referensi akademik, penambahan sub-bab penting (OpenAI API/LLM), dan penyempurnaan format, kualitas bab ini akan meningkat secara signifikan dan layak untuk dipresentasikan dalam seminar hasil. Mahasiswa disarankan untuk melakukan **proofreading menyeluruh** sebelum finalnya.

---

*Laporan ini dibuat berdasarkan hasil audit visual terhadap draft skripsi yang diserahkan. Mahasiswa diharapkan melakukan revisi sesuai catatan di atas dan mengkonsultasikan hasilnya kembali kepada pembimbing.*
