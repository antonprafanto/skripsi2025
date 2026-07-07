# BAB III — METODOLOGI PENELITIAN

---

## 3.1 Tahapan Pelaksanaan Penelitian

Penelitian ini dilaksanakan melalui tujuh tahapan yang ditunjukkan pada Gambar 3.1. Setiap tahapan dijelaskan sebagai berikut:

**Gambar 3.1 Tahapan Pelaksanaan Penelitian**

```
[1. Identifikasi Masalah & Studi Pustaka]
              ↓
[2. Pengumpulan Data]
              ↓
[3. Pra-pemrosesan Data]
              ↓
[4. Perancangan & Implementasi Sistem]
              ↓
[5. Pengujian & Evaluasi]
              ↓
[6. Pembahasan Hasil]
              ↓
[7. Penyusunan Laporan]
```

**Tabel 3.0 Ringkasan Tahapan Penelitian**

| Tahap | Kegiatan | Output |
|-------|----------|--------|
| 1. Identifikasi Masalah & Studi Pustaka | Memahami permasalahan penghitungan lalu lintas manual; mempelajari arsitektur YOLOv7, MS COCO, dan metode deteksi objek terkait | Rumusan masalah, tinjauan pustaka |
| 2. Pengumpulan Data | Merekam video lalu lintas di flyover Air Hitam, Samarinda, pada sore dan malam hari | File video .mp4 (1920×1080, 30 fps) |
| 3. Pra-pemrosesan Data | Mengekstrak frame video menggunakan OpenCV (`cv2.VideoCapture`); validasi format dan resolusi | Frame siap inferensi |
| 4. Perancangan & Implementasi | Mengonfigurasi model `yolov7.pt`; memodifikasi `detect_and_track.py`; menjalankan inferensi | Video output beranotasi |
| 5. Pengujian & Evaluasi | *Black Box Testing* (EP & BVA); evaluasi visual dan pengukuran FPS | Tabel hasil pengujian, metrik |
| 6. Pembahasan Hasil | Menganalisis hasil deteksi pada kedua skenario pencahayaan; mengidentifikasi keterbatasan | Bab IV |
| 7. Penyusunan Laporan | Mendokumentasikan seluruh proses, hasil, dan kesimpulan | Skripsi |

---

## 3.2 Pengumpulan Data

### 3.2.1 Lokasi dan Waktu Pengambilan Data

Data dikumpulkan secara langsung di **simpang flyover Air Hitam, Samarinda, Kalimantan Timur**. Lokasi ini dipilih karena:

1. Merupakan titik krusial dengan volume lalu lintas tinggi pada jam sibuk.
2. Flyover menyediakan sudut pandang *high angle* (dari atas) yang meminimalkan oklusi.
3. Terdapat dua ruas jalan utama (Letnan Jend. Suprapto dan Kadrie Oening) yang memungkinkan perbandingan kondisi.

### 3.2.2 Spesifikasi Perekaman

Rekaman video diambil menggunakan kamera *smartphone* dengan spesifikasi:

| Parameter | Nilai |
|-----------|-------|
| Resolusi | 1920 × 1080 (Full HD) |
| Frame rate | 30 fps |
| Format file | .mp4 (H.264) |
| Sudut pandang | *High angle* (dari atas flyover, ±45°–60°) |
| Stabilisasi | Handheld (tangan), dengan posisi relatif stabil di atas pagar flyover |

### 3.2.3 Skenario Pengambilan Data

Pengambilan data dilakukan pada **dua skenario waktu** yang berbeda:

| Skenario | Waktu | Ruas Jalan | Nama File* | Karakteristik |
|----------|-------|------------|------------|---------------|
| Sore hari | ±16.00–18.00 WITA | Letnan Jend. Suprapto | `FOS_01.mp4` | Kepadatan tinggi, pencahayaan alami (matahari), aktivitas puncak |
| Malam hari | ±19.00–21.00 WITA | Kadrie Oening | Video malam | Kepadatan rendah–sedang, pencahayaan lampu jalan, aktivitas menurun |

> *Nama file video disesuaikan dengan file aktual mahasiswa. Pada draft asli, `FOS_01.mp4` digunakan untuk inferensi. Jika video malam hanya satu file, gunakan nama yang sama secara konsisten di seluruh bab dan lampiran.

### 3.2.4 Karakteristik Data

Sudut pandang *high angle* dipilih untuk meminimalkan **oklusi** (*occlusion*) — kondisi di mana kendaraan saling menutupi sehingga sulit dideteksi. Dari sudut atas, sebagian besar kendaraan terlihat secara utuh, berbeda dengan sudut horizontal CCTV yang sering terhalang oleh kendaraan di depannya.

