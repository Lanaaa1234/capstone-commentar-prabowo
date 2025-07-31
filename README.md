# 🧠 _Capstone Project: Decoding Public Sentiment_
## _AI-Driven Analysis_ Komentar YouTube Pidato Pertama Prabowo Subianto Pasca Menang Pilpres Indonesia Tahun 2024
### Dengan NLP Berbasis LLM (GPT-3.5-turbo)

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
- Mengukur distribusi **sentimen** (positif, netral, negatif)  
- Mengidentifikasi **topik** pembahasan utama dalam komentar  
- Menyusun **ringkasan naratif** opini publik per topik  
- Memberikan **rekomendasi** berbasis data untuk stakeholder  

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
   - YouTube Data API v3 → `komentar_prabowo.csv` (3.597 baris × 4 kolom)  
2. **_Data Cleaning & Emoji Removal_**  
   - Regex & Python → `komentar_prabowo_unemot.csv` (3.487 baris × 4 kolom)  
3. **Preprocessing Teks dengan LLM**  
   - GPT-3.5-turbo: normalisasi kata, perbaikan ejaan → `komentar_preprocess_gpt35.csv` (3.487 baris × 5 kolom)  
4. **_Sentiment Analysis (LLM)_**  
   - Klasifikasi positif/netral/negatif → `komentar_sentimen_gpt35.csv` (3.410 baris × 3 kolom)  
5. **_Topic Classification (LLM)_**  
   - 6 kategori topik yang dikodekan A–F → `komentar_topik_OKGPT35.csv`  
6. **Visualisasi**  
   - Bar chart, pie chart, grouped bar chart, heatmap, word cloud  
7. **_Summarization by Topic (LLM)_**  
   - Ringkasan naratif 1.000–3.000 karakter per topik → `ringkasan_topik_full.csv`  
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
- **Akurasi & Skala Analisis**  
  Dengan GPT-3.5-turbo, proyek ini berhasil mengklasifikasikan 3.401 komentar ke dalam sentimen (positif 56,4 %, negatif 26,9 %, netral 16,6 %) dan enam topik utama. Ini menunjukkan LLM dapat menangani volume data besar dalam bahasa Indonesia.
- **Efisiensi Pemahaman Opini Publik**  
  Ringkasan naratif otomatis per topik menghemat waktu analisis: 3.401 komentar tersaring menjadi 6 laporan ringkas (masing-masing 1.000–3.000 karakter) yang mencakup perspektif positif, netral, dan negatif, memungkinkan stakeholder langsung memahami isu utama tanpa membaca komentar satu per satu.
- **Keterbatasan & Peluang**  
  Meski hasilnya kuat, proses preprocessing dan summarization masih memerlukan 40–60 menit setiap running sel dan sensitif terhadap kualitas prompt. Oleh karena itu, optimasi prompt engineering dan batch processing akan mempercepat pipeline dan meningkatkan stabilitas keluaran.

---

## 🌟 _7. Recommendations_
1. **Tim Komunikasi & Strategi Politik**  
   - Manfaatkan **insight topik dan sentimen** untuk menyusun pesan yang tepat sasaran.  
   - Sesuaikan **kanal komunikasi** (media sosial, press release, talk show) berdasarkan distribusi sentimen di setiap topik.
2. **Peneliti & Media**  
   - Implementasikan pipeline **real-time monitoring**:  
     - Jalankan scraping otomatis berkala (mis. via Cloud Function) untuk mendeteksi perubahan tren sentimen/topik.  
     - Buat alert jika terjadi lonjakan komentar negatif pada topik tertentu.  
   - Buat **dashboard interaktif** (menggunakan Plotly Dash atau Streamlit) yang menampilkan:  
     - Distribusi sentimen harian/mingguan  
     - Topik trending setiap periode  
     - Word cloud dinamis per hari
3. **Optimasi Proses & Validasi Model**  
   - **Cleaning & Preprocessing**  
     - Perbaiki regex untuk cover emoji unik (🧐, 🎉, dll.) dan simbol khusus yang belum terdeteksi.  
     - Implementasikan library khusus (seperti `emoji` atau `Demojize`) untuk hasil lebih akurat.  
   - **Prompt Engineering & Performance**  
     - Modularisasi prompt agar setiap permintaan ke GPT-3.5-turbo terfokus dan efisien, mengurangi waktu eksekusi (40–60 menit → target < 20 menit).  
     - Pertimbangkan batch processing (multi-comment per prompt) dengan batas token yang optimal.  
   - **Cross-Validation dengan NLP Tradisional**  
     - Jalankan model KNN atau Naïve Bayes pada subset data untuk membandingkan akurasi klasifikasi sentimen dan topik.  
     - Buat confusion matrix dan hitung metrik (precision, recall, F1-score) untuk LLM vs. model klasik.  
   - **Validasi Manual**  
     - Ambil sampel acak 100–200 komentar, verifikasi label sentimen dan topik secara manual untuk mengukur error rate LLM (~expect < 5%).
4. **Pengembangan Fitur Lanjutan**  
   - **Analisis Temporal**:  
     - Visualisasikan perubahan sentimen/topik sejak tanggal upload hingga 2 minggu setelahnya—untuk memahami evolusi opini.  
   - **Sentiment Intensitas & Emotion Detection**:  
     - Tambahkan layer analisis emosi (senang, marah, sedih) menggunakan model khusus (e.g., `transformers` fine-tuned).  
   - **Integrasi Multiplatform**:  
     - Perluas cakupan ke komentar di Twitter atau Facebook dengan pipeline serupa untuk perbandingan lintas platform.

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

