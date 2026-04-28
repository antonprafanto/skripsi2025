# Laporan Audit Draft Skripsi

## Identitas audit
- Dokumen yang diaudit: potongan draft skripsi Bab III dan bagian perancangan/pengujian.
- Sumber audit: 15 gambar halaman yang diunggah pengguna.
- Fokus audit: konsistensi metodologi, kualitas akademik, kejelasan penjelasan, kualitas tabel/gambar, dan kesiapan menuju seminar/ujian.

## Ringkasan hasil audit
Secara umum, draft sudah memiliki struktur Bab III yang cukup runtut: tahapan penelitian, pengumpulan data, perancangan data, perancangan proses, perancangan tampilan, dan perancangan pengujian. Topik juga sudah relatif konsisten, yaitu pengembangan sistem chatbot AI untuk platform Resmeku.

Namun, masih terdapat beberapa catatan penting yang perlu direvisi agar naskah lebih kuat secara ilmiah dan lebih rapi secara penulisan. Isu utama yang terlihat adalah: ketidakkonsistenan istilah, uraian metodologi yang masih terlalu deskriptif, hubungan antara kebutuhan sistem–desain–pengujian yang belum sepenuhnya ditautkan secara eksplisit, dan beberapa bagian visual/tabel yang masih tampak seperti placeholder atau belum cukup informatif.

## Temuan utama

### 1. Kekuatan naskah
- Struktur subbab sudah berurutan dan mudah diikuti.
- Sudah ada pemisahan antara kebutuhan fungsional dan non-fungsional.
- Sudah menyertakan artefak desain seperti flowchart, use case diagram, sequence diagram, rancangan UI, risk assessment, serta rancangan pengujian.
- Pengujian dibedakan menjadi blackbox testing dan uji kesesuaian respons, ini sudah tepat untuk topik chatbot.
- Sudah ada penggunaan skala Likert dan interpretasi persentase pada evaluasi.

### 2. Temuan substansi metodologi
#### 2.1 Tahapan penelitian masih dominan naratif
Bagian 3.1 menjelaskan tahapan pelaksanaan penelitian, tetapi alasan pemilihan tahapan dan hubungan antar tahap masih belum cukup kuat. Misalnya, belum dijelaskan mengapa pendekatan waterfall dipilih dibanding alternatif lain, padahal sistem chatbot sering membutuhkan iterasi pada knowledge base dan evaluasi respons.

**Saran revisi:**
- Tambahkan alasan akademik pemilihan metode waterfall, misalnya karena ruang lingkup kebutuhan relatif terdefinisi, waktu penelitian terbatas, dan fokus penelitian adalah implementasi terstruktur.
- Tambahkan satu paragraf yang menjelaskan hubungan antartahap: analisis kebutuhan → penyusunan knowledge base → desain sistem → implementasi → pengujian → evaluasi.

#### 2.2 Pengumpulan data belum cukup operasional
Pada bagian 3.2, metode pengumpulan data hanya ditulis sebagai studi pustaka dan observasi. Ini masih terlalu umum dan belum menunjukkan bagaimana data benar-benar dikumpulkan lalu diubah menjadi knowledge base chatbot.

**Saran revisi:**
- Jelaskan objek observasi secara rinci: halaman apa yang diamati, jenis informasi apa yang diambil, dan bagaimana data divalidasi.
- Tambahkan output dari studi pustaka dan observasi, misalnya: daftar kategori informasi, alur layanan, FAQ, dan kebutuhan pengguna.
- Jika ada wawancara/admin validation, pertimbangkan ditambahkan agar sumber knowledge base lebih kuat.

#### 2.3 Perancangan data masih terlalu singkat
Bagian 3.3 hanya memuat kategori knowledge base. Secara konsep ini bagus, tetapi belum cukup menunjukkan bentuk rancangan data yang siap diimplementasikan.

**Saran revisi:**
- Tambahkan struktur data knowledge base, misalnya field dokumen: judul, kategori, isi, kata kunci, sumber, tanggal pembaruan.
- Jelaskan bagaimana kategori “Profil”, “Layanan”, “Prosedur”, “FAQ”, dan “Informasi pendukung” dipakai oleh sistem saat merespons pertanyaan.
- Jika sistem menggunakan pencarian dokumen atau retrieval, jelaskan alurnya secara singkat.

#### 2.4 Kebutuhan fungsional belum diturunkan menjadi modul sistem
Pada 3.4.1 kebutuhan fungsional sudah ada, tetapi transisinya ke desain sistem belum terlalu kuat. Pembaca belum benar-benar dibantu untuk melihat bahwa setiap kebutuhan sudah dipetakan ke diagram, halaman, dan pengujian.

**Saran revisi:**
- Buat tabel keterlacakan (traceability matrix) sederhana: kebutuhan → desain/modul → skenario uji.
- Contoh: “Pengguna mengajukan pertanyaan melalui widget” → use case/sequence diagram → uji blackbox proses percakapan.

