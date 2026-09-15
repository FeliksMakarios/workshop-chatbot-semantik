# Panduan Fasilitator
## Workshop Chatbot Cerdas dengan AI, 90 Menit untuk Siswa SMA

---

## 1. Isi repositori

| Berkas | Untuk siapa | Keterangan |
|---|---|---|
| `README.md` | Peserta | Halaman depan repo, memuat tombol Open in Colab dan lima langkah awal |
| `chatbot_workshop_SISWA.ipynb` | Peserta | Notebook utama, bagian TUGAS masih kosong |
| `data/faq_wisata.csv` | Peserta | 24 pasang tanya jawab tempat wisata |
| `data/faq_sejarah.csv` | Peserta | 24 pasang tanya jawab sejarah dunia |
| `fasilitator/chatbot_workshop_KUNCI.ipynb` | Anda | Versi lengkap, semua TUGAS terisi |
| `docs/PANDUAN_FASILITATOR.md` | Anda | Berkas ini |

Peserta memilih sendiri mau tema wisata atau sejarah lewat menu di dalam notebook.
Kedua tema memakai notebook yang sama persis, jadi hanya ada satu berkas notebook peserta.

**Catatan soal notebook kunci.** Repositori publik berarti peserta bisa menemukan berkas kunci
kalau mereka menelusuri folder. Isinya hanya contoh jawaban TUGAS, bukan kunci ujian, jadi
umumnya tidak masalah. Kalau Anda lebih suka peserta tidak menemukannya, hapus folder
`fasilitator` dari repositori dan simpan berkas itu di laptop Anda sendiri.

---

## 2. Persiapan sebelum hari pelaksanaan

### Langkah 2.1. Buat repositori

1. Buat repositori baru di GitHub dengan nama **`workshop-chatbot-semantik`**
2. Atur sebagai **Public**. Colab tidak bisa membuka notebook dari repositori privat tanpa proses masuk, dan peserta pasti tidak punya akses itu
3. Unggah seluruh isi folder ini, termasuk struktur foldernya (`data/`, `fasilitator/`, `docs/`)
4. Pastikan nama cabang utamanya `main`, yaitu bawaan GitHub saat ini

**Kalau Anda memakai nama repo yang berbeda**, ubah dua tempat berikut:

1. Baris `GITHUB_REPO` di sel Bagian 2 pada kedua notebook
2. Dua alamat pada tombol Open in Colab di `README.md`

### Langkah 2.2. Pastikan alamat datanya hidup

Buka alamat berikut di browser. Isi berkas CSV harus langsung tampil sebagai teks biasa.

```
https://raw.githubusercontent.com/FeliksMakarios/workshop-chatbot-semantik/main/data/faq_wisata.csv
https://raw.githubusercontent.com/FeliksMakarios/workshop-chatbot-semantik/main/data/faq_sejarah.csv
```

Kalau yang muncul halaman 404, berarti repositori masih privat atau letak berkasnya berbeda.

### Langkah 2.3. Tempelkan link kuesioner

Pada notebook peserta, sel teks paling akhir memuat tulisan `GANTI_DENGAN_LINK_KUESIONER`.
Ganti dengan link kuesioner Anda supaya peserta tidak perlu mencatat link secara manual.

### Langkah 2.4. Siapkan link pendek

Alamat repositori sudah cukup pendek untuk diketik, yaitu `github.com/FeliksMakarios/workshop-chatbot-semantik`.
Kalau ingin lebih pendek lagi, buat pengalihan lewat s.id atau bit.ly.
Pilih akhiran yang gampang diketik dan hindari huruf yang mirip angka.
Tuliskan link itu besar-besar di papan atau slide pembuka.

Arahkan peserta ke halaman depan repositori, bukan langsung ke berkas notebook.
Halaman depan sudah memuat tombol Open in Colab dan lima langkah awal.

### Langkah 2.5. Uji coba penuh, jangan dilewati

1. Buka notebook kunci lewat Colab, jalankan semua sel dari atas sampai bawah untuk kedua tema
2. Catat berapa lama sel persiapan berjalan
3. Perhatikan rentang skor yang muncul di TUGAS 3, lalu sesuaikan nilai awal `AMBANG` di notebook peserta kalau perlu
4. Uji juga lewat mode penyamaran atau akun Google lain untuk memastikan repositori benar-benar publik

### Langkah 2.6. Periksa jaringan lokasi

Peserta hanya butuh akses browser ke dua domain, yaitu `colab.research.google.com` dan `github.com`.
Pengunduhan model dan pembacaan berkas CSV terjadi di server Google, bukan di laptop peserta,
jadi kecepatan jaringan lokasi tidak memengaruhi keduanya.

