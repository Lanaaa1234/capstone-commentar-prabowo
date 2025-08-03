# 🧠 _Capstone Project: Decoding Public Sentiment_
## _AI-Driven Analysis_ Komentar YouTube Pidato Pertama Prabowo Subianto Pasca Menang Pilpres Indonesia Tahun 2024
### Dengan NLP Berbasis LLM (GPT-3.5-turbo)

**NOTED:** Pada Capstone Project kali ini saya sebelumnya sudah menggunakan model LLM **IBM Granite** namun output terkait preprocessing data untuk Classification dan Summarization hasil IBM Granit kurang maksimal, masih ditemukan banyak makna lain dan juga klasifikasi kurang valid dari komentar aslinya. Sehingga saya menggunakan model **openAI (GPT-3.5-turbo)**, ketika kelas Data Classification & Summarization dari mentor memperbolehkan hal tersebut.

---

### 👤 _Author & Contact_  
- **Nama**         : Maulana Diki Wicaksono
- **NIM**          : 23031030001
- **Universitas**  : Universitas Negeri Yogyakarta  
- **Email**        : maulanadiki963@gmail.com  
- **GitHub**       : [github.com/Lanaaa1234](https://github.com/Lanaaa1234)  
- **LinkedIn**     : [linkedin.com/in/maulana-diki-wicaksono](https://www.linkedin.com/in/maulana-diki-wicaksono/)  
- **Instagram**:   : [@maulanadikii_24](https://www.instagram.com/maulanadikii_24/)  

---

## 📌 _1. Project Overview_  
**Latar Belakang & Masalah**  
Setelah KPU menetapkan Prabowo Subianto sebagai Presiden RI 2024–2029, pidato pertamanya di kanal youtube KOMPASTV memicu ribuan komentar publik. Komentar ini mencerminkan opini, emosi, dan sikap politik masyarakat Indonesia yang penting untuk dianalisis guna memahami persepsi publik.  

**Tujuan**  
- Mengolah komentar YouTube pidato Prabowo Subianto secara otomatis untuk **memahami opini publik**.
- Mengidentifikasi **sentimen** (positif, netral, negatif) dan mengelompokkan **topik pembahasan** dari komentar publik.
- Menyusun **ringkasan naratif** per topik pembahasan.
- Mendemonstrasikan peran **AI (GPT-3.5-turbo)** dalam menangani data teks bahasa Indonesia berskala besar secara efisien. 


---

## 🔗 2. Notebook & Dataset  
- 📒 **Google Colab Notebook**:  
  https://colab.research.google.com/drive/1-cFq7F3w-H_aA-5pnUkAiZUd_xAV-F16?usp=sharing  
- 📁 **Dataset & output (Google Drive)**:  
  https://drive.google.com/drive/folders/1zIb7QLEWGsypM1agrUuKQS5oO_yBqJuy?usp=sharing  
- 📽️ **Sumber Video YouTube**:  
  https://youtu.be/5DbCvqfg-9I?si=cLabiu4VVIFclz_2  

---

## ⚙️ _3. Methodology_ 
1. **_Data Collection (Scraping)_**  
   - YouTube Data API v3 → `komentar_prabowo.csv` (3.596 baris × 4 kolom)  
2. **_Data Cleaning & Emoji Removal_**  
   - Regex & Python → `komentar_prabowo_unemot.csv` (3.486 baris × 4 kolom)  
3. **Preprocessing Teks dengan LLM**  
   - GPT-3.5-turbo: normalisasi kata, perbaikan ejaan → `komentar_preprocess_gpt35.csv` (3.486 baris × 5 kolom)  
4. **_Sentiment Analysis (LLM)_**  
   - Klasifikasi positif/netral/negatif → `komentar_sentimen_gpt35.csv` (3.409 baris × 3 kolom)  
5. **_Topic Classification (LLM)_**  
   - 6 kategori topik yang dikodekan A–F → `komentar_topik_OKGPT35.csv`  
6. **Visualisasi**  
   - Bar chart, pie chart, grouped bar chart, heatmap, word cloud  
7. **_Summarization by Topic (LLM)_**  
   - Ringkasan naratif  per topik → `ringkasan_topik_full.csv`  
8. **_Fun Fact & Word Frequency_**  
   - 20 kata teratas & word cloud  

---

## 📊 _4. Insight & Findings_  
- **Sentimen**: 56,4% positif, 26,9% negatif, 16,6% netral  
- **Topik Teratas**:   
  - A: ucapan selamat dan dukungan (1.429 komentar)  
  - C: kritik atau sindiran politik (974 komentar)
  - B: harapan dan doa (511 komentar)
- **Sekilas relasi Topik–Sentimen**:
  - topik komentar terkait ucapan selamat dan dukungan memiliki mayoritas sentimen positif yakni sejumlah 1.346 dari 1.429 komentar
  - topik komentar terkait kritik atau sindiran politik memiliki mayoritas sentimen negatif sejumlah 758 dari 974 komentar 
- **Word Cloud**: dominasi kata “prabowo”, “semoga”, “selamat”, “indonesia”

---
## 🤖 _5. AI Support Explanation_  
- 🧹 **_Preprocessing_**: GPT-3.5-turbo membersihkan & memperbaiki ejaan  
- 📊 **_Sentiment Analysis_**: klasifikasi komentar ke dalam 3 kategori (positif, netral, negatif) 
- 🧠 **_Topic Classification_**: pengelompokan ke kode A–F  
- 📚 **_Summarization_**: ringkasan naratif per topik & sentimen  
- 📈 **_Visual Code Generation_**: LLM bantu generate kode Python untuk grafik  

---

## 📝 _6. Conclusions_

- **Efektivitas Model LLM dalam Analisis Komentar Publik**  
  Proyek ini menunjukkan bahwa GPT-3.5-turbo mampu menangani ribuan komentar dalam Bahasa Indonesia dengan konsistensi klasifikasi yang tinggi. Sentimen dan topik berhasil dipetakan dari lebih dari 3.400 komentar yang tersebar dalam enam kategori utama.

- **Efisiensi dalam Merangkum Opini Publik**  
  Dengan pendekatan berbasis LLM, komentar publik yang sangat masif dapat disarikan menjadi ringkasan naratif per topik dalam rentang 1.000–1.500 karakter. Hal ini memungkinkan stakeholder untuk memahami persepsi masyarakat tanpa harus membaca komentar satu per satu.

- **Keterbatasan Teknis dan Peluang Pengembangan**  
  Proses preprocessing dan summarization masih membutuhkan waktu eksekusi cukup lama (±40–60 menit per batch) dan sensitif terhadap kualitas prompt. Hal ini membuka ruang pengembangan pada aspek optimasi prompt engineering, batching, serta integrasi metode validasi manual dan tradisional untuk memperkuat akurasi hasil.

---

## 🌟 _7. Recommendations_

1. **Pemanfaatan untuk Strategi Komunikasi Publik**  
   Analisis topik dan sentimen dapat dimanfaatkan untuk merancang pesan komunikasi yang lebih terarah dan memilih kanal distribusi yang sesuai, berdasarkan persebaran sentimen publik terhadap isu tertentu.

2. **Pengembangan Sistem Pemantauan Opini Real-Time**  
   Dapat dipertimbangkan integrasi sistem pemantauan otomatis berbasis scraping berkala dan dashboard interaktif (misalnya menggunakan Streamlit atau Plotly Dash) untuk:
   - Mendeteksi perubahan tren sentimen dan topik secara real-time  
   - Menghasilkan notifikasi ketika terjadi lonjakan komentar negatif pada isu tertentu

3. **Optimasi Pipeline dan Validasi Model**  
   - Tingkatkan akurasi pembersihan teks dengan penggunaan pustaka khusus (mis. `emoji`, `demojize`)
   - Modularisasi prompt dan penerapan batch processing untuk efisiensi waktu komputasi
   - Lakukan validasi hasil klasifikasi dengan pendekatan:
     - NLP tradisional (KNN, Naïve Bayes)
     - Verifikasi manual pada sampel data acak

4. **Pengayaan Analisis dan Ekspansi Cakupan**  
   - Visualisasikan dinamika sentimen dan topik dari waktu ke waktu (analisis temporal)
   - Tambahkan analisis emosi publik (senang, marah, sedih) menggunakan model lanjutan
   - Perluas cakupan data ke platform lain (Twitter, Facebook) untuk analisis lintas kanal


---


## 📊 Lampiran Visualisasi Komentar YouTube

### a. Analisis Sentimen
![Bar Chart Sentimen](images/sentimen-bar.png)
![Pie Chart Sentimen](images/sentimen-pie.png)

### b. Distribusi Topik dan Sentimen
![Grouped Bar Chart](images/grouped-bar-topic.png)
![Heatmap Topik](images/heatmap-topic.png)

### c. Analisis Kata
![Top 20 Most Common Words](images/top20-words.png)
![Word Cloud of Comments](images/wordcloud.png)

