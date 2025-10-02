# 🎬 Analisis Popularitas Film – IFEST DAC 2025

## 📌 Deskripsi Proyek

Proyek ini dibuat untuk kompetisi **Data Analytics Competition (DAC) IFEST 2025** dengan tim **DuoChandra+1**.
Fokus utama adalah **analisis popularitas film** berdasarkan data TMDB, dengan tujuan menemukan faktor-faktor yang paling memengaruhi popularitas film serta memvalidasi hipotesis menggunakan eksplorasi data, uji statistik, dan interpretabilitas model (SHAP).

## 👥 Tim

* **Bagus Cipta Pratama**
* **Rhafael Chandra**
* **Darryl Chandra**

## 🎯 Problem Statement & Objective

Popularitas film dipengaruhi oleh banyak faktor seperti **genre, tahun rilis, bahasa, deskripsi, dan franchise/sekuel**.
Namun, sulit menentukan faktor dominan.
Tujuan dari proyek ini adalah:

1. Melakukan **EDA (Exploratory Data Analysis)**.
2. Menyusun hipotesis berdasarkan pola data.
3. Melakukan **validasi hipotesis** dengan uji statistik & SHAP analysis.

## 📂 Dataset

* Jumlah data: **12,999 film** dengan **6 kolom**.
* Missing values:

  * `genre_label`: 2,000 (15,39%)
  * `summary`: 5 (0,04%)
* Duplikat: **3,008 baris** persis sama.
* Film remake/sekuel: **314 judul**.

Dataset mengalami proses **cleaning & imputation** dengan teknik berikut:

1. **Pooling Genre**: mengambil genre dari film dengan judul utama sama.
2. **TMDB API**: melengkapi genre berdasarkan judul & tahun rilis.
3. **Final Cleaning**: menghapus sisa data kosong.

## 🔎 Eksplorasi Data (EDA)

Beberapa temuan utama dari EDA:

* **Tren Popularitas**: film baru (2000–2025) cenderung lebih populer.
* **Jumlah Genre**: film dengan 3–6 genre lebih populer; terlalu banyak genre (7–8) menurunkan popularitas.
* **Bahasa**: film Jepang relatif sedikit namun konsisten populer.
* **Remake vs Original**: distribusi popularitas mirip.

## 🧪 Hipotesis

> **Film franchise (sekuel/prekuel) memiliki popularitas lebih tinggi dibanding film standalone karena adanya fanbase dan brand recognition.**

## ✅ Validasi Hipotesis

* Rata-rata popularitas: **Franchise 75.1 vs Standalone 29.2** (+157%).
* Uji Statistik: signifikan (Mann-Whitney U, *p-value* ≈ 4.88e-116).
* Cohen’s d: sedang (0.21) pada skor mentah, kuat (0.70) pada persentil.
* SHAP Analysis: `movie_has_multiple` menjadi **fitur penting** dengan kontribusi SHAP +24.56 (franchise) vs –2.33 (standalone).

## ⚙️ Teknologi yang Digunakan

* **Python** (pandas, numpy, matplotlib, seaborn, scikit-learn, XGBoost, SHAP)
* **Natural Language Processing**: spaCy untuk ekstraksi judul utama.
* **API**: TMDB untuk melengkapi genre.
* **Statistik**: Mann-Whitney U Test, Cohen’s d.

## 📊 Hasil Utama

* Analisis konsisten menunjukkan **franchise effect** nyata: film franchise lebih populer daripada standalone.
* Validasi diperkuat dengan **EDA, uji statistik, dan SHAP analysis**.

## 🏆 Kesimpulan

Film franchise terbukti **secara statistik dan model interpretasi** lebih populer daripada film standalone. Efek ini konsisten dengan keberadaan **fanbase dan brand recognition**.