---

## 3. Rundown 90 menit

| Waktu | Durasi | Kegiatan |
|---|---|---|
| 00.00 sampai 00.15 | 15 menit | Pembukaan dan setup. Peserta membuka repositori, klik Open in Colab, menyimpan salinan ke Drive masing-masing, lalu **langsung menjalankan sel persiapan di Bagian 0** |
| 00.15 sampai 00.32 | 17 menit | Penjelasan konsep dan demo dari notebook kunci |
| 00.32 sampai 01.15 | 43 menit | Praktik mandiri, Anda berkeliling |
| 01.15 sampai 01.30 | 15 menit | Pengisian kuesioner dan foto bersama |

**Kunci efisiensi waktu:** suruh peserta menjalankan sel persiapan sejak menit-menit awal,
sebelum Anda mulai menjelaskan. Pengunduhan model berjalan di server Google sambil Anda bicara,
sehingga saat masuk sesi praktik semua peserta sudah siap.

### Alokasi 43 menit praktik

| Bagian | Menit |
|---|---|
| Bagian 0 sampai 1, persiapan dan intuisi vektor | 8 |
| Bagian 2 sampai 3, memuat data dan membangun chatbot | 8 |
| TUGAS 1, uji dengan kalimat sendiri | 6 |
| TUGAS 2, menambah pengetahuan sendiri | 10 |
| TUGAS 3, ambang batas | 6 |
| TUGAS 4, bonus, dan sesi ngobrol | sisa |

TUGAS 1 sampai 3 adalah inti. TUGAS 4 dan bagian bonus boleh dilewati kalau waktu menipis.

---

## 4. Kerangka penjelasan 17 menit

1. **Menit 1 sampai 3.** Tanya peserta: pernah bertanya ke mesin pencari atau asisten suara lalu jawabannya meleset? Kenapa bisa begitu?
2. **Menit 3 sampai 7.** Jelaskan bahwa komputer tidak mengerti huruf, komputer mengerti angka. Pakai analogi peta: kalimat bermakna mirip diletakkan berdekatan di peta, kalimat berbeda makna diletakkan berjauhan.
3. **Menit 7 sampai 11.** Demo Bagian 1 dari notebook kunci. Tunjukkan dua kalimat berbeda susunan kata yang skornya tinggi, dan satu kalimat asing yang skornya rendah.
4. **Menit 11 sampai 15.** Jelaskan tiga langkah kerja chatbot: ubah semua pertanyaan di tabel jadi vektor, ubah pertanyaan pengguna jadi vektor, ambil yang paling dekat. Demo Bagian 3.
5. **Menit 15 sampai 17.** Tunjukkan letak bagian TUGAS, tegaskan aturan main, persilakan mulai.

Istilah yang layak disebut sekali dan ditulis di papan: **vektor**, **transformer**, **pencarian semantik**.

---

## 5. Pertanyaan pemantik saat berkeliling

1. Kenapa skor dua kalimat yang mirip tidak pernah tepat 1.000?
2. Kalau sekolahmu mau memakai chatbot ini untuk menjawab pertanyaan siswa baru, data apa yang harus disiapkan lebih dulu?
3. Apa bedanya chatbot ini dengan ChatGPT? Jawaban yang diharapkan: chatbot ini hanya memilih dari jawaban yang sudah ditulis manusia, sedangkan ChatGPT menyusun kalimat baru.
4. Apa yang terjadi kalau tabel pengetahuannya berisi informasi yang salah?

Pertanyaan nomor 4 adalah pintu masuk paling bagus untuk bicara soal tanggung jawab dalam memakai AI.

---

## 6. Penanganan masalah

| Gejala | Penyebab paling mungkin | Tindakan |
|---|---|---|
| Sel persiapan berjalan sangat lama | Model sedang diunduh pertama kali | Wajar, tunggu sampai muncul MODEL SIAP DIPAKAI. Kalau lewat 5 menit, minta peserta memilih Runtime lalu Restart session, dan menjalankan ulang |
| `HTTPError 404` saat memuat data | Repositori masih privat, nama repo berbeda, atau letak berkas tidak sesuai | Periksa Langkah 2.1 dan 2.2. Sementara itu arahkan peserta ke Lampiran A di notebook untuk mengunggah CSV secara manual |
| Colab bilang notebook tidak ditemukan | Repositori privat, atau nama cabang bukan `main` | Ubah repositori menjadi publik, atau sesuaikan alamat pada tombol Open in Colab |
| Peserta tidak bisa mengedit sel | Peserta membuka notebook langsung dari GitHub tanpa menyalin | Minta peserta memilih File lalu Save a copy in Drive, lalu bekerja pada salinannya |
| Muncul tombol RESTART SESSION | Ada peserta yang menjalankan Lampiran B | Tekan tombol itu, lalu jalankan ulang dari Bagian 0 |
| `NameError: cari_jawaban` | Peserta melompati sel | Minta peserta memilih Runtime lalu Run all, atau menjalankan ulang berurutan dari Bagian 0 |
| Chatbot menjawab ngawur untuk pertanyaan yang benar | Nilai AMBANG kebetulan kelewat tinggi | Turunkan nilai AMBANG, ini justru bahan diskusi yang bagus |
| Peserta tidak punya akun Google | Colab butuh akun Google | Siapkan beberapa laptop cadangan yang sudah masuk akun, atau pasangkan peserta berdua |

