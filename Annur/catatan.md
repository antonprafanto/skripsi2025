# Catatan Tanggapan: Penggantian Judul Skripsi

**Dari:** Pembimbing  
**Perihal:** Usulan ganti judul (monitoring air sumur → perangkap hama cahaya + YOLO)  
**Status sementara:** **Boleh diganti**, dengan syarat arsitektur & ruang lingkup diperjelas dulu  

---

## Baca ini dulu

Assalamualaikum. Terima kasih sudah menyampaikan alasan penggantian judul dengan jelas.

**Ringkasan keputusan:**

| Pertanyaan | Jawaban singkat |
|---|---|
| Boleh ganti judul? | **Boleh**, asal sudah dikonsultasikan & disetujui pembimbing (dan ikut prosedur prodi jika ada) |
| Topik baru layak skripsi Informatika S1? | **Layak**, jika fokusnya jelas: IoT + deteksi objek + evaluasi kinerja (bukan hanya “bikin alat”) |
| Langsung tulis ulang proposal? | **Belum.** Jawab dulu poin wajib di bawah, terutama: **di mana YOLOv5 dijalankan** dan **cara menghitung hama tanpa double-count** |

Alasan lapangan (KKN, keluhan petani, PLTS, internet, dukungan Balai Tani) sudah bagus sebagai **latar belakang**. Tapi latar belakang saja **belum cukup**. Yang ditimbang penguji: rumusan masalah, metode, batasan, cara menguji, dan kontribusi ke bidang Informatika.

### Aturan kerja sekarang

1. Kerjakan **poin wajib (P0)** dulu. Jangan loncat rakit alat besar atau tulis proposal 30 halaman.
2. Semua bagian nanti harus **saling nyambung**: rumusan ↔ tujuan ↔ batasan ↔ metode ↔ pengujian.
3. Ganti topik = **tulis ulang proposal total** (BAB I–III). Bukan hanya ganti judul di cover.
4. Kalau bingung, tanya dengan pertanyaan spesifik (ada contoh di akhir).

---

## Judul lama vs judul baru

**Judul lama (dilepas):**  
Sistem Monitoring Kualitas Air Sumur Berbasis IoT ESP32-MQTT dengan Metode Water Quality Index dan Fuzzy Logic untuk Klasifikasi Indikasi Pencemaran Limbah Domestik dan Notifikasi Telegram.

**Judul baru (diusulkan):**  
Rancang Bangun Perangkap Hama Cahaya Otomatis Berbasis ESP32-CAM dengan Algoritma YOLOv5 untuk Deteksi, Klasifikasi, dan Penghitungan Hama serta Notifikasi Telegram.

**Catatan judul:** Arahnya sudah “informatika”, tetapi masih berisiko dibaca seolah ESP32-CAM menjalankan YOLOv5. Judul final menyesuaikan arsitektur. Kata **“otomatis”** juga harus jelas: otomatis apa (jadwal lampu? capture? deteksi? notifikasi?).

---

## Yang sudah baik dari usulanmu

1. **Masalah nyata** di lokasi KKN/Balai Tani — mudah dijelaskan di BAB I.
2. **Infrastruktur mendukung** (PLTS + internet) — mengurangi risiko alat tidak jalan.
3. **Ada mitra** (dukungan pendanaan Balai Pertanian) — bagus untuk implementasi & uji lapangan.
4. **Ada unsur komputasi** (deteksi, klasifikasi, counting) — ini yang membuat topik pantas skripsi Informatika.
5. **Ada luaran terukur** (jumlah hama, ambang batas, notifikasi Telegram) — cocok untuk pengujian.

Simpan empat poin di atas. Yang diperbaiki: teknis, ruang lingkup, dan klaim ilmiah.

---

## Yang TIDAK perlu dikerjakan dulu

Supaya tidak melebar, **jangan** menambah ini sebelum arsitektur & proposal disetujui:

- aplikasi mobile / Flutter / Android
- dashboard web yang rumit (cukup Telegram dulu, kecuali sangat sederhana)
- terlalu banyak kelas hama (di atas 4 kelas di awal)
- klaim “alat ini berhasil menurunkan serangan hama / meningkatkan hasil panen” tanpa desain eksperimen pertanian
- perbandingan banyak model sekaligus (YOLOv5 vs v7 vs v8 vs v11) di tahap awal
- fitur otomatisasi berlebihan (robot, servo, AI chatbot, dsb.)

