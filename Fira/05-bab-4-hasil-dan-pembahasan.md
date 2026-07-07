# BAB IV — HASIL DAN PEMBAHASAN

---

## 4.1 Penerapan/Pengolahan Data

Berdasarkan metodologi pada Bab III, data yang diperoleh berupa rekaman video dengan sudut pandang tinggi (*high angle*) dari flyover Air Hitam, Samarinda. Sudut pandang ini menurunkan kemungkinan oklusi pada proses deteksi dibandingkan sudut horizontal CCTV.

### 4.1.1 Data Video Sore Hari

Pada Gambar 4.1 terlihat sudut pandang rekaman video yang mengarah ke ruas jalan Letnan Jend. Suprapto. Gambar 4.2 menunjukkan kondisi kepadatan lalu lintas yang tinggi di area lampu lalu lintas — kendaraan, terutama sepeda motor, cenderung menumpuk saat lampu merah aktif. Kondisi ini menjadi tantangan utama bagi model deteksi karena oklusi tinggi antar kendaraan.

> **Gambar 4.1 Potongan video raw — sore hari, ruas Letnan Jend. Suprapto**  
> *(disisipkan pada naskah final)*

> **Gambar 4.2 Kepadatan lalu lintas pada video raw — sore hari**  
> *(disisipkan pada naskah final)*

**Tabel 4.0 Karakteristik Data Video**

| Atribut | Sore Hari (`FOS_01.mp4`) | Malam Hari (video malam) |
|---------|--------------------------|---------------------------|
| Ruas jalan | Letnan Jend. Suprapto | Kadrie Oening |
| Waktu rekaman | ±16.00–18.00 WITA | ±19.00–21.00 WITA |
| Resolusi | 1920 × 1080 | 1920 × 1080 |
| Frame rate | 30 fps | 30 fps |
| Pencahayaan | Alami (matahari) | Lampu jalan |
| Kepadatan | Tinggi (lampu merah) | Rendah–sedang |
| Kendaraan dominan | Sepeda motor, mobil | Sepeda motor, mobil |

### 4.1.2 Data Video Malam Hari

Gambar 4.3 menunjukkan rekaman pada malam hari di ruas jalan Kadrie Oening. Kepadatan kendaraan terlihat lebih rendah dibandingkan sore hari, meskipun kedua ruas berada di simpang lampu lalu lintas yang sama. Perbedaan kepadatan dan pencahayaan ini menjadikan data cocok untuk membandingkan performa deteksi pada kondisi berbeda.

> **Gambar 4.3 Potongan video raw — malam hari, ruas Kadrie Oening**  
> *(disisipkan pada naskah final)*

### 4.1.3 Proses Pengolahan Data

Video hasil rekaman diproses menggunakan *script* `detect_and_track.py` yang dimodifikasi dari `detect_count_and_track.py` pada repository GitHub YOLOv7 (Krisna Rengga). *Script* ini memanfaatkan model pre-trained `yolov7.pt` (MS COCO, 80 kelas) dengan penyaringan 4 kelas kendaraan.

Proses pengolahan meliputi:

1. **Pembacaan video** — setiap frame diekstrak menggunakan `cv2.VideoCapture`.
2. **Frame skipping** — inferensi YOLOv7 dijalankan pada setiap frame ke-3; frame lainnya menggunakan hasil pelacakan SORT dari frame sebelumnya.
3. **Inferensi model** — frame diresize ke 640 × 640 px, kemudian diproses oleh YOLOv7.
4. **Penyaringan kelas** — hanya deteksi dengan class ID 2, 3, 5, 7 yang ditampilkan.
5. **Pelacakan SORT** — setiap deteksi diberi ID pelacakan untuk konsistensi antar frame.
6. **Visualisasi** — *bounding box* oranye dan label kelas digambar pada frame.
7. **Penyimpanan** — frame beranotasi dikompilasi menjadi video output .mp4.

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

## 4.2 Penerapan Proses Algoritma YOLOv7

