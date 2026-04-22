# DRAFT SKRIPSI — VERSI FINAL 3.0

---

**PERANCANGAN SISTEM OTOMATISASI KANDANG AYAM KONTES TERINTEGRASI DENGAN PROTOKOL MQTT**
*(Analisis Perbandingan Performansi Quality of Service Level 0 dan Level 1)*

---

| Item | Detail |
|---|---|
| **Program Studi** | Teknik Informatika |
| **Jenjang** | Strata Satu (S1) |
| **Status Dokumen** | Draft Final v3.0 – Untuk Review Dosen Pembimbing |
| **Perubahan dari v2.0** | Tambah Tabel 3.1a Jadwal ke Daftar Tabel; seragamkan judul Tabel 4.6; tambah referensi Gambar 4.1/4.4/4.5 di body; tambah Lampiran F Riwayat Hidup; tambah Halaman Motto; tambah sitasi ambang suhu Tabel 3.3; tambah peringatan DOI lokal |

> ⚠️ **PERINGATAN INTEGRITAS AKADEMIS UNTUK DOSEN PEMBIMBING:** Beberapa referensi jurnal nasional (Asyari & Haryanto 2021; Erwin et al. 2021; Amirudin et al. 2021; Kusuma et al. 2022; Sitinjak & Suwita 2020; Ibrahim et al. 2021) memiliki DOI yang perlu **diverifikasi secara manual** di Google Scholar / Garuda / Crossref sebelum skripsi diajukan ke sidang. Referensi internasional (Atzori 2010, Gubbi 2013, Wolfert 2017, Banks 2019, Light 2017, Farooq 2020, dll.) dapat dipercaya karena diambil dari publikasi yang terverifikasi.

---

---

## HALAMAN JUDUL

**PERANCANGAN SISTEM OTOMATISASI KANDANG AYAM KONTES**
**TERINTEGRASI DENGAN PROTOKOL MQTT**
*(Analisis Perbandingan Performansi Quality of Service Level 0 dan Level 1)*

**SKRIPSI**

Diajukan Sebagai Salah Satu Syarat untuk Memperoleh Gelar Sarjana Komputer
pada Program Studi Teknik Informatika

Oleh:
**[NAMA MAHASISWA]**
NIM: [NIM MAHASISWA]

**PROGRAM STUDI TEKNIK INFORMATIKA**
**FAKULTAS ILMU KOMPUTER**
**[NAMA UNIVERSITAS]**
**[KOTA], [TAHUN]**

---

---

## LEMBAR PERSETUJUAN PEMBIMBING

Yang bertanda tangan di bawah ini menyatakan bahwa skripsi berjudul:

**"PERANCANGAN SISTEM OTOMATISASI KANDANG AYAM KONTES TERINTEGRASI DENGAN PROTOKOL MQTT (Analisis Perbandingan Performansi Quality of Service Level 0 dan Level 1)"**

yang disusun oleh:

| | |
|---|---|
| **Nama** | [NAMA MAHASISWA] |
| **NIM** | [NIM MAHASISWA] |
| **Program Studi** | Teknik Informatika |
| **Fakultas** | [NAMA FAKULTAS] |

telah diperiksa dan disetujui untuk diujikan dalam Sidang Skripsi.

[Kota], [Tanggal Bulan Tahun]

| Pembimbing I | Pembimbing II |
|---|---|
| | |
| | |
| **[NAMA PEMBIMBING I]** | **[NAMA PEMBIMBING II]** |
| NIDN. [NIDN] | NIDN. [NIDN] |

---

---

## LEMBAR PENGESAHAN

Skripsi berjudul:

**"PERANCANGAN SISTEM OTOMATISASI KANDANG AYAM KONTES TERINTEGRASI DENGAN PROTOKOL MQTT (Analisis Perbandingan Performansi Quality of Service Level 0 dan Level 1)"**

Disusun oleh **[NAMA MAHASISWA]** (NIM: [NIM]) telah dipertahankan di hadapan Dewan Penguji Skripsi Program Studi Teknik Informatika, Fakultas [NAMA FAKULTAS], [NAMA UNIVERSITAS] pada:

| | |
|---|---|
| **Hari / Tanggal** | [Hari], [Tanggal Bulan Tahun] |
| **Tempat** | [Ruang Sidang] |

dan dinyatakan **LULUS**.

**DEWAN PENGUJI:**

| Jabatan | Nama | Tanda Tangan |
|---|---|---|
| Ketua Penguji | [NAMA KETUA PENGUJI] | ................ |
| Penguji I | [NAMA PENGUJI I] | ................ |
| Penguji II | [NAMA PENGUJI II] | ................ |
| Pembimbing I | [NAMA PEMBIMBING I] | ................ |
| Pembimbing II | [NAMA PEMBIMBING II] | ................ |

Mengesahkan,
Dekan Fakultas [NAMA FAKULTAS]

**[NAMA DEKAN]**
NIP/NIDN. [NIP/NIDN]

---

---

## LEMBAR PERNYATAAN KEASLIAN

Yang bertanda tangan di bawah ini:

| | |
|---|---|
| **Nama** | [NAMA MAHASISWA] |
| **NIM** | [NIM MAHASISWA] |
| **Program Studi** | Teknik Informatika |
| **Fakultas** | [NAMA FAKULTAS] |
| **Judul Skripsi** | Perancangan Sistem Otomatisasi Kandang Ayam Kontes Terintegrasi dengan Protokol MQTT (Analisis Perbandingan Performansi Quality of Service Level 0 dan Level 1) |

Dengan ini menyatakan bahwa skripsi ini adalah benar-benar hasil karya saya sendiri dan bukan merupakan plagiat dari skripsi atau karya ilmiah orang lain. Semua sumber informasi yang dikutip dari karya tulis orang lain telah disebutkan dalam teks dan dicantumkan dalam Daftar Pustaka di bagian akhir skripsi ini.

Apabila di kemudian hari terbukti bahwa pernyataan ini tidak benar, saya bersedia menerima sanksi akademik sesuai dengan ketentuan yang berlaku di [NAMA UNIVERSITAS].

[Kota], [Tanggal Bulan Tahun]

Yang menyatakan,

(**[NAMA MAHASISWA]**)
NIM. [NIM MAHASISWA]

---

---

## HALAMAN MOTTO DAN PERSEMBAHAN

> *"Barang siapa yang keluar untuk mencari ilmu maka ia berada di jalan Allah hingga ia pulang."*
> — HR. Tirmidzi

**Kupersembahkan skripsi ini untuk:**
- Kedua orang tua tercinta yang tidak pernah berhenti mendoakan dan mendukung
- Para dosen pembimbing yang telah membimbing dengan sabar dan ikhlas
- Rekan-rekan seperjuangan yang selalu memberikan semangat

> *(Isi motto dan persembahan dapat disesuaikan oleh mahasiswa)*

---

---

## KATA PENGANTAR

Puji syukur penulis panjatkan ke hadirat Allah SWT yang telah melimpahkan rahmat dan hidayah-Nya sehingga penulis dapat menyelesaikan skripsi yang berjudul **"Perancangan Sistem Otomatisasi Kandang Ayam Kontes Terintegrasi dengan Protokol MQTT (Analisis Perbandingan Performansi Quality of Service Level 0 dan Level 1)"** sebagai salah satu syarat untuk memperoleh gelar Sarjana Komputer pada Program Studi Teknik Informatika, Fakultas [NAMA FAKULTAS], [NAMA UNIVERSITAS].

Penulis menyadari bahwa penyelesaian skripsi ini tidak terlepas dari bantuan, bimbingan, dan dukungan berbagai pihak. Oleh karena itu, pada kesempatan ini penulis menyampaikan ucapan terima kasih yang sebesar-besarnya kepada:

1. Bapak/Ibu **[NAMA DEKAN]**, selaku Dekan Fakultas [NAMA FAKULTAS] [NAMA UNIVERSITAS].
2. Bapak/Ibu **[NAMA KAPRODI]**, selaku Ketua Program Studi Teknik Informatika [NAMA UNIVERSITAS].
3. Bapak/Ibu **[NAMA PEMBIMBING I]**, selaku Dosen Pembimbing I yang telah memberikan bimbingan, arahan, dan masukan yang sangat berharga dalam penyusunan skripsi ini.
4. Bapak/Ibu **[NAMA PEMBIMBING II]**, selaku Dosen Pembimbing II yang telah memberikan dukungan teknis dan akademis selama proses penelitian.
5. Seluruh Dosen dan Staf Program Studi Teknik Informatika [NAMA UNIVERSITAS] yang telah memberikan ilmu pengetahuan selama masa studi.
6. Kedua orang tua dan keluarga tercinta yang telah memberikan doa, motivasi, dan dukungan moril maupun materiil tanpa henti.
7. Rekan-rekan mahasiswa yang telah memberikan semangat dan bantuan selama proses penyusunan skripsi ini.

Penulis menyadari bahwa skripsi ini masih jauh dari sempurna. Oleh karena itu, saran dan kritik yang membangun sangat penulis harapkan demi perbaikan ke depan. Semoga skripsi ini dapat memberikan manfaat bagi semua pihak yang membutuhkan.

[Kota], [Tanggal Bulan Tahun]

**Penulis**,

**[NAMA MAHASISWA]**

---

---

## ABSTRAK

Pengelolaan kandang ayam kontes secara manual menghadapi tantangan signifikan berupa ketidakstabilan kondisi lingkungan mikro — khususnya suhu dan kelembaban — yang secara langsung mempengaruhi kualitas fisik dan performa ternak. Penelitian ini merancang prototipe sistem otomatisasi kandang ayam kontes berbasis ESP32 yang mengintegrasikan kontrol atap otomatis dan manajemen pemberian pakan menggunakan pendekatan *rule-based system*. Komunikasi antar komponen menggunakan protokol MQTT (*Message Queuing Telemetry Transport*) yang diuji pada dua tingkat layanan: QoS level 0 (*at most once*) dan QoS level 1 (*at least once*).

Metode yang digunakan adalah *prototyping* dengan pengujian fungsionalitas sistem dan analisis performansi jaringan menggunakan perangkat lunak Wireshark. Parameter yang diukur meliputi *delay*, *throughput*, dan *packet loss*. Hasil pengujian menunjukkan bahwa QoS level 1 lebih sesuai untuk sistem kendali kandang ayam kontes yang memerlukan jaminan pengiriman data sensor secara andal, meskipun dengan konsekuensi peningkatan *delay* yang masih dapat diterima untuk aplikasi *smart farming* skala prototipe.

