# Laporan Audit Draft Skripsi

## Identitas Audit
- **Objek audit**: Draft skripsi BAB I (halaman 1–4 dari cuplikan yang diberikan)
- **Topik**: Perancangan/pengembangan website chatbot AI pada platform Resmeku menggunakan metode Waterfall
- **Cakupan audit**: Latar belakang, rumusan masalah, batasan masalah, tujuan penelitian, manfaat penelitian, dan kontribusi penelitian.

## Ringkasan Umum
Secara umum, struktur BAB I sudah mengikuti pola akademik yang lazim: ada latar belakang, rumusan masalah, batasan masalah, tujuan, manfaat, dan kontribusi. Topik yang diangkat juga cukup relevan dengan kebutuhan otomatisasi layanan pelanggan.

Namun, dari sisi kualitas ilmiah dan penulisan, masih ada beberapa hal yang perlu diperbaiki agar lebih kuat saat seminar maupun penilaian naskah. Masalah utama yang terlihat adalah: **alur argumentasi latar belakang belum sepenuhnya tajam, rumusan masalah masih terlalu umum, konsistensi istilah belum rapi, kontribusi penelitian masih bertumpuk dengan manfaat, serta beberapa kalimat masih panjang dan kurang efektif**.

## Temuan Audit per Bagian

### 1. Latar Belakang
**Kekuatan:**
- Sudah dimulai dari konteks umum perkembangan teknologi informasi menuju masalah spesifik layanan pelanggan.
- Sudah menjelaskan urgensi penggunaan chatbot AI.
- Sudah mengaitkan masalah pada platform Resmeku.
- Sudah menyebut alasan pemilihan metode Waterfall.

**Catatan masalah:**
- Alur masalah belum cukup tajam dari "kondisi ideal" → "masalah aktual" → "dampak" → "solusi yang diusulkan".
- Klaim tentang kondisi Resmeku masih cenderung deskriptif, tetapi belum terlihat didukung data konkret seperti jumlah pertanyaan, durasi respons, atau temuan observasi/wawancara.
- Alasan memilih **Waterfall** masih normatif. Perlu diperkuat kenapa metode ini paling cocok dibanding metode lain untuk konteks penelitian ini.
- Ada beberapa kalimat terlalu panjang sehingga menurunkan ketegasan argumentasi.
- Istilah seperti *chatbot AI*, *website chatbot AI*, *sistem chatbot berbasis website*, dan *layanan chatbot* digunakan bergantian; sebaiknya dipilih istilah utama yang konsisten.

**Saran revisi:**
- Tambahkan data atau hasil observasi awal yang lebih konkret tentang permasalahan layanan pelanggan di Resmeku.
- Tegaskan gap penelitian/praktik: misalnya, Resmeku belum memiliki sistem layanan otomatis berbasis knowledge base terstruktur.
- Ringkas kalimat-kalimat panjang menjadi lebih fokus pada satu gagasan per kalimat.
- Tambahkan justifikasi metodologis pemilihan Waterfall berdasarkan karakteristik kebutuhan sistem yang stabil.

**Contoh arah revisi:**
> Platform Resmeku masih mengandalkan layanan pelanggan manual melalui email dan media sosial. Pola layanan ini menimbulkan kendala berupa lambatnya respons, tingginya pertanyaan berulang, dan ketergantungan pada ketersediaan admin. Kondisi tersebut menunjukkan perlunya sistem chatbot AI berbasis website yang mampu memberikan respons otomatis secara real-time berdasarkan knowledge base terstruktur.

### 2. Rumusan Masalah
**Kekuatan:**
- Rumusan masalah sudah selaras dengan topik penelitian.
- Sudah memuat unsur perancangan, knowledge base, integrasi sistem, dan tujuan layanan informasi.

**Catatan masalah:**
- Rumusan masalah masih terlalu luas karena memuat banyak unsur sekaligus dalam satu kalimat.
- Bentuk pertanyaan masih cenderung mengarah ke proses perancangan, belum menonjolkan aspek evaluasi hasil.

**Saran revisi:**
- Bila kampus memperbolehkan, pecah menjadi 2–3 rumusan masalah agar lebih operasional.
- Tambahkan unsur pengujian/fungsionalitas agar selaras dengan tujuan penelitian.

**Contoh revisi:**
1. Bagaimana merancang sistem chatbot AI berbasis website pada platform Resmeku menggunakan metode Waterfall?
2. Bagaimana mengintegrasikan knowledge base terstruktur ke dalam sistem chatbot AI pada platform Resmeku?
3. Bagaimana hasil pengujian fungsionalitas dan kesesuaian respons sistem chatbot AI yang dikembangkan?

### 3. Batasan Masalah
**Kekuatan:**
- Sudah membatasi model AI, ruang lingkup data, aspek keamanan, dan pengujian.
- Batasan cukup membantu menjaga fokus penelitian.

**Catatan masalah:**
- Penyebutan model eksternal sangat spesifik (qwen3.5-flash), tetapi belum dijelaskan apakah ini tetap atau bisa berubah jika layanan API berubah.
- Batasan nomor 2 tentang keamanan data sensitif pengguna perlu redaksi yang lebih hati-hati agar tidak terkesan mengabaikan keamanan sistem.
- Batasan pengujian masih umum; perlu disebut jenis uji yang dilakukan secara lebih jelas.

