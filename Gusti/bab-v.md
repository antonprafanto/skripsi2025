# Audit — BAB V: Kesimpulan dan Saran

**Halaman isi:** 72–73 (PDF hal. 88–89)  
**Status:** Cukup — revisi minor

---

## Ringkasan Bab

Bab V ringkas: 4 poin kesimpulan selaras hasil pengujian; 3 poin saran pengembangan lanjutan. Panjang **sesuai** untuk penutup skripsi.

**Nilai substansi:** 7,5/10  
**Nilai format:** 8/10

---

## 5.1 Kesimpulan

| Poin | Isi | Evaluasi |
|------|-----|----------|
| 1 | Sistem chatbot + Waterfall + integrasi Resmeku | ✓ Selaras Bab IV |
| 2 | Blackbox 100% | ✓ |
| 3 | UAT 86% Sangat Sesuai | ✓ |
| 4 | Efektif mendukung layanan informasi KB | ✓ |

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| Sedang | Poin 1: *"terintegrasi langsung ke dalam ekosistem platform Resmeku"* — sebenarnya sistem **terpisah** + embed | Sesuaikan: *"terintegrasi melalui widget embed tanpa modifikasi inti platform"* |
| OK | Kesimpulan tidak over-claim (tidak klaim RAG/ML) | — |

---

## 5.2 Saran

| Poin | Isi | Evaluasi |
|------|-----|----------|
| 1 | Pertimbangkan **RAG** | ⚠ Perlu framing |
| 2 | Perluas & perbarui KB | ✓ Masuk akal |
| 3 | **Hybrid** rule-based + AI | ✓ Masuk akal |

### Temuan

| Prioritas | Temuan | Saran |
|-----------|--------|-------|
| **Wajib** | Saran #1 RAG seolah penelitian **belum** punya KB — padahal inti penelitian = **KB terstruktur + prompt injection** | Tambahkan: *"Saat ini sistem menggunakan injeksi KB ke system prompt; RAG dengan retrieval semantik/embedding dapat meningkatkan akurasi pada skenario kompleks (cf. Skenario 7 & 10)."* |
| Sedang | Saran #3 hybrid — bagus, tapi tidak disebut di Bab I–IV | OK sebagai future work |
| OK | 3 saran = jumlah wajar | — |

---

## Kesimpulan Bab V

Bab V **tidak perlu diperpanjang**. Cukup **perjelas poin 1 kesimpulan** (embed vs monolith) dan **frame saran RAG** sebagai evolusi teknis, bukan koreksi kesalahan penelitian.
