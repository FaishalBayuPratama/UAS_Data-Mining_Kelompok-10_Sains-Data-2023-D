# 🔍 Deteksi Rasisme pada Media Sosial Berbahasa Indonesia

Proyek Data Mining Kelompok 10 | Sains Data 2023D

---

## 📋 Deskripsi Proyek

Proyek ini bertujuan untuk mendeteksi komentar berbau rasisme pada media sosial berbahasa Indonesia secara otomatis menggunakan pendekatan machine learning. Dengan meningkatnya volume konten di media sosial, deteksi rasisme secara manual menjadi tidak efisien. Model dalam proyek ini mengklasifikasikan teks sebagai **rasis** atau **non-rasis** menggunakan tiga algoritma klasifikasi utama (SVM, Random Forest, dan Naive Bayes) yang dikombinasikan dengan dua teknik representasi teks (TF-IDF dan Bag-of-Words), serta penanganan ketidakseimbangan data menggunakan SMOTE.

---

## 👥 Anggota Kelompok

| No | Nama | NIM |
|----|------|-----|
| 1 | Muhammad Dafa Alvian Ramadhani | 23031554017 |
| 2 | Faishal Bayu Pratama | 23031554092 |
| 3 | Azriel Kevin Alfarizqi | 23031554190 |
| 4 | Muhammad Alif Mahbubi | 23031554031 |

---

## 🗂️ Struktur Repository

Seluruh file dataset dan kamus pendukung telah dijadikan satu di dalam folder `dataset/` (atau nama folder yang kamu sesuaikan). Path pada file notebook juga sudah otomatis menyesuaikan struktur ini.

```text
.
├── UAS_Data_Mining_Kelompok_10.ipynb     # Notebook utama
├── /Kamus kamus dan file sentimen rasis (PROJEK DATMIN)/                              # Folder berisi semua data dan kamus pendukung
│   ├── RASIS.csv                         # Dataset utama (hasil integrasi)
│   ├── Rasis 1.csv                       # Dataset sumber 1
│   ├── Rasis 2.csv                       # Dataset sumber 2
│   ├── Rasis 3.csv                       # Dataset sumber 3
│   ├── Rasis 4.csv                       # Dataset sumber 4
│   ├── Kamus Singkatan Indonesia.csv     # Kamus singkatan
│   ├── Kamus Baku Tidak Baku_update.csv  # Kamus normalisasi kata
│   ├── new_kamusalay.csv             # Kamus kata alay
│   └── emoticons.csv                 # Kamus emotikon
├── requirements.txt                      # Daftar dependensi Python
└── README.md

---

## ⚙️ Alur Proyek

Data Collecting → Data Selection → Data Integration
        ↓
     EDA (Exploratory Data Analysis)
        ↓
   Preprocessing Teks:
   Cleaning → Casefolding → Translasi → Normalisasi Singkatan
   → Normalisasi Kata Baku → Stopword Removal → Emoji/Emotikon
        ↓
   Feature Engineering: TF-IDF & Bag-of-Words
        ↓
   Modeling: SVM, Random Forest, Naive Bayes
        ↓
   Evaluasi: Tanpa SMOTE vs Dengan SMOTE

---

## 🚀 Cara Menjalankan

### Prasyarat

-Python versi 3.8 ke atas terinstal di komputer.
-pip (Python package manager).
-Disarankan menggunakan virtual environment (VS Code / Command Prompt / Terminal).

---
#### 1. Clone / Download Repository

```bash
git clone https://github.com/<username>/<nama-repo>.git
cd <nama-repo>
```

#### 2. Buat Virtual Environment (Opsional tapi Direkomendasikan)

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux / macOS
source venv/bin/activate
```

#### 3. Install Semua Dependensi

```bash
pip install -r requirements.txt
```

#### 4. Download NLTK Data

Jalankan perintah berikut di Python shell atau tambahkan di awal notebook:

```python
import nltk
nltk.download('stopwords')
nltk.download('punkt')
```

#### 5. Sesuaikan Path File CSV

