# BAB II — TINJAUAN PUSTAKA

---

## 2.1 Penelitian Terkait

Dalam rangka mendukung penelitian ini, dilakukan kajian terhadap penelitian-penelitian terkait yang telah dilakukan sebelumnya di bidang deteksi, klasifikasi, dan pemantauan kendaraan. Ringkasan penelitian terkait disajikan pada Tabel 2.1.

**Tabel 2.1 Penelitian Terkait Deteksi dan Klasifikasi Kendaraan**

| No | Peneliti (Tahun) | Metode | Dataset/Lokasi | Hasil Utama |
|----|------------------|--------|----------------|-------------|
| 1 | Tahir et al. (2023) | CCTV Video Analytics, Event-Driven Framework | CCTV jalan raya | Sistem pemantauan lalu lintas *real-time* dengan akurasi kompetitif |
| 2 | Ashraf et al. (2023) | HVD-Net (CNN) + SORT | PASCAL VOC, UA-DETRAC (3 kota di China) | mAP 91,04% (statis), 80,71% (dinamis) |
| 3 | Ge et al. (2022) | YOLOv3-tiny + ResNet-18 | KITTI (Car, Van, Truck) | mAP meningkat dari 79,57% menjadi 93,66% |
| 4 | Wang et al. (2022) | YOLOv7 (E-ELAN, trainable bag-of-freebies) | MS COCO | State-of-the-art *real-time* detector, ≥30 FPS pada GPU |
| 5 | Jawale et al. (2023) | CNN (ALPDR) | Plat nomor kendaraan India | Akurasi 98,5% pada pengenalan karakter |
| 6 | Jiménez et al. (2023) | YOLO + LiDAR | Gerbang tol *free-flow* | Point cloud berlabel jenis kendaraan |
| 7 | Aljebreen et al. (2023) | HBOAEL-VDC (ensemble DL) | VEDAI, ISPRS Potsdam | Akurasi 99,05% dan 98,92% |
| 8 | Lin et al. (2021) | YOLOv4 + Virtual Detection Zone + GMM | MAVD, GRAM-RTM | Akurasi klasifikasi 98,91%–99,5% |
| 9 | Bose et al. (2022) | YOLOv3 | Video CCTV lalu lintas | Deteksi dan penghitungan mobil, motor, bus, truk |
| 10 | Rani et al. (2024) | LV-YOLO | Video lalu lintas | Deteksi, klasifikasi, dan penghitungan kendaraan *real-time* |
| 11 | Anggraini et al. (2019) | Manual Traffic Counting | Kota Pekanbaru, Indonesia | Metode manual masih dominan; perlu otomatisasi |
| 12 | Kurniawan & Sulistiyo (2023) | YOLOv7 (tinjauan literatur) | Berbagai benchmark | YOLOv7 unggul dalam kompromi akurasi-kecepatan |

### Analisis Penelitian Terkait

**Penelitian internasional (No. 1–3, 5–10):** Mayoritas penelitian menggunakan arsitektur CNN khusus atau varian YOLO (v3, v4) dengan dataset internasional seperti KITTI, PASCAL VOC, UA-DETRAC, dan MAVD. Ashraf et al. (2023) mengintegrasikan deteksi HVD-Net dengan pelacakan SORT (*Simple Online and Realtime Tracking*) untuk estimasi kecepatan kendaraan, mencapai mAP 91,04% pada data statis. Ge et al. (2022) menunjukkan bahwa penggantian ekstraktor fitur pada YOLOv3-tiny dengan ResNet-18 dapat meningkatkan mAP dari 79,57% menjadi 93,66%. Lin et al. (2021) menggabungkan YOLOv4 dengan *Virtual Detection Zone* untuk penghitungan kendaraan, mencapai akurasi klasifikasi hingga 99,5% pada dataset GRAM-RTM, termasuk evaluasi pada kondisi siang (99,1%), malam (98,6%), dan hujan (98%).

