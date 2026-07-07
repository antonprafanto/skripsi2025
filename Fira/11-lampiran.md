# LAMPIRAN — Dokumentasi Source Code

---

## Lampiran 1: Source Code `detect_and_track.py`

Lampiran ini mendokumentasikan *script* `detect_and_track.py` yang digunakan dalam penelitian. Kode lengkap tersimpan di dokumen Word asli (halaman 35–49). Berikut penjelasan bagian-bagian penting beserta modifikasi dari *script* asli `detect_count_and_track.py`.

### 1. Informasi Umum

| Atribut | Nilai |
|---------|-------|
| Nama file | `detect_and_track.py` |
| Sumber asli | `detect_count_and_track.py` — Repository YOLOv7 (Krisna Rengga) |
| Bahasa | Python 3.x |
| Dependensi utama | PyTorch, OpenCV, NumPy, SORT (`sort.py`) |
| Fungsi utama | Deteksi, klasifikasi, pelacakan, dan visualisasi kendaraan pada video |

### 2. Import dan Dependensi

```python
import argparse
import time
from pathlib import Path
import cv2
import torch
import torch.backends.cudnn as cudnn
from numpy import random
from models.experimental import attempt_load
from utils.datasets import LoadStreams, LoadImages
from utils.general import (check_img_size, non_max_suppression, scale_coords, ...)
from utils.plots import plot_one_box
from utils.torch_utils import select_device, time_synchronized

# Untuk SORT tracking
import skimage
from sort import *
```

**Penjelasan:**
- `torch` / `models.experimental` — memuat model YOLOv7 (`yolov7.pt`).
- `cv2` (OpenCV) — membaca video, resize frame, menggambar anotasi, menyimpan output.
- `sort` — modul SORT (*Simple Online and Realtime Tracking*) untuk pelacakan objek antar frame.

### 3. Parameter Command-Line (Argparse)

```python
parser.add_argument('--weights', nargs='+', type=str, default='yolov7.pt')
parser.add_argument('--source', type=str, default='samples')
parser.add_argument('--img-size', type=int, default=416)      # DIUBAH → 640
parser.add_argument('--conf-thres', type=float, default=0.65)  # DIUBAH → 0.45
parser.add_argument('--iou-thres', type=float, default=0.45)
parser.add_argument('--device', default='cpu')                 # DIUBAH → 0 (GPU)
parser.add_argument('--classes', nargs='+', type=int)        # DITAMBAH → 2 3 5 7
```

**Modifikasi parameter:**

| Parameter | Default Asli | Nilai Penelitian | Alasan |
|-----------|-------------|------------------|--------|
| `--img-size` | 416 | **640** | Deteksi objek kecil lebih baik |
| `--conf-thres` | 0.65 | **0.45** | Lebih banyak deteksi pada lalu lintas padat |
| `--device` | `cpu` | **0** | Akselerasi GPU T4 (Colab) |
| `--classes` | Semua (80) | **2 3 5 7** | Filter 4 kelas kendaraan |

### 4. Fungsi `draw_boxes()` — Visualisasi

```python
def draw_boxes(img, bbox, identities=None, categories=None, names=None, offset=(0, 0)):
    for i, box in enumerate(bbox):
        x1, y1, x2, y2 = [int(i) for i in box]
        # ... offset koordinat ...
        cat = int(categories[i]) if categories is not None else 0
        # Gambar bounding box dan label
        cv2.rectangle(img, (x1, y1), (x2, y2), (255, 144, 30), 1)  # Oranye
        cv2.putText(img, label, (x1, y1 - 5), cv2.FONT_HERSHEY_SIMPLEX, 0.6, (255, 255, 255), 1)
    return img
```

**Modifikasi:** Warna *bounding box* diatur ke oranye RGB(255, 144, 30), font HERSHEY_SIMPLEX skala 0.6, warna teks putih.

