# Midterm Exam: Deep Learning Portfolio

**Nama:** ANOM NUR MAULID
**NIM:** 1103223193
**Kelas:** TK-46-01

## 🧠 Overview
Repository ini merupakan submisi resmi untuk Ujian Tengah Semester (UTS) mata kuliah **Deep Learning**. Proyek ini berfokus pada implementasi arsitektur **Artificial Neural Networks (ANN)** untuk menyelesaikan dua permasalahan kompleks: **Fraud Detection** (Klasifikasi) dan **Song Year Prediction** (Regresi).

Semua model dibangun menggunakan framework **TensorFlow/Keras** dengan akselerasi GPU.

---

## 🛡️ Project 1: Fraud Detection (Classification)

### 1. Objective
Membangun pipeline Deep Learning yang mampu mendeteksi probabilitas transaksi penipuan (*fraud*) dari dataset IEEE-CIS yang sangat besar dan tidak seimbang.

### 2. Methodology
* **Data Engineering:**
    * **Merging:** Menggabungkan tabel Transaksi dan Identitas (`train_transaction` + `train_identity`) untuk memperkaya fitur.
    * **Optimization:** Menggunakan `Polars` untuk kecepatan I/O dan manajemen RAM yang efisien.
* **Preprocessing:**
    * Encoding variabel kategori, mengisi missing values (-1), dan standarisasi data.
* **Deep Learning Architecture:**
    * **Architecture:** 3 Hidden Layers (Dense/ReLU) + BatchNormalization + Dropout.
    * **Output Layer:** 1 Neuron dengan aktivasi **Sigmoid** (Output probabilitas 0-1).
* **Training Strategy:**
    * **Imbalance Handling:** Menggunakan **Class Weights** manual untuk memastikan model fokus pada kelas minoritas (Fraud).

### 3. Results
* **Metric:** AUC Score (Area Under Curve).
* **Validation AUC:** Mencapai sekitar **~0.85**.
* **Conclusion:** Arsitektur Deep Learning terbukti stabil dan efektif dalam memprediksi Fraud pada data yang kompleks dan tidak seimbang.

---

## 🎵 Project 2: Song Year Prediction (Regression)

### 1. Objective
Memprediksi tahun rilis lagu (nilai kontinu) menggunakan Deep Neural Network berdasarkan 90 fitur audio (Timbre).

### 2. Methodology
* **Preprocessing:**
    * **Fix Load:** Membaca data dengan `header=None` untuk menghindari kehilangan baris data.
    * **Standard Scaler:** Wajib dilakukan agar Neural Network dapat konvergen dengan cepat.
* **Deep Learning Architecture:**
    * **Architecture:** Menggunakan 3 Hidden Layers (256 -> 128 -> 64 neuron) dengan aktivasi ReLU.
    * **Output Layer:** 1 Neuron dengan aktivasi **Linear** (karena target adalah nilai kontinu/tahun).
* **Loss Function:** Mean Squared Error (MSE).

### 3. Results
* **Metric:** Mean Absolute Error (MAE).
* **Performance:** Model berhasil memprediksi tahun lagu dengan rata-rata kesalahan **MAE ~5.86 Tahun**.
* **Conclusion:** Model Deep Learning menghasilkan error terendah dibandingkan model Machine Learning tradisional (seperti Random Forest MAE 6.45), membuktikan superioritasnya dalam menangkap pola non-linear pada data audio.

---

## 💻 How to Run
1.  Buka file notebook (`.ipynb`) yang tersedia di repository ini menggunakan **Google Colab**.
2.  **PENTING:** Ubah Runtime ke **T4 GPU** agar proses training Neural Network berjalan cepat.
3.  Jalankan cell secara berurutan.

---
*Created for Midterm Exam - Telkom University*