**Penelitian YOLOv7 (No. 4, 12):** Wang et al. (2022) memperkenalkan YOLOv7 dengan arsitektur E-ELAN (*Extended Efficient Layer Aggregation Network*) dan teknik *trainable bag-of-freebies* yang meningkatkan akurasi tanpa menambah biaya inferensi. Kurniawan & Sulistiyo (2023) dalam tinjauan literatur menyimpulkan bahwa YOLOv7 merupakan salah satu detektor *real-time* terbaik saat dirilis. Penelitian Thakuria & Erkinbaev (2023) juga menggunakan YOLOv7 namun pada domain pertanian (grading biji kanola) — konteks yang berbeda dari transportasi, sehingga tidak dimasukkan ke tabel utama tetapi menunjukkan fleksibilitas arsitektur YOLOv7 lintas domain.

**Penelitian lokal Indonesia (No. 11):** Anggraini et al. (2019) mendokumentasikan bahwa penghitungan kendaraan di Kota Pekanbaru masih dilakukan secara manual di wilayah pengembangan II dan III. Temuan ini relevan dengan konteks penelitian ini di Samarinda, di mana otomatisasi berbasis *computer vision* dapat menjadi alternatif yang lebih efisien.

### Perbedaan dengan Penelitian Sebelumnya

Berdasarkan Tabel 2.1, perbedaan dan kontribusi penelitian ini terletak pada:

| Aspek | Penelitian Sebelumnya | Penelitian Ini |
|-------|----------------------|----------------|
| Versi YOLO | Umumnya YOLOv3/v4 | **YOLOv7** (versi terbaru saat penelitian) |
| Dataset/Lokasi | Dataset internasional (KITTI, UA-DETRAC, dll.) | **Data lokal** — flyover Air Hitam, Samarinda |
| Pendekatan | Banyak melakukan *training*/*fine-tuning* | **Inferensi model pre-trained** MS COCO tanpa *fine-tuning* |
| Kondisi pencahayaan | Sering satu kondisi atau dataset terkontrol | **Dua skenario**: sore dan malam hari |
| Sudut kamera | Variatif (CCTV horizontal, LiDAR, dll.) | ***High angle*** dari flyover — meminimalkan oklusi |
| Evaluasi | Umumnya kuantitatif (mAP, akurasi) | Kualitatif + fungsional (*Black Box Testing*) + kerangka kuantitatif |

---

## 2.2 Kecerdasan Buatan

Kecerdasan buatan (*Artificial Intelligence*/AI) adalah cabang ilmu komputer yang mengembangkan sistem yang mampu meniru kemampuan kognitif manusia, seperti belajar, bernalar, memecahkan masalah, dan mengambil keputusan (Hartati, 2021). AI mencakup berbagai sub-bidang, antara lain:

- ***Machine learning*** — sistem yang belajar dari data.
- ***Computer vision*** — sistem yang memahami informasi visual.
- **Robotika** — sistem yang berinteraksi dengan lingkungan fisik.
- **Sistem pakar** — sistem berbasis aturan dan pengetahuan domain.

Dalam beberapa dekade terakhir, kemajuan AI didorong oleh ketersediaan data dalam skala besar, peningkatan kapasitas komputasi (terutama GPU), dan perkembangan arsitektur *deep learning*. Bidang AI telah diterapkan secara luas, mulai dari asisten virtual, diagnosis medis, hingga kendaraan otonom dan pemantauan lalu lintas cerdas (Gong et al., 2023).

Dalam penelitian ini, kecerdasan buatan diterapkan melalui *deep learning* untuk mendeteksi dan mengklasifikasi objek kendaraan dari data video secara otomatis. Pipeline AI pada penelitian ini meliputi: (1) input rekaman video, (2) ekstraksi frame, (3) inferensi model YOLOv7, (4) visualisasi hasil deteksi, dan (5) evaluasi output.

---

## 2.3 Machine Learning