Buka file `UAS_Data_Mining_Kelompok_10.ipynb`, lalu ubah path file CSV dari format Colab:

```python
# Sebelum (Google Colab)
data = pd.read_csv("/Kamus kamus dan file sentimen rasis (PROJEK DATMIN)/RASIS.csv", engine='python')

# Sesudah (lokal — sesuaikan dengan lokasi file di komputer Anda)
data = pd.read_csv("RASIS.csv", engine='python')
```

Lakukan hal yang sama untuk semua path berikut:

| Baris Asli (Colab) | Ganti Menjadi (Lokal) |
|---|---|
| `"/Kamus kamus dan file sentimen rasis (PROJEK DATMIN)/RASIS.csv"` | `"RASIS.csv"` |
| `"/Kamus kamus dan file sentimen rasis (PROJEK DATMIN)/Kamus Singkatan Indonesia.csv"` | `"Kamus Singkatan Indonesia.csv"` |
| `"/Kamus kamus dan file sentimen rasis (PROJEK DATMIN)/Kamus Baku Tidak Baku.csv"` | `"Kamus Baku Tidak Baku.csv"` |
| `'/Kamus kamus dan file sentimen rasis (PROJEK DATMIN)/emoticons.csv'` | `'emoticons.csv'` |
| `'/Kamus kamus dan file sentimen rasis (PROJEK DATMIN)/new_kamusalay.csv'` | `'new_kamusalay.csv'` |

#### 6. Jalankan Notebook

```bash
jupyter notebook UAS_Data_Mining_Kelompok_10.ipynb
```

Kemudian jalankan semua sel secara berurutan dari atas ke bawah.

---

## 📦 Daftar Library dan Cara Install

| Library | Kegunaan | Cara Install |
|--------|---------|-------------|
| `numpy` | Operasi numerik | `pip install numpy` |
| `pandas` | Manipulasi dataframe | `pip install pandas` |
| `matplotlib` | Visualisasi grafik | `pip install matplotlib` |
| `seaborn` | Visualisasi statistik | `pip install seaborn` |
| `wordcloud` | Visualisasi word cloud | `pip install wordcloud` |
| `nltk` | NLP: stopwords, tokenisasi | `pip install nltk` |
| `scikit-learn` | Model ML, TF-IDF, BoW | `pip install scikit-learn` |
| `imbalanced-learn` | SMOTE untuk oversampling | `pip install imbalanced-learn` |
| `missingno` | Visualisasi missing value | `pip install missingno` |
| `langdetect` | Deteksi bahasa | `pip install langdetect` |
| `googletrans` | Translasi teks otomatis | `pip install googletrans==4.0.0-rc1` |
| `emoji` | Konversi emoji ke teks | `pip install emoji` |
| `PySastrawi` | Stemming Bahasa Indonesia | `pip install PySastrawi` |

Atau install semua sekaligus:

```bash
pip install -r requirements.txt
```

---

## ⚠️ Catatan Penting

- **`googletrans==4.0.0-rc1`**: Versi ini diperlukan karena versi lain dapat menyebabkan error. Jika masih bermasalah, pertimbangkan melewati cell translasi atau menggunakan library alternatif seperti `deep-translator`.
- **Dataset besar**: File `RASIS.csv` dan `Rasis 2.csv` berukuran cukup besar (~2–4 MB). Pastikan RAM mencukupi (minimal 4 GB direkomendasikan).

---

## 📊 Metode yang Digunakan

- **Preprocessing**: Cleaning, casefolding, translasi, normalisasi singkatan & kata baku, stopword removal, penanganan emoji & emotikon
- **Feature Engineering**: TF-IDF, Bag-of-Words (BoW dengan n-gram 1–3)
- **Modeling**: Support Vector Machine (SVM), Random Forest, Naive Bayes
- **Penyeimbangan Data**: SMOTE (Synthetic Minority Over-sampling Technique)
- **Evaluasi**: Accuracy, F1-Score, Recall, Confusion Matrix
