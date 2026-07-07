# Halaman Depan & Bagian Awal

---

## No. Urut Skripsi

```
Diisi oleh bagian akademik Fakultas Teknik
(format mengikuti template resmi Universitas Mulawarman)
```

---

## Halaman Judul

```
KLASIFIKASI JENIS KENDARAAN MENGGUNAKAN YOLOv7

SKRIPSI

Diajukan sebagai salah satu syarat untuk menyelesaikan pendidikan
pada Program Studi Strata 1 Informatika,
Fakultas Teknik, Universitas Mulawarman

Oleh:
FIRA AGUSTINA
1915026031

FAKULTAS TEKNIK
UNIVERSITAS MULAWARMAN
SAMARINDA
2026
```

---

## Pernyataan Keaslian Skripsi

Saya menyatakan dengan sesungguhnya bahwa skripsi dengan judul:

**KLASIFIKASI JENIS KENDARAAN MENGGUNAKAN YOLOv7**

yang dibuat sebagai salah satu syarat untuk menyelesaikan pendidikan pada Program Studi S1 Informatika, Fakultas Teknik, Universitas Mulawarman, sejauh yang saya ketahui bukan merupakan tiruan atau duplikasi dari skripsi yang sudah dipublikasikan dan/atau pernah dipakai untuk mendapatkan gelar kesarjanaan di lingkungan Universitas Mulawarman maupun di perguruan tinggi atau instansi manapun, kecuali bagian yang sumber informasinya dicantumkan sebagaimana mestinya.

Samarinda, 6 Juli 2026

Materai

Fira Agustina  
NIM. 1915026031

---

## Halaman Pengesahan

```
KLASIFIKASI JENIS KENDARAAN MENGGUNAKAN YOLOv7

Oleh:
Fira Agustina
1915026031

Telah diujikan pada ................. dan dinyatakan telah memenuhi syarat

Samarinda, ..........................

Disahkan oleh:

Pembimbing I,
Anton Prafanto, S.Kom., MT
NIP. 199310222019031016

Pembimbing II,
Prof. Dr. Anindita Septiarini, S.T., M.Cs
NIP. 198209012009122003

Mengetahui,
Dekan Fakultas Teknik
Universitas Mulawarman
Prof. Dr. Ir. H. Tamrin, S.T., M.T., IPU., ASEAN.Eng., APEC Eng.
NIP. 197002272000121001
```

## Abstrak (Bahasa Indonesia)

**KLASIFIKASI JENIS KENDARAAN MENGGUNAKAN YOLOv7**

Fira Agustina — NIM. 1915026031  
Program Studi Informatika  
Dosen Pembimbing: I. Anton Prafanto, S.Kom., MT | II. Prof. Dr. Anindita Septiarini, S.T., M.Cs

Pertumbuhan populasi dan urbanisasi di Indonesia telah meningkatkan kepadatan kendaraan, terutama di kota-kota besar. Data Badan Pusat Statistik melalui Korlantas Polri menunjukkan bahwa total jumlah kendaraan bermotor di Indonesia pada tahun 2023 mencapai 157.080.504 unit. Peningkatan penggunaan kendaraan bermotor berujung pada kemacetan, sehingga pemantauan dan penghitungan volume lalu lintas menjadi hal penting dalam perencanaan transportasi. Namun, penghitungan tersebut masih banyak dilakukan secara manual menggunakan *manual counter* dan lembar formulir survei.

Tujuan penelitian ini adalah menerapkan algoritma You Only Look Once versi 7 (YOLOv7) untuk mendeteksi dan mengklasifikasi jenis kendaraan secara otomatis dari rekaman video. Metode yang digunakan adalah YOLOv7 dengan model pre-trained `yolov7.pt` yang telah dilatih pada dataset MS COCO, dengan penyaringan empat kelas kendaraan (mobil, motor, bus, truk). Sistem dikembangkan menggunakan Python dengan pustaka OpenCV dan PyTorch, dijalankan pada Google Colab dengan GPU T4. *Script* `detect_and_track.py` — modifikasi dari `detect_count_and_track.py` — digunakan untuk inferensi dengan parameter `conf-thres 0.45` dan `img-size 640`. Pengujian dilakukan menggunakan metode *Black Box Testing* dengan teknik *Equivalence Partitioning* dan *Boundary Value Analysis*. Data berupa rekaman video lalu lintas dari simpang flyover Air Hitam, Samarinda, dengan resolusi 1920 × 1080 dan 30 fps, diambil pada dua skenario waktu: sore hari dan malam hari.

Hasil percobaan menunjukkan bahwa model YOLOv7 mampu mendeteksi dan mengklasifikasi empat jenis kendaraan dengan *bounding box* yang akurat dan label kelas yang tepat pada kedua skenario pencahayaan. Mayoritas skenario pengujian *Black Box Testing* yang dieksekusi dinyatakan lulus. Model menunjukkan performa baik pada kondisi pencahayaan siang dan malam hari dengan sudut pandang *high angle* dari flyover. Keterbatasan ditemukan pada kendaraan yang sedang berhenti atau menumpuk akibat oklusi; namun ketika kendaraan kembali bergerak, model berhasil mendeteksi kembali dengan label yang sesuai.

Penelitian ini diharapkan dapat membantu Dinas Perhubungan Kota Samarinda dalam pengembangan sistem pemantauan lalu lintas kendaraan bermotor secara lebih efisien berbasis *computer vision*.

**Kata kunci:** YOLOv7, deteksi kendaraan, *computer vision*, klasifikasi kendaraan, *deep learning*

---