Penerapan deteksi dan klasifikasi kendaraan menggunakan YOLOv7 berjalan melalui alur kerja berikut:

**Tabel 4.1a Alur Kerja Inferensi YOLOv7**

| Langkah | Proses | Pustaka/Fungsi | Keterangan |
|---------|--------|---------------|------------|
| 1 | Pembacaan video input | `cv2.VideoCapture` | File .mp4, 1920×1080, 30 fps |
| 2 | Increment frame counter | `frame_counter += 1` | Penghitung frame untuk skipping |
| 3 | Cek frame skipping | `frame_counter % 3` | Inferensi hanya pada frame ke-3 |
| 4 | Resize frame | `cv2.resize` | 1920×1080 → 640×640 px |
| 5 | Konversi warna | `cv2.cvtColor` | BGR → RGB |
| 6 | Inferensi YOLOv7 | PyTorch + `yolov7.pt` | Prediksi bbox + kelas + confidence |
| 7 | Non-Maximum Suppression | `non_max_suppression()` | Hapus deteksi duplikat (IoU 0.45) |
| 8 | Filter kelas | `--classes 2 3 5 7` | Hanya 4 jenis kendaraan |
| 9 | Pelacakan SORT | `sort.Sort()` | Asosiasi ID antar frame |
| 10 | Gambar anotasi | `draw_boxes()` | Bbox oranye + label putih |
| 11 | Simpan frame | `cv2.VideoWriter` | Kompilasi ke video output |

### 4.2.1 Hasil Inferensi per Kelas Kendaraan

Berdasarkan observasi visual pada seluruh cuplikan video, distribusi deteksi per kelas kendaraan:

**Tabel 4.1b Observasi Deteksi per Kelas Kendaraan**

| Kelas | Sore Hari | Malam Hari | Catatan |
|-------|-----------|------------|---------|
| Car (mobil) | Sering terdeteksi | Sering terdeteksi | Dominan di jalur mobil |
| Motorcycle (motor) | Sangat sering | Sering | Jumlah terbanyak; oklusi tinggi saat berhenti |
| Bus | Jarang muncul | Sangat jarang | Frekuensi rendah di lokasi |
| Truck (truk) | Jarang muncul | Jarang muncul | Terdeteksi saat muncul (Gambar 4.8, 4.9) |

---

## 4.3 Penerapan Tampilan

Hasil inferensi divisualisasikan berupa *bounding box* berwarna oranye dan label kelas di setiap kendaraan terdeteksi.

### 4.3.1 Hasil Sore Hari

Pada Gambar 4.4 dan 4.5, hasil anotasi sore hari menunjukkan label kelas yang tepat pada setiap *bounding box*. Model berhasil mendeteksi mobil (*car*) dan sepeda motor (*motorcycle*) yang dominan di ruas jalan tersebut. *Bounding box* mengelilingi kendaraan dengan posisi yang akurat, dan label kelas sesuai dengan jenis kendaraan yang terlihat.

**Temuan positif sore hari:**
- Deteksi akurat pada kendaraan bergerak dengan kecepatan normal.
- Label *car* dan *motorcycle* konsisten pada kendaraan yang terlihat jelas.
- Model mampu mendeteksi beberapa kendaraan secara simultan dalam satu frame (multi-object detection).

**Temuan negatif sore hari:**
- Pada area kendaraan motor yang menumpuk atau berhenti di lampu merah, model gagal mendeteksi dan melabeli beberapa objek. Hal ini disebabkan oleh **oklusi** (*occlusion*) — kendaraan saling menutupi — yang menyulitkan model mengenali objek individual.
- Beberapa motor kecil yang berada di belakang mobil besar tidak terdeteksi karena tertutup sepenuhnya.

> **Gambar 4.4 Hasil anotasi sore hari (a)**  
> *(disisipkan pada naskah final)*

> **Gambar 4.5 Hasil anotasi sore hari (b)**  
> *(disisipkan pada naskah final)*

### 4.3.2 Hasil Malam Hari