**Saran revisi:**
- Ubah redaksi agar lebih akademik, misalnya: penelitian ini tidak membahas audit keamanan secara mendalam, bukan berarti keamanan diabaikan.
- Perjelas jenis pengujian: black-box testing, uji respons jawaban, atau uji user acceptance sederhana.

**Contoh revisi poin 2:**
> Penelitian ini tidak membahas audit keamanan data dan pengujian kerentanan sistem secara mendalam, melainkan berfokus pada perancangan, implementasi, dan pengujian fungsional sistem chatbot.

### 4. Tujuan Penelitian
**Kekuatan:**
- Sudah sesuai dengan topik dan rumusan masalah.
- Sudah memuat unsur implementasi dan pengujian.

**Catatan masalah:**
- Tujuan masih ditulis dalam satu paragraf panjang.
- Akan lebih kuat jika diturunkan langsung dari rumusan masalah dalam bentuk poin.

**Saran revisi:**
Gunakan format poin agar lebih terukur:
1. Merancang sistem chatbot AI berbasis website pada platform Resmeku menggunakan metode Waterfall.
2. Mengimplementasikan knowledge base terstruktur ke dalam sistem chatbot.
3. Menguji fungsionalitas sistem dan kesesuaian respons layanan yang dihasilkan.

### 5. Manfaat Penelitian
**Kekuatan:**
- Sudah memisahkan manfaat bagi penulis, mahasiswa, dan instansi.
- Isi manfaat sudah cukup relevan.

**Catatan masalah:**
- Bagian manfaat untuk penulis dan mahasiswa masih terlalu mirip, sehingga terkesan repetitif.
- Kalimat "metode/teknik/algoritma/cara" terlalu banyak sinonim dalam satu frasa dan membuat tulisan kurang efektif.
- Manfaat untuk instansi masih berupa harapan, belum spesifik pada output penelitian.

**Saran revisi:**
- Sederhanakan redaksi agar tiap pihak memperoleh manfaat yang berbeda dan jelas.
- Fokuskan manfaat instansi pada penggunaan hasil penelitian sebagai prototipe/referensi pengembangan layanan.

**Contoh perbaikan singkat:**
- **Bagi penulis**: menambah pengalaman dalam merancang dan mengimplementasikan sistem chatbot AI berbasis website dengan integrasi API pihak ketiga.
- **Bagi mahasiswa**: menjadi referensi pembelajaran terkait penerapan metode Waterfall pada pengembangan sistem chatbot.
- **Bagi instansi**: menjadi alternatif solusi awal untuk meningkatkan efisiensi layanan informasi pada platform Resmeku.

### 6. Kontribusi Penelitian
**Catatan utama:**
- Bagian ini masih bertumpang tindih dengan manfaat penelitian.
- Kontribusi seharusnya menonjolkan **kebaruan atau sumbangan nyata** penelitian, bukan sekadar manfaat umum.

**Saran revisi:**
Fokuskan kontribusi pada hal berikut:
- menghasilkan prototipe chatbot AI berbasis website untuk layanan informasi Resmeku,
- menyediakan implementasi knowledge base terstruktur pada konteks layanan pelanggan,
- memberi contoh penerapan Waterfall pada pengembangan sistem chatbot di lingkungan studi kasus nyata.

**Contoh revisi:**
> Kontribusi penelitian ini adalah menghasilkan prototipe sistem chatbot AI berbasis website yang terintegrasi dengan knowledge base layanan Resmeku, serta mendokumentasikan tahapan pengembangannya menggunakan metode Waterfall sebagai referensi implementasi pada penelitian sejenis.

## Catatan Kebahasaan dan Teknis Penulisan
- Gunakan istilah yang konsisten, misalnya pilih salah satu: **"chatbot AI berbasis website"**.
- Hindari kalimat terlalu panjang; satu kalimat sebaiknya memuat satu ide utama.
- Periksa kembali konsistensi huruf miring untuk istilah asing seperti *real-time*, *knowledge base*, *platform*, *chatbot*, *Waterfall* (sesuaikan dengan pedoman kampus).
- Pastikan penulisan nama platform konsisten: **Resmeku**.
- Cek kembali sitasi di daftar pustaka: nama penulis, tahun, dan format harus konsisten dengan aturan kampus.
- Jika menggunakan klaim yang bersifat faktual pada objek penelitian, usahakan ada sumber data primer seperti observasi, wawancara, atau dokumentasi internal.

## Prioritas Revisi
### Prioritas tinggi
- Pertajam latar belakang dengan data masalah yang lebih konkret.
- Pecah rumusan masalah dan tujuan menjadi lebih operasional.
- Bedakan dengan jelas manfaat penelitian dan kontribusi penelitian.
- Perkuat alasan pemilihan metode Waterfall.

### Prioritas menengah
- Rapikan konsistensi istilah.
- Sederhanakan kalimat yang terlalu panjang.
- Perjelas batasan pengujian dan keamanan.

### Prioritas rendah
- Rapikan gaya bahasa akademik.
- Cek konsistensi format italic, sitasi, dan penomoran.

## Rekomendasi Penilaian Sementara
**Status draft:** Layak dilanjutkan dengan revisi.

**Alasan:**
Topik penelitian sudah relevan dan struktur BAB I sudah terbentuk dengan baik. Akan tetapi, agar naskah lebih meyakinkan secara akademik, penulis perlu memperkuat dasar masalah, memperjelas fokus penelitian, dan menata ulang bagian kontribusi agar tidak tumpang tindih dengan manfaat.
