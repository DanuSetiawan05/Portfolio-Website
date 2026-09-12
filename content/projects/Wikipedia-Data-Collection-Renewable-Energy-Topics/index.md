---
title: "Wikipedia Data Collection: Renewable Energy Topics"
weight: 5
date: 2025-11-09
share: false
summary: "Mengotomatisasi ekstraksi artikel Wikipedia berbahasa Indonesia terkait Energi Terbarukan ke dalam format CSV terstruktur untuk keperluan pemrosesan Natural Language Processing (NLP)."
tags: 
  - Data Science
  - Natural Language Processing
  - Data Collection
  - Wikipedia API
  - Text Analysis
tech_stack:
  - Python
  - Wikipedia-API
  - RegEx
  - Pandas
links:
  - type: github
    url: https://github.com/DanuSetiawan05/Wikipedia-Data-Collection-Renewable-Energy-Topics
    label: Code Repository
featured: true
status: "Completed"
role: "Data Scientist (Solo Project)"
duration: "1 weeks"
team_size: 1
highlights:
  - "Mengekstrak konten dan ringkasan artikel secara otomatis dengan penanganan error bawaan (seperti halaman disambiguasi dan halaman tidak ditemukan)."
  - "Memastikan integritas teks yang panjang dengan mengekspor data ke format CSV menggunakan delimiter titik koma (;) dan format quote-all."
  - "Melakukan Text Analysis dasar menggunakan Regular Expression (RegEx) dan filter custom stopword untuk mengidentifikasi 10 kata paling dominan."
---

Proyek *Data Engineering* berbasis Python untuk mengumpulkan artikel Wikipedia berbahasa Indonesia dengan topik "Energi Terbarukan". Alat ini tidak hanya mengambil teks dari halaman web secara otomatis, tetapi juga merapikannya ke dalam dataset terstruktur (CSV) dan melakukan analisis teks dasar sebagai langkah persiapan menuju pemodelan *Natural Language Processing* (NLP).

## Overview (Gambaran Umum)

Dalam membangun model NLP yang andal, ketersediaan korpus teks yang bersih dan relevan adalah kunci utama. Wikipedia merupakan salah satu sumber informasi paling kaya, namun mengekstrak teksnya secara manual sangat tidak efisien. Proyek ini mendemonstrasikan kemampuan merancang *pipeline* pengumpulan data otomatis dengan memanfaatkan API Wikipedia, menangani anomali pencarian secara sistematis, serta melakukan ekstraksi wawasan dasar dari kumpulan dokumen teks tersebut.

## Metodologi Pengumpulan & Analisis Data

### 1. Ekstraksi Artikel (Wikipedia API Integration)
- Menggunakan *library* `wikipedia` dan `wikipedia-api` yang dikonfigurasi khusus untuk korpus Bahasa Indonesia (`id`).
- Sistem dirancang dengan mekanisme *error handling* (`try-except`) yang pintar: jika sistem mendeteksi `DisambiguationError` (halaman memiliki makna ganda), ia akan secara otomatis memilih rujukan opsi pertama, dan akan melewati halaman yang memicu `PageError`.

### 2. Penyimpanan Terstruktur (Data Structuring)
- Teks dari Wikipedia sering kali mengandung koma, kutipan, dan baris baru yang dapat merusak struktur tabel jika diekspor begitu saja. 
- Data dibersihkan secara otomatis (mengganti baris baru/tab dengan spasi) dan diekspor menggunakan modul `csv` bawaan Python dengan pembatas titik koma (`;`) serta parameter `csv.QUOTE_ALL` untuk memastikan keamanan integritas dokumen.

### 3. Analisis Teks Dasar (Basic Text Analysis)
- **Tokenisasi Sederhana:** Menggunakan *Regular Expression* (`\b\w+\b`) untuk menghitung jumlah kata (Word Count) secara akurat pada setiap artikel yang telah diunduh.
- **Word Frequency:** Menerapkan *custom stopword filtering* (menghapus kata sambung/umum berbahasa Indonesia) dan menghitung kemunculan kata terbanyak menggunakan `collections.Counter`.

## Hasil dan Insight Awal

Proyek ini berhasil mengumpulkan 10 artikel komprehensif, mulai dari "Energi terbarukan" (2.912 kata) hingga artikel institusional seperti "Kementerian Energi dan Sumber Daya Mineral Republik Indonesia" (960 kata). 

Berdasarkan hasil analisis frekuensi, berikut adalah **5 kata yang paling sering dibicarakan** di seluruh artikel (setelah di-*filter*):
1. **Energi:** 589 kali
2. **Terbarukan:** 142 kali
3. **Tahun:** 134 kali
4. **Listrik:** 117 kali
5. **Pertamina:** 101 kali

*Distribusi ini memberikan sinyal yang sangat baik bahwa data yang diekstrak relevan dengan topik, dan memunculkan entitas seperti "Listrik" dan "Pertamina" sebagai sub-topik dominan.*

## Langkah Selanjutnya (Next Steps untuk NLP)

Dataset `artikel_energi_terbarukan.csv` ini sudah sangat siap untuk digunakan dalam tahap pemrosesan NLP lanjutan. Rencana pengembangan ke depannya meliputi:
1. Ekstraksi bobot kata menggunakan analisis **TF-IDF**.
2. Pemodelan topik (*Topic Modeling*) menggunakan **LDA (Latent Dirichlet Allocation)** atau **BERTopic** untuk menemukan sub-topik secara otomatis.
3. Eksperimen pembangunan model klasifikasi teks atau peringkasan dokumen (*Text Summarization*).

---

**Project Status**: ✅ Completed  
**GitHub**: [Lihat Kode Lengkap (Jupyter Notebook)](https://github.com/DanuSetiawan05/Wikipedia-Data-Collection-Renewable-Energy-Topics)