Fokus sekarang: **arsitektur realistis + deteksi/counting yang bisa diuji + batasan jelas**.

---

## Poin wajib P0 (harus dipahami sebelum lanjut)

### 1. ESP32-CAM hampir pasti **tidak bisa** menjalankan YOLOv5 sendiri

Ini poin paling penting.

| Perangkat | Kemampuan kasar | Cocok untuk YOLO? |
|---|---|---|
| ESP32-CAM | Ambil gambar, kirim via WiFi, sumber daya sangat terbatas | **Tidak cocok** menjalankan YOLOv5 penuh |
| Raspberry Pi / PC / laptop / server / cloud | Proses inference model YOLO | **Cocok** |
| ESP32-CAM + model sangat ringan (TinyML) | Mungkin, tapi itu **bukan YOLOv5 biasa** | Perlu penyesuaian besar + judul diganti |

Penguji akan bertanya: **“YOLOv5-nya dijalankan di mana?”**

Pilih salah satu:

**Skenario A (disarankan untuk S1):**  
ESP32-CAM = kamera + pengirim gambar → Raspberry Pi / PC mini menjalankan YOLOv5 → hasil ke Telegram.

**Skenario B:**  
Inference di cloud setelah gambar diunggah → hasil notifikasi Telegram.

**Skenario C (lebih sulit):**  
Model sangat ringan di edge (bukan YOLOv5 penuh). Jika ini, **jangan pakai nama YOLOv5 di judul** kecuali benar-benar YOLOv5 yang berhasil dijalankan.

**Tugas:** pilih skenario, sesuaikan judul + metodologi agar konsisten.

---

### 2. Penghitungan hama mudah salah jika tidak dirancang

Judulmu menyebut **penghitungan**. Ini sering jadi titik lemah.

Masalah khas:
- foto diambil berkali-kali → **hama yang sama dihitung berulang** (double counting);
- serangga bergerak cepat / blur;
- serangga mati menempel lama di perangkap.

Kamu harus tentukan strategi, contoh:

| Strategi | Ide singkat | Cocok jika |
|---|---|---|
| Sampling berkala | Ambil 1 foto tiap N menit, hitung objek di foto itu (bukan “total sepanjang malam” tanpa aturan) | Ingin sederhana di S1 |
| Window waktu | Hitung “jumlah terdeteksi per jam” dari frame sampel | Mau tren populasi kasar |
| Tracking (SORT/ByteTrack) | Lacak ID objek antar frame agar tidak double-count | Lebih kuat, lebih sulit |

Di proposal wajib ada jawaban:
1. counting dihitung sebagai apa? (per foto / per jam / per malam)
2. bagaimana mengurangi double-count?
3. **ground truth** lapangan bagaimana? (mis. hitung manual dari foto uji / dari tangkapan fisik di perangkap)

Tanpa ini, klaim “penghitungan” mudah digoyang di sidang.

---

### 3. Skripsi Informatika ≠ hanya merakit perangkap hama

Penguji menilai kontribusi **sistem/algoritma**, misalnya:

- akurasi deteksi & klasifikasi (precision, recall, mAP, F1);
- kesalahan counting vs ground truth (MAE / % error);
- latensi (tangkap gambar → hasil → Telegram);
- false alarm notifikasi;
- uji kondisi malam / jarak kamera / intensitas lampu, jika relevan.

**Batasan klaim penting:**  
Boleh bilang sistem **membantu monitoring** populasi hama di perangkap.  
**Jangan** mengklaim sebagai bukti ilmiah bahwa alat “berhasil memberantas hama” atau “meningkatkan panen”, kecuali ada desain eksperimen pertanian yang terpisah dan disetujui. Itu ranah berbeda.

Pastikan inti skripsi: **deteksi–klasifikasi–counting–notifikasi + evaluasi**.

---

### 4. Ruang lingkup harus diperkecil sejak awal

| Aspek | Contoh batasan yang wajar |
|---|---|
| Jenis hama | 2–4 kelas hama utama di lokasi (sebutkan nama) |
| Non-hama | Apakah ada kelas “other”, atau diabaikan? |
| Lokasi uji | Balai Tani ECO-STEP / lahan tertentu |
| Waktu uji | mis. malam hari selama X malam |
| Sampling | foto setiap … menit |
| Dataset | target jumlah gambar train/valid/test |
| Fungsi perangkap | alat bantu mengumpulkan hama ke area kamera |
| Ambang notifikasi | > N deteksi / jam (angka jelas) |
| Varian model | mis. YOLOv5n atau YOLOv5s + alasan |

