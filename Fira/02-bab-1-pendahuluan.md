# BAB I — PENDAHULUAN

---

## 1.1 Latar Belakang

Pertumbuhan populasi dan urbanisasi di Indonesia telah meningkatkan kepadatan kendaraan, terutama di kota-kota besar. Data Badan Pusat Statistik (BPS) melalui Korlantas Polri menunjukkan bahwa total jumlah kendaraan bermotor di Indonesia pada tahun 2023 mencapai 157.080.504 unit, dengan sepeda motor sebagai jenis kendaraan terbanyak sebanyak 132.433.679 unit (Korlantas Polri, 2025). Data dari Kementerian Perhubungan melalui portal HUBNET juga memuat perkembangan jumlah kendaraan bermotor menurut jenis secara periodik, yang menjadi dasar penting bagi perencanaan transportasi nasional (Kementerian Perhubungan, 2025).

Kota Samarinda sebagai ibu kota Provinsi Kalimantan Timur turut mengalami peningkatan volume kendaraan seiring pertumbuhan ekonomi dan aktivitas perkotaan. Simpang flyover Air Hitam merupakan salah satu titik krusial di jaringan jalan kota ini, menghubungkan beberapa ruas jalan utama seperti Letnan Jend. Suprapto dan Kadrie Oening. Pada jam sibuk, terutama sore hari, area ini kerap mengalami penumpukan kendaraan di dekat lampu lalu lintas. Kondisi tersebut menuntut pengelolaan lalu lintas yang lebih efisien, salah satunya melalui pemahaman terhadap komposisi jenis kendaraan yang melintas.

Peningkatan jumlah kendaraan bermotor berujung pada kemacetan, terutama di kota-kota besar. Salah satu upaya mengatasi kemacetan adalah menghitung volume lalu lintas kendaraan pada ruas jalan tertentu. Data arus lalu lintas yang tersegmentasi menurut jenis kendaraan — mobil, sepeda motor, bus, dan truk — sangat penting bagi perencanaan infrastruktur, penjadwalan lampu lalu lintas adaptif, dan evaluasi kebijakan transportasi. Saat ini, penghitungan tersebut masih banyak dilakukan secara manual menggunakan *manual counter* dan lembar formulir survei (Anggraini et al., 2019). Metode manual ini memakan waktu lama, rentan terhadap kesalahan manusia, membutuhkan tenaga survei di lapangan, dan sulit dilakukan secara kontinyu maupun pada kondisi malam hari.

Perkembangan teknologi *computer vision* dan *deep learning* membuka peluang otomatisasi proses pemantauan lalu lintas. Sistem berbasis kamera — baik kamera pengawas (CCTV) maupun kamera *smartphone* — dapat memproses rekaman video untuk mengenali objek kendaraan tanpa intervensi manusia secara langsung. Deteksi objek *real-time* merupakan topik penelitian penting dalam *computer vision* yang terus berkembang seiring kemajuan arsitektur jaringan saraf dan teknik optimasi pelatihan (Kurniawan & Sulistiyo, 2023). Berbagai pendekatan deteksi objek — mulai dari *anchor-based*, *keypoint-based*, hingga *transformer-based* — masing-masing memiliki kelebihan dan keterbatasan dalam hal akurasi, kecepatan, dan efisiensi sumber daya (Kamath & Renuka, 2023). Evaluasi terhadap berbagai jaringan deteksi *real-time* menunjukkan bahwa keluarga model YOLO (*You Only Look Once*) terus menunjukkan performa unggul dalam kompromi antara akurasi dan kecepatan inferensi (Yasmine et al., 2023).

*Computer vision* adalah bidang ilmu yang mengembangkan cara agar komputer dapat melihat dan memahami konten gambar digital, termasuk foto dan video (Szeliski, 2022). Dalam konteks transportasi, *computer vision* memungkinkan sistem otomatis untuk mengenali dan mengklasifikasi objek kendaraan dari rekaman kamera tanpa intervensi manusia. Perlu dipahami bahwa dalam penelitian ini, istilah **"klasifikasi jenis kendaraan"** merujuk pada proses pengenalan kategori kendaraan (*car*, *motorcycle*, *bus*, *truck*) yang dilakukan secara bersamaan dengan **deteksi objek** oleh model YOLOv7. YOLOv7 merupakan model *object detection* yang secara simultan memprediksi lokasi objek (*bounding box*) dan kelas objek dalam satu kali inferensi — sehingga deteksi dan klasifikasi terjadi dalam satu pipeline, bukan sebagai dua sistem terpisah.