Rekaman malam hari (Gambar 4.6 dan 4.7) menunjukkan bahwa model tetap mampu menghasilkan *bounding box* dengan label yang sesuai meskipun pencahayaan lebih rendah dan bersumber dari lampu jalan.

**Temuan positif malam hari:**
- Model tetap berfungsi pada kondisi pencahayaan buatan (lampu jalan).
- Deteksi pada kendaraan bergerak tetap akurat.
- Jumlah *false positive* tidak meningkat signifikan dibandingkan sore hari.

**Temuan negatif malam hari:**
- Masalah yang sama terjadi pada kendaraan yang sedang berhenti — model gagal mendeteksi beberapa objek.
- Sorotan lampu kendaraan (headlight) kadang menyebabkan silau yang mengurangi kontras objek.
- Namun, ketika kendaraan mulai bergerak kembali, model berhasil mendeteksi dan memberikan label yang tepat.

> **Gambar 4.6 Hasil anotasi malam hari (a)**  
> *(disisipkan pada naskah final)*

> **Gambar 4.7 Hasil anotasi malam hari (b)**  
> *(disisipkan pada naskah final)*

### 4.3.3 Deteksi Bus dan Truk

Tidak semua kelas kendaraan muncul dalam setiap cuplikan video karena frekuensi bus dan truk di lokasi pengambilan data relatif rendah. Namun, ketika kendaraan tersebut muncul, model tetap mampu mendeteksinya.

Gambar 4.8 dan 4.9 menunjukkan deteksi truk (*truck*) yang berhasil pada sore dan malam hari, dengan *bounding box* dan label yang akurat. Hal ini menunjukkan bahwa model pre-trained MS COCO tidak bias hanya pada kelas yang frekuensinya tinggi — kelas langka tetap terdeteksi saat objek muncul di frame.

> **Gambar 4.8 Deteksi 'truck' pada sore hari**  
> *(disisipkan pada naskah final)*

> **Gambar 4.9 Deteksi 'truck' pada malam hari**  
> *(disisipkan pada naskah final)*

---

## 4.4 Hasil Pengujian menggunakan Metode Black Box

Pengujian dilakukan berdasarkan rancangan pada Bab 3.6. Hasil pengujian disajikan pada Tabel 4.2.

**Tabel 4.2 Hasil Pengujian Black Box Testing**

| No | Skenario Pengujian | Teknik | Input | Hasil yang Diharapkan | Hasil Aktual | Status |
|----|-------------------|--------|-------|----------------------|--------------|--------|
| 1 | Fungsi input — valid | EP | File .mp4, 1920×1080 | Video berhasil dibaca | Video terbaca dan diproses tanpa error | **Lulus** |
| 1b | Fungsi input — invalid | EP | File .avi | Pesan error | Belum diuji pada penelitian ini | **Belum diuji** |
| 2 | Fungsi parameter — kelas | EP | `--classes 2 3 5 7` | Hanya 4 kelas kendaraan | Hanya *car*, *motorcycle*, *bus*, *truck* ditampilkan | **Lulus** |
| 2b | BVA confidence — bawah | BVA | `--conf-thres 0.0` | Banyak deteksi (termasuk noise) | Deteksi sangat banyak, termasuk objek non-kendaraan sebelum filter kelas | **Lulus** |
| 2c | BVA confidence — atas | BVA | `--conf-thres 1.0` | Tidak ada deteksi | Tidak ada *bounding box* yang ditampilkan | **Lulus** |
| 3 | Visualisasi — sore | EP | `FOS_01.mp4` | Bbox oranye, label sesuai | Warna RGB(255,144,30), font 0.6, label benar | **Lulus** |
| 3b | Visualisasi — malam | EP | Video malam | Bbox dan label tetap muncul | Visualisasi konsisten dengan sore hari | **Lulus** |
| 4 | Output | EP | Video selesai diproses | File .mp4 tersimpan | File tersimpan, dapat diputar, tidak korup | **Lulus** |