### 5. Frame Skipping — Optimasi Kecepatan

```python
frame_counter = 0
last_tracked_dets = np.empty((0, 6))

for path, img, im0s, vid_cap in dataset:
    frame_counter += 1

    # FRAME SKIPPING: inferensi hanya setiap frame ke-3
    if frame_counter % 3 != 0 and len(last_tracked_dets) > 0:
        tracked_dets = last_tracked_dets
        # Lewati inferensi model, gunakan deteksi frame sebelumnya
    else:
        # ... jalankan inferensi YOLOv7 penuh ...
        # ... jalankan SORT tracking ...
        last_tracked_dets = tracked_dets
```

**Penjelasan:**
- Inferensi YOLOv7 berat secara komputasi (~30–50 ms/frame pada T4).
- Dengan skipping 1:3, hanya 1 dari 3 frame yang melalui inferensi penuh.
- Frame yang dilewati menggunakan hasil pelacakan SORT dari frame terakhir yang diinferensi.
- Meningkatkan kecepatan pemrosesan ~3× tanpa kehilangan akurasi signifikan pada kendaraan bergerak.

### 6. Integrasi SORT Tracking

```python
from sort import *

# Inisialisasi tracker
tracker = Sort()
tracked_dets = tracker.update(dets)
```

**Penjelasan:**
- SORT menggunakan filter Kalman untuk memprediksi posisi objek pada frame berikutnya.
- Algoritma Hungarian mencocokkan deteksi baru dengan *track* yang ada berdasarkan IoU.
- Setiap kendaraan mendapat ID pelacakan unik antar frame.
- SORT menjaga konsistensi *bounding box* saat frame skipping aktif.

### 7. Modul Penghitungan (Dinonaktifkan)

```python
count_vehicle = 0
# ...
# add vehicles counting
# if len(array_ids) > 0:
#     if id not in array_ids:
#         array_ids.append(id)
# Kode counting di-comment karena penelitian fokus deteksi+klasifikasi
```

**Penjelasan:** Modul `count_vehicle` dan logika `array_ids` dari *script* asli `detect_count_and_track.py` **tidak diaktifkan** karena penelitian ini berfokus pada deteksi dan klasifikasi, bukan perhitungan volume lalu lintas. Infrastruktur SORT tetap aktif untuk pelacakan visual.

### 8. Alur Utama Fungsi `detect()`

```
1. Parse argumen command-line
2. Muat model YOLOv7 (yolov7.pt) ke GPU
3. Buka video input (cv2.VideoCapture)
4. Inisialisasi SORT tracker
5. Untuk setiap frame:
   a. Cek frame skipping (counter % 3)
   b. Jika frame inferensi → resize 640×640 → inferensi YOLOv7 → NMS → filter kelas
   c. Jika frame skip → gunakan last_tracked_dets
   d. Update SORT tracker
   e. Gambar bounding box + label (draw_boxes)
   f. Tulis frame ke video output (cv2.VideoWriter)
6. Simpan video output
7. Cetak statistik waktu (FPS)
```

### 9. Perintah Eksekusi

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

### 10. Konsistensi dengan Narasi Bab

| Aspek | Bab III/IV | Lampiran (Kode) | Status |
|-------|-----------|-----------------|--------|
| Nama script | `detect_and_track.py` | `detect_and_track.py` | ✅ Konsisten |
| Sumber asli | `detect_count_and_track.py` | `detect_count_and_track.py` | ✅ Konsisten |
| conf-thres | 0.45 | 0.45 (via argumen) | ✅ Konsisten |
| img-size | 640 | 640 (via argumen) | ✅ Konsisten |
| Frame skipping | Setiap 3 frame | `frame_counter % 3` | ✅ Konsisten |
| SORT tracking | Dijelaskan | `from sort import *` | ✅ Konsisten |
| count_vehicle | Dinonaktifkan | Di-comment | ✅ Konsisten |

---