Tanpa batasan ini, proposal terbaca terlalu ambisius.

---

### 5. Dataset, labeling, dan kualitas gambar malam

YOLOv5 butuh data beranotasi (bounding box + class). Siapkan:

1. Sumber gambar (perangkap lapangan / setup uji)?
2. Target jumlah per kelas?
3. Tool labeling (Roboflow, LabelImg, dll.)?
4. Augmentasi?
5. Split train/valid/test?
6. **Rencana foto malam:** pencahayaan, jarak kamera–lampu, cegah blur/silau?

ESP32-CAM sering menghasilkan gambar malam yang sulit. Kalau input buruk, model bagus sekalipun hasilnya jelek.

---

### 6. Diferensiasi: kenapa penelitianmu bukan “YOLO hama biasa”?

Paper deteksi hama dengan YOLO sudah banyak. Di proposal wajib tulis **beda penelitianmu**, contoh kombinasi yang masuk akal:

- integrasi perangkap cahaya + ESP32-CAM + pipeline notifikasi Telegram di lokasi Balai Tani;
- fokus counting + ambang peringatan (bukan hanya deteksi);
- kelas hama spesifik lokasi + uji lapangan malam hari;
- evaluasi end-to-end (akurasi model + kinerja sistem notifikasi).

Jangan hanya mengandalkan “belum ada di lokasi X”. Itu terlalu tipis.

---

### 7. Dukungan dana mitra ≠ otomatis lolos akademik

Dukungan Balai Pertanian membantu **implementasi**. Proposal/skripsi tetap harus kuat di rumusan, tinjauan pustaka, metode, metrik, dan pembahasan.

Simpan bukti dukungan (surat/WA resmi) untuk lampiran. Tetap urus izin lokasi penelitian.

---

## Contoh arah rumusan, tujuan, dan variabel (boleh disusun ulang)

Supaya BAB I nyambung, arahnya kurang lebih seperti ini:

**Contoh rumusan masalah**
1. Bagaimana merancang sistem deteksi dan klasifikasi hama pada perangkap cahaya menggunakan ESP32-CAM dan YOLOv5?
2. Bagaimana sistem menghitung jumlah hama terdeteksi secara berkala tanpa double counting yang berlebihan?
3. Bagaimana kinerja sistem (mAP / precision-recall / error counting / latensi notifikasi) pada uji lapangan?

**Contoh tujuan**
1. Membangun prototype sistem capture → inference YOLOv5 → notifikasi Telegram.
2. Mengevaluasi kinerja deteksi/klasifikasi pada kelas hama yang ditentukan.
3. Mengevaluasi akurasi penghitungan dibanding ground truth dan menguji notifikasi ambang batas.

**Contoh variabel**
- X: sistem deteksi berbasis YOLOv5 pada citra perangkap hama (plus parameter sampling/threshold).
- Y: kinerja deteksi (mAP/F1), error penghitungan, dan keberhasilan/ketepatan notifikasi.

Sesuaikan setelah arsitektur final dipilih.

---

## Keputusan pembimbing (sementara)

**Ya, topik ini layak diarahkan sebagai skripsi**, dengan kondisi:

1. Arsitektur jelas (ESP32-CAM biasanya hanya kamera/pengirim; YOLOv5 di perangkat lain — kecuali kamu bukti sebaliknya).
2. Fokus = deteksi + klasifikasi + penghitungan + notifikasi, dibuktikan metrik.
3. Ada strategi counting + ground truth.
4. Batasan kelas hama, lokasi, sampling, dataset ditulis sejak proposal.
5. Tidak overclaim hasil pertanian.
6. Judul jujur terhadap arsitektur.
7. Proposal lama diganti menyeluruh (BAB I–III).

Setelah kamu jawab tertulis, kita rapikan judul final & outline proposal baru.

---

## Checklist sebelum menulis ulang proposal

### A. Keputusan teknis (P0)
- [ ] Skenario A / B / C dipilih: __________
- [ ] Diagram blok sistem sudah digambar
- [ ] YOLOv5 dijalankan di: __________
- [ ] Varian model (mis. YOLOv5n/s): __________
- [ ] Interval pengambilan gambar: tiap ____ detik/menit
- [ ] Strategi counting + anti double-count: __________
- [ ] Cara ground truth counting: __________