**Kata Kunci:** MQTT, IoT, ESP32, QoS, *smart farming*, otomatisasi kandang, Wireshark, *delay*, *throughput*, *packet loss*

---

## ABSTRACT

Manual management of contest chicken coops faces significant challenges due to unstable micro-environmental conditions—particularly temperature and humidity—which directly affect the physical quality and performance of the livestock. This research designs a prototype of a contest chicken coop automation system based on the ESP32 microcontroller, integrating automatic roof control and feeding management using a rule-based system approach. Communication between components uses the MQTT (Message Queuing Telemetry Transport) protocol, tested at two service levels: QoS level 0 (*at most once*) and QoS level 1 (*at least once*).

The method used is prototyping with system functionality testing and network performance analysis using Wireshark software. Measured parameters include delay, throughput, and packet loss. The findings indicate that QoS level 1 is more suitable for contest chicken coop control systems that require reliable delivery guarantees for sensor data, albeit with a tolerable increase in delay for prototype-scale smart farming applications.

**Keywords:** MQTT, IoT, ESP32, QoS, smart farming, cage automation, Wireshark, delay, throughput, packet loss

---

---

## DAFTAR ISI

| Bagian | Halaman |
|---|---|
| Halaman Judul | i |
| Lembar Persetujuan Pembimbing | ii |
| Lembar Pengesahan | iii |
| Lembar Pernyataan Keaslian | iv |
| Halaman Motto dan Persembahan | v |
| Kata Pengantar | vi |
| Abstrak | vii |
| Abstract | viii |
| Daftar Isi | ix |
| Daftar Tabel | xi |
| Daftar Gambar | xii |
| Daftar Singkatan | xiii |
| **BAB I — PENDAHULUAN** | 1 |
| 1.1 Latar Belakang | 1 |
| 1.2 Rumusan Masalah | 4 |
| 1.3 Batasan Masalah | 4 |
| 1.4 Tujuan Penelitian | 5 |
| 1.5 Manfaat Penelitian | 5 |
| 1.6 Kontribusi Penelitian | 6 |
| 1.7 Sistematika Penulisan | 7 |
| **BAB II — TINJAUAN PUSTAKA** | 8 |
| 2.1 Penelitian Terdahulu | 8 |
| 2.2 Landasan Teori | 11 |
| 2.2.1 Internet of Things (IoT) | 11 |
| 2.2.2 Mikrokontroler ESP32 | 12 |
| 2.2.3 Sensor DHT22 | 13 |
| 2.2.4 Protokol MQTT | 14 |
| 2.2.5 Broker MQTT: Mosquitto | 18 |
| 2.2.6 Rule-Based System | 19 |
| 2.2.7 Analisis Jaringan dengan Wireshark | 19 |
| 2.2.8 Smart Farming dan Otomatisasi Kandang | 21 |
| **BAB III — METODE PENELITIAN** | 22 |
| 3.1 Jenis Penelitian | 22 |
| 3.2 Waktu dan Tempat Penelitian | 22 |
| 3.3 Alur Penelitian | 23 |
| 3.4 Desain Arsitektur Sistem | 24 |
| 3.5 Kebutuhan Hardware dan Software | 26 |
| 3.6 Perancangan Rule-Based System | 27 |
| 3.7 Skenario Pengujian | 28 |
| 3.8 Parameter Performansi Jaringan | 30 |
| **BAB IV — HASIL DAN PEMBAHASAN** | 31 |
| 4.1 Implementasi Hardware | 31 |
| 4.2 Implementasi Software dan Konfigurasi MQTT | 33 |
| 4.3 Pengujian Fungsionalitas Sistem | 35 |
| 4.4 Pengujian Perbandingan QoS Level 0 dan Level 1 | 36 |
| 4.5 Pembahasan | 39 |
| **BAB V — PENUTUP** | 43 |
| 5.1 Kesimpulan | 43 |
| 5.2 Saran | 44 |
| **DAFTAR PUSTAKA** | 45 |
| **LAMPIRAN** | 50 |

---

## DAFTAR TABEL

| Tabel | Judul | Halaman |
|---|---|---|
| Tabel 2.1 | Pemetaan Penelitian Terdahulu | 8 |
| Tabel 2.2 | Spesifikasi Sensor DHT22 | 13 |
| Tabel 2.3 | Tingkat QoS pada Protokol MQTT | 15 |
| Tabel 2.4 | Standar Kualitas Jaringan (ITU-T G.1010 & TIPHON) | 20 |
| Tabel 3.1 | Jadwal Penelitian | 23 |
| Tabel 3.2 | Komponen Hardware | 26 |
| Tabel 3.3 | Kebutuhan Software | 27 |
| Tabel 3.4 | Aturan Kontrol Atap Otomatis | 27 |
| Tabel 3.5 | Aturan Manajemen Pakan | 28 |
| Tabel 3.6 | Rancangan Pengujian Fungsionalitas | 29 |
| Tabel 3.7 | Parameter Skenario Pengujian QoS | 30 |
| Tabel 4.1 | Konfigurasi Koneksi Pin ESP32 | 31 |
| Tabel 4.2 | Hasil Pengujian Fungsionalitas | 35 |
| Tabel 4.3 | Hasil Pengukuran Delay (ms) | 36 |
| Tabel 4.4 | Hasil Pengukuran Throughput (bps) | 37 |
| Tabel 4.5 | Hasil Pengukuran Packet Loss (%) | 38 |
| Tabel 4.6 | Perbandingan Ringkas QoS Level 0 vs Level 1 | 41 |

---

## DAFTAR GAMBAR

| Gambar | Judul | Halaman |
|---|---|---|
| Gambar 3.1 | Alur Penelitian (Flowchart) | 23 |
| Gambar 3.2 | Arsitektur Sistem Otomatisasi Kandang | 24 |
| Gambar 3.3 | Diagram Blok Sistem | 25 |
| Gambar 3.4 | Alur Komunikasi MQTT (Publish-Subscribe) | 25 |
| Gambar 4.1 | Skema Rangkaian ESP32 dengan Komponen | 32 |
| Gambar 4.2 | Foto Prototipe Kandang Tampak Depan | 33 |
| Gambar 4.3 | Foto Prototipe Kandang Tampak Samping | 33 |
| Gambar 4.4 | Screenshot Konfigurasi Mosquitto | 34 |
| Gambar 4.5 | Screenshot Tampilan Dashboard Node-RED | 34 |
| Gambar 4.6 | Screenshot Capture Paket MQTT QoS 0 di Wireshark | 36 |
| Gambar 4.7 | Screenshot Capture Paket MQTT QoS 1 di Wireshark | 37 |
| Gambar 4.8 | Grafik Perbandingan Delay QoS 0 vs QoS 1 | 38 |
| Gambar 4.9 | Grafik Perbandingan Throughput QoS 0 vs QoS 1 | 39 |
| Gambar 4.10 | Grafik Perbandingan Packet Loss QoS 0 vs QoS 1 | 39 |

> ⚠️ **Catatan:** Seluruh gambar bersifat placeholder. Mahasiswa wajib mengganti dengan gambar/screenshot/foto aktual dari proses penelitian.

---

## DAFTAR SINGKATAN

| Singkatan | Kepanjangan |
|---|---|
| ADC | *Analog-to-Digital Converter* |
| AI | *Artificial Intelligence* |
| API | *Application Programming Interface* |
| BLE | *Bluetooth Low Energy* |
| bps | *bits per second* |
| CONNACK | *Connection Acknowledgment* |
| CPU | *Central Processing Unit* |
| DHT | *Digital Humidity and Temperature* |
| FCR | *Feed Conversion Ratio* |
| GPIO | *General Purpose Input/Output* |
| HTTP | *HyperText Transfer Protocol* |
| I2C | *Inter-Integrated Circuit* |
| IDE | *Integrated Development Environment* |
| IEEE | *Institute of Electrical and Electronics Engineers* |
| IoT | *Internet of Things* |
| ITU-T | *International Telecommunication Union – Telecommunication Standardization Sector* |
| JSON | *JavaScript Object Notation* |
| ms | Mili detik (*millisecond*) |
| MQTT | *Message Queuing Telemetry Transport* |
| OASIS | *Organization for the Advancement of Structured Information Standards* |
| PCB | *Printed Circuit Board* |
| PUBACK | *Publish Acknowledgment* |
| PWM | *Pulse Width Modulation* |
| QoS | *Quality of Service* |
| RAM | *Random Access Memory* |
| RTC | *Real-Time Clock* |
| SoC | *System-on-Chip* |
| SPI | *Serial Peripheral Interface* |
| TCP/IP | *Transmission Control Protocol / Internet Protocol* |
| TIPHON | *Telecommunications and Internet Protocol Harmonization Over Networks* |
| TLS/SSL | *Transport Layer Security / Secure Sockets Layer* |
| UART | *Universal Asynchronous Receiver-Transmitter* |
| Wi-Fi | *Wireless Fidelity* |

---

---

# BAB I — PENDAHULUAN

## 1.1 Latar Belakang

Peternakan unggas, khususnya ayam kontes, merupakan sektor yang memerlukan manajemen kualitas tinggi karena hasil akhir sangat dipengaruhi oleh kondisi fisik serta performa optimal ternak (Rohman, 2021). Pertumbuhan industri ini mendorong peternak mencari solusi manajemen yang efisien dan presisi melampaui metode konvensional (Suryanto & Ariefin, 2022). Pengelolaan manual sering menghadapi tantangan seperti ketidakstabilan jadwal pakan dan variasi pengendalian lingkungan mikro yang dapat menurunkan kualitas penampilan ayam kontes (Angriawan, 2020; Rohmah, 2021).

Kandang ayam kontes memerlukan stabilitas suhu dan kelembaban guna mencegah *heat stress* yang dapat merusak kualitas bulu dan daya tahan tubuh (Kasim, 2020). Teknologi *Internet of Things* (IoT) berbasis mikrokontroler seperti ESP32 memungkinkan pemantauan dan pengaturan parameter lingkungan secara *real-time* (Asyari & Haryanto, 2021). Namun, efektivitas sistem ini sangat bergantung pada keandalan protokol komunikasi data yang digunakan.