Penelitian pemantauan lalu lintas telah banyak dilakukan dengan berbagai pendekatan. Zhang et al. (2018) menggunakan *improved histogram of gradient* dan *Kalman filter* untuk deteksi kendaraan *real-time*. Penelitian berbasis *deep learning* juga berkembang pesat, seperti penggunaan HVD-Net berbasis CNN untuk deteksi dan pelacakan kendaraan (Ashraf et al., 2023), YOLOv3-tiny yang dioptimalkan untuk deteksi kendaraan ringan (Ge et al., 2022), serta YOLOv3 untuk klasifikasi dan penghitungan kendaraan pada video CCTV (Bose et al., 2022). Di tingkat lokal, penelitian terkait penghitungan kendaraan manual di Kota Pekanbaru (Anggraini et al., 2019) menunjukkan bahwa kebutuhan akan metode otomatis masih sangat relevan di konteks Indonesia.

You Only Look Once (YOLO) merupakan metode deteksi objek *real-time* yang memproses seluruh gambar dalam satu kali inferensi, sehingga lebih cepat dibandingkan metode dua tahap seperti R-CNN (Redmon et al., 2015). Seiring perkembangannya, YOLO telah mengalami berbagai iterasi — dari YOLOv2, YOLOv3, hingga YOLOv7 yang dirilis pada tahun 2022. YOLOv7 mengusulkan arsitektur *trainable bag-of-freebies* yang meningkatkan akurasi deteksi tanpa menambah biaya inferensi secara signifikan (Wang et al., 2022). Model pre-trained pada dataset MS COCO (*Microsoft Common Objects in Context*) dapat langsung digunakan untuk inferensi pada domain baru tanpa pelatihan ulang — pendekatan yang dikenal sebagai **inferensi model pre-trained** — sehingga cocok untuk penelitian aplikatif dengan keterbatasan waktu dan dataset anotasi.

Berdasarkan uraian di atas, penelitian ini mengangkat judul **"Klasifikasi Jenis Kendaraan Menggunakan YOLOv7"** dengan menerapkan model pre-trained YOLOv7 pada rekaman video lalu lintas di simpang flyover Air Hitam, Samarinda. Penelitian ini diharapkan dapat memberikan alternatif solusi otomatis untuk mendeteksi dan mengklasifikasi jenis kendaraan bermotor dari rekaman video, yang sebelumnya dilakukan secara manual — sebagai langkah awal menuju sistem pemantauan lalu lintas berbasis kamera yang lebih efisien.

---

## 1.2 Rumusan Masalah

Berdasarkan latar belakang di atas, rumusan masalah penelitian ini adalah:

> **Bagaimana penerapan algoritma You Only Look Once versi 7 (YOLOv7) dengan model pre-trained MS COCO dapat digunakan untuk mendeteksi dan mengklasifikasi jenis kendaraan bermotor (mobil, motor, bus, dan truk) pada rekaman video lalu lintas di simpang flyover Air Hitam, Samarinda?**

Rumusan masalah di atas mencakup beberapa aspek teknis yang akan dijawab melalui implementasi dan evaluasi:

1. Bagaimana konfigurasi model pre-trained YOLOv7 (`yolov7.pt`) agar hanya mendeteksi empat kelas kendaraan MS COCO?
2. Bagaimana performa deteksi dan klasifikasi pada dua kondisi pencahayaan berbeda (sore dan malam hari)?
3. Apakah sistem yang dibangun memenuhi spesifikasi fungsional berdasarkan pengujian *Black Box Testing*?

---

## 1.3 Batasan Masalah

Agar penelitian terfokus dan dapat diselesaikan sesuai waktu yang tersedia, ruang lingkup penelitian dibatasi pada hal-hal berikut:

1. Objek yang dideteksi dan diklasifikasi terbatas pada empat jenis kendaraan bermotor: mobil (*car*, class ID 2), sepeda motor (*motorcycle*, class ID 3), bus (class ID 5), dan truk (*truck*, class ID 7) sesuai taksonomi MS COCO.
2. Data berupa rekaman video lalu lintas yang diambil di simpang flyover Air Hitam, Samarinda, menggunakan kamera *smartphone* dengan resolusi 1920 × 1080 dan 30 fps.
3. Pengambilan data dilakukan pada dua skenario waktu: sore hari (±16.00–18.00 WITA, ruas Letnan Jend. Suprapto) dan malam hari (±19.00–21.00 WITA, ruas Kadrie Oening).
4. Implementasi sistem menggunakan bahasa pemrograman Python dengan pustaka OpenCV dan PyTorch, dijalankan pada Google Colab dengan GPU T4.
5. Model yang digunakan adalah YOLOv7 (`yolov7.pt`) pre-trained pada dataset MS COCO **tanpa pelatihan ulang** (*fine-tuning*) dan tanpa anotasi dataset kustom.
6. *Script* yang digunakan adalah `detect_and_track.py`, hasil modifikasi dari `detect_count_and_track.py` pada repository YOLOv7 (Krisna Rengga), dengan fokus pada deteksi, klasifikasi, dan visualisasi — **bukan** perhitungan volume lalu lintas.
7. Pengujian sistem dilakukan menggunakan metode *Black Box Testing* dengan teknik *Equivalence Partitioning* (EP) dan *Boundary Value Analysis* (BVA).
8. Evaluasi hasil dilakukan secara kualitatif (visual) dan fungsional; evaluasi kuantitatif (mAP, precision, recall) dilakukan jika tersedia anotasi *ground truth* manual.

---

## 1.4 Tujuan Penelitian

Tujuan penelitian ini adalah:

1. Menerapkan algoritma YOLOv7 dengan model pre-trained MS COCO untuk mendeteksi dan mengklasifikasi empat jenis kendaraan bermotor pada rekaman video lalu lintas di flyover Air Hitam, Samarinda.
2. Menguji kemampuan model dalam kondisi pencahayaan berbeda (sore hari dan malam hari) pada sudut pandang *high angle* dari flyover.
3. Mengevaluasi fungsionalitas sistem menggunakan metode *Black Box Testing* untuk memastikan seluruh komponen berjalan sesuai spesifikasi.

---

## 1.5 Manfaat Penelitian

Penelitian ini diharapkan memberikan manfaat sebagai berikut:

**1. Bagi Penulis**

- Mengembangkan kemampuan dalam menerapkan algoritma deteksi objek berbasis *deep learning* pada kasus nyata pemantauan lalu lintas.
- Memperdalam pemahaman tentang *computer vision*, arsitektur YOLOv7, pengolahan data video, dan metodologi pengujian perangkat lunak (*Black Box Testing*).
- Memperoleh pengalaman praktis dalam memodifikasi *script* inferensi, mengonfigurasi parameter model, dan mendokumentasikan hasil penelitian ilmiah.

**2. Bagi Mahasiswa**

- Menjadi referensi bagi mahasiswa Program Studi Informatika yang tertarik pada bidang *computer vision* dan deteksi objek.
- Memberikan contoh penerapan model pre-trained YOLO pada data lokal Indonesia tanpa memerlukan infrastruktur pelatihan model yang mahal.
- Menunjukkan alur penelitian aplikatif dari pengumpulan data lapangan hingga evaluasi hasil.

**3. Bagi Instansi/Lembaga**

- Diharapkan dapat menjadi rujukan bagi Dinas Perhubungan Kota Samarinda dalam mengembangkan sistem pemantauan lalu lintas berbasis kamera secara otomatis.
- Menjadi dasar pengembangan lebih lanjut, seperti perhitungan volume kendaraan otomatis berdasarkan hasil deteksi dan pelacakan (*tracking*).
- Mendukung perencanaan transportasi berbasis data (*data-driven*) di tingkat kota.

---

## 1.6 Kontribusi Penelitian

Kontribusi penelitian ini meliputi:

1. **Penerapan YOLOv7 pada data lokal** — Dokumentasi penerapan model YOLOv7 pre-trained MS COCO pada rekaman lalu lintas lokal (flyover Air Hitam, Samarinda) yang belum banyak dibahas dalam literatur penelitian Indonesia.
2. **Evaluasi multi-kondisi pencahayaan** — Analisis performa deteksi dan klasifikasi kendaraan pada dua kondisi pencahayaan berbeda (sore dan malam) dengan sudut pandang *high angle*, memberikan wawasan tentang ketahanan model pre-trained pada kondisi lapangan nyata.
3. **Dokumentasi implementasi yang dapat direplikasi** — Penyediaan dokumentasi lengkap mengenai modifikasi *script*, konfigurasi parameter inferensi, skenario pengujian *Black Box Testing*, dan prosedur evaluasi yang dapat dijadikan acuan penelitian serupa.

> **Catatan tentang kebaruan (*novelty*):** Penelitian ini merupakan *application study* — penerapan model yang sudah ada pada domain dan lokasi spesifik — bukan pengembangan arsitektur model baru. Kebaruan terletak pada konteks aplikasi (lalu lintas Samarinda, sudut flyover, dua skenario pencahayaan) dan dokumentasi implementasi, bukan pada algoritma deteksi itu sendiri.

---