### 3. Temuan desain sistem
#### 3.1 Flowchart, use case, dan sequence diagram sudah ada tetapi perlu dipertajam
Diagram yang ditampilkan sudah membantu, namun penjelasannya masih cenderung mengulang isi gambar secara naratif. Nilai ilmiahnya akan lebih kuat jika dijelaskan fungsi tiap komponen dan batasan sistem.

**Saran revisi:**
- Pada use case diagram, jelaskan sistem boundary dan alasan hanya ada satu aktor utama.
- Pada sequence diagram, pertegas urutan proses: input → validasi → pencarian knowledge base → request API AI → penyimpanan riwayat → output.
- Pada flowchart, pastikan simbol keputusan dan alur “pertanyaan baru” benar-benar konsisten dengan narasi.

#### 3.2 Bagian pengkodean masih deskriptif umum
Pada 3.4.3 sudah menyebut Next.js, MongoDB, Mongoose, Tailwind CSS, shadcn/ui, REST API, dan API AI. Namun belum dijelaskan peran tiap teknologi dalam arsitektur.

**Saran revisi:**
- Tambahkan tabel kecil “Teknologi dan Fungsinya”.
- Contoh: Next.js untuk frontend/backend route, MongoDB untuk penyimpanan data chatbot dan riwayat, Mongoose untuk ODM, Tailwind untuk styling, API AI untuk generasi respons.
- Jelaskan juga alasan pemilihan stack secara singkat.

#### 3.3 Risk assessment masih minim
Tabel risk assessment sudah bagus sebagai nilai tambah, tetapi jumlah risikonya masih sedikit untuk sistem chatbot berbasis AI.

**Saran revisi:**
Tambahkan risiko seperti:
- Halusinasi jawaban AI.
- Ketidaksesuaian isi knowledge base.
- Kebocoran data percakapan.
- Kegagalan koneksi internet/server.
- Query ambigu dari pengguna.

Lalu sertakan mitigasi yang lebih operasional, misalnya validation layer, logging, pembatasan akses, backup, dan monitoring.

### 4. Temuan rancangan tampilan
#### 4.1 Deskripsi UI cukup runtut tetapi visual masih berupa wireframe kasar
Bagian 3.5 menjelaskan halaman utama, pendaftaran, autentikasi, manajemen organisasi, manajemen chatbot, dan detail chatbot. Namun gambar yang ditampilkan tampak masih berupa wireframe/placeholder sederhana.

**Saran revisi:**
- Jika ini memang tahap rancangan, nyatakan secara eksplisit bahwa gambar merupakan wireframe low-fidelity.
- Jika sistem sudah diimplementasikan, sebaiknya ganti dengan screenshot antarmuka nyata agar lebih meyakinkan.
- Tambahkan penjelasan elemen utama tiap halaman: tujuan halaman, input utama, aksi pengguna, dan output sistem.

#### 4.2 Konsistensi istilah antarmuka perlu diperbaiki
Ada penggunaan istilah seperti “Daftar”, “Masuk”, “My Organizations”, “My Chatbots”, “Detail Chatbot”. Sebagian berbahasa Indonesia, sebagian berbahasa Inggris.

**Saran revisi:**
- Konsistenkan satu bahasa pada seluruh naskah dan mockup.
- Jika aplikasi memakai bahasa Inggris, jelaskan bahwa antarmuka sistem dirancang dalam bahasa Inggris. Jika skripsi berbahasa Indonesia, lebih baik istilah UI diterjemahkan atau diberi keterangan.

### 5. Temuan pengujian
#### 5.1 Blackbox testing sudah tepat, tetapi perlu hasil realisasi
Tabel 3.3 memuat rancangan pengujian blackbox yang baik. Namun dari halaman yang tersedia, yang tampak baru rancangan, belum hasil pengujian aktual.

**Saran revisi:**
- Tambahkan tabel hasil pengujian aktual: skenario, input, output yang diharapkan, output aktual, status valid/tidak valid.
- Pisahkan secara tegas antara “rancangan pengujian” dan “hasil pengujian”.

#### 5.2 Uji kesesuaian respons masih perlu definisi operasional yang lebih kuat
Tabel 3.4 sudah berisi kasus uji yang relevan untuk chatbot. Namun kriteria “sesuai” masih belum dijabarkan secara rinci, sehingga evaluasi berpotensi subjektif.

**Saran revisi:**
- Definisikan indikator penilaian, misalnya: relevansi jawaban, kelengkapan informasi, konsistensi konteks, kejelasan bahasa, dan ketepatan solusi.
- Jelaskan siapa respondennya, berapa jumlahnya, dan bagaimana proses pengisian kuesioner dilakukan.
- Jelaskan apakah satu skenario menghasilkan satu penilaian atau beberapa item penilaian.

