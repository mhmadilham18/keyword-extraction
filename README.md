# Studi Eksploratif: Klasifikasi Soal Otomatis Berdasarkan Taksonomi Bloom

![Python](https://img.shields.io/badge/python-3.9%2B-blue.svg)
![Libraries](https://img.shields.io/badge/libraries-pandas%20%7C%20sastrawi%20%7C%20sklearn-orange.svg)

Repositori ini berisi kode dan analisis untuk studi eksploratif mengenai kelayakan mengklasifikasikan butir soal akademik ke dalam level kognitif Taksonomi Bloom secara otomatis dengan pendekatan Natural Language Processing (NLP).

---

## 📖 Latar Belakang & Tujuan Proyek

Dalam pengembangan **asesmen adaptif**, kemampuan mengukur tingkat kesulitan soal secara otomatis adalah kunci. Proyek ini bertujuan untuk mengeksplorasi apakah level kognitif soal berdasarkan **Taksonomi Bloom**, yang diwakili oleh **Kata Kerja Operasional (KKO)**, dapat menjadi indikator kesulitan yang andal.

Dua pertanyaan utama yang ingin dijawab:
1.  Seberapa akurat sistem sederhana berbasis pencocokan KKO dapat mengklasifikasikan soal?
2.  Apakah ada korelasi antara label `level` kesulitan soal yang ada dengan Taksonomi Bloom?

## 📊 Temuan Utama (Key Findings)

* **Akurasi Terbatas:** Sistem klasifikasi berbasis KKO menunjukkan performa terbatas, dengan akurasi terbaik **20.20%** setelah melalui siklus perbaikan kamus kata kunci.
* **Korelasi Rendah:** Tidak ditemukan korelasi kuat antara `level` kesulitan soal (1-3) dengan level kognitif Taksonomi Bloom.
* **Ketergantungan pada Kamus:** Kualitas dan kelengkapan kamus KKO menjadi faktor penentu utama performa sistem.
* **Karakteristik Bank Soal:** Dataset soal cenderung fokus pada *Lower-Order Thinking Skills* (C1-C3).

## ⚙️ Alur Kerja Analisis

1.  **Definisi Proyek:** Menetapkan hipotesis korelasi kesulitan soal dengan level Bloom.
2.  **Akuisisi & Persiapan Data:** Mengumpulkan bank soal, literatur KKO, dan melakukan validasi *ground truth* oleh pakar pendidikan (FKIP).
3.  **Preprocessing & Feature Engineering:**
    * Uji coba dan pemilihan metode POS Tagging (GPT terpilih).
    * Ekstraksi KKO dari teks soal.
    * Normalisasi dengan *stemming* (Sastrawi).
4.  **Eksperimen & Evaluasi:**
    * Membangun *classifier* berbasis aturan dan mengevaluasi akurasinya.
    * Melakukan analisis profil eksploratif untuk mencari pola korelasi.
5.  **Interpretasi & Iterasi:** Menganalisis hasil, menarik kesimpulan, dan merumuskan langkah perbaikan.

## 🚀 Cara Menjalankan Proyek

### a. Prasyarat
* Python 3.9+
* Jupyter Notebook / Lab

### b. Instalasi
1.  Clone repositori ini:
    ```bash
    git clone [https://github.com/mhmadilham18/keyword-extraction.git](https://github.com/mhmadilham18/keyword-extraction.git)
    cd keyword-extraction
    ```
2.  (Sangat disarankan) Buat dan aktifkan *virtual environment*:
    ```bash
    python -m venv venv
    source venv/bin/activate  # Untuk Linux/macOS
    .\venv\Scripts\activate  # Untuk Windows
    ```
3.  Instal semua dependensi yang dibutuhkan:
    ```bash
    pip install pandas sastrawi scikit-learn matplotlib seaborn jupyterlab
    ```

### c. Eksekusi
Buka file Jupyter Notebook (`.ipynb`) dan jalankan sel-sel kode secara berurutan dari atas ke bawah untuk mereplikasi seluruh proses analisis.

## 👥 Tim Proyek

* **M. Ilham Abdul Shaleh (F1D022061):** Studi Literatur, Data Cleaning, Pengumpulan KKO, Notasi Stanza, Implementasi Kode Analisis, Validasi, Penyusunan Laporan.
* **Nazila Imkani (F1D022084):** Preprocessing (Notasi Manual), Perbandingan Model Notasi, Analisis Kelayakan Anotasi, Padding Manual.
* **Fernandao Kwangtama Tekayadi (F1D022120):** Preprocessing (Notasi GPT), Mapping & Padding Model Notasi.

## 💡 Rencana Pengembangan

* Memperkaya dan memvalidasi kamus KKO secara masif.
* Mengeksplorasi model yang lebih canggih (misal: *fine-tuning* IndoBERT) untuk menangkap konteks semantik.
* Melakukan evaluasi ulang terhadap definisi `level` kesulitan soal.ileNotFoundError`.