Perbedaan skenario sore dan malam memberikan variasi pada:

- **Intensitas cahaya** — matahari vs. lampu jalan.
- **Kepadatan kendaraan** — puncak sore vs. menurun malam.
- **Kontras visual** — bayangan panjang (sore) vs. sorotan lampu (malam).
- **Komposisi kendaraan** — dominasi motor pada sore hari di area lampu merah.

---

## 3.3 Perancangan Data

Perancangan data melibatkan konfigurasi model pre-trained yang digunakan untuk inferensi dan klasifikasi kendaraan.

### 3.3.1 Model Weights

Model menggunakan *weight* **`yolov7.pt`** yang telah dilatih (*pre-trained*) pada dataset MS COCO (*Microsoft Common Objects in Context*). MS COCO memiliki 80 kelas objek dengan lebih dari 330.000 gambar dan 2,5 juta anotasi. Model ini diunduh dari repository resmi YOLOv7 dan tidak mengalami pelatihan ulang (*fine-tuning*) dalam penelitian ini.

| Atribut Model | Nilai |
|---------------|-------|
| Nama file | `yolov7.pt` |
| Arsitektur | YOLOv7 (E-ELAN backbone) |
| Dataset pelatihan | MS COCO (80 kelas) |
| Input inferensi | 640 × 640 px (diresize dari 1920 × 1080) |
| *Framework* | PyTorch |

### 3.3.2 Filter Jenis Kendaraan

Karena MS COCO memiliki 80 kelas, dilakukan penyaringan agar hanya 4 kelas kendaraan yang dideteksi dan ditampilkan:

| Class ID | Nama Kelas (MS COCO) | Nama Indonesia | Frekuensi di Lokasi |
|----------|---------------------|----------------|-------------------|
| 2 | Car | Mobil | Tinggi |
| 3 | Motorcycle | Sepeda Motor | Sangat tinggi |
| 5 | Bus | Bus | Rendah |
| 7 | Truck | Truk | Rendah |

Penyaringan dilakukan melalui parameter `--classes 2 3 5 7` saat menjalankan inferensi. Objek lain yang terdeteksi model (pejalan kaki, lampu lalu lintas, dll.) diabaikan dan tidak ditampilkan pada video output.

---

## 3.4 Perancangan Proses/Algoritma

Alur kerja sistem deteksi dan klasifikasi kendaraan ditunjukkan pada Gambar 3.2.

**Gambar 3.2 Flowchart Proses Deteksi dan Klasifikasi Kendaraan**

```
[Video Input (.mp4)]
        ↓
[Baca Frame — cv2.VideoCapture]
        ↓
[Frame Counter += 1]
        ↓
    ┌───────────────────────────────────┐
    │ Frame ke-3? (frame_counter % 3)   │
    │ YA → Inferensi YOLOv7             │
    │ TIDAK → Gunakan deteksi frame     │
    │         sebelumnya (frame skip)   │
    └───────────────────────────────────┘
        ↓
[Resize frame → 640 × 640 px]
        ↓
[Inferensi YOLOv7 (yolov7.pt)]
        ↓
[Non-Maximum Suppression (NMS)]
        ↓
[Filter kelas: 2, 3, 5, 7]
        ↓
[Pelacakan SORT — asosiasi ID antar frame]
        ↓
[Gambar bounding box + label — draw_boxes()]
        ↓
[Simpan frame → cv2.VideoWriter]
        ↓
[Video Output (.mp4 beranotasi)]
```

### 3.4.1 Sumber dan Modifikasi Script

Sistem diimplementasikan menggunakan *script* **`detect_and_track.py`**, yang merupakan modifikasi dari **`detect_count_and_track.py`** pada repository GitHub YOLOv7 oleh Krisna Rengga. Modifikasi yang dilakukan:

| No | Modifikasi | Tujuan |
|----|-----------|--------|
| 1 | Penyaringan kelas kendaraan (`--classes 2 3 5 7`) | Hanya 4 jenis kendaraan yang ditampilkan |
| 2 | Kustomisasi fungsi `draw_boxes()` | Warna oranye (RGB: 255, 144, 30), font skala 0.6 |
| 3 | *Frame skipping* (inferensi setiap 3 frame) | Mengurangi beban komputasi GPU |
| 4 | Integrasi SORT *tracking* | Konsistensi *bounding box* antar frame |
| 5 | Penonaktifan `count_vehicle` | Fokus deteksi+klasifikasi, bukan penghitungan |
| 6 | Penyesuaian parameter default | `conf-thres 0.45`, `img-size 640` |

### 3.4.2 Frame Skipping

