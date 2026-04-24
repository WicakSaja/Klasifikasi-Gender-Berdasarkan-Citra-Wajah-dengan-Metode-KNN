--------------------------------------------------------------------------------
📊 Klasifikasi Gender Berdasarkan Citra Wajah menggunakan KNN (Lanjutan Ekstraksi Fitur)
📌 Deskripsi
Project ini merupakan materi lanjutan yang bertujuan untuk melakukan klasifikasi gender (male/female) menggunakan algoritma K-Nearest Neighbor (KNN)
. Klasifikasi ini didasarkan pada dataset ekstraksi fitur citra wajah yang telah dibuat pada tahap sebelumnya menggunakan metode fitur warna (HSV) dan fitur tekstur (GLCM)
.
🧠 Metode yang Digunakan
Ekstraksi Fitur Warna (HSV) dan Tekstur (GLCM) (Telah diselesaikan pada tahap sebelumnya)
.
Pra-pemrosesan Data (Data Preprocessing):
Data Split: Pemisahan data latih (training) sebesar 80% dan data uji (testing) sebesar 20%.
Feature Scaling: Menggunakan StandardScaler untuk menyamakan rentang skala antar fitur (Sangat krusial untuk mencegah dominasi fitur bernilai besar seperti contrast terhadap fitur bernilai kecil seperti energy).
Klasifikasi KNN (K-Nearest Neighbor)
:
Hyperparameter Tuning: Mencari nilai tetangga terbaik (n_neighbors) dengan melakukan perulangan (looping) dari K=1 hingga 14.
Evaluasi Model:
Classification Report (Precision, Recall, F1-Score, dan Accuracy).
Confusion Matrix (Heatmap).
📂 Struktur Dataset
Dataset citra wajah asli berasal dari: Indonesian Public Figure Faces (https://www.kaggle.com/datasets/arifnuriman/indonesian-public-figure-faces)
. ⚠️ PENTING: Untuk menjalankan tahap klasifikasi ini, pastikan Anda telah memiliki output data berupa fitur_citra_wajah.csv dari hasil ekstraksi fitur citra wajah laki-laki (male) dan perempuan (female) sebelumnya
.
⚙️ Cara Menjalankan
1. Mount Google Drive (Google Colab)
Hubungkan environment Anda dengan Google Drive untuk mengakses dataset.
2. Persiapan Data (Load CSV)
Muat dataset fitur_citra_wajah.csv yang berisi fitur HSV & GLCM beserta labelnya
.
Pisahkan fitur utama (X) dan label target (y).
3. Data Splitting & Feature Scaling
Lakukan pemisahan data latih dan data uji menggunakan train_test_split.
Lakukan transformasi standar (StandardScaler) agar rata-rata fitur menjadi 0 dan standar deviasi menjadi 1.
4. Training Model & Tuning
Latih model menggunakan algoritma KNN
.
Jalankan proses Hyperparameter Tuning untuk mencari nilai K yang menghasilkan akurasi tetinggi.
5. Testing & Evaluasi
Sistem akan memprediksi gender dari data uji menggunakan Final Model
.
Analisis hasil evaluasi klasifikasi menggunakan Confusion Matrix.
📊 Output & Hasil Klasifikasi
Best n_neighbors (K): 9
Akurasi Terbaik (Total): 0.6097 (~61%)
Hasil Evaluasi: Berhasil memprediksi dengan tepat 12 True Female dan 13 True Male dari 41 data pengujian (berdasarkan Confusion Matrix).
File dataset fitur masih berformat .csv dan hasil klasifikasi akan ditampilkan sebagai log / grafik pada output visual
.
⚠️ Catatan
Feature Scaling wajib dilakukan! Tanpa proses ini, akurasi bisa anjlok (hanya ~25%) karena metrik perhitungan jarak Euclidean akan kacau.
Dataset tergolong kecil → akurasi belum optimal (~61%), sehingga perlu penambahan data agar performa presisi model meningkat
.
👨‍💻 Author
Project ini dibuat untuk keperluan materi Computer Vision 2026 – Ekstraksi Fitur dan Klasifikasi Lanjutan
.