## Abstract (Bahasa Inggris)

**VEHICLE TYPE CLASSIFICATION USING YOLOv7**

Fira Agustina — Student ID. 1915026031  
Informatics Study Program  
Supervisors: I. Anton Prafanto, S.Kom., MT | II. Prof. Dr. Anindita Septiarini, S.T., M.Cs

Population growth and urbanization in Indonesia have increased vehicle density, particularly in major cities. Data from the Central Statistics Agency through the Indonesian National Police Traffic Corps shows that the total number of motor vehicles in Indonesia in 2023 reached 157,080,504 units. The rising number of motor vehicles leads to traffic congestion, making traffic monitoring and volume counting an important aspect of transportation planning. However, traffic volume counting is still largely performed manually using manual counters and survey forms.

The objective of this research is to apply the You Only Look Once version 7 (YOLOv7) algorithm to detect and classify vehicle types automatically from video recordings. The method used is YOLOv7 with a pre-trained `yolov7.pt` model trained on the MS COCO dataset, filtered to four vehicle classes (car, motorcycle, bus, and truck). The system was developed using Python with OpenCV and PyTorch libraries, executed on Google Colab with T4 GPU. The `detect_and_track.py` script — modified from `detect_count_and_track.py` — was used for inference with parameters `conf-thres 0.45` and `img-size 640`. Testing was conducted using Black Box Testing with Equivalence Partitioning and Boundary Value Analysis techniques. Data consists of traffic video recordings from the Air Hitam flyover intersection in Samarinda, with a resolution of 1920 × 1080 at 30 fps, collected under two time scenarios: afternoon and night.

Experimental results demonstrate that the YOLOv7 model successfully detected and classified four vehicle types with accurate bounding boxes and correct class labels under both lighting scenarios. Most executed Black Box Testing scenarios passed. The model performed well under both daytime and nighttime lighting with a high-angle view from the flyover. Limitations were observed with stationary or clustered vehicles due to occlusion; however, detection resumed with correct labels once vehicles began moving again.

This research is expected to assist the Samarinda City Transportation Agency in developing more efficient computer vision-based motor vehicle traffic monitoring systems.

**Keywords:** YOLOv7, vehicle detection, computer vision, vehicle classification, deep learning

---

## Kata Pengantar

Puji syukur ke hadirat Allah SWT, Tuhan Yang Maha Esa, atas rahmat dan karunia-Nya sehingga penulis dapat menyelesaikan skripsi dengan judul **"Klasifikasi Jenis Kendaraan Menggunakan YOLOv7"**. Skripsi ini disusun sebagai salah satu syarat untuk menyelesaikan pendidikan pada Program Studi S1 Informatika, Fakultas Teknik, Universitas Mulawarman.

Penulis menyampaikan terima kasih kepada:

1. Orang tua dan saudara-saudara penulis atas doa, bimbingan, serta kasih sayangnya.
2. Bapak Prof. Dr. Ir. H. Tamrin, S.T., M.T., IPU., ASEAN.Eng., APEC Eng. selaku Dekan Fakultas Teknik Universitas Mulawarman.
3. Bapak Awang Harsa Kridalaksana, S.Kom., M.Kom. selaku Ketua Program Studi Informatika.
4. Bapak Anton Prafanto, S.Kom., MT selaku Pembimbing I yang telah memberikan arahan, masukan, dan bantuan selama proses penelitian.
5. Ibu Prof. Dr. Anindita Septiarini, S.T., M.Cs selaku Pembimbing II atas masukan dan bimbingannya.
6. Segenap dosen Program Studi Informatika yang telah memberikan ilmu pengetahuan selama perkuliahan.
7. Rekan-rekan seperjuangan yang terus memberikan dukungan dan semangat.

Penulis menyadari bahwa skripsi ini masih memiliki kekurangan. Oleh karena itu, kritik dan saran yang membangun sangat diharapkan.

Samarinda, 7 Juli 2026

Penulis,

Fira Agustina

---

## Daftar Istilah/Lambang

| Istilah/Lambang | Makna/Arti |
|-----------------|------------|
| AI | *Artificial Intelligence* / Kecerdasan Buatan |
| ANN | *Artificial Neural Network* / Jaringan Saraf Tiruan |
| AP | *Average Precision* |
| BPS | Badan Pusat Statistik |
| BVA | *Boundary Value Analysis* |
| CNN | *Convolutional Neural Network* |
| CV | *Computer Vision* |
| EP | *Equivalence Partitioning* |
| FN | *False Negative* |
| FP | *False Positive* |
| FPS | *Frames Per Second* |
| GPU | *Graphics Processing Unit* |
| GUI | *Graphical User Interface* |
| IoU | *Intersection over Union* |
| mAP | *mean Average Precision* |
| ML | *Machine Learning* |
| MOT | *Multi-Object Tracking* |
| MS COCO | *Microsoft Common Objects in Context* |
| NMS | *Non-Maximum Suppression* |
| SORT | *Simple Online and Realtime Tracking* |
| TP | *True Positive* |
| YOLO | *You Only Look Once* |

---

## Daftar Singkatan

| Singkatan | Makna/Arti |
|-----------|------------|
| AI | *Artificial Intelligence* |
| BPS | Badan Pusat Statistik |
| CNN | *Convolutional Neural Network* |
| fps | *frames per second* |
| GPU | *Graphics Processing Unit* |
| IoU | *Intersection over Union* |
| mAP | *mean Average Precision* |
| NMS | *Non-Maximum Suppression* |
| SORT | *Simple Online and Realtime Tracking* |
| YOLO | *You Only Look Once* |

---