Untuk mengoptimalkan kecepatan pemrosesan video, diterapkan **frame skipping** — inferensi model YOLOv7 hanya dijalankan pada **setiap frame ke-3** (`frame_counter % 3 == 0`). Pada frame 1 dan 2, sistem menggunakan hasil deteksi dan pelacakan dari frame sebelumnya (`last_tracked_dets`).

Logika frame skipping dalam *script*:

```python
# Frame skipping: hanya jalankan inferensi pada setiap frame ke-3
if frame_counter % 3 != 0 and len(last_tracked_dets) > 0:
    tracked_dets = last_tracked_dets
    # Lewati inferensi model, gunakan deteksi sebelumnya
else:
    # Jalankan inferensi YOLOv7 penuh
    ...
```

**Alasan frame skipping:**

- Inferensi YOLOv7 membutuhkan waktu signifikan per frame (~30–50 ms pada GPU T4).
- Video 30 fps berarti 33 ms per frame — inferensi setiap frame menyebabkan *bottleneck*.
- Dengan skipping 1:3, kecepatan pemrosesan meningkat ~3× tanpa kehilangan akurasi signifikan pada kendaraan bergerak.
- SORT *tracking* menjaga konsistensi posisi *bounding box* pada frame yang dilewati.

### 3.4.3 Pelacakan SORT

*Simple Online and Realtime Tracking* (SORT) diintegrasikan untuk melacak identitas kendaraan antar frame. SORT menggunakan:

1. **Filter Kalman** — memprediksi posisi *bounding box* berdasarkan kecepatan dan arah gerakan.
2. **Algoritma Hungarian** — mencocokkan deteksi baru dengan *track* yang ada berdasarkan IoU.

Meskipun modul **penghitungan kendaraan** (`count_vehicle`) di dalam *script* tidak diaktifkan (kode terkait di-*comment*), infrastruktur SORT tetap berjalan untuk:

- Memberikan ID pelacakan konsisten pada setiap kendaraan.
- Menjaga stabilitas *bounding box* saat frame skipping aktif.
- Menyiapkan fondasi untuk pengembangan penghitungan kendaraan di penelitian lanjutan.

### 3.4.4 Parameter Inferensi

**Tabel 3.1 Spesifikasi Lingkungan Inferensi**

| Komponen | Spesifikasi |
|----------|-------------|
| Bahasa pemrograman | Python 3.x |
| Pustaka utama | OpenCV 4.x, PyTorch 1.x, NumPy |
| Model | YOLOv7 (`yolov7.pt`, pre-trained MS COCO) |
| *Virtual hardware* | T4 GPU (Google Colab, 15 GB VRAM) |
| *Script* | `detect_and_track.py` (modifikasi dari `detect_count_and_track.py`) |
| Sumber repository | GitHub YOLOv7 — Krisna Rengga |
| Input | Video .mp4, 1920 × 1080, 30 fps |
| Output | Video .mp4 dengan anotasi *bounding box* dan label |

**Tabel 3.1a Parameter Inferensi**

| Parameter | Nilai Default Script | Nilai Digunakan | Alasan Perubahan |
|-----------|---------------------|-----------------|------------------|
| `--weights` | `yolov7.pt` | `yolov7.pt` | Model pre-trained MS COCO |
| `--img-size` | 416 | **640** | Resolusi lebih tinggi → deteksi objek kecil lebih baik |
| `--conf-thres` | 0.65 | **0.45** | Ambang lebih rendah → lebih banyak deteksi pada kondisi padat |
| `--iou-thres` | 0.45 | **0.45** | Tidak diubah — standar NMS |
| `--device` | `cpu` | **0** (GPU T4) | Akselerasi CUDA |
| `--classes` | Semua (80 kelas) | **2 3 5 7** | Filter 4 kelas kendaraan |

> **Penjelasan parameter:**
> - **`conf-thres 0.45`**: Nilai *confidence threshold* menentukan ambang minimum skor kepercayaan model untuk menampilkan deteksi. Nilai default 0.65 terlalu tinggi untuk kondisi lalu lintas padat di Samarinda — banyak kendaraan motor dengan skor confidence 0.45–0.60 terlewat. Setelah percobaan awal, nilai 0.45 dipilih sebagai keseimbangan antara jumlah deteksi dan *false positive*.
> - **`img-size 640`**: Resolusi input inferensi. Nilai 640 (vs. default 416) meningkatkan akurasi deteksi objek kecil (motor jauh) dengan sedikit penambahan waktu komputasi.

Perintah eksekusi:

```bash
python detect_and_track.py \
  --weights yolov7.pt \
  --source FOS_01.mp4 \
  --device 0 \
  --img-size 640 \
  --conf-thres 0.45 \
  --iou-thres 0.45 \
  --classes 2 3 5 7
```

---

