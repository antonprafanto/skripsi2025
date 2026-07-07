# BAB V — KESIMPULAN DAN SARAN

---

## 5.1 Kesimpulan

Berdasarkan penelitian mengenai klasifikasi jenis kendaraan menggunakan algoritma YOLOv7 pada rekaman video lalu lintas di simpang flyover Air Hitam, Samarinda, dapat disimpulkan sebagai berikut:

1. **Penerapan YOLOv7 berhasil dilakukan.** Model YOLOv7 dengan pre-trained weight MS COCO (`yolov7.pt`) berhasil mendeteksi dan mengklasifikasi empat jenis kendaraan — mobil (*car*), sepeda motor (*motorcycle*), bus, dan truk (*truck*) — pada rekaman video lalu lintas. Implementasi dilakukan melalui *script* `detect_and_track.py` dengan parameter `--classes 2 3 5 7`, `--conf-thres 0.45`, dan `--img-size 640`.

2. **Model menunjukkan ketahanan terhadap variasi pencahayaan.** Hasil deteksi pada kedua skenario — sore hari (ruas Letnan Jend. Suprapto) dan malam hari (ruas Kadrie Oening) — menunjukkan *bounding box* yang akurat dan label kelas yang tepat. Tidak terdapat perbedaan signifikan pada kemampuan deteksi dan pelabelan antara kedua kondisi pencahayaan, meskipun jumlah deteksi per frame berbeda sesuai kepadatan kendaraan.

3. **Sistem memenuhi spesifikasi fungsional.** Mayoritas skenario pengujian *Black Box Testing* yang dieksekusi — meliputi fungsi input valid, fungsi parameter (termasuk BVA pada `conf-thres`), visualisasi, dan output — dinyatakan **lulus** sesuai spesifikasi yang ditetapkan pada Bab III.

**Keterbatasan utama** yang ditemukan adalah pada kondisi oklusi tinggi (kendaraan motor menumpuk/berhenti di lampu merah), di mana model gagal mendeteksi beberapa objek. Keterbatasan ini bukan disebabkan oleh variasi pencahayaan, melainkan oleh kendaraan yang saling menutupi. Ketika kendaraan kembali bergerak dan oklusi berkurang, model berhasil mendeteksi kembali dengan label yang sesuai.

---

## 5.2 Saran

Berdasarkan hasil penelitian dan keterbatasan yang ditemukan, saran untuk penelitian selanjutnya adalah:

1. **Menambahkan perhitungan volume kendaraan.** Mengaktifkan dan mengembangkan modul penghitungan (`count_vehicle`) yang sudah tersedia di *script* `detect_count_and_track.py`, dikombinasikan dengan pelacakan SORT dan *Virtual Detection Line*, sehingga data arus lalu lintas per jenis kendaraan dapat diperoleh secara otomatis. Hal ini menjawab kebutuhan awal yang disebutkan di latar belakang mengenai penggantian metode penghitungan manual.

2. **Melakukan fine-tuning pada dataset lokal.** Mengumpulkan dan menganotasi gambar kendaraan di Samarinda — termasuk angkot, becak motor, mobil pickup, dan kendaraan khas lokal lainnya — untuk melatih ulang model YOLOv7. Fine-tuning diharapkan meningkatkan akurasi deteksi pada kondisi lalu lintas Indonesia dan mengurangi *false negative* akibat perbedaan domain MS COCO.

3. **Menambahkan evaluasi kuantitatif.** Melakukan anotasi manual (*ground truth*) pada minimal 100 frame (50 sore + 50 malam) untuk menghitung metrik precision, recall, F1-score, dan mAP. Evaluasi kuantitatif akan memberikan ukuran objektif performa model yang melengkapi evaluasi visual yang dilakukan dalam penelitian ini.

4. **Menguji pada kondisi dan lokasi berbeda.** Memperluas pengujian ke simpang lain di Samarinda, kondisi cuaca berbeda (hujan, berkabut), dan sudut kamera alternatif (horizontal CCTV) untuk menilai generalisasi model dan mengidentifikasi konfigurasi kamera optimal.

5. **Membandingkan versi YOLO terbaru.** Membandingkan performa YOLOv7 dengan versi lebih baru (YOLOv8, YOLOv9, YOLOv11) pada dataset dan kondisi yang sama, mengukur peningkatan akurasi, kecepatan inferensi (FPS), dan kebutuhan sumber daya komputasi.

6. **Mengembangkan antarmuka pengguna (GUI).** Membangun aplikasi berbasis web (misalnya menggunakan Streamlit atau Flask) atau desktop agar sistem deteksi dapat digunakan oleh operator Dinas Perhubungan tanpa perlu menjalankan *script* Python secara manual di terminal.

---
