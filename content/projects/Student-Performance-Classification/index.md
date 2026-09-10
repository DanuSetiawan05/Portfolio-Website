---
title: "Student Performance Classification: Decision Tree vs KNN"
weight: 2
date: 2024-12-15
share: false
summary: "Klasifikasi status kelulusan siswa (Lulus/Tidak Lulus) berdasarkan faktor-faktor performa akademik, dengan membandingkan performa algoritma Decision Tree dan K-Nearest Neighbors (KNN)."
tags: 
  - Data Science
  - Machine Learning
  - Classification
  - Decision Tree
  - KNN
tech_stack:
  - Python
  - Scikit-Learn
  - Pandas
  - Matplotlib
  - Seaborn
links:
  - type: github
    url: https://github.com/DanuSetiawan05/Student-Performance-Classification-DT-vs-KNN
    label: Code Repository
featured: true
status: "Completed"
role: "author"
duration: "1 month"
team_size: 1
highlights:
  - "Mencapai akurasi klasifikasi terbaik sebesar 84.7% menggunakan algoritma Decision Tree (max_depth=8)."
  - "Mengidentifikasi faktor Attendance dan Hours_Studied sebagai prediktor terkuat untuk kelulusan siswa."
  - "Melakukan tuning hyperparameter secara adil pada kedua model melalui 10-fold cross-validation."
---

Proyek analisis data dan Machine Learning untuk mengklasifikasi status kelulusan siswa (Lulus/Tidak Lulus) berdasarkan faktor-faktor performa akademik. Proyek ini membandingkan performa dua algoritma klasifikasi, yaitu **Decision Tree** dan **K-Nearest Neighbors (KNN)**, untuk menemukan model terbaik dalam memprediksi hasil evaluasi belajar siswa.

## Overview (Gambaran Umum)

Performa akademik siswa dipengaruhi oleh banyak faktor mulai dari kebiasaan belajar, kehadiran di kelas, keterlibatan orang tua, hingga kondisi lingkungan sekitar. Tujuan dari analisis ini adalah mengidentifikasi faktor mana yang paling berpengaruh dan membangun model prediktif sehingga pihak sekolah dapat melakukan intervensi (seperti bimbingan tambahan atau konseling) lebih awal terhadap siswa yang berisiko tidak lulus.

## Metodologi Analisis

### 1. Data Preparation & EDA
- **Pemilihan Fitur:** Melakukan eksplorasi korelasi fitur numerik dan rata-rata skor per kategori terhadap *Exam_Score* untuk memilih fitur yang paling relevan secara objektif.
- **Penanganan Data:** Menghapus baris data dengan nilai kosong (missing value) pada fitur terpilih agar tidak mengganggu proses pemodelan.
- **Kategorisasi Target:** Mengubah variabel kontinu `Exam_Score` menjadi label biner `Pass_Status` (Lulus/Tidak Lulus) dengan menetapkan ambang batas nilai 67, yang merupakan nilai median dari distribusi skor.

### 2. Preprocessing & Data Splitting
- **Pembagian Data:** Membagi dataset menjadi data latih (80%) dan data uji (20%) menggunakan *stratified split* agar proporsi kelas "Lulus" dan "Tidak Lulus" tetap seimbang.
- **Normalisasi:** Melakukan normalisasi *MinMax* pada fitur numerik untuk mencegah fitur berskala besar mendominasi perhitungan jarak, sehingga mengoptimalkan kinerja algoritma KNN.

### 3. Pendekatan Klasifikasi (Decision Tree vs KNN)
- **Tuning Hyperparameter:** Pemilihan kedalaman pohon optimal (`max_depth`) untuk Decision Tree dan nilai ketetanggaan (`K`) untuk KNN dievaluasi secara adil menggunakan metode *10-fold cross-validation*.

## Hasil dan Evaluasi Model

### Kinerja Model Decision Tree
- **Parameter Terbaik:** max_depth=8
- **Akurasi (Accuracy):** 84.7%
- **F1-Score:** 86.8%
- **Precision & Recall:** Precision 85.1% dan Recall 88.5%

### Kinerja Model KNN
- **Parameter Terbaik:** K=14
- **Akurasi (Accuracy):** 73.6%
- **F1-Score:** 76.7%

## Visualisasi Utama

![Distribusi Exam Score](exam-score-dist.png)
*Gambar 1: Distribusi Exam Score dengan garis batas median pada nilai 67 yang dijadikan acuan klasifikasi Lulus/Tidak Lulus.*

![Heatmap Korelasi](correlation-heatmap.png)
*Gambar 2: Heatmap korelasi fitur numerik yang menunjukkan Attendance dan Hours_Studied memiliki hubungan paling kuat terhadap skor ujian.*

## Kesimpulan & Rekomendasi Kebijakan

1. **Keunggulan Model Berbasis Aturan:** Model Decision Tree secara konsisten mengungguli KNN di seluruh metrik evaluasi untuk kasus klasifikasi ini. Hal ini menunjukkan bahwa dataset performa akademik ini memiliki batas keputusan (*decision boundary*) yang lebih cocok direpresentasikan dalam bentuk aturan bertingkat (*tree-based*) dibandingkan pendekatan jarak geometris (*distance-based*).
2. **Faktor Dominan Penentu Kelulusan:** Faktor kehadiran (`Attendance`) dan jam belajar (`Hours_Studied`) adalah faktor numerik dengan korelasi terkuat terhadap kelulusan, sedangkan faktor demografis seperti `Gender` hampir tidak memiliki pengaruh sama sekali. Rekomendasi praktis bagi sekolah dan orang tua adalah memfokuskan program intervensi pada perbaikan kehadiran dan kedisiplinan jam belajar.

---

**Project Status**: ✅ Completed  
**GitHub**: [Lihat Kode Lengkap (Jupyter Notebook)](https://github.com/DanuSetiawan05/Student-Performance-Classification-DT-vs-KNN)