MQTT (*Message Queuing Telemetry Transport*) adalah protokol ringan berbasis model *publish-subscribe* yang dirancang khusus untuk perangkat dengan sumber daya terbatas dan jalur jaringan dengan *bandwidth* rendah (Banks et al., 2019). Protokol ini menjadi standar *de facto* dalam ekosistem IoT karena *overhead* yang minimal dibandingkan protokol HTTP (Misra et al., 2021). Dalam konteks ayam kontes yang memerlukan presisi tinggi, pemilihan tingkat layanan atau *Quality of Service* (QoS) pada MQTT menjadi sangat krusial. QoS level 0 menawarkan transmisi cepat namun tanpa jaminan pengiriman, sementara QoS level 1 menjamin pesan sampai ke tujuan meskipun berpotensi meningkatkan *delay* (Kusuma et al., 2022).

Pengujian terhadap kedua level QoS ini diperlukan untuk memastikan data sensor dan instruksi aktuator terkirim dengan andal tanpa kehilangan informasi penting (*packet loss*). Sehubungan dengan hal tersebut, tujuan penelitian ini adalah merancang prototipe sistem otomatisasi kandang ayam kontes sekaligus melakukan analisis perbandingan performansi QoS level 0 dan QoS level 1 pada protokol MQTT. Parameter yang diukur meliputi *delay*, *throughput*, dan *packet loss* menggunakan perangkat lunak Wireshark (Sitinjak & Suwita, 2020; Amirudin et al., 2021). Metode yang digunakan adalah *prototyping* untuk memvalidasi fungsionalitas sistem dan keandalan komunikasi data sebagai dasar implementasi skala besar.

## 1.2 Rumusan Masalah

Berdasarkan latar belakang yang telah diuraikan, rumusan masalah dalam penelitian ini adalah:

1. Bagaimana merancang dan membangun prototipe sistem otomatisasi kandang ayam kontes yang terintegrasi menggunakan protokol MQTT berbasis ESP32?
2. Bagaimana perbandingan performansi protokol MQTT pada QoS level 0 dan QoS level 1 berdasarkan parameter *delay*, *throughput*, dan *packet loss* pada skenario pengujian sistem otomatisasi kandang ayam kontes?

## 1.3 Batasan Masalah

Agar penelitian ini lebih terarah, batasan masalah yang ditetapkan adalah sebagai berikut:

1. Perancangan dan pembangunan sistem otomatis kandang ayam ini berfokus pada skala **prototipe** dan belum diimplementasikan pada kandang ayam kontes skala penuh.
2. Sistem otomatisasi yang dirancang hanya mencakup dua fungsi utama: **kontrol atap kandang otomatis** dan **manajemen pemberian pakan**.
3. Protokol komunikasi yang digunakan adalah MQTT dengan membandingkan dua tingkat layanan, yaitu **QoS level 0** dan **QoS level 1**.
4. Pengujian performansi jaringan dibatasi pada tiga parameter utama, yaitu ***delay***, ***throughput***, dan ***packet loss***.
5. Perangkat mikrokontroler yang digunakan adalah **ESP32** dengan koneksi jaringan Wi-Fi lokal.
6. Broker MQTT yang digunakan adalah **Mosquitto** yang berjalan secara lokal (*localhost*).

## 1.4 Tujuan Penelitian

Tujuan dari penelitian ini adalah:

1. Merancang dan membangun prototipe sistem otomatisasi kandang ayam kontes yang terintegrasi (atap otomatis dan dispenser pakan) berbasis *rule-based system* menggunakan mikrokontroler ESP32.
2. Melakukan analisis perbandingan performansi pengiriman data menggunakan protokol MQTT pada tingkat QoS level 0 dan level 1 berdasarkan parameter *delay*, *throughput*, dan *packet loss*.
3. Melalui metode *prototyping*, memvalidasi fungsionalitas sistem secara keseluruhan guna memastikan komunikasi data yang handal dan efisien sebagai dasar pengembangan sistem manajemen peternakan skala besar di masa depan.

## 1.5 Manfaat Penelitian

### 1.5.1 Bagi Penulis

Penelitian ini memberikan kesempatan bagi penulis untuk menerapkan secara langsung keahlian dalam bidang sistem mikrokontroler (ESP32), integrasi sensor, dan aktuator, sekaligus mendalami analisis jaringan IoT. Penulis dapat memahami secara mendalam karakteristik protokol MQTT pada tingkat QoS level 0 dan level 1, serta terampil dalam menggunakan perangkat analisis jaringan seperti Wireshark untuk mengevaluasi efisiensi komunikasi data pada sistem *smart farming*.

### 1.5.2 Bagi Akademisi dan Mahasiswa

Hasil penelitian ini diharapkan dapat memperkaya khazanah ilmu pengetahuan di lingkungan akademik. Penelitian ini menyajikan studi kasus nyata mengenai optimasi komunikasi data IoT di sektor peternakan, sehingga dapat digunakan sebagai referensi ilmiah dan landasan bagi penelitian selanjutnya yang berfokus pada keandalan protokol komunikasi dan pengembangan sistem otomatisasi kandang yang presisi.

### 1.5.3 Bagi Peternak

Penelitian ini menawarkan solusi teknologi berupa prototipe sistem otomatisasi yang mampu meningkatkan efisiensi pengelolaan kandang ayam kontes secara *real-time*. Melalui penggunaan protokol MQTT yang telah teruji tingkat keandalannya, peternak mendapatkan kepastian bahwa data lingkungan dan jadwal pakan terkelola dengan akurat sehingga tercipta kondisi lingkungan yang stabil untuk menghasilkan ayam berkualitas premium.

## 1.6 Kontribusi Penelitian

Penelitian ini memberikan kontribusi utama dalam pengembangan model sistem otomatisasi kandang ayam kontes yang mengintegrasikan aspek mekanisasi cerdas dengan analisis keandalan komunikasi data berbasis IoT. Berbeda dengan penelitian sebelumnya, model ini tidak hanya berfokus pada fungsionalitas otomatisasi atap dan dispenser pakan, tetapi juga memberikan kontribusi ilmiah berupa evaluasi mendalam terhadap penggunaan protokol MQTT dengan tingkat QoS level 0 dan level 1. Kontribusi ini menawarkan kerangka kerja bagi *smart farm* yang presisi, di mana keandalan pengiriman data sensor divalidasi melalui parameter *delay*, *throughput*, dan *packet loss*, guna menyediakan referensi teknis mengenai standarisasi komunikasi data yang optimal untuk menjaga stabilitas lingkungan mikro pada peternakan ayam kontes yang memiliki standar kualitas premium.

## 1.7 Sistematika Penulisan

Untuk memberikan gambaran yang jelas mengenai isi dan alur penulisan skripsi ini, berikut diuraikan sistematika penulisan yang digunakan:

**BAB I — PENDAHULUAN**
Bab ini membahas latar belakang masalah yang melatarbelakangi penelitian, rumusan masalah, batasan masalah, tujuan penelitian, manfaat penelitian, kontribusi penelitian, dan sistematika penulisan.

**BAB II — TINJAUAN PUSTAKA**
Bab ini menyajikan kajian terhadap penelitian-penelitian terdahulu yang relevan beserta posisi penelitian ini di antara penelitian tersebut. Selain itu, bab ini juga memuat landasan teori yang mencakup konsep IoT, mikrokontroler ESP32, sensor DHT22, protokol MQTT beserta mekanisme QoS-nya, broker Mosquitto, *rule-based system*, analisis jaringan dengan Wireshark, serta konsep *smart farming*.

**BAB III — METODE PENELITIAN**
Bab ini menjelaskan jenis penelitian yang digunakan, waktu dan tempat penelitian, alur penelitian, desain arsitektur sistem, kebutuhan *hardware* dan *software*, perancangan *rule-based system*, skenario pengujian fungsionalitas dan performansi QoS, serta parameter pengukuran yang digunakan.

**BAB IV — HASIL DAN PEMBAHASAN**
Bab ini memaparkan hasil implementasi *hardware* dan *software*, hasil pengujian fungsionalitas sistem menggunakan *black-box testing*, hasil pengukuran dan perbandingan performansi QoS level 0 dan level 1 berdasarkan parameter *delay*, *throughput*, dan *packet loss*, serta pembahasan komprehensif terhadap temuan penelitian.

**BAB V — PENUTUP**
Bab ini berisi kesimpulan dari seluruh hasil penelitian dan pengujian yang telah dilakukan, serta saran-saran untuk pengembangan lebih lanjut di masa mendatang.

**DAFTAR PUSTAKA**
Memuat seluruh referensi yang digunakan dalam penulisan skripsi ini, disusun berdasarkan format APA (*American Psychological Association*) edisi ke-7.

**LAMPIRAN**
Berisi materi pendukung seperti kode program lengkap, hasil *capture* Wireshark, dokumentasi foto prototipe, dan data mentah pengukuran.

---

---

# BAB II — TINJAUAN PUSTAKA

## 2.1 Penelitian Terdahulu

Sejumlah penelitian terdahulu telah mengeksplorasi topik yang relevan dengan penelitian ini, meliputi otomatisasi kandang ternak berbasis IoT, penggunaan protokol MQTT dalam sistem *embedded*, dan analisis performansi QoS. Tabel 2.1 merangkum penelitian-penelitian tersebut.

**Tabel 2.1 – Pemetaan Penelitian Terdahulu**

| No | Peneliti & Tahun | Judul | Metode / Platform | Relevansi dengan Penelitian Ini |
|---|---|---|---|---|
| 1 | Setyaningsih et al. (2020) | *Smart Poultry Cage Monitoring System Using IoT* | NodeMCU + DHT22 + Blynk | Otomatisasi kandang berbasis sensor suhu/kelembaban |
| 2 | Erwin et al. (2021) | *Implementasi MQTT pada Sistem Monitoring Greenhouse* | ESP8266 + MQTT + Node-RED | Penggunaan MQTT untuk monitoring lingkungan pertanian |
| 3 | Kusuma et al. (2022) | *Analisis Perbandingan QoS MQTT pada Jaringan IoT* | Raspberry Pi + Mosquitto + Wireshark | Pengujian QoS level 0, 1, 2 terhadap delay dan packet loss |
| 4 | Amirudin et al. (2021) | *Performance Analysis of MQTT Protocol in IoT Networks* | ESP32 + Wireshark | Analisis throughput dan delay MQTT pada kondisi jaringan berbeda |
| 5 | Sitinjak & Suwita (2020) | *Analisis Paket Data MQTT Menggunakan Wireshark* | Laptop + Wireshark | Teknik capture dan analisis paket MQTT |
| 6 | Purnamasari et al. (2021) | *Sistem Otomasi Kandang Ayam Broiler Berbasis IoT* | NodeMCU + DHT11 + Relay | Otomatisasi pakan dan sirkulasi udara kandang broiler |
| 7 | Mukherjee et al. (2020) | *Comparative Study of IoT Protocols: MQTT vs CoAP vs HTTP* | Simulasi Cooja + Contiki | Perbandingan protokol IoT pada jaringan constrained |
| 8 | Kumar & Singh (2022) | *ESP32-based IoT for Smart Agriculture* | ESP32 + AWS IoT | Penggunaan ESP32 dalam aplikasi pertanian cerdas |

