# Audit — BAB II: Tinjauan Pustaka

**Halaman:** 6–30 (PDF ~25–49)  
**Status:** Baik secara substansi; perlu perbaikan minor

---

## Ringkasan Bab

Bab II komprehensif dan relevan: mHealth, Android, Jetpack Compose, Laravel, prototype, UML, Black Box, EP/BVA. **Firebase & Figma** ada di teori/istilah tetapi kurang selaras dengan implementasi.

**Nilai substansi:** 8,5/10  
**Nilai konsistensi dengan implementasi:** 7/10

---

## Yang Sudah Baik

- Landasan mHealth & aplikasi kesehatan didukung literatur terkini
- Penjelasan Jetpack Compose, Laravel cukup mendalam
- Firebase & FCM dipakai di implementasi (landasan teori Bab II masih tipis)
- Metode prototype (Evolutionary) dijelaskan dengan tahapan jelas
- UML (Use Case, Sequence, Class) dan Black Box Testing diuraikan dengan baik
- Persamaan 2.1 (persentase keberhasilan) relevan untuk Bab IV

---

## Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Disarankan | **§2.8 XAMPP** dijelaskan panjang, tetapi implementasi memakai **Laravel** (bukan stack XAMPP sebagai fokus) | Singkatkan XAMPP sebagai lingkungan dev lokal ATAU jelaskan bahwa Laravel dijalankan via XAMPP/artisan serve |
| Disarankan | **EP & BVA** dijelaskan (§2.12), tetapi Bab IV hanya menyebut **Black Box** tanpa label EP/BVA pada skenario | Tambahkan 1–2 contoh skenario EP/BVA di Bab IV ATAU kurangi penekanan EP/BVA di Bab II |
| Disarankan | Beberapa URL DOI di Daftar Pustaka **rusak** (spasi, karakter aneh) — contoh entri Ismail & Efendi | Perbaiki format DOI: `https://doi.org/10.xxxx/...` |
| Disarankan | **ISO 25010** disebut di Tabel 2.1 (penelitian terdahulu) tetapi penelitian ini memakai **Tabel 2.5 (Dewi et al.)** — bukan ISO 25010 | Jelaskan pemilihan instrumen kelayakan atau samakan terminologi |
| Disarankan | Inkonsistensi penulisan **back-end / Back-end / Back-End** di caption gambar | Seragamkan (disarankan **back-end** atau **Back-End**) |
| Disarankan | **Gambar 2.2** (Tahapan Metode Prototype) ada di Bab II, **tidak di Daftar Gambar** | Tambahkan ke Daftar Gambar |
| Disarankan | **Figma §2.13** di teori, praktik memakai **wireframe** — tidak dijelaskan | Hubungkan atau singkatkan §2.13 |
| Disarankan | **Firebase** inti sistem, **tidak ada subbab teori** Bab II | Tambahkan landasan Firebase singkat |
| Disarankan | **Tidak ada diagram ERD** — hanya Tabel 3.1–3.7 | Tambahkan ERD jika diwajibkan |
| Disarankan | Paragraf **kebaruan §2.1** menyebut **admin**, belum **Super Admin** | Perbarui setelah iterasi 2 |
| Opsional | Caption Gambar 2.2: **"Roger S & Pressman,  2010"** — format tidak standar | **Pressman, R. S. (2010)** |

---

## Konsistensi Istilah

| Istilah | Status |
|---------|--------|
| Prototype / Prototyping | Konsisten |
| Black Box Testing | Konsisten |
| Jetpack Compose vs XML | Jelas — Compose dipakai |
| REST API | Konsisten dengan Bab III–IV |

---

## Checklist Revisi Bab II

```
[ ] Selaraskan XAMPP dengan stack aktual (Laravel)
[ ] EP/BVA: hubungkan ke Bab IV atau kurangi di teori
[ ] Tambahkan Gambar 2.2 ke Daftar Gambar
[ ] Jelaskan wireframe vs Figma; tambahkan teori Firebase
[ ] Deklarasikan Evolutionary Prototyping di Bab III §3.1
[ ] Perbarui paragraf kebaruan (Super Admin)
[ ] (Lintas bab) Perbaiki DOI rusak di Daftar Pustaka
```

**Estimasi waktu:** 1–2 jam
