---
title: "Twitter/X Data Collection: Climate Change Topics"
weight: 4
date: 2025-11-02
share: false
summary: "Mengumpulkan dan menganalisis tweet berbahasa Indonesia terkait perubahan iklim menggunakan Twitter/X API (Tweepy) sebagai persiapan data untuk pemrosesan NLP."
tags: 
  - Data Science
  - Natural Language Processing
  - Data Collection
  - Twitter API
  - Tweepy
tech_stack:
  - Python
  - Tweepy
  - Pandas
  - python-dotenv
links:
  - type: github
    url: https://github.com/DanuSetiawan05/Twitter-Data-Collection-Climate-Change-Topics
    label: Code Repository
featured: true
status: "Completed"
role: "author"
duration: "2 weeks"
team_size: 1
highlights:
  - "Mengotomatisasi ekstraksi 100 tweet original (non-retweet) berbahasa Indonesia menggunakan Tweepy dan API v2."
  - "Mengekspor data secara terstruktur ke format JSON dan CSV yang dilengkapi dengan file metadata dan auto-generated README."
  - "Melakukan Exploratory Data Analysis (EDA) teks dasar seperti perhitungan rata-rata engagement dan word frequency."
---

Proyek *Data Engineering* dan pengumpulan data otomatis berbasis Python untuk mengekstrak tweet berbahasa Indonesia mengenai "perubahan iklim" melalui API Twitter/X. Alat ini dirancang tidak hanya untuk mengambil data mentah, tetapi juga melakukan analisis keterlibatan dasar dan mengekspor hasilnya dalam format yang siap digunakan untuk tahapan *Natural Language Processing* (NLP) selanjutnya.

## Overview (Gambaran Umum)

Perubahan iklim adalah isu global yang sangat relevan dan sering memicu diskusi hangat di media sosial Indonesia. Untuk menganalisis opini publik terkait isu ini, diperlukan dataset tekstual yang berkualitas. Proyek ini mendemonstrasikan proses otomatisasi *web data collection* secara aman menggunakan token otentikasi API, penyaringan data yang terstruktur, hingga menghasilkan dataset tabular yang siap dieksplorasi oleh model kecerdasan buatan.

## Kueri dan Pengumpulan Data

**Metode Pengumpulan:**
Pengumpulan data difokuskan untuk mendapatkan opini orisinal dengan memfilter *retweets*. Kueri utama yang digunakan adalah:
`"perubahan iklim" lang:id -is:retweet`

**Spesifikasi Dataset:**
- **Total Tweets:** 100
- **Bahasa:** Indonesia
- **Saringan Ekstra:** Hanya mencakup tweet orisinal dengan manajemen otentikasi API menggunakan variabel lingkungan (environment variables) via `python-dotenv`.

## Metodologi Analisis

### 1. Ekstraksi Data (Tweepy API Integration)
- Mengambil tweet terbaru yang sesuai dengan kueri topik "perubahan iklim".
- Menyaring hasil tweet berdasarkan ambang batas keterlibatan minimum (minimum *likes* = 0).

### 2. Basic Text Analysis (Analisis Dasar)
- **Engagement Statistics:** Menghitung rata-rata *likes*, *retweets*, dan *replies* pada keseluruhan data.
- **Word Frequency:** Melakukan penyaringan kata (*stopword removal* sederhana) untuk menghitung dan mengekstrak kata-kata yang paling sering muncul.
- **User Profiling:** Mengidentifikasi pengguna Twitter/X yang paling aktif atau memiliki pengikut (*followers*) terbanyak di dalam dataset.

### 3. Data Export & Structuring
- Mengekspor data yang terkumpul ke dalam direktori khusus berlabel *timestamp*. 
- Folder ekstraksi berisi data dalam bentuk `tweets.json`, `tweets.csv`, `metadata.json`, serta dokumentasi `README.md` yang otomatis digenerasi oleh sistem.

## Hasil dan Insight Awal

Walaupun proyek ini berfokus pada tahapan pengumpulan data, beberapa *insight* awal berhasil diidentifikasi:

* **Tingkat Keterlibatan (Engagement):** Dari 100 tweet yang dikumpulkan, rata-rata *Likes* berada di angka 2.95 dan *Retweets* di angka 1.12. Total *engagement* yang berhasil dicatat adalah 407 interaksi.
* **Distribusi Teks Populer:** Ekstraksi kata dasar menunjukkan bahwa kata "perubahan" (102 kali) dan "iklim" (70 kali) paling mendominasi, diikuti oleh konteks dampak ("terhadap", "dampak", "menghadapi").
* **Pengaruh Akun Besar:** Salah satu pengguna dengan pengikut terbanyak yang mendiskusikan topik ini adalah akun media berita nasional `@detikcom` dengan lebih dari 24,8 juta pengikut.

## Langkah Selanjutnya (Next Steps untuk NLP)

Dataset yang diekstrak telah dipersiapkan dengan kolom terstruktur (seperti `text`, `likes`, `engagement`, dll.) agar dapat digunakan untuk tahapan NLP yang lebih dalam, meliputi:
1. **Text Preprocessing:** *Cleaning*, *tokenization*, dan *stopword removal* lanjutan.
2. **Sentiment Analysis:** Pemodelan sentimen untuk mengukur persepsi publik (misal: positif, negatif, atau netral).
3. **Topic Modeling:** Menggunakan LDA atau BERTopic untuk memetakan sub-topik tersembunyi.
4. **Time Series Analysis:** Melacak fluktuasi diskusi publik seiring berjalannya waktu.

---

**Project Status**: ✅ Completed  
**GitHub**: [Lihat Kode Lengkap](https://github.com/DanuSetiawan05/Twitter-Data-Collection-Climate-Change-Topics)