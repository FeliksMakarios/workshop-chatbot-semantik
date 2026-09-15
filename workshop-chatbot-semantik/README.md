# Workshop Chatbot Cerdas dengan AI

Materi workshop pemrosesan bahasa alami untuk siswa SMA. Peserta membangun chatbot yang
memahami makna pertanyaan, bukan sekadar mencocokkan kata kunci, memakai model transformer
dan teknik pencarian semantik.

Peserta memilih sendiri temanya: **tempat wisata dunia** atau **sejarah dunia**.

---

## Mulai di sini

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/FeliksMakarios/workshop-chatbot-semantik/blob/main/chatbot_workshop_SISWA.ipynb)

Klik tombol biru di atas untuk membuka notebook workshop di Google Colab.

---

## Lima langkah untuk peserta

1. **Klik tombol "Open in Colab"** di atas. Notebook akan terbuka di browser, tidak perlu memasang apa pun di laptop.
2. **Simpan salinanmu sendiri.** Di menu atas pilih `File` lalu `Save a copy in Drive`. Tanpa langkah ini, sel tidak bisa kamu ubah dan pekerjaanmu tidak tersimpan. Kerjakan pada tab baru yang terbuka.
3. **Jalankan sel persiapan di Bagian 0 sekarang juga.** Sel ini butuh satu sampai dua menit karena sedang mengunduh model AI. Jalankan sambil menunggu penjelasan pemateri. Tunggu sampai muncul tulisan `MODEL SIAP DIPAKAI`.
4. **Ikuti notebook dari atas ke bawah.** Jalankan sel berurutan, jangan melompat. Baca tulisan di antara sel kode karena di situ penjelasannya. Sel bertanda **TUGAS** adalah bagian yang kamu kerjakan sendiri.
5. **Kalau ada masalah, panggil pemateri.** Jangan menghapus sel atau mengubah bagian yang bukan TUGAS. Tulisan merah panjang itu hal biasa dan bisa diperbaiki.

Perkiraan waktu praktik: 40 menit.

---

## Apa yang akan kamu pelajari

1. Cara komputer mengubah kalimat menjadi deretan angka yang disebut vektor
2. Cara mengukur kemiripan makna dua kalimat lewat angka tersebut
3. Cara membangun chatbot yang tetap paham meski pertanyaan disusun dengan kata yang berbeda
4. Cara mengajari sistem AI berkata "tidak tahu" ketika pertanyaan di luar pengetahuannya
5. Perbedaan nyata antara pencocokan kata kunci dan pencocokan makna

---

## Isi repositori

| Berkas | Keterangan |
|---|---|
| `chatbot_workshop_SISWA.ipynb` | Notebook utama untuk peserta |
| `data/faq_wisata.csv` | 24 pasang tanya jawab tempat wisata dunia dan Indonesia |
| `data/faq_sejarah.csv` | 24 pasang tanya jawab peristiwa sejarah dunia |
| `fasilitator/chatbot_workshop_KUNCI.ipynb` | Versi lengkap dengan semua TUGAS terisi |
| `docs/PANDUAN_FASILITATOR.md` | Rundown 90 menit, persiapan, dan penanganan masalah |

Notebook memuat berkas CSV langsung dari repositori ini, jadi peserta tidak perlu
mengunduh apa pun secara manual.

---

## Catatan teknis

Model yang dipakai adalah
[`sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2`](https://huggingface.co/sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2),
berlisensi Apache 2.0, berukuran sekitar 100 juta parameter, menghasilkan vektor sepanjang
384 angka, dan mendukung 50 bahasa termasuk Bahasa Indonesia.

Notebook tidak memasang pustaka tambahan apa pun dan berjalan pada runtime CPU bawaan Colab.
Tidak perlu GPU.

---

## Untuk fasilitator

Baca [`docs/PANDUAN_FASILITATOR.md`](docs/PANDUAN_FASILITATOR.md) sebelum menyelenggarakan sesi.
Panduan itu memuat rundown 90 menit, kerangka penjelasan, pertanyaan pemantik, tabel penanganan
masalah, dan daftar hal yang masih perlu diuji sendiri.