---

## 7. Catatan teknis

### Model yang dipakai

`sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2`, model resmi dari proyek
sentence-transformers, berlisensi Apache 2.0, berukuran sekitar 100 juta parameter,
menghasilkan vektor sepanjang 384 angka, dan mendukung 50 bahasa termasuk Bahasa Indonesia.

### Kenapa tidak memakai API model bahasa besar

Memanggil API seperti ChatGPT atau Gemini menuntut kunci API untuk tiap peserta,
menambah risiko kuota habis, dan menambah satu lapisan setup. Pendekatan pencarian semantik
tetap memakai model transformer sungguhan, berjalan sepenuhnya di dalam Colab, dan tanpa biaya.

### Kenapa notebook tidak memasang pustaka apa pun di awal

Notebook memakai pustaka `transformers` yang sudah tersedia di Colab, sehingga tidak ada
waktu terbuang untuk pemasangan dan tidak ada risiko munculnya permintaan restart di tengah sesi.
Kalau Anda tetap ingin memakai pustaka `sentence-transformers`, Lampiran B di notebook menyediakannya.
Sel persiapan mengenali sendiri pustaka mana yang tersedia, dan hasil kedua jalur identik.

### Tidak perlu GPU

Jumlah data sangat kecil, jadi runtime CPU bawaan Colab sudah cukup.
Justru jangan menyuruh peserta mengganti runtime ke GPU karena hanya menambah waktu.

### Memperbarui materi setelah workshop

Notebook membaca CSV dari cabang `main` secara langsung. Setiap kali Anda mengubah isi
berkas di folder `data`, notebook peserta ikut memakai data terbaru tanpa perlu diubah.

---

## 8. Batas pengujian yang sudah dan belum dilakukan

**Sudah diverifikasi:**

1. Struktur JSON kedua notebook valid dan terbaca sebagai notebook Jupyter
2. Seluruh sel kode lolos pemeriksaan sintaks Python
3. Alur logika lengkap dijalankan untuk kedua tema pada kedua versi notebook, memakai encoder tiruan sebagai pengganti model asli
4. Semua fungsi terbentuk pada urutan yang benar, dan penambahan pengetahuan di TUGAS 2 benar-benar menambah isi tabel
5. Kedua berkas CSV terbaca pandas, tanpa sel kosong, tanpa pertanyaan kembar
6. Nama fungsi dan parameter pustaka `sentence-transformers` dicocokkan langsung dengan kode sumber versi 6.0.1
7. Pembacaan CSV lewat `pandas.read_csv` dari alamat `raw.githubusercontent.com` diuji dengan berkas nyata dan berhasil
8. Pola alamat Colab untuk membuka notebook dari GitHub dicocokkan dengan notebook demo resmi Google

**Belum diverifikasi, wajib Anda uji sendiri lewat Langkah 2.5:**

1. Pengunduhan model sungguhan beserta lama waktunya, karena huggingface.co tidak bisa diakses dari lingkungan tempat berkas ini dibuat
2. Nilai skor kemiripan yang sebenarnya, termasuk apakah angka awal `AMBANG` sebesar 0.5 sudah pas
3. Ketepatan jawaban chatbot pada pertanyaan parafrase, karena pengujian memakai encoder tiruan yang tidak mengandung makna
4. Pemuatan CSV dari repositori Anda sendiri, karena alamatnya baru hidup setelah repositori dibuat

---

## 9. Saran penutup sesi

Sisakan tiga menit sebelum kuesioner untuk bertanya ke peserta: menurut kalian, di mana lagi
cara kerja seperti ini dipakai dalam kehidupan sehari-hari? Jawaban yang biasanya muncul antara lain
mesin pencari, fitur bantuan aplikasi, dan rekomendasi video. Tutup dengan pesan bahwa kualitas
sistem AI sangat ditentukan kualitas data yang diberikan manusia kepadanya.