#### 5.3 Rumus evaluasi perlu diperjelas konteksnya
Bagian skala Likert sudah benar secara umum, tetapi perlu penjelasan tentang unit analisis dan interpretasi hasil.

**Saran revisi:**
- Jelaskan arti variabel f dan N dengan contoh singkat perhitungan.
- Tambahkan alasan penggunaan interval interpretasi 0–20, 21–40, dst., apakah mengacu pada referensi tertentu atau ditetapkan peneliti.
- Jika ada referensi metodologis, cantumkan sitasinya pada naskah asli.

## Temuan kebahasaan dan akademik

### 1. Konsistensi istilah
Beberapa istilah campuran muncul dalam bahasa Indonesia dan Inggris, misalnya *knowledge base*, *widget chatbot*, *Blackbox Testing*, *risk assessment*, *preview*, *real-time*, *dashboard*, *role-based access control*. Ini boleh saja, tetapi harus konsisten dan mengikuti gaya selingkung kampus.

**Saran revisi:**
- Miringkan istilah asing secara konsisten.
- Gunakan satu bentuk penulisan yang tetap, misalnya pilih “black-box testing” atau “Blackbox Testing”, jangan berganti-ganti.
- Pertimbangkan glosarium istilah jika dosen pembimbing meminta.

### 2. Gaya ilmiah masih bisa dipadatkan
Beberapa paragraf masih mengulang informasi yang sebenarnya sudah tampak pada gambar atau tabel.

**Saran revisi:**
- Kurangi kalimat yang hanya mendeskripsikan ulang gambar.
- Ganti dengan penjelasan analitis: fungsi, alasan desain, dan kontribusi terhadap sistem.

### 3. Potensi kekurangan sitasi
Dari halaman gambar yang terlihat, beberapa bagian metodologis tampak belum menunjukkan sumber rujukan langsung, misalnya pemilihan waterfall, UML, blackbox testing, dan skala Likert.

**Saran revisi:**
- Pastikan setiap konsep metodologis utama memiliki sitasi.
- Minimal tambahkan referensi pada: model waterfall, UML/use case/sequence diagram, blackbox testing, dan skala Likert.

## Daftar revisi prioritas

### Prioritas tinggi
1. Perkuat alasan pemilihan metode waterfall.
2. Operasionalkan proses pengumpulan data dan penyusunan knowledge base.
3. Tambahkan keterlacakan antara kebutuhan, desain, dan pengujian.
4. Perjelas indikator uji kesesuaian respons dan karakteristik responden.
5. Bedakan rancangan pengujian dan hasil pengujian aktual.

### Prioritas menengah
1. Tambahkan struktur data knowledge base.
2. Tambahkan tabel teknologi dan fungsinya.
3. Perluas risk assessment.
4. Konsistenkan istilah bahasa Indonesia/Inggris.

### Prioritas rendah
1. Rapikan narasi yang terlalu deskriptif.
2. Ganti wireframe dengan screenshot implementasi jika tersedia.
3. Tambahkan contoh perhitungan Likert.

## Contoh revisi kalimat

### Contoh 1
Kalimat saat ini:
> Pengumpulan data dilakukan melalui studi pustaka dan observasi.

Usulan revisi:
> Pengumpulan data dilakukan melalui studi pustaka untuk memperoleh landasan teoritis mengenai chatbot, knowledge base, dan metode pengembangan sistem, serta observasi terhadap platform Resmeku untuk mengidentifikasi alur layanan, informasi yang tersedia, dan kebutuhan konten yang akan disusun ke dalam knowledge base chatbot.

### Contoh 2
Kalimat saat ini:
> Perancangan proses bertujuan untuk menentukan alur dan tahapan yang diperlukan.

Usulan revisi:
> Perancangan proses bertujuan untuk memetakan alur kerja sistem chatbot mulai dari input pertanyaan oleh pengguna, pencarian informasi pada knowledge base, pengiriman permintaan ke layanan AI, hingga penyajian respons kembali kepada pengguna secara terstruktur.

### Contoh 3
Kalimat saat ini:
> Uji kesesuaian respons chatbot dilakukan untuk menilai kemampuan sistem.

Usulan revisi:
> Uji kesesuaian respons chatbot dilakukan untuk menilai tingkat relevansi, kelengkapan, dan konsistensi jawaban sistem terhadap konteks pertanyaan pengguna berdasarkan skenario uji yang merepresentasikan kebutuhan layanan pelanggan pada platform Resmeku.

## Rekomendasi akhir
Draft ini sudah berada pada arah yang benar dan cukup layak untuk dilanjutkan, tetapi belum optimal jika langsung dianggap final. Revisi paling penting adalah memperkuat logika metodologi, menambah detail operasional pada data/knowledge base, serta memperjelas instrumen dan hasil pengujian agar kontribusi ilmiahnya terlihat lebih kuat.