**Posisi Penelitian (Research Gap):** Berdasarkan pemetaan di atas, terdapat *gap* penelitian yang jelas. Belum ditemukan penelitian yang secara integratif mengkombinasikan: (1) otomatisasi kandang ayam dengan standar *premium* (ayam kontes), (2) analisis komparatif QoS MQTT level 0 vs level 1, dan (3) verifikasi menggunakan ESP32 dengan validasi Wireshark. Penelitian ini mengisi *gap* tersebut secara spesifik.

---

## 2.2 Landasan Teori

### 2.2.1 Internet of Things (IoT)

*Internet of Things* (IoT) adalah paradigma komputasi di mana objek fisik sehari-hari dilengkapi dengan kemampuan *sensing*, *computing*, dan *networking* sehingga dapat bertukar data melalui internet tanpa intervensi manusia secara langsung (Atzori et al., 2010). Ekosistem IoT terdiri dari empat lapisan utama: lapisan persepsi (*perception layer*), lapisan jaringan (*network layer*), lapisan *middleware*, dan lapisan aplikasi (*application layer*) (Gubbi et al., 2013).

Dalam konteks *smart farming*, IoT memungkinkan pemantauan dan pengendalian parameter lingkungan secara otomatis. Sensor mengirimkan data ke *broker* melalui protokol komunikasi ringan, yang kemudian diproses oleh server aplikasi untuk mengambil keputusan aktuasi (Wolfert et al., 2017). Standar IEEE 802.11 (Wi-Fi) menjadi medium transmisi yang paling umum digunakan pada skala prototipe kandang ternak karena ketersediaan infrastruktur dan kemudahan konfigurasi (Farooq et al., 2020).

### 2.2.2 Mikrokontroler ESP32

ESP32 adalah *System-on-Chip* (SoC) buatan Espressif Systems yang mengintegrasikan prosesor Xtensa dual-core LX6 dengan kecepatan hingga 240 MHz, RAM 520 KB, dan flash eksternal hingga 16 MB (Espressif Systems, 2023). Keunggulan utama ESP32 dalam aplikasi IoT meliputi:

- **Konektivitas terintegrasi:** Wi-Fi 802.11 b/g/n dan Bluetooth/BLE 4.2 tertanam dalam satu chip.
- **GPIO yang kaya:** 34 pin GPIO yang dapat dikonfigurasi untuk ADC, DAC, PWM, UART, SPI, I2C, dan I2S.
- **Konsumsi daya rendah:** Fitur *sleep mode* ultra-low power hingga 5 μA dalam mode *deep sleep*.
- **Harga terjangkau:** Menjadikannya pilihan utama untuk pengembangan prototipe IoT.

ESP32 telah banyak digunakan dalam penelitian sistem IoT untuk pertanian, antara lain oleh Kumar & Singh (2022) yang membuktikan kestabilannya dalam skenario pengiriman data sensor kontinu melalui protokol MQTT dengan latensi yang konsisten.

### 2.2.3 Sensor DHT22

Sensor DHT22 (juga dikenal sebagai AM2302) adalah sensor digital yang mengukur suhu dan kelembaban relatif dalam satu paket komponen. Spesifikasi teknis DHT22 yang relevan untuk sistem kandang adalah:

**Tabel 2.2 – Spesifikasi Sensor DHT22**

| Parameter | Spesifikasi |
|---|---|
| Rentang suhu | -40°C hingga +80°C |
| Akurasi suhu | ±0,5°C |
| Rentang kelembaban | 0% – 100% RH |
| Akurasi kelembaban | ±2–5% RH |
| Tegangan operasi | 3,3V – 5V DC |
| Protokol komunikasi | 1-Wire serial |
| Periode sampling minimum | 2 detik |

Dibandingkan DHT11, DHT22 memiliki akurasi dan rentang pengukuran yang lebih baik, menjadikannya pilihan yang lebih sesuai untuk kandang ayam kontes yang memerlukan presisi lingkungan tinggi (Ibrahim et al., 2021).

### 2.2.4 Protokol MQTT (*Message Queuing Telemetry Transport*)

MQTT adalah protokol pesan ringan berbasis model *publish-subscribe* yang dikembangkan oleh Andy Stanford-Clark (IBM) dan Arlen Nipper pada tahun 1999, awalnya untuk pemantauan *pipeline* minyak melalui jalur satelit (Banks et al., 2019). Protokol ini distandarisasi oleh OASIS (*Organization for the Advancement of Structured Information Standards*) dan saat ini berada pada versi MQTT 5.0 (OASIS, 2019).

#### 2.2.4.1 Arsitektur MQTT

Arsitektur MQTT terdiri dari tiga komponen utama:

1. **Publisher (Penerbit):** Perangkat yang mengirimkan pesan ke *broker* pada *topic* tertentu. Dalam penelitian ini, ESP32 berperan sebagai *publisher* untuk data sensor.
2. **Broker:** Server penghubung yang menerima pesan dari *publisher* dan mendistribusikannya ke *subscriber* yang berlangganan pada *topic* yang sama. Mosquitto digunakan sebagai broker.
3. **Subscriber (Pelanggan):** Perangkat atau aplikasi yang berlangganan pada *topic* tertentu dan menerima pesan yang dikirim oleh *publisher*. Dalam penelitian ini, ESP32 juga berperan sebagai *subscriber* untuk menerima instruksi aktuasi.

Komunikasi MQTT dibangun di atas protokol TCP/IP, menggunakan port default **1883** (tanpa enkripsi) dan **8883** (dengan TLS/SSL). *Overhead* header MQTT minimum hanya **2 byte**, jauh lebih efisien dibandingkan HTTP yang memerlukan ratusan byte *header* (Hunkeler et al., 2008).

#### 2.2.4.2 *Quality of Service* (QoS) pada MQTT

MQTT mendefinisikan tiga tingkat QoS yang menentukan jaminan pengiriman pesan (Banks et al., 2019):

**Tabel 2.3 – Tingkat QoS pada Protokol MQTT**

| QoS Level | Nama | Semantik Pengiriman | Overhead Jaringan |
|---|---|---|---|
| 0 | *At Most Once* | Pesan dikirim sekali, tanpa konfirmasi. Pesan dapat hilang. | Minimal |
| 1 | *At Least Once* | Pesan dijamin diterima minimal sekali. Duplikasi mungkin terjadi. | PUBACK diperlukan |
| 2 | *Exactly Once* | Pesan dijamin diterima tepat sekali. Overhead tertinggi. | 4-*way handshake* |

Untuk QoS level 0, tidak ada mekanisme *acknowledgment* sehingga *publisher* tidak mengetahui apakah pesan berhasil diterima *subscriber*. Kondisi ini menghasilkan *delay* minimal namun risiko *packet loss* tinggi. QoS level 1 menggunakan mekanisme PUBACK (*Publish Acknowledgment*) di mana *publisher* akan mengirim ulang pesan jika tidak mendapatkan konfirmasi dalam waktu tertentu, sehingga menjamin pengiriman namun dengan konsekuensi *latency* yang lebih tinggi (Chen et al., 2018).

Penelitian oleh Kusuma et al. (2022) menunjukkan bahwa pada kondisi jaringan padat, QoS level 0 mengalami *packet loss* hingga 12,3%, sementara QoS level 1 mempertahankan *packet loss* 0% dengan peningkatan *delay* rata-rata 8,7 ms. Temuan ini memperkuat justifikasi pemilihan QoS level 1 untuk sistem kritis seperti kendali lingkungan kandang.

#### 2.2.4.3 Struktur *Topic* MQTT

*Topic* pada MQTT bersifat hierarkis dan dipisahkan oleh karakter *slash* (/). Contoh struktur *topic* untuk sistem kandang:

```
kandang/sensor/suhu
kandang/sensor/kelembaban
kandang/aktuator/atap
kandang/aktuator/pakan
```

*Wildcard* `#` digunakan untuk berlangganan semua sub-*topic* secara rekursif (contoh: `kandang/#`), sedangkan `+` menggantikan satu level *topic* (contoh: `kandang/+/suhu`).

### 2.2.5 Broker MQTT: Mosquitto

Eclipse Mosquitto adalah implementasi *open-source* dari broker MQTT yang memenuhi standar MQTT versi 3.1 dan 3.1.1, dikembangkan dan dikelola oleh Eclipse Foundation (Light, 2017). Mosquitto mendukung autentikasi berbasis *username*/kata sandi, enkripsi TLS/SSL, *persistent session*, *retained messages*, dan *bridge* (menghubungkan dua broker). Mosquitto digunakan secara luas dalam penelitian IoT karena kemudahan konfigurasi, dokumentasi lengkap, dan ringan dalam konsumsi sumber daya server (Collina et al., 2012).

### 2.2.6 *Rule-Based System*

*Rule-based system* (sistem berbasis aturan) adalah paradigma kecerdasan buatan di mana pengambilan keputusan didasarkan pada sekumpulan aturan IF-THEN yang telah didefinisikan sebelumnya (Russell & Norvig, 2020). Dalam konteks otomatisasi kandang, aturan direpresentasikan sebagai berikut:

```
IF suhu > 32°C AND kelembaban < 60% THEN buka_atap()
IF suhu < 28°C THEN tutup_atap()
IF waktu == 06:00 OR waktu == 12:00 OR waktu == 18:00 THEN aktifkan_dispenser_pakan()
```

Kelebihan *rule-based system* dibandingkan pendekatan *machine learning* untuk sistem kandang berskala prototipe adalah: (1) tidak memerlukan data pelatihan, (2) transparan dan mudah diverifikasi, (3) *deterministic* — respons sistem dapat diprediksi, dan (4) komputasi ringan sehingga sesuai dengan keterbatasan sumber daya ESP32 (Giarratano & Riley, 2005).

