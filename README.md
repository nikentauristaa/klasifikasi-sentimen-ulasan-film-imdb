# 🎬 Klasifikasi Sentimen Ulasan Film IMDb

## 📖 Deskripsi Proyek

Proyek ini bertujuan untuk melakukan **klasifikasi sentimen ulasan film IMDb** ke dalam dua kelas, yaitu **sentimen positif** dan **sentimen negatif**, menggunakan teknik **Natural Language Processing (NLP)**.

Pada penelitian ini dilakukan **perbandingan performa tiga model**, yaitu **LSTM**, **BERT**, dan **DistilBERT**, untuk mengetahui model mana yang memberikan hasil terbaik dalam tugas analisis sentimen berbasis teks. Seluruh proses implementasi, mulai dari preprocessing data hingga evaluasi model, dilakukan dalam satu file notebook **`UAP.ipynb`**.

---

## 📂 Struktur Repository

```
klasifikasi-sentimen-ulasan-film-imdb
 ┣ 📄 UAP.ipynb
 ┗ 📄 README.md
```

---

## 📊 Dataset

Dataset yang digunakan adalah **IMDb Movie Reviews Dataset**, yang berisi ulasan film berbahasa Inggris dengan label sentimen biner:

* **0** → Sentimen Negatif
* **1** → Sentimen Positif

Karena ukuran dataset cukup besar, dataset **tidak disertakan langsung di repository GitHub**.

🔗 **Link Dataset Resmi:**
[https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews?resource=download](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews?resource=download)

**Informasi Dataset:**

* Total data: 50.000 ulasan film
* Pembagian data: data latih dan data uji
* Jumlah data uji pada evaluasi: **10.000 data (seimbang)**
* Bahasa: Inggris

Dataset diunduh secara mandiri dan diproses langsung di dalam notebook **`UAP.ipynb`**.

---

## ⚙️ Preprocessing Data

Tahapan preprocessing yang dilakukan pada data teks meliputi:

1. Case folding (mengubah teks menjadi huruf kecil)
2. Penghapusan tanda baca dan karakter khusus
3. Tokenisasi teks
4. Penghapusan stopwords
5. Padding dan truncating (khusus untuk model LSTM)
6. Tokenisasi berbasis transformer (khusus untuk BERT dan DistilBERT)

Preprocessing ini bertujuan untuk meningkatkan kualitas representasi teks sebelum masuk ke tahap pelatihan model.

---

## 🧠 Model yang Digunakan

### 1️⃣ LSTM (Long Short-Term Memory)

Model LSTM digunakan untuk menangkap pola urutan kata dan dependensi jangka panjang pada teks ulasan film dengan memanfaatkan embedding layer dan layer LSTM.

### 2️⃣ BERT (Bidirectional Encoder Representations from Transformers)

BERT merupakan model transformer pre-trained yang mampu memahami konteks kata secara dua arah (bidirectional), sehingga menghasilkan representasi teks yang lebih kontekstual.

### 3️⃣ DistilBERT

DistilBERT adalah versi ringan dari BERT yang telah melalui proses distilasi pengetahuan. Model ini memiliki ukuran lebih kecil dan waktu inferensi lebih cepat, namun tetap mempertahankan performa yang kompetitif.

---

## 📈 Hasil Evaluasi Model

Evaluasi model dilakukan menggunakan metrik **precision**, **recall**, **f1-score**, dan **accuracy** pada data uji.

### 🔹 Hasil Detail Tiap Model

#### LSTM

| Kelas        | Precision | Recall | F1-Score |
| ------------ | --------- | ------ | -------- |
| Negatif (0)  | 0.65      | 0.85   | 0.74     |
| Positif (1)  | 0.79      | 0.55   | 0.65     |
| **Accuracy** |           |        | **0.70** |

#### BERT

| Kelas        | Precision | Recall | F1-Score |
| ------------ | --------- | ------ | -------- |
| Negatif (0)  | 0.59      | 0.78   | 0.68     |
| Positif (1)  | 0.68      | 0.47   | 0.55     |
| **Accuracy** |           |        | **0.62** |

#### DistilBERT

| Kelas        | Precision | Recall | F1-Score |
| ------------ | --------- | ------ | -------- |
| Negatif (0)  | 0.76      | 0.63   | 0.69     |
| Positif (1)  | 0.69      | 0.80   | 0.74     |
| **Accuracy** |           |        | **0.72** |

---

## 📊 Tabel Perbandingan Model

| Model          | Accuracy | Kelebihan                               | Kekurangan                                          |
| -------------- | -------- | --------------------------------------- | --------------------------------------------------- |
| LSTM           | 0.70     | Stabil, mampu memahami urutan kata      | Kurang optimal dalam menangkap konteks global       |
| BERT           | 0.62     | Representasi teks kontekstual           | Performa kurang optimal pada konfigurasi eksperimen |
| **DistilBERT** | **0.72** | Cepat, ringan, performa paling seimbang | Sedikit lebih rendah dari BERT full-scale           |

---

## 📌 Analisis Perbandingan

Berdasarkan hasil evaluasi, **DistilBERT** menunjukkan performa terbaik dengan **accuracy tertinggi (72%)** serta keseimbangan precision dan recall yang lebih baik dibandingkan LSTM dan BERT.

Model LSTM memiliki performa cukup baik, namun masih terbatas dalam menangkap konteks global kalimat. Sementara itu, model BERT menunjukkan performa terendah, yang kemungkinan disebabkan oleh keterbatasan konfigurasi pelatihan, seperti jumlah epoch atau parameter fine-tuning.

---

## ▶️ Panduan Menjalankan Program Secara Lokal

1. Clone repository:

```bash
git clone https://github.com/nikentauristaa/klasifikasi-sentimen-ulasan-film-imdb.git
```

2. Masuk ke folder project:

```bash
cd klasifikasi-sentimen-ulasan-film-imdb
```

3. Jalankan notebook:

```bash
jupyter notebook UAP.ipynb
```

4. Jalankan seluruh cell secara berurutan untuk melihat proses dan hasil eksperimen.

---

## 👤 Author

**Nama:** Niken Permata
**Mata Kuliah:** Ujian Akhir Praktikum
**Program Studi:** (isi prodi)
**Universitas:** (isi kampus)

---

## 🔗 Live Demo

Belum tersedia.