### B. Objek penelitian (P0)
- [ ] 2–4 kelas hama + alasan (wawancara/observasi/pustaka)
- [ ] Kebijakan untuk serangga non-hama
- [ ] Ambang notifikasi (angka + satuan waktu)

### C. Data & evaluasi (P0)
- [ ] Target jumlah gambar per kelas
- [ ] Cara labeling
- [ ] Metrik: mAP / precision / recall / F1 / error counting / latensi Telegram
- [ ] Baseline: minimal bandingkan vs hitung manual (ground truth)
- [ ] Skenario uji lapangan (berapa malam, jam, lokasi)
- [ ] Catatan risiko kualitas gambar malam

### D. Administratif
- [ ] Konfirmasi penggantian judul ke pembimbing
- [ ] Cek prosedur prodi (form ganti judul / usulan judul)
- [ ] Simpan bukti dukungan Balai Tani + rencana izin lokasi

---

## Saran arah judul (belum final)

**Lebih aman (eksplisit sistem deteksi, tidak menyesatkan):**  
> Rancang Bangun Sistem Deteksi dan Penghitungan Hama pada Perangkap Cahaya Menggunakan ESP32-CAM dan YOLOv5 dengan Notifikasi Telegram

**Jika inference di Raspberry Pi (disarankan ditulis di isi, opsional di judul):**  
> Rancang Bangun Sistem Monitoring Hama pada Perangkap Cahaya Berbasis ESP32-CAM dan YOLOv5 dengan Notifikasi Telegram

Intinya: jangan memberi kesan ESP32-CAM “menjalankan” YOLOv5, kecuali itu benar.

---

## Yang harus kamu kirim ke pembimbing minggu ini

Kirim **1–2 halaman** berisi:

1. Judul usulan (versi terbaru)
2. Diagram blok arsitektur
3. Jawaban: YOLOv5 dijalankan di mana? Varian apa?
4. Interval sampling gambar
5. Strategi counting + anti double-count + ground truth
6. Daftar 2–4 kelas hama + alasan
7. Rencana dataset (jumlah kasar)
8. Metrik keberhasilan + baseline
9. Batasan masalah (5–8 poin)
10. Jadwal bulanan realistis sampai sidang
11. Satu paragraf: **apa bedanya** penelitianmu dari deteksi hama YOLO pada umumnya

Kalau poin di atas sudah jelas, baru lanjut proposal lengkap.

### Template jawaban cepat (boleh ditiru)

```text
Skenario: A
Perangkat kamera: ESP32-CAM
Inference: Raspberry Pi 4, YOLOv5s
Sampling: 1 foto / 5 menit
Counting: jumlah objek terdeteksi per jam dari foto sampel
Anti double-count: tidak menjumlah antar-frame kontinyu; agregasi per window waktu
Ground truth: hitung manual pada 100 foto uji + sampel fisik perangkap pada N malam
Kelas: (1) ..., (2) ..., (3) ...
Threshold Telegram: > 20 deteksi/jam
Metrik: mAP@0.5, precision, recall, MAE counting, latensi notifikasi
```

---

## Contoh pertanyaan ke pembimbing

1. “Pak, ESP32-CAM hanya capture + kirim, YOLOv5s di Raspberry Pi 4. Disetujui?”
2. “Untuk S1, 3 kelas hama + mAP + MAE counting 7 malam cukup?”
3. “Counting saya agregasi per jam dari foto tiap 5 menit (tanpa tracking). Apakah diterima?”
4. “Apakah judul perlu menyebut Raspberry Pi, atau cukup ESP32-CAM + YOLOv5?”
5. “Target dataset awal berapa gambar per kelas sebelum fine-tuning?”

---

## Pesan penutup

Topiknya **menarik dan relevan** (masalah lapangan + dukungan mitra). Modal itu bagus.

Yang harus diluruskan sekarang:
1. arsitektur teknis masuk akal (YOLO tidak “di dalam” ESP32-CAM kecuali terbukti);
2. counting dirancang agar tidak double-count;
3. klaim tetap di ranah monitoring/informatika, bukan overclaim pertanian;
4. ada diferensiasi jelas dari paper YOLO hama lain.

Kerjakan checklist P0, kirim jawaban 1–2 halaman, lalu kita bedah untuk finalisasi judul dan kerangka proposal baru.

Semangat. Diskusikan ulang jika ada bagian yang masih membingungkan.