Mayoritas skenario pengujian fungsional yang dieksekusi dinyatakan **lulus** (*pass*). Skenario input invalid (`.avi`) belum diuji dan direkomendasikan sebagai pekerjaan lanjutan agar cakupan EP lebih lengkap.

### 4.4.1 Hasil Pengujian Boundary Value Analysis (conf-thres)

Pengujian BVA pada parameter `conf-thres` menghasilkan perilaku yang sesuai ekspektasi:

| Nilai conf-thres | Perilaku Model | Interpretasi |
|------------------|---------------|--------------|
| 0.0 | Semua prediksi ditampilkan, sangat banyak *bounding box* termasuk noise | Batas bawah — sensitivitas maksimum |
| 0.45 | Keseimbangan antara jumlah deteksi dan akurasi — digunakan dalam penelitian | Nilai operasional |
| 0.65 | Default script — beberapa motor terlewat pada kondisi padat | Terlalu tinggi untuk lokasi ini |
| 1.0 | Tidak ada deteksi yang memenuhi ambang | Batas atas — spesifisitas maksimum |

Pemilihan nilai 0.45 dibuktikan lebih optimal daripada default 0.65 untuk kondisi lalu lintas padat di flyover Air Hitam, di mana banyak kendaraan motor memiliki skor *confidence* antara 0.45 dan 0.60.

---

## 4.5 Evaluasi Kuantitatif

### 4.5.1 Pengukuran Kecepatan Inferensi (FPS)

Kecepatan inferensi diukur dari log waktu proses pada *script* `detect_and_track.py`. Pengukuran dilakukan pada Google Colab dengan GPU T4.

**Tabel 4.3 Hasil Pengukuran FPS**

| Kondisi | Resolusi Input | conf-thres | Frame Skip | FPS Inferensi* | FPS Efektif* |
|---------|---------------|------------|------------|----------------|--------------|
| Sore hari | 640 px | 0.45 | 1:3 | — (diisi dari log eksekusi) | — (dihitung dari FPS inferensi) |
| Malam hari | 640 px | 0.45 | 1:3 | — (diisi dari log eksekusi) | — (dihitung dari FPS inferensi) |

> *Mahasiswa mengisi nilai FPS dari log `detect_and_track.py`. Contoh cara membaca log: jika t1-t0 = 0.035 detik per frame inferensi, maka FPS inferensi = 1/0.035 ≈ 28.6 FPS. FPS efektif dengan frame skip 1:3 ≈ 28.6 × 3 ≈ 85.7 FPS pemrosesan video.

**Cara mendapatkan nilai FPS:**
1. Jalankan `detect_and_track.py` pada Colab.
2. Perhatikan output log yang mencetak waktu per frame.
3. Hitung: FPS = 1 / (waktu rata-rata per frame inferensi).
4. Isi Tabel 4.3 dengan nilai aktual.

### 4.5.2 Evaluasi Visual Kuantitatif (Opsional)

Jika tersedia waktu dan sumber daya, evaluasi tambahan dapat dilakukan dengan anotasi manual *ground truth*:

**Tabel 4.4 Kerangka Evaluasi Manual (Opsional)**

| Metrik | Rumus | Cara Pengukuran |
|--------|-------|-----------------|
| Precision | TP / (TP + FP) | Annotasi manual 50–100 frame, bandingkan dengan prediksi |
| Recall | TP / (TP + FN) | Idem |
| F1-Score | 2 × (P × R) / (P + R) | Dihitung dari precision dan recall |
| mAP | Rata-rata AP semua kelas | Membutuhkan anotasi bbox manual per frame |

**Prosedur anotasi manual:**
1. Pilih 50 frame acak dari video sore dan 50 frame dari video malam.
2. Annotasi manual setiap kendaraan (bbox + label) menggunakan tools seperti LabelImg atau CVAT.
3. Bandingkan prediksi model dengan anotasi manual.
4. Hitung TP (deteksi benar), FP (deteksi salah), FN (terlewat).

---

## 4.6 Pembahasan