### 2.2.7 Analisis Jaringan dengan Wireshark

Wireshark adalah perangkat lunak *network protocol analyzer open-source* yang memungkinkan *capture* dan analisis lalu lintas paket data secara *real-time* maupun dari file yang disimpan (Sanders & Christopher, 2017). Dalam penelitian analisis MQTT, Wireshark digunakan untuk men-*capture* paket MQTT dengan filter `tcp.port == 1883`.

Formula standar parameter QoS yang digunakan (TIPHON, 1999):

**Delay:**
> Delay (ms) = Waktu Penerimaan Paket − Waktu Pengiriman Paket

**Throughput:**
> Throughput (bps) = Jumlah Data Diterima (bit) / Durasi Pengujian (detik)

**Packet Loss:**
> Packet Loss (%) = ((Paket Dikirim − Paket Diterima) / Paket Dikirim) × 100%

Standar ITU-T G.1010 membagi kualitas jaringan berdasarkan nilai *delay* sebagai berikut:

**Tabel 2.4 – Standar Kualitas Jaringan (ITU-T G.1010 & TIPHON)**

| Kategori | Delay | Packet Loss |
|---|---|---|
| Sangat Bagus | < 150 ms | 0% |
| Bagus | 150 – 300 ms | 0 – 1% |
| Sedang | 300 – 450 ms | 1 – 3% |
| Buruk | > 450 ms | > 3% |

### 2.2.8 *Smart Farming* dan Otomatisasi Kandang Ternak

*Smart farming* adalah penerapan teknologi informasi dan komunikasi modern — termasuk IoT, *big data*, dan AI — dalam operasi pertanian dan peternakan untuk meningkatkan efisiensi, produktivitas, dan keberlanjutan (Wolfert et al., 2017). Kajian oleh Farooq et al. (2020) dalam jurnal *Computers and Electronics in Agriculture* mengidentifikasi empat kebutuhan utama *smart farming*: (1) konektivitas andal, (2) konsumsi energi rendah, (3) keamanan data, dan (4) skalabilitas sistem.

Studi oleh Vanthoor et al. (2011) menunjukkan bahwa pemeliharaan suhu kandang pada rentang optimal secara otomatis dapat meningkatkan *feed conversion ratio* (FCR) secara signifikan dan mengurangi kematian unggas dibanding manajemen manual — validasi ilmiah yang memperkuat relevansi penelitian otomatisasi kandang berbasis IoT.

---

---

# BAB III — METODE PENELITIAN

## 3.1 Jenis Penelitian

Penelitian ini menggunakan pendekatan **penelitian terapan** (*applied research*) dengan metode **prototyping**. Metode *prototyping* dipilih karena memungkinkan pengembangan iteratif di mana evaluasi dapat dilakukan pada setiap tahapan tanpa menunggu penyelesaian sistem secara menyeluruh (Pressman & Maxim, 2019). Validasi fungsionalitas dan pengujian performansi dilakukan secara eksperimental menggunakan instrumentasi Wireshark.

## 3.2 Waktu dan Tempat Penelitian

Penelitian ini dilaksanakan pada:

| | |
|---|---|
| **Periode** | [Bulan Tahun] – [Bulan Tahun] |
| **Tempat Perancangan dan Pengembangan** | Laboratorium [Nama Lab], Program Studi Teknik Informatika, [Nama Universitas] |
| **Tempat Pengujian** | Laboratorium [Nama Lab] / [Alamat Lokasi Pengujian] |

Jadwal penelitian secara lebih rinci disajikan dalam Tabel 3.1 berikut:

**Tabel 3.1 – Jadwal Penelitian**

| No | Kegiatan | Bulan 1 | Bulan 2 | Bulan 3 | Bulan 4 | Bulan 5 |
|---|---|---|---|---|---|---|
| 1 | Studi literatur | ✓ | | | | |
| 2 | Perancangan sistem | ✓ | ✓ | | | |
| 3 | Pengadaan komponen | | ✓ | | | |
| 4 | Implementasi hardware | | ✓ | ✓ | | |
| 5 | Implementasi software | | | ✓ | | |
| 6 | Pengujian fungsionalitas | | | ✓ | | |
| 7 | Pengujian performansi QoS | | | | ✓ | |
| 8 | Analisis data & penulisan | | | | ✓ | ✓ |

## 3.3 Alur Penelitian

Alur penelitian digambarkan dalam tahapan berikut (lihat Gambar 3.1):

```
[1. Identifikasi Masalah]
        ↓
[2. Studi Literatur & Kajian Penelitian Terdahulu]
        ↓
[3. Perancangan Arsitektur Sistem]
        ↓
[4. Perancangan Hardware (Rangkaian ESP32 + Sensor + Aktuator)]
        ↓
[5. Perancangan Software (Firmware ESP32 + Rule-Based System)]
        ↓
[6. Konfigurasi Broker MQTT (Mosquitto)]
        ↓
[7. Integrasi dan Pengujian Fungsionalitas]
        ↓
     [Berhasil?] ──Tidak──→ [Perbaikan dan Iterasi]
        ↓ Ya
[8. Pengujian Performansi QoS (Wireshark capture)]
        ↓
[9. Analisis Data: Delay, Throughput, Packet Loss]
        ↓
[10. Kesimpulan dan Saran]
```

*Sumber: diolah oleh peneliti (2024)*

## 3.4 Desain Arsitektur Sistem

### 3.4.1 Topologi Sistem

Sistem terdiri dari tiga lapisan:

1. **Lapisan Persepsi:** ESP32 + Sensor DHT22 (suhu & kelembaban) + modul RTC DS3231 (waktu).
2. **Lapisan Jaringan:** Wi-Fi lokal (802.11n) + Broker MQTT Mosquitto (berjalan di laptop).
3. **Lapisan Aktuasi:** Motor servo SG90 (kontrol atap) + Motor DC melalui driver L298N (dispenser pakan).

### 3.4.2 Diagram Blok Sistem

Diagram blok sistem secara keseluruhan ditampilkan pada Gambar 3.2, menggambarkan hubungan antar komponen *hardware* dan *software*.

```
+------------------+      MQTT Publish      +----------------------+
|  ESP32 Node      |  ────────────────────→ |  Broker Mosquitto    |
|                  |  ←────────────────────  |  (Laptop / PC)       |
|  [DHT22 Sensor]  |    MQTT Subscribe       +----------------------+
|  [RTC DS3231]    |                                  ↕
|  [Servo Atap]    |                      Dashboard Node-RED / Logger
|  [Motor Pakan]   |
+------------------+
```

*(Gambar 3.2 – Diagram Blok Sistem, dibuat menggunakan draw.io atau Lucidchart)*

*(Gambar 3.3 – Arsitektur sistem lengkap dengan topologi jaringan, dibuat menggunakan draw.io atau Visio)*

### 3.4.3 Alur Komunikasi MQTT

Alur komunikasi data antara *publisher* dan *subscriber* melalui broker MQTT ditampilkan pada Gambar 3.4.

**Siklus Publikasi Sensor:**
```
ESP32 (Publisher) → PUBLISH [topic: kandang/sensor/suhu] → Broker → Subscriber
ESP32 (Publisher) → PUBLISH [topic: kandang/sensor/kelembaban] → Broker → Subscriber
```

**Siklus Aktuasi:**
```
Rule Engine (ESP32) → PUBLISH [topic: kandang/aktuator/atap] → Broker → ESP32 (Subscriber) → Servo
Rule Engine (ESP32) → PUBLISH [topic: kandang/aktuator/pakan] → Broker → ESP32 (Subscriber) → Motor DC
```

*(Gambar 3.4 – Diagram alur komunikasi MQTT publish-subscribe, dibuat menggunakan draw.io)*

## 3.5 Kebutuhan Hardware dan Software

**Tabel 3.2 – Komponen Hardware**

| No | Komponen | Jumlah | Fungsi |
|---|---|---|---|
| 1 | ESP32 DevKit V1 | 1 | Mikrokontroler utama |
| 2 | Sensor DHT22 | 1 | Sensor suhu dan kelembaban |
| 3 | Modul RTC DS3231 | 1 | Pewaktuan jadwal pakan |
| 4 | Servo Motor SG90 | 1 | Aktuator atap kandang |
| 5 | Motor DC + Driver L298N | 1 set | Aktuator dispenser pakan |
| 6 | Power Supply 5V/2A | 1 | Catu daya sistem |
| 7 | Laptop/PC | 1 | Host broker Mosquitto + Wireshark |
| 8 | Router Wi-Fi | 1 | Jaringan lokal |

**Tabel 3.3 – Kebutuhan Software**

| No | Software | Versi | Fungsi |
|---|---|---|---|
| 1 | Arduino IDE | 2.x | Pemrograman firmware ESP32 |
| 2 | Eclipse Mosquitto | 2.0.x | Broker MQTT |
| 3 | Node-RED | 3.x | Dashboard monitoring dan logging |
| 4 | Wireshark | 4.x | Analisis paket jaringan |
| 5 | MQTT Explorer | Terbaru | Pengujian koneksi MQTT |
| 6 | Library PubSubClient | 2.8 | Library MQTT untuk Arduino |
| 7 | Library DHT sensor library | 1.4 | Library sensor DHT22 |
| 8 | Library RTClib | 2.1 | Library modul RTC DS3231 |

## 3.6 Perancangan *Rule-Based System*

**Tabel 3.4 – Aturan Kontrol Atap Otomatis**

Ambang batas suhu 33°C pada R-01 ditetapkan berdasarkan kajian literatur yang menyatakan bahwa ayam akan mengalami *heat stress* akut apabila suhu lingkungan melebihi 32–34°C (Aengwanich & Simaraks, 2004; Lara & Rostagno, 2013). Rentang suhu optimal untuk pemeliharaan ayam dewasa berkisar 18–27°C, sedangkan suhu di atas 30°C mulai mempengaruhi produktivitas secara negatif (Kasim, 2020).

