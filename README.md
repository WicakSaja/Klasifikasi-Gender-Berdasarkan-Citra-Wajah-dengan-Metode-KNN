# 📊 Klasifikasi Gender Berdasarkan Citra Wajah Menggunakan KNN  
## (Lanjutan Ekstraksi Fitur)

## 📌 Deskripsi
Project ini merupakan tahap lanjutan untuk melakukan **klasifikasi gender (male/female)** menggunakan algoritma **K-Nearest Neighbor (KNN)**.

Proses klasifikasi dilakukan berdasarkan dataset hasil **ekstraksi fitur citra wajah**, yang pada tahap sebelumnya telah diekstrak menggunakan:

- **Fitur Warna (HSV)**
- **Fitur Tekstur (GLCM)**

---

## 🧠 Metode yang Digunakan

### 1. Ekstraksi Fitur
Tahap ekstraksi fitur telah dilakukan sebelumnya dengan metode:

- **HSV (Hue, Saturation, Value)** untuk fitur warna
- **GLCM (Gray Level Co-occurrence Matrix)** untuk fitur tekstur

### 2. Pra-pemrosesan Data
Meliputi beberapa tahapan:

- **Data Split**  
  Data dibagi menjadi:
  - **80% data latih**
  - **20% data uji**

- **Feature Scaling**  
  Menggunakan `StandardScaler` untuk menyamakan skala seluruh fitur agar tidak terjadi dominasi fitur dengan nilai besar seperti `contrast` terhadap fitur kecil seperti `energy`.

### 3. Klasifikasi KNN
Model klasifikasi menggunakan algoritma **K-Nearest Neighbor (KNN)**.

- **Hyperparameter Tuning**  
  Dilakukan pencarian nilai `n_neighbors` terbaik dengan iterasi nilai **K = 1 sampai 14**.

### 4. Evaluasi Model
Evaluasi dilakukan menggunakan:

- **Classification Report**
  - Precision
  - Recall
  - F1-Score
  - Accuracy

- **Confusion Matrix**
  - Ditampilkan dalam bentuk **heatmap**

---

## 📂 Struktur Dataset

Dataset citra wajah asli berasal dari Kaggle:

**Indonesian Public Figure Faces**  
https://www.kaggle.com/datasets/arifnuriman/indonesian-public-figure-faces

> ⚠️ **Penting:**  
> Untuk menjalankan tahap klasifikasi ini, pastikan Anda telah memiliki file hasil ekstraksi fitur berupa `fitur_citra_wajah.csv` yang berisi fitur wajah **male** dan **female** dari tahap sebelumnya.

---

## ⚙️ Cara Menjalankan

### 1. Mount Google Drive
Hubungkan Google Colab dengan Google Drive untuk mengakses dataset.

### 2. Load Dataset CSV
Muat file `fitur_citra_wajah.csv`, lalu pisahkan:

- **X** → fitur HSV & GLCM
- **y** → label gender

### 3. Data Splitting & Feature Scaling
- Gunakan `train_test_split` untuk membagi data latih dan data uji
- Gunakan `StandardScaler` untuk standarisasi fitur

### 4. Training Model & Hyperparameter Tuning
- Latih model menggunakan **KNN**
- Cari nilai **K terbaik** berdasarkan akurasi tertinggi

### 5. Testing & Evaluasi
- Lakukan prediksi pada data uji menggunakan model terbaik
- Evaluasi hasil menggunakan **Confusion Matrix** dan **Classification Report**

---

## 📊 Output & Hasil Klasifikasi

Hasil terbaik yang diperoleh:

- **Best n_neighbors (K):** `9`
- **Akurasi Terbaik:** `0.6097` (~61%)

### Hasil Confusion Matrix:
- **12** data **Female** terklasifikasi benar
- **13** data **Male** terklasifikasi benar

Total data pengujian: **41 data**

Output klasifikasi akan ditampilkan dalam bentuk:

- **Log evaluasi**
- **Visualisasi grafik / heatmap**

---

## ⚠️ Catatan Penting

### Feature Scaling Wajib Dilakukan
Tanpa proses scaling, akurasi model dapat turun drastis hingga sekitar **25%**, karena algoritma KNN menggunakan **Euclidean Distance** yang sensitif terhadap skala fitur.

### Ukuran Dataset Masih Kecil
Akurasi saat ini masih sekitar **61%**, sehingga performa model masih dapat ditingkatkan dengan:

- Menambah jumlah data latih
- Menambahkan fitur yang lebih representatif
- Melakukan optimasi parameter lebih lanjut

---

## 👨‍💻 Author
Project ini dibuat untuk keperluan materi **Computer Vision 2026 – Ekstraksi Fitur dan Klasifikasi Lanjutan**.