## 3.5 Perancangan Tampilan

Perancangan tampilan pada penelitian berbasis *computer vision* ini bukan berupa antarmuka grafis (GUI) aplikasi, melainkan **visualisasi anotasi** (*bounding box*) pada video output. Komponen tampilan:

| Komponen | Deskripsi | Spesifikasi |
|----------|-----------|-------------|
| Video Feed | Rekaman video asli dengan *bounding box* di sekitar kendaraan terdeteksi | Resolusi asli 1920 × 1080 |
| Label Kelas | Teks label jenis kendaraan di atas *bounding box* | *Car*, *Motorcycle*, *Bus*, *Truck* |
| Warna Bounding Box | Warna kotak deteksi | Oranye — RGB(255, 144, 30) |
| Ketebalan Garis | Ketebalan garis *bounding box* | 1 px |
| Ukuran Teks | Font dan skala label | HERSHEY_SIMPLEX, skala 0.6, warna putih |
| Titik Tengah | Penanda pusat objek (untuk SORT) | Lingkaran radius 1 px |

Konfigurasi visual diatur melalui modifikasi fungsi `draw_boxes()` pada file `detect_and_track.py`. Fungsi ini menerima parameter *bounding box* (koordinat x1, y1, x2, y2), identitas pelacakan, kategori kelas, dan nama kelas — kemudian menggambar kotak dan label pada frame.

---

## 3.6 Perancangan Pengujian

Pengujian dirancang menggunakan metode ***Black Box Testing*** untuk memastikan seluruh fungsi sistem berjalan sesuai spesifikasi tanpa memeriksa kode internal.

**Objek pengujian:** Fungsionalitas *script* `detect_and_track.py` saat mengeksekusi video rekaman flyover.

### 3.6.1 Skenario Pengujian

**Tabel 3.2 Rancangan Skenario Pengujian Black Box Testing**

| No | Skenario | Teknik | Input | Hasil yang Diharapkan |
|----|----------|--------|-------|----------------------|
| 1 | Fungsi input — valid | EP | File video .mp4, 1920×1080 | Sistem berhasil membaca dan memproses video |
| 1b | Fungsi input — invalid | EP | File .avi / .mkv / rusak | Sistem menampilkan pesan error, tidak crash |
| 2 | Fungsi parameter — kelas valid | EP | `--classes 2 3 5 7` | Hanya 4 kelas kendaraan yang ditampilkan |
| 2a | Fungsi parameter — kelas invalid | EP | `--classes 0 1 99` | Tidak ada kendaraan terdeteksi / kelas tidak relevan |
| 2b | Batas confidence — bawah | BVA | `--conf-thres 0.0` | Semua deteksi ditampilkan (banyak *false positive*) |
| 2c | Batas confidence — atas | BVA | `--conf-thres 1.0` | Tidak ada deteksi yang ditampilkan |
| 2d | Batas img-size — bawah | BVA | `--img-size 320` | Deteksi berjalan, objek kecil mungkin terlewat |
| 2e | Batas img-size — atas | BVA | `--img-size 1280` | Deteksi berjalan, waktu proses lebih lama |
| 3 | Visualisasi — sore hari | EP | Video `FOS_01.mp4` | *Bounding box* oranye dan label muncul sesuai rancangan |
| 3b | Visualisasi — malam hari | EP | Video malam | *Bounding box* dan label tetap muncul pada pencahayaan rendah |
| 4 | Output | EP | Video selesai diproses | File .mp4 tersimpan tanpa korupsi, dapat diputar |
| 5 | Performa — FPS | Pengukuran | Log waktu proses per frame | FPS tercatat dan dilaporkan |

### 3.6.2 Prosedur Pengukuran FPS

Kecepatan inferensi diukur menggunakan log waktu pada *script*:

```python
t0 = time.time()
# ... proses inferensi ...
t1 = time.time()
fps = 1 / (t1 - t0)
```

FPS dihitung sebagai rata-rata dari seluruh frame yang melalui inferensi (bukan frame yang di-skip). Hasil dilaporkan pada Bab IV.

### 3.6.3 Kriteria Keberhasilan

| Kriteria | Standar Lulus |
|----------|--------------|
| Pembacaan video | File .mp4 terbaca tanpa error |
| Filter kelas | Hanya mobil, motor, bus, truk yang ditampilkan |
| Visualisasi | Warna, font, ketebalan sesuai rancangan tampilan pada Subbab 3.5 |
| Output video | File tersimpan, dapat diputar, tidak korup |
| BVA conf-thres 0.0 | Deteksi > conf-thres 1.0 (sesuai ekspektasi batas) |
| BVA conf-thres 1.0 | Nol deteksi ditampilkan |

---