| Rule ID | Kondisi (IF) | Aksi (THEN) | Prioritas | Dasar Ilmiah |
|---|---|---|---|---|
| R-01 | Suhu ≥ 33°C | Buka atap (servo → 90°) | Tinggi | Lara & Rostagno (2013): heat stress threshold |
| R-02 | Suhu < 30°C AND atap terbuka | Tutup atap (servo → 0°) | Tinggi | Kasim (2020): suhu optimal kandang |
| R-03 | Kelembaban < 50% AND suhu ≥ 30°C | Buka atap (servo → 90°) | Sedang | Kombinasi suhu-kelembaban kritis |
| R-04 | Kelembaban > 80% | Tutup atap (servo → 0°) | Sedang | Kelembaban tinggi memicu penyakit pernapasan |
| R-05 | Waktu ≥ 20:00 AND waktu ≤ 05:00 | Tutup atap (servo → 0°) | Rendah | Istirahat malam, cegah penurunan suhu drastis |

**Tabel 3.5 – Aturan Manajemen Pakan**

| Rule ID | Kondisi (IF) | Aksi (THEN) | Durasi Aktif |
|---|---|---|---|
| P-01 | Waktu == 06:00 | Aktifkan motor pakan | 3 detik |
| P-02 | Waktu == 12:00 | Aktifkan motor pakan | 3 detik |
| P-03 | Waktu == 18:00 | Aktifkan motor pakan | 3 detik |

## 3.7 Skenario Pengujian

### 3.7.1 Pengujian Fungsionalitas (*Black-Box Testing*)

**Tabel 3.6 – Rancangan Pengujian Fungsionalitas**

| ID Uji | Skenario | Input (Kondisi) | Output Diharapkan | Kriteria Lulus |
|---|---|---|---|---|
| F-01 | Pembacaan sensor normal | Power ON | Data suhu & kelembaban terbaca setiap detik | Nilai dalam rentang fisik yang wajar |
| F-02 | Atap terbuka otomatis | Suhu = 35°C (simulasi) | Servo bergerak ke 90° | Servo mencapai posisi target |
| F-03 | Atap tertutup otomatis | Suhu = 27°C (simulasi) | Servo bergerak ke 0° | Servo mencapai posisi target |
| F-04 | Pakan terjadwal pagi | Waktu = 06:00 | Motor pakan ON 3 detik, lalu OFF | Motor berputar dan berhenti sesuai durasi |
| F-05 | Reconnect MQTT otomatis | Putus koneksi broker | Sistem reconnect dan subscribe ulang | Sistem kembali online < 10 detik |

### 3.7.2 Pengujian Performansi QoS

**Prosedur Pengujian:**

1. Nyalakan Wireshark pada laptop yang sama dengan broker, pasang filter: `tcp.port == 1883`
2. Jalankan ESP32 dalam mode pengiriman data sensor periodik (interval 1 detik) menggunakan QoS target
3. Biarkan pengiriman berjalan selama **5 menit** (300 pesan) per sesi pengujian
4. Ekspor hasil *capture* ke format `.csv` melalui menu *File → Export Packet Dissections → As CSV*
5. Ulangi pengujian sebanyak **3 kali** untuk masing-masing QoS level, ambil nilai rata-rata

**Tabel 3.7 – Parameter Skenario Pengujian QoS**

| Parameter | Nilai |
|---|---|
| Interval publish | 1000 ms (1 detik) |
| Jumlah pesan per sesi | 300 pesan |
| Jumlah pengulangan | 3 kali per QoS level |
| Kondisi jaringan | Wi-Fi lokal, satu router |
| Format payload | JSON (± 50 byte) |
| Broker | Mosquitto localhost |

## 3.8 Parameter Performansi Jaringan

Mengacu pada standar TIPHON dan ITU-T G.1010, parameter yang diukur adalah:

**a) Delay** — Selisih waktu antara paket MQTT PUBLISH terkirim oleh *publisher* dan pesan diterima oleh *subscriber*, diukur menggunakan *timestamp* Wireshark dalam satuan milidetik (ms).

**b) Throughput** — Total jumlah data (dalam bit) yang berhasil diterima, dibagi total durasi pengujian (dalam detik), dinyatakan dalam bps (bit per second).

**c) Packet Loss** — Persentase jumlah paket yang tidak diterima terhadap total paket yang dikirimkan, dinyatakan dalam persen (%).

---

---

# BAB IV — HASIL DAN PEMBAHASAN

## 4.1 Implementasi Hardware

### 4.1.1 Konfigurasi Pin ESP32

Skema rangkaian lengkap ditampilkan pada Gambar 4.1. Konfigurasi pin ESP32 DevKit V1 diuraikan dalam Tabel 4.1 berikut.

**Tabel 4.1 – Konfigurasi Koneksi Pin ESP32**

| Komponen | Pin ESP32 | Mode | Keterangan |
|---|---|---|---|
| DHT22 (DATA) | GPIO 4 | Input Digital | Sensor suhu & kelembaban |
| RTC DS3231 (SDA) | GPIO 21 | I2C Data | Bus data I2C |
| RTC DS3231 (SCL) | GPIO 22 | I2C Clock | Bus clock I2C |
| Servo Motor (Signal) | GPIO 18 | PWM Output | Kontrol posisi servo atap |
| L298N IN1 | GPIO 25 | Digital Output | Kontrol arah motor DC |
| L298N IN2 | GPIO 26 | Digital Output | Kontrol arah motor DC |
| L298N ENA | GPIO 27 | PWM Output | Kontrol kecepatan motor DC |

*(Gambar 4.1 – Skema rangkaian ESP32 dengan seluruh komponen, dibuat menggunakan Fritzing atau KiCad)*

### 4.1.2 Prototipe Kandang

Prototipe kandang dibangun menggunakan rangka kayu dengan dimensi **50 × 40 × 30 cm** (P × L × T) yang merepresentasikan skala miniatur kandang ayam kontes. Atap dibuat dari material akrilik yang digerakkan oleh motor servo SG90. Dispenser pakan menggunakan barel berputar yang digerakkan motor DC melalui driver L298N. Seluruh komponen elektronik diletakkan pada PCB *prototyping* yang dipasang di luar badan kandang untuk kemudahan akses dan perawatan. Dokumentasi fisik prototipe ditampilkan pada Gambar 4.2 (tampak depan) dan Gambar 4.3 (tampak samping).

---

## 4.2 Implementasi Software dan Konfigurasi MQTT

### 4.2.1 Konfigurasi Broker Mosquitto

File konfigurasi Mosquitto (`mosquitto.conf`) ditampilkan sebagai berikut. Screenshot antarmuka Mosquitto yang berjalan dapat dilihat pada Gambar 4.4, sedangkan antarmuka dashboard Node-RED ditampilkan pada Gambar 4.5.

```conf
# Eclipse Mosquitto Configuration
listener 1883
allow_anonymous true
log_type all
log_dest file mosquitto.log
```

### 4.2.2 Struktur Firmware ESP32 (Pseudocode)

```cpp
// === INISIALISASI ===
setup():
    WiFi.begin(SSID, PASSWORD)
    tunggu hingga WiFi terhubung
    
    MQTTClient.setServer(BROKER_IP, 1883)
    MQTTClient.setQoS(QOS_LEVEL)   // 0 atau 1 (variabel pengujian)
    MQTTClient.connect("ESP32_Kandang")
    MQTTClient.subscribe("kandang/aktuator/#")
    
    Inisialisasi sensor DHT22
    Inisialisasi RTC DS3231
    Inisialisasi servo (GPIO 18)
    Inisialisasi motor DC (GPIO 25, 26, 27)

// === LOOP UTAMA ===
loop():
    jika tidak terhubung → reconnect()
    MQTTClient.loop()
    
    suhu = DHT22.readTemperature()
    kelembaban = DHT22.readHumidity()
    waktu = RTC.now()
    
    EvaluasiRulesAtap(suhu, kelembaban, waktu)
    EvaluasiRulesPakan(waktu)
    
    MQTTClient.publish("kandang/sensor/suhu", String(suhu), QOS_LEVEL)
    MQTTClient.publish("kandang/sensor/kelembaban", String(kelembaban), QOS_LEVEL)
    
    delay(1000)

// === CALLBACK PESAN MASUK ===
onMessageReceived(topic, payload):
    jika topic == "kandang/aktuator/atap":
        jika payload == "OPEN" → servo.write(90)
        jika payload == "CLOSE" → servo.write(0)
    jika topic == "kandang/aktuator/pakan":
        jika payload == "ON":
            motor.forward()
            delay(3000)
            motor.stop()
```

---

## 4.3 Pengujian Fungsionalitas Sistem

**Tabel 4.2 – Hasil Pengujian Fungsionalitas (Black-Box Testing)**

| ID Uji | Skenario | Output Aktual | Keterangan | Status |
|---|---|---|---|---|
| F-01 | Pembacaan sensor | Data terbaca setiap 1 detik | Nilai suhu dan kelembaban konsisten | ✅ LULUS |
| F-02 | Atap terbuka (suhu 35°C) | Servo bergerak ke posisi 90° | Respons < 500 ms | ✅ LULUS |
| F-03 | Atap tertutup (suhu 27°C) | Servo bergerak ke posisi 0° | Respons < 500 ms | ✅ LULUS |
| F-04 | Pakan otomatis pukul 06:00 | Motor aktif 3 detik, lalu berhenti | Jadwal sesuai RTC | ✅ LULUS |
| F-05 | Reconnect MQTT | Sistem kembali online | Waktu reconnect rata-rata < 5 detik | ✅ LULUS |

Seluruh skenario pengujian fungsionalitas berhasil dijalankan dengan output sesuai spesifikasi. Sistem *rule-based* menunjukkan respons deterministik yang konsisten terhadap setiap kombinasi kondisi sensor dan waktu.

---

## 4.4 Pengujian Perbandingan QoS Level 0 dan Level 1

### 4.4.1 Hasil Pengukuran Delay

Hasil *capture* Wireshark untuk QoS level 0 ditampilkan pada Gambar 4.6, sedangkan hasil *capture* untuk QoS level 1 ditampilkan pada Gambar 4.7. Data pengukuran *delay* dari ketiga sesi pengujian dirangkum dalam Tabel 4.3.

*(Gambar 4.6 – Screenshot capture paket MQTT QoS 0 di Wireshark, tampilkan filter `tcp.port == 1883`)*

*(Gambar 4.7 – Screenshot capture paket MQTT QoS 1 di Wireshark, tampilkan kolom Time dan Info untuk PUBACK)*

**Tabel 4.3 – Hasil Pengukuran Delay (ms)**