*Machine learning* (ML) adalah cabang kecerdasan buatan yang memungkinkan komputer belajar dari data tanpa diprogram secara eksplisit untuk setiap aturan (Mueller & Massaron, 2021). Algoritma ML menganalisis pola dalam data untuk membuat prediksi atau keputusan. ML merupakan **sub-bidang dari AI** — setiap sistem ML adalah bagian dari AI, meskipun tidak semua AI menggunakan ML (misalnya sistem pakar berbasis aturan).

ML dikategorikan menjadi tiga jenis pembelajaran:

**1. Supervised Learning (Pembelajaran Terawasi)**

Model belajar dari pasangan data input-output yang sudah berlabel. Contoh: klasifikasi gambar (input: foto kendaraan, output: label "mobil" atau "motor"), regresi (prediksi kecepatan kendaraan). Dalam penelitian ini, model YOLOv7 menggunakan pendekatan *supervised learning* karena telah dilatih menggunakan dataset MS COCO yang memiliki anotasi *bounding box* dan label kelas.

**2. Unsupervised Learning (Pembelajaran Tidak Terawasi)**

Model menemukan pola tersembunyi dalam data tanpa label. Contoh: *clustering* kendaraan berdasarkan pola pergerakan, reduksi dimensi fitur.

**3. Reinforcement Learning (Pembelajaran Penguatan)**

Model belajar melalui interaksi dengan lingkungan dan sinyal *reward*/*penalty*. Contoh: navigasi kendaraan otonom, optimasi lampu lalu lintas adaptif.

Pemilihan jenis pembelajaran bergantung pada ketersediaan data berlabel dan tujuan aplikasi. Untuk deteksi objek dengan model pre-trained, pendekatan *supervised learning* dengan transfer learning dari model yang sudah dilatih merupakan strategi yang efisien.

---

## 2.4 Deep Learning

*Deep learning* adalah sub-kategori *machine learning* yang menggunakan jaringan saraf tiruan (*Artificial Neural Network*/ANN) dengan banyak lapisan (*layer*) tersembunyi (Sree et al., 2023). Istilah "deep" merujuk pada kedalaman jaringan — jumlah lapisan yang cukup banyak untuk mempelajari representasi fitur secara hierarkis.

### Arsitektur Jaringan Saraf Konvolusi (CNN)

Detektor objek modern, termasuk YOLO, dibangun di atas *Convolutional Neural Network* (CNN). CNN terdiri dari beberapa jenis lapisan:

| Lapisan | Fungsi |
|---------|--------|
| *Convolutional layer* | Mengekstrak fitur lokal (tepi, tekstur, bentuk) menggunakan kernel/filter |
| *Pooling layer* | Mengurangi dimensi spasial, meningkatkan invarians terhadap translasi |
| *Activation layer* (ReLU, SiLU) | Menambahkan non-linearitas agar jaringan dapat memodelkan hubungan kompleks |
| *Fully connected layer* | Menggabungkan fitur untuk prediksi akhir (kelas, koordinat) |
| *Batch normalization* | Menstabilkan dan mempercepat proses pelatihan |

Keunggulan *deep learning* dibandingkan ML tradisional:

- Dapat memproses data dalam jumlah besar (gambar, video, audio).
- Ekstraksi fitur dilakukan **otomatis** tanpa *feature engineering* manual.
- Performa meningkat seiring bertambahnya data pelatihan dan kapasitas model.
- *Transfer learning* memungkinkan pemanfaatan model pre-trained pada tugas baru.

YOLOv7 merupakan contoh arsitektur *deep learning* yang digunakan untuk deteksi objek. Model ini dilatih end-to-end pada dataset MS COCO dengan jutaan anotasi objek, sehingga mampu mengenali 80 kelas objek termasuk kendaraan.

---

## 2.5 Python

Python adalah bahasa pemrograman tingkat tinggi yang banyak digunakan dalam pengembangan aplikasi berbasis kecerdasan buatan (Matthes, 2023). Python dipilih karena beberapa alasan:

**Keunggulan Python:**

1. **Sintaks sederhana** — mudah dibaca dan ditulis, cocok untuk prototyping cepat.
2. **Ekosistem pustaka lengkap:**
   - NumPy — komputasi numerik dan operasi matriks.
   - Pandas — pengolahan dan analisis data terstruktur.
   - Matplotlib/Seaborn — visualisasi data.
   - PyTorch/TensorFlow — *framework deep learning*.
   - OpenCV — pengolahan citra dan *computer vision*.
3. **Kompatibilitas lintas platform** — Windows, Linux, macOS.
4. **Dukungan komunitas** — dokumentasi luas, forum aktif, banyak tutorial.

Dalam penelitian ini, Python digunakan sebagai bahasa pemrograman utama untuk:

- Menjalankan inferensi model YOLOv7 melalui PyTorch.
- Membaca dan memproses video menggunakan OpenCV (`cv2.VideoCapture`).
- Menggambar *bounding box* dan label pada frame hasil deteksi.
- Menyimpan video output beranotasi.

Implementasi dilakukan pada Google Colab — platform *cloud* berbasis Jupyter Notebook yang menyediakan akses GPU gratis (T4) — sehingga tidak memerlukan perangkat keras lokal yang mahal (Raschka et al., 2022).

---

## 2.6 OpenCV

OpenCV (*Open Source Computer Vision Library*) adalah pustaka *open-source* untuk pengolahan citra dan *computer vision*, pertama kali dikembangkan oleh Intel pada tahun 1999 (Bradski & Kaehler, 2008). OpenCV menyediakan lebih dari 2.500 algoritma yang dioptimalkan, mencakup deteksi objek, pelacakan gerakan, segmentasi citra, dan kalibrasi kamera.

### Fungsi OpenCV dalam Penelitian Ini

| Fungsi | Kegunaan dalam Pipeline |
|--------|------------------------|
| `cv2.VideoCapture` | Membuka dan membaca frame dari file video input (.mp4) |
| `cv2.resize` | Mengubah ukuran frame ke resolusi inferensi (640 × 640 px) |
| `cv2.cvtColor` | Konversi ruang warna BGR → RGB sebelum inferensi model |
| `cv2.rectangle` | Menggambar *bounding box* di sekitar kendaraan terdeteksi |
| `cv2.putText` | Menampilkan label kelas kendaraan di atas *bounding box* |
| `cv2.VideoWriter` | Menyimpan frame beranotasi ke file video output (.mp4) |
| `cv2.circle` | Menandai titik tengah objek (digunakan dalam modul pelacakan) |

OpenCV berperan sebagai **lapisan pra-pemrosesan dan pasca-pemrosesan** dalam pipeline deteksi. Model YOLOv7 dijalankan melalui PyTorch, sedangkan OpenCV menangani I/O video dan visualisasi hasil. Pemisahan ini memungkinkan fleksibilitas dalam mengganti model deteksi tanpa mengubah pipeline video.

---

## 2.7 Black Box Testing

*Black box testing* adalah metode pengujian perangkat lunak yang dilakukan **tanpa mengetahui struktur internal atau kode sumber** program (Hidayat & Muttaqin, 2020). Pengujian berfokus pada fungsi *input-output* berdasarkan spesifikasi kebutuhan — penguji bertindak seperti pengguna akhir yang hanya melihat perilaku sistem dari luar.

### Mengapa Black Box Testing?

Dalam penelitian ini, *black box testing* dipilih karena:

1. Objek pengujian adalah **fungsionalitas sistem secara keseluruhan** (baca video → deteksi → simpan output), bukan unit kode individual.
2. Penguji (mahasiswa/pembimbing) dapat memverifikasi hasil tanpa harus memahami seluruh kode YOLOv7.
3. Metode ini sesuai dengan standar pengujian perangkat lunak pada skripsi S1 Informatika.

### Teknik Pengujian

**1. Equivalence Partitioning (EP)**

Membagi data input ke dalam kelompok (*partisi*) yang dianggap memiliki karakteristik serupa. Pengujian dilakukan pada satu representasi dari setiap kelompok — jika satu nilai dalam partisi lulus, seluruh partisi dianggap valid.

| Partisi Input | Nilai Valid (Contoh) | Nilai Invalid (Contoh) |
|---------------|---------------------|----------------------|
| Format video | `.mp4` | `.avi`, `.mkv`, file rusak |
| Kelas kendaraan | `--classes 2 3 5 7` | `--classes 0 1 99` |
| Resolusi video | 1920 × 1080 | 0 × 0, file kosong |
| Parameter device | `--device 0` (GPU) | `--device 99` |

**2. Boundary Value Analysis (BVA)**

Pengujian pada nilai batas input, karena kesalahan sering muncul pada kondisi tepi (*edge cases*).

| Parameter | Batas Bawah | Nilai Normal (Penelitian) | Batas Atas |
|-----------|-------------|--------------------------|------------|
| `conf-thres` | 0.0 (semua deteksi) | **0.45** | 1.0 (tidak ada deteksi) |
| `img-size` | 320 px | **640 px** | 1280 px |
| `iou-thres` | 0.0 | **0.45** | 1.0 |

Dalam penelitian ini, *black box testing* digunakan untuk menguji fungsionalitas *script* `detect_and_track.py` — meliputi pembacaan video, pemfilteran kelas, visualisasi, penyimpanan output, dan respons terhadap parameter batas.

---

## 2.8 You Only Look Once (YOLO)

You Only Look Once (YOLO) adalah algoritma deteksi objek *real-time* yang memformulasikan deteksi sebagai **masalah regresi tunggal**. Berbeda dengan metode dua tahap seperti R-CNN yang pertama mendeteksi *region of interest* lalu mengklasifikasi, YOLO memproses seluruh citra dalam **satu kali inferensi** jaringan saraf (Redmon et al., 2015).

### Prinsip Kerja YOLO

1. Citra input dibagi menjadi grid S × S.
2. Setiap sel grid memprediksi B *bounding box* beserta *confidence score*.
3. Setiap *bounding box* memprediksi 5 nilai: (x, y, w, h, confidence) + probabilitas kelas.
4. *Non-Maximum Suppression* (NMS) diterapkan untuk menghilangkan deteksi duplikat.
5. Output akhir: daftar *bounding box* dengan label kelas dan skor kepercayaan.

### Evolusi YOLO

| Versi | Tahun | Kontribusi Utama |
|-------|-------|------------------|
| YOLOv1 | 2015 | Deteksi *real-time* end-to-end, 45 FPS |
| YOLOv2 | 2016 | *Anchor boxes*, batch normalization |
| YOLOv3 | 2018 | Multi-scale prediction (3 skala) |
| YOLOv4 | 2020 | CSPDarknet53 + PANet + mosaic augmentation |
| YOLOv5 | 2020 | Implementasi PyTorch, mudah digunakan |
| YOLOv7 | 2022 | E-ELAN, trainable bag-of-freebies, model scaling |
| YOLOv8+ | 2023+ | Arsitektur anchor-free, peningkatan berkelanjutan |

Tinjauan komprehensif evolusi YOLO disajikan oleh Ali & Zhang (2024) dan Shoman et al. (2025), yang mendokumentasikan peningkatan bertahap dari segi akurasi, kecepatan, dan efisiensi parameter.

### 2.8.1 YOLOv7 — Arsitektur dan Keunggulan

YOLOv7 dikembangkan oleh Wang et al. (2022) dengan fokus pada peningkatan akurasi **tanpa menambah biaya inferensi**. Kontribusi utama YOLOv7:

**1. E-ELAN (Extended Efficient Layer Aggregation Network)**

Arsitektur backbone yang memperluas kapasitas pembelajaran jaringan tanpa merusak jalur gradien asli. E-ELAN menggunakan strategi perluasan grup konvolusi untuk meningkatkan diversitas fitur.

**2. Model Scaling untuk Konjugasi**

Teknik penskalaan model yang mempertimbangkan **depth** (kedalaman), **width** (lebar channel), dan **resolution** (resolusi input) secara bersamaan — bukan hanya satu dimensi seperti pendekatan sebelumnya.

**3. Label Assignment yang Dapat Dilatih (*Trainable Bag-of-Freebies*)**

Pendekatan *coarse-to-fine* untuk penugasan label yang lebih akurat selama pelatihan, meningkatkan kualitas prediksi tanpa biaya tambahan saat inferensi.

**4. Performa**

YOLOv7 mencapai performa state-of-the-art pada dataset MS COCO:

- YOLOv7 (input 640px): 51,4% AP pada 30 FPS+ pada GPU V100.
- YOLOv7-X: 53,1% AP — mengungguli detektor *real-time* sebelumnya.

Dalam penelitian ini, digunakan varian standar `yolov7.pt` yang telah dilatih pada MS COCO dengan 80 kelas objek.

### 2.8.2 MS COCO Dataset

*Microsoft Common Objects in Context* (MS COCO) adalah dataset standar untuk deteksi, segmentasi, dan *captioning* objek. Karakteristik MS COCO:

| Atribut | Nilai |
|---------|-------|
| Jumlah gambar | >330.000 |
| Jumlah anotasi | >2,5 juta |
| Jumlah kelas | 80 kategori objek |
| Format anotasi | *Bounding box* + segmentasi + *keypoint* |
| Pembagian | Train / Val / Test |

Kelas kendaraan yang relevan dengan penelitian ini:

| Class ID | Nama Kelas (MS COCO) | Nama Indonesia | Digunakan |
|----------|---------------------|----------------|-----------|
| 1 | Bicycle | Sepeda | ✗ |
| 2 | Car | Mobil | ✓ |
| 3 | Motorcycle | Sepeda Motor | ✓ |
| 4 | Airplane | Pesawat | ✗ |
| 5 | Bus | Bus | ✓ |
| 6 | Train | Kereta | ✗ |
| 7 | Truck | Truk | ✓ |

Model `yolov7.pt` yang digunakan dalam penelitian ini telah dilatih pada MS COCO, sehingga dapat langsung digunakan untuk inferensi tanpa pelatihan ulang. Penyaringan kelas dilakukan melalui parameter `--classes 2 3 5 7` agar hanya empat jenis kendaraan yang ditampilkan pada output.

### 2.8.3 Deteksi Objek vs. Klasifikasi

Perlu dibedakan dua tugas dalam *computer vision*:

| Tugas | Input | Output | Contoh |
|-------|-------|--------|--------|
| **Klasifikasi gambar** | 1 gambar | 1 label kelas | "Gambar ini berisi mobil" |
| **Deteksi objek** | 1 gambar | Banyak *bounding box* + label | "Ada 3 mobil di (x1,y1)-(x2,y2), 2 motor di ..." |

YOLOv7 melakukan **deteksi objek** yang secara simultan mengklasifikasi setiap objek terdeteksi. Judul penelitian "Klasifikasi Jenis Kendaraan" merujuk pada aspek klasifikasi kelas kendaraan dalam pipeline deteksi — bukan klasifikasi gambar tunggal.

---

## 2.9 Computer Vision

*Computer vision* adalah bidang ilmu yang mengembangkan cara agar komputer dapat melihat dan memahami isi gambar digital, termasuk foto dan video (Szeliski, 2022). Bidang ini menjadi fondasi bagi berbagai aplikasi modern yang memerlukan interpretasi informasi visual.

### Tahapan Pipeline Computer Vision

```
[Akuisisi Data] → [Pra-pemrosesan] → [Ekstraksi Fitur] → [Deteksi/Klasifikasi] → [Visualisasi/Output]
```

1. **Akuisisi data** — pengambilan gambar/video dari kamera, file, atau sensor.
2. **Pra-pemrosesan** — resize, normalisasi, konversi warna, augmentasi.
3. **Ekstraksi fitur** — pengenalan tepi, sudut, tekstur (manual atau otomatis via CNN).
4. **Deteksi/klasifikasi** — identifikasi lokasi dan jenis objek.
5. **Visualisasi** — penampilan hasil dalam bentuk *bounding box*, label, atau metrik.

### Aplikasi Computer Vision dalam Transportasi

Integrasi *deep learning* dengan *computer vision* telah menghasilkan kemajuan signifikan (Davies & Turk, 2022). Aplikasi dalam transportasi meliputi:

- **Pemantauan lalu lintas** — deteksi dan penghitungan kendaraan dari CCTV.
- **Pengenalan plat nomor** (ALPR/ANPR) — identifikasi kendaraan secara otomatis.
- **Estimasi kecepatan** — pengukuran kecepatan kendaraan dari video.
- **Navigasi otonom** — deteksi pejalan kaki, kendaraan, rambu lalu lintas.
- ***Smart city*** — analisis pola lalu lintas untuk perencanaan kota cerdas (Gong et al., 2023).

Dalam penelitian ini, *computer vision* diterapkan untuk memproses rekaman video lalu lintas dari flyover Air Hitam: mendeteksi kendaraan, mengklasifikasi jenisnya, dan menampilkan hasil secara visual pada video output.

### Tantangan Computer Vision pada Lalu Lintas Nyata

Beberapa tantangan yang dihadapi sistem *computer vision* pada kondisi lapangan:

| Tantangan | Penjelasan | Dampak pada Deteksi |
|-----------|------------|---------------------|
| Oklusi (*occlusion*) | Kendaraan saling menutupi | *False negative* — objek tidak terdeteksi |
| Variasi pencahayaan | Siang, malam, hujan, silau | Akurasi menurun pada kondisi ekstrem |
| Skala objek | Kendaraan jauh vs. dekat | *Bounding box* tidak akurat pada objek kecil |
| Kepadatan tinggi | Banyak kendaraan dalam satu frame | NMS gagal memisahkan objek berdekatan |
| Domain gap | Model dilatih di negara lain | Kendaraan lokal (angkot, becak) tidak dikenali |

Tantangan-tantangan ini menjadi pertimbangan dalam evaluasi hasil penelitian dan saran pengembangan selanjutnya (Bab V).

---

## 2.10 Simple Online and Realtime Tracking (SORT)

*Simple Online and Realtime Tracking* (SORT) adalah algoritma pelacakan objek *multi-object tracking* (MOT) yang menggabungkan filter Kalman untuk prediksi posisi objek dengan asosiasi Hungarian untuk mencocokkan deteksi antar frame (Bewley et al., 2016, sebagaimana dirujuk dalam Ashraf et al., 2023).

### Prinsip Kerja SORT

1. **Prediksi** — Filter Kalman memprediksi posisi *bounding box* objek pada frame berikutnya berdasarkan kecepatan dan arah gerakan.
2. **Asosiasi** — Algoritma Hungarian mencocokkan prediksi dengan deteksi baru berdasarkan *Intersection over Union* (IoU).
3. **Update** — Filter Kalman diperbarui dengan deteksi yang cocok; deteksi tanpa pasangan memulai *track* baru.

SORT digunakan dalam *script* `detect_and_track.py` pada penelitian ini untuk memberikan **ID pelacakan** pada setiap kendaraan terdeteksi antar frame. Meskipun modul penghitungan kendaraan (`count_vehicle`) tidak diaktifkan dalam penelitian ini, infrastruktur pelacakan SORT tetap berjalan untuk menjaga konsistensi *bounding box* antar frame — terutama saat diterapkan *frame skipping* (inferensi hanya pada setiap frame ke-3).

---