Penelitian ini menerapkan algoritma YOLOv7 dengan model pre-trained MS COCO (`yolov7.pt`) untuk mendeteksi dan mengklasifikasi empat jenis kendaraan — *car*, *motorcycle*, *bus*, dan *truck* — pada rekaman video lalu lintas dari flyover Air Hitam, Samarinda. Data dikumpulkan pada dua skenario: sore hari (ruas Letnan Jend. Suprapto) dan malam hari (ruas Kadrie Oening).

### 4.6.1 Performa Deteksi dan Klasifikasi

Berdasarkan evaluasi visual dan pengujian fungsional, model YOLOv7 menunjukkan kemampuan baik dalam:

1. **Deteksi kendaraan bergerak** — *bounding box* akurat dan label kelas sesuai jenis kendaraan pada kedua skenario pencahayaan. Hal ini mengkonfirmasi bahwa model pre-trained MS COCO memiliki generalisasi yang memadai untuk kondisi lalu lintas Indonesia tanpa *fine-tuning*.

2. **Ketahanan terhadap variasi pencahayaan** — model tetap berfungsi pada sore hari (pencahayaan alami) dan malam hari (lampu jalan). Temuan ini sejalan dengan Lin et al. (2021) yang melaporkan akurasi klasifikasi 99,1% siang hari dan 98,6% malam hari menggunakan YOLOv4.

3. **Deteksi kelas langka** — bus dan truk tetap terdeteksi meskipun frekuensinya rendah di lokasi pengambilan data. Model tidak mengalami *bias* terhadap kelas dominan (motor dan mobil).

4. **Sudut pandang *high angle*** — meminimalkan oklusi dan memudahkan deteksi kendaraan individual. Pemilihan lokasi flyover terbukti tepat untuk tujuan deteksi visual.

5. **Multi-object detection** — model mampu mendeteksi puluhan kendaraan dalam satu frame secara simultan, menunjukkan skalabilitas YOLOv7 pada kondisi kepadatan tinggi.

### 4.6.2 Analisis Keterbatasan

Beberapa keterbatasan yang ditemukan dan analisis penyebabnya:

**Tabel 4.5 Analisis Keterbatasan**

| Keterbatasan | Penyebab | Dampak | Solusi Potensial |
|-------------|--------|--------|-----------------|
| Kendaraan berhenti/menumpuk tidak terdeteksi | Oklusi tinggi — motor saling menutupi di lampu merah | *False negative* pada motor berhenti | Fine-tuning pada data oklusi; sudut kamera alternatif |
| Model pre-trained, bukan fine-tuned | MS COCO dilatih di konteks Barat — kendaraan lokal berbeda | Angkot, becak motor, mobil pickup tidak terdeteksi | Kumpulkan & annotasi dataset lokal |
| Tidak ada perhitungan volume | Modul `count_vehicle` dinonaktifkan | Data arus lalu lintas kuantitatif tidak tersedia | Aktifkan counting + SORT tracking |
| Evaluasi dominan kualitatif | Tidak ada ground truth annotation | mAP/precision/recall tidak dihitung | Annotasi manual 50–100 frame |
| Frame skipping 1:3 | Inferensi hanya setiap 3 frame | Deteksi kendaraan sangat cepat mungkin terlewat | Kurangi skip ratio atau gunakan GPU lebih cepat |
| Satu lokasi pengambilan data | Hanya flyover Air Hitam | Generalisasi ke lokasi lain belum teruji | Uji di beberapa simpang berbeda |

**Analisis oklusi mendalam:**

Keterbatasan utama penelitian ini terjadi pada kondisi **oklusi tinggi** — ketika kendaraan motor menumpuk di lampu merah. Pada kondisi ini:

- Motor di barisan belakang tertutup sepenuhnya oleh motor di depannya.
- Model YOLOv7 cenderung melihatnya sebagai satu klaster objek, bukan individu terpisah.
- NMS (*Non-Maximum Suppression*) menggabungkan deteksi yang tumpang tindih.
- Ketika kendaraan mulai bergerak dan oklusi berkurang, model berhasil mendeteksi kembali.