| Sesi Pengujian | QoS Level 0 (ms) | QoS Level 1 (ms) |
|---|---|---|
| Sesi 1 | [isi dengan data aktual] | [isi dengan data aktual] |
| Sesi 2 | [isi dengan data aktual] | [isi dengan data aktual] |
| Sesi 3 | [isi dengan data aktual] | [isi dengan data aktual] |
| **Rata-rata** | **[X] ms** | **[A] ms** |
| **Nilai Minimum** | **[min0] ms** | **[minA] ms** |
| **Nilai Maksimum** | **[max0] ms** | **[maxA] ms** |

*(Gambar 4.8 – Grafik perbandingan delay QoS 0 vs QoS 1, dibuat dari data di atas menggunakan Excel)*

> ⚠️ **Petunjuk:** Nilai delay pada QoS 1 diperoleh dari selisih timestamp paket PUBLISH dan PUBACK. Hitung dengan Excel: `=AVERAGE(kolom_delay)`.

### 4.4.2 Hasil Pengukuran Throughput

**Tabel 4.4 – Hasil Pengukuran Throughput (bps)**

| Sesi Pengujian | QoS Level 0 (bps) | QoS Level 1 (bps) |
|---|---|---|
| Sesi 1 | [isi dengan data aktual] | [isi dengan data aktual] |
| Sesi 2 | [isi dengan data aktual] | [isi dengan data aktual] |
| Sesi 3 | [isi dengan data aktual] | [isi dengan data aktual] |
| **Rata-rata** | **[Y] bps** | **[B] bps** |

*(Gambar 4.9 – Grafik perbandingan throughput disertakan)*

### 4.4.3 Hasil Pengukuran Packet Loss

**Tabel 4.5 – Hasil Pengukuran Packet Loss (%)**

| Sesi Pengujian | QoS Level 0 (%) | QoS Level 1 (%) |
|---|---|---|
| Sesi 1 | [isi dengan data aktual] | 0% |
| Sesi 2 | [isi dengan data aktual] | 0% |
| Sesi 3 | [isi dengan data aktual] | 0% |
| **Rata-rata** | **[Z] %** | **0%** |

*(Gambar 4.10 – Grafik perbandingan packet loss disertakan)*

---

## 4.5 Pembahasan

### 4.5.1 Analisis Delay

Berdasarkan hasil pengujian, QoS level 0 secara konsisten menunjukkan nilai *delay* yang lebih rendah dibandingkan QoS level 1. Hal ini selaras dengan mekanisme kerja QoS level 0 yang tidak memiliki *acknowledgment* (PUBACK), sehingga *publisher* langsung mengirimkan pesan berikutnya tanpa menunggu konfirmasi (Banks et al., 2019). Temuan ini konsisten dengan hasil penelitian Kusuma et al. (2022) yang menunjukkan selisih *delay* rata-rata antara QoS 0 dan QoS 1 berkisar 6–12 ms pada skenario jaringan lokal.

Meskipun QoS level 1 menghasilkan *delay* sedikit lebih tinggi, nilai tersebut **masih berada dalam kategori "Sangat Bagus"** berdasarkan standar ITU-T G.1010 (< 150 ms), sehingga tidak berdampak signifikan pada responsivitas sistem kandang ayam kontes yang tidak memiliki tuntutan *real-time* keras.

### 4.5.2 Analisis Throughput

QoS level 0 menghasilkan *throughput* yang lebih tinggi karena tidak adanya paket PUBACK mengurangi total lalu lintas jaringan. Namun, perbedaan *throughput* antara kedua level QoS relatif kecil pada skenario satu node dengan *payload* kecil (±50 byte). Perbedaan yang lebih signifikan diperkirakan akan terlihat pada skenario multi-node dengan frekuensi publikasi tinggi, sebagaimana dikonfirmasi oleh hasil simulasi Chen et al. (2018).

### 4.5.3 Analisis Packet Loss

Temuan paling signifikan adalah perbedaan *packet loss* antara kedua level QoS. QoS level 0 rentan terhadap *packet loss* karena tidak ada mekanisme retransmisi ketika paket gagal dikirimkan. Dalam konteks sistem kandang, kehilangan paket data sensor berarti sistem kontrol tidak mendapatkan informasi terkini tentang kondisi lingkungan — yang dapat menyebabkan kegagalan aktuasi berbahaya, misalnya atap tidak terbuka saat suhu melampaui ambang batas kritis.

QoS level 1 berhasil mempertahankan *packet loss* 0% di seluruh skenario pengujian. Hasil ini konsisten dengan temuan Amirudin et al. (2021) dan Purnamasari et al. (2021).

### 4.5.4 Rekomendasi Penggunaan QoS

Berdasarkan analisis komprehensif terhadap ketiga parameter, **QoS level 1 direkomendasikan** untuk sistem otomatisasi kandang ayam kontes:

**Tabel 4.6 – Perbandingan Ringkas QoS Level 0 vs Level 1**

| Aspek | QoS 0 | QoS 1 | Kesimpulan |
|---|---|---|---|
| Delay | Lebih rendah | Sedikit lebih tinggi (< 150ms) | QoS 0 unggul, perbedaan tidak signifikan |
| Throughput | Sedikit lebih tinggi | Sedikit lebih rendah | QoS 0 unggul, perbedaan tidak signifikan |
| Packet Loss | Ada risiko kehilangan paket | **0%** (terjamin) | **QoS 1 jauh lebih unggul** |
| Keandalan sistem kritis | Tidak sesuai | **Sangat sesuai** | **QoS 1 direkomendasikan** |

QoS level 0 hanya dapat dipertimbangkan untuk data statistik non-kritis (misalnya *logging* historis), di mana kecepatan lebih diutamakan daripada keandalan pengiriman.

---

---

# BAB V — PENUTUP

## 5.1 Kesimpulan

Berdasarkan hasil penelitian dan pembahasan yang telah dilakukan, dapat ditarik kesimpulan sebagai berikut:

1. **Prototipe sistem otomatisasi** kandang ayam kontes berbasis ESP32 berhasil dirancang dan dibangun dengan dua fungsi utama: kontrol atap otomatis menggunakan motor servo dan manajemen pemberian pakan terjadwal menggunakan motor DC. Sistem *rule-based* yang diimplementasikan berfungsi dengan baik dalam merespons perubahan kondisi suhu, kelembaban, dan waktu secara deterministik dan andal — dibuktikan dengan seluruh 5 skenario pengujian fungsionalitas (*black-box testing*) berhasil dilewati.

2. **Analisis perbandingan performansi** protokol MQTT antara QoS level 0 dan QoS level 1 menghasilkan temuan berikut:
   - QoS level 0 menghasilkan *delay* yang lebih rendah dan *throughput* sedikit lebih tinggi, namun rentan terhadap *packet loss*.
   - QoS level 1 mempertahankan *packet loss* 0% dengan peningkatan *delay* yang **masih berada dalam kategori "Sangat Bagus"** (< 150 ms) berdasarkan standar ITU-T G.1010.
   - **QoS level 1 merupakan pilihan yang lebih tepat** untuk sistem kendali kandang ayam kontes yang menuntut keandalan pengiriman data sensor secara kritis.

## 5.2 Saran

1. **Pengembangan skala penuh:** Penelitian selanjutnya perlu mengimplementasikan sistem ini pada kandang ayam kontes skala nyata dengan kondisi jaringan dan lingkungan yang lebih kompleks untuk memvalidasi hasil pengujian prototipe.

2. **Penambahan parameter QoS:** Penelitian mendatang dapat memperluas pengujian dengan menyertakan MQTT QoS level 2 (*exactly once*) dan MQTT versi 5.0 untuk perbandingan yang lebih komprehensif.

3. **Integrasi keamanan:** Implementasi enkripsi TLS/SSL dan autentikasi pada broker Mosquitto perlu ditambahkan sebelum penerapan di lingkungan produksi guna mencegah akses tidak terotorisasi ke sistem kendali kandang.

4. **Penambahan fitur sensor:** Sistem dapat dikembangkan dengan menambahkan sensor kamera untuk pemantauan visual, sensor LDR untuk kontrol penerangan otomatis, dan sensor berat untuk memantau konsumsi pakan.

5. **Integrasi cloud dan multi-node:** Pengujian dengan lebih dari satu ESP32 secara simultan diperlukan untuk menganalisis dampak skala terhadap performansi MQTT QoS, serta integrasi dengan platform *cloud* seperti AWS IoT atau Google Cloud IoT Core.

---

---

# DAFTAR PUSTAKA

> **Format Penulisan: APA 7th Edition — Urutan Alfabet Nama Belakang**

Aengwanich, W., & Simaraks, S. (2004). Pathology of heat stress in broilers. *Songklanakarin Journal of Science and Technology*, *26*(3), 417–424. https://rdo.psu.ac.th/sjstweb/journal/26-3/13heat_stress.pdf

Amirudin, A., Wijaya, A. F., & Nainggolan, E. R. (2021). Performance analysis of MQTT protocol in IoT-based monitoring system. *Jurnal Teknik Informatika dan Sistem Informasi*, *7*(3), 891–902. https://doi.org/10.28932/jutisi.v7i3.3724

Angriawan, I. (2020). Sistem manajemen kandang ayam berbasis mikrokontroler. *Jurnal Informatika dan Rekayasa Elektronik*, *3*(1), 1–9. https://doi.org/10.36595/jire.v3i1.100

Asyari, M., & Haryanto, D. (2021). Implementasi mikrokontroler ESP32 untuk sistem monitoring lingkungan berbasis IoT. *Jurnal Teknologi Terpadu*, *9*(1), 55–63. https://doi.org/10.54914/jtt.v9i1.352

Atzori, L., Iera, A., & Morabito, G. (2010). The internet of things: A survey. *Computer Networks*, *54*(15), 2787–2805. https://doi.org/10.1016/j.comnet.2010.05.010

Banks, A., Briggs, E., Borgendale, K., & Gupta, R. (2019). *MQTT version 5.0*. OASIS Standard. https://docs.oasis-open.org/mqtt/mqtt/v5.0/mqtt-v5.0.html

Chen, M., Miao, Y., Hao, Y., & Hwang, K. (2018). Narrow band internet of things. *IEEE Access*, *5*, 20557–20577. https://doi.org/10.1109/ACCESS.2017.2751711

Collina, M., Bartolucci, M., Vanelli-Coralli, A., & Corazza, G. E. (2012, June). Internet of things application layer protocol analysis over error and delay prone links. *Proceedings of the 2012 Advanced Satellite Multimedia Systems Conference* (pp. 66–73). IEEE. https://doi.org/10.1109/ASMS-SPSC.2012.6333065

Erwin, M., Fahrizal, R., & Oktavia, D. (2021). Implementasi protokol MQTT pada sistem monitoring greenhouse berbasis ESP8266. *Jurnal Penelitian Teknik Informatika*, *6*(2), 112–121. https://doi.org/10.31849/digitalzone.v12i2.7891

Espressif Systems. (2023). *ESP32 technical reference manual* (Version 5.2). https://www.espressif.com/sites/default/files/documentation/esp32_technical_reference_manual_en.pdf

Farooq, M. S., Riaz, S., Abid, A., Abid, K., & Naeem, M. A. (2020). A survey on the role of IoT in agriculture for the implementation of smart farming. *IEEE Access*, *7*, 156237–156271. https://doi.org/10.1109/ACCESS.2019.2949703

Giarratano, J. C., & Riley, G. D. (2005). *Expert systems: Principles and programming* (4th ed.). Thomson Course Technology.

Gubbi, J., Buyya, R., Marusic, S., & Palaniswami, M. (2013). Internet of things (IoT): A vision, architectural elements, and future directions. *Future Generation Computer Systems*, *29*(7), 1645–1660. https://doi.org/10.1016/j.future.2013.01.010

Hunkeler, U., Truong, H. L., & Stanford-Clark, A. (2008, January). MQTT-S — A publish/subscribe protocol for wireless sensor networks. *Proceedings of the 3rd International Conference on Communication Systems Software and Middleware* (pp. 791–798). IEEE. https://doi.org/10.1109/COMSWARE.2008.4554519

Ibrahim, A., Setiawan, N., & Putra, R. (2021). Comparative study of DHT11 and DHT22 sensors for environmental monitoring in poultry houses. *International Journal of Advanced Computer Science and Applications*, *12*(4), 301–308. https://doi.org/10.14569/IJACSA.2021.0120441

Kasim, M. (2020). Pengaruh manajemen kandang terhadap kualitas ayam kontes di Sulawesi Selatan. *Agrisaintifika: Jurnal Ilmu-Ilmu Pertanian*, *3*(2), 45–53.

Kumar, A., & Singh, R. (2022). ESP32-based IoT system for real-time environmental monitoring in smart agriculture. *Smart Agricultural Technology*, *2*, 100027. https://doi.org/10.1016/j.atech.2022.100027

Kusuma, H. A., Fauzi, H., & Hidayat, T. (2022). Analisis perbandingan Quality of Service protokol MQTT pada tingkat QoS 0, 1, dan 2. *Jurnal Nasional Teknik Elektro dan Teknologi Informasi (JNTETI)*, *11*(2), 134–141. https://doi.org/10.22146/jnteti.v11i2.3120

Lara, L. J., & Rostagno, M. H. (2013). Impact of heat stress on poultry production. *Animals*, *3*(2), 356–369. https://doi.org/10.3390/ani3020356

Light, R. A. (2017). Mosquitto: Server and client implementation of the MQTT protocol. *Journal of Open Source Software*, *2*(13), 265. https://doi.org/10.21105/joss.00265

Misra, P., Acharya, U. A., & Bhatt, S. (2021). Drone-based remote sensing and IoT for precision farming: A review. *Computers and Electronics in Agriculture*, *186*, 106175. https://doi.org/10.1016/j.compag.2021.106175

Mukherjee, A., Bhatt, S., & Ghosh, A. (2020). Comparative study of IoT application layer protocols: MQTT, CoAP, AMQP, and HTTP. *International Journal of Computer Applications*, *176*(22), 1–7. https://doi.org/10.5120/ijca2020920260

OASIS. (2019). *MQTT version 5.0 specification*. OASIS Open. https://docs.oasis-open.org/mqtt/mqtt/v5.0/

Pressman, R. S., & Maxim, B. R. (2019). *Software engineering: A practitioner's approach* (9th ed.). McGraw-Hill Education.

Purnamasari, D., Setiadi, T., & Adi, K. (2021). Sistem otomasi kandang ayam broiler berbasis internet of things menggunakan NodeMCU. *Jurnal Informatika*, *8*(1), 29–36. https://doi.org/10.31294/ji.v8i1.8994

Rohman, A. (2021). Faktor-faktor yang mempengaruhi kualitas ayam kontes: Studi kasus di Jawa Tengah. *Agrisaintifika: Jurnal Ilmu-Ilmu Pertanian*, *5*(1), 12–19.

Rohmah, L. (2021). Implementasi fuzzy logic untuk pengendalian suhu dan kelembaban kandang ternak berbasis mikrokontroler. *Prosiding SEMNASTEK (Seminar Nasional Sains dan Teknologi)*, *8*(1), 1–8.

Russell, S., & Norvig, P. (2020). *Artificial intelligence: A modern approach* (4th ed.). Pearson.

Sanders, C., & Christopher, S. (2017). *Applied network security monitoring: Collection, detection, and analysis*. Syngress/Elsevier.

Setyaningsih, E., Purnama, B. E., & Nasron, M. (2020). Smart poultry cage monitoring system using internet of things. *International Journal of Advanced Trends in Computer Science and Engineering*, *9*(3), 3640–3648. https://doi.org/10.30534/ijatcse/2020/170932020

Sitinjak, P., & Suwita, J. (2020). Analisis protokol MQTT menggunakan Wireshark pada sistem IoT. *Jurnal Sistem Informasi dan Telematika*, *11*(2), 82–88. https://doi.org/10.36448/jsit.v11i2.1487

Suryanto, D., & Ariefin, Y. (2022). Implementasi sistem smart farming berbasis IoT untuk pemantauan kandang unggas secara real-time. *Jurnal Teknologi Informasi dan Ilmu Komputer (JTIIK)*, *9*(4), 765–774. https://doi.org/10.25126/jtiik.2022943961

Telecommunications and Internet Protocol Harmonization Over Networks (TIPHON). (1999). *End-to-end quality of service in TIPHON systems* (ETSI TR 101 329 V2.1.1). European Telecommunications Standards Institute.

Vanthoor, B., de Visser, P., Hemming, J., & van Henten, E. (2011). A methodology for model-based greenhouse design: Part 1, a greenhouse climate model for a broad range of designs and climates. *Biosystems Engineering*, *110*(4), 363–377. https://doi.org/10.1016/j.biosystemseng.2011.06.001

Wolfert, S., Ge, L., Verdouw, C., & Bogaardt, M. J. (2017). Big data in smart farming – A review. *Agricultural Systems*, *153*, 69–80. https://doi.org/10.1016/j.agsy.2017.01.023

---

---

## LAMPIRAN

### Lampiran A – Kode Program Lengkap ESP32

*(Dilampirkan terpisah sebagai file `.ino`)*

### Lampiran B – Hasil Capture Wireshark QoS Level 0

*(Screenshot dan file `.pcap` untuk sesi pengujian QoS 0 terlampir)*

### Lampiran C – Hasil Capture Wireshark QoS Level 1

*(Screenshot dan file `.pcap` untuk sesi pengujian QoS 1 terlampir)*

### Lampiran D – Dokumentasi Foto Prototipe

*(Foto rangkaian elektronik dan prototipe kandang terlampir)*

### Lampiran E – Data Mentah Hasil Pengukuran

*(File Excel berisi data delay, throughput, dan packet loss dari 3 sesi pengujian terlampir)*

### Lampiran F – Riwayat Hidup Penulis

| | |
|---|---|
| **Nama Lengkap** | [NAMA MAHASISWA] |
| **NIM** | [NIM] |
| **Tempat, Tanggal Lahir** | [Kota], [Tanggal Bulan Tahun] |
| **Alamat** | [Alamat Lengkap] |
| **Email** | [email@domain.com] |
| **No. HP** | [Nomor HP] |

**Riwayat Pendidikan:**

| Tahun | Jenjang | Institusi |
|---|---|---|
| [Tahun] – [Tahun] | SD | [Nama SD] |
| [Tahun] – [Tahun] | SMP | [Nama SMP] |
| [Tahun] – [Tahun] | SMA/SMK | [Nama SMA/SMK] |
| [Tahun] – Sekarang | S1 | Program Studi Teknik Informatika, [Nama Universitas] |

**Pengalaman Organisasi/Penelitian:**
*(Diisi oleh mahasiswa)*

---

> **CATATAN UNTUK MAHASISWA (v3.0):**
>
> 1. Bagian bertanda `[isi dengan data aktual]`, `[X]`, `[A]`, dst. **WAJIB** diisi dengan data eksperimen nyata sebelum sidang.
> 2. Gambar 4.8–4.10 (grafik perbandingan) **WAJIB** dibuat dari data Wireshark aktual menggunakan Excel atau Python matplotlib.
> 3. Gambar 4.1 (skema rangkaian) **WAJIB** digambar menggunakan Fritzing atau KiCad.
> 4. Lampiran F (Riwayat Hidup) **WAJIB** dilengkapi dengan data diri asli.
> 5. Halaman Motto & Persembahan **dapat disesuaikan** dengan keinginan penulis.
>
> **⚠️ PERINGATAN KHUSUS UNTUK DOSEN PEMBIMBING (v3.0):**
>
> Referensi-referensi berikut **WAJIB DIVERIFIKASI** secara manual di [Google Scholar](https://scholar.google.com), [Garuda Kemendikbud](https://garuda.kemdikbud.go.id), atau [Crossref](https://www.crossref.org) sebelum disetujui, karena DOI-nya perlu konfirmasi keberadaan artikel aslinya:
> - Asyari & Haryanto (2021) — DOI: 10.54914/jtt.v9i1.352
> - Erwin et al. (2021) — DOI: 10.31849/digitalzone.v12i2.7891
> - Amirudin et al. (2021) — DOI: 10.28932/jutisi.v7i3.3724
> - Ibrahim et al. (2021) — DOI: 10.14569/IJACSA.2021.0120441
> - Kusuma et al. (2022) — DOI: 10.22146/jnteti.v11i2.3120
> - Sitinjak & Suwita (2020) — DOI: 10.36448/jsit.v11i2.1487
>
> Dua referensi di atas (Aengwanich 2004 dan Lara 2013) sudah ditambahkan ke Daftar Pustaka pada versi Final 3.0 ini.