Fenomena ini konsisten dengan temuan penelitian lain: Ashraf et al. (2023) melaporkan penurunan mAP dari 91,04% (statis) menjadi 80,71% (dinamis) akibat kondisi video yang lebih kompleks. Oklusi merupakan tantangan inheren dalam deteksi objek pada video lalu lintas nyata.

### 4.6.3 Perbandingan Sore vs. Malam Hari

**Tabel 4.6 Perbandingan Performa Deteksi: Sore vs. Malam Hari**

| Aspek | Sore Hari | Malam Hari | Analisis |
|-------|-----------|------------|----------|
| Kepadatan kendaraan | Tinggi (area lampu merah) | Rendah–sedang | Sore lebih banyak objek per frame |
| Pencahayaan | Alami (matahari) | Lampu jalan | Keduanya memadai untuk deteksi |
| Jumlah deteksi per frame | Lebih banyak | Lebih sedikit | Proporsional dengan jumlah kendaraan |
| Akurasi label (visual) | Baik | Baik | Tidak ada perbedaan signifikan |
| Masalah oklusi | Sering (motor menumpuk) | Jarang | Kepadatan sore menyebabkan oklusi |
| False positive | Rendah | Rendah | Model stabil pada kedua kondisi |
| Kendaraan dominan | Motor > Mobil | Motor > Mobil | Konsisten dengan profil lalu lintas Indonesia |
| Bus/Truk terdeteksi | Ya (saat muncul) | Ya (saat muncul) | Kelas langka tetap terdeteksi |

**Kesimpulan perbandingan:** Tidak terdapat perbedaan signifikan pada kemampuan deteksi dan pelabelan antara sore dan malam hari. Perbedaan utama terletak pada **jumlah deteksi per frame** (proporsional dengan kepadatan kendaraan) dan **frekuensi oklusi** (lebih sering pada sore hari karena kepadatan tinggi). Model pre-trained YOLOv7 menunjukkan **ketahanan yang baik** terhadap variasi pencahayaan.

### 4.6.4 Implikasi Praktis

Hasil penelitian ini memiliki beberapa implikasi praktis:

1. **Kelayakan penerapan** — Model pre-trained YOLOv7 dapat langsung diterapkan pada rekaman video lalu lintas lokal tanpa pelatihan ulang, mengurangi biaya dan waktu implementasi.

2. **Kebutuhan fine-tuning** — Untuk akurasi produksi, *fine-tuning* pada dataset kendaraan Indonesia (termasuk angkot, becak motor) sangat direkomendasikan.

3. **Integrasi dengan sistem kota cerdas** — Pipeline deteksi+klasifikasi ini dapat menjadi modul dalam sistem pemantauan lalu lintas Dinas Perhubungan, terutama jika dikombinasikan dengan penghitungan volume dan estimasi kecepatan.

4. **Pemilihan lokasi kamera** — Sudut *high angle* terbukti efektif; rekomendasi untuk instalasi CCTV pemantauan lalu lintas di Samarinda.

### 4.6.5 Jawaban atas Rumusan Masalah

| Rumusan Masalah | Jawaban |
|----------------|---------|
| Bagaimana penerapan YOLOv7 pre-trained MS COCO untuk deteksi dan klasifikasi 4 jenis kendaraan? | Berhasil diterapkan melalui `detect_and_track.py` dengan parameter `--classes 2 3 5 7`, `conf-thres 0.45`, `img-size 640`. Keempat kelas kendaraan terdeteksi dan dilabeli dengan benar. |
| Bagaimana performa pada dua kondisi pencahayaan? | Model menunjukkan ketahanan baik pada sore dan malam hari. Perbedaan utama pada jumlah deteksi (proporsional kepadatan) dan frekuensi oklusi. |
| Apakah sistem memenuhi spesifikasi fungsional? | Ya — mayoritas skenario *Black Box Testing* yang dieksekusi dinyatakan lulus; satu skenario input invalid belum diuji. |

---
