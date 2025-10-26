# Analisis Prediksi Probabilitas Attrition pada Karyawan

**Nadine Zahirah Putri Widianti** — NRP: 5003231005<br>
**Firda Amallia Trisnawati** — NRP: 5003231006<br>
**Andra Eka Wijayanti** — NRP: 5003231012<br>

Mata Kuliah **Statistics Machine Learning A**<br>
Departemen Statistika, Institut Teknologi Sepuluh Nopember (ITS)

---

## 📚 Daftar Isi
- [Domain Proyek: Sumber Daya Manusia (HR)](#domain-proyek-sumber-daya-manusia-hr)
  - [Referensi](#referensi)
- [Business Understanding](#business-understanding)
  - [Problem Statements](#problem-statements)
  - [Goals](#goals)
  - [Solution Statements](#solution-statements)
  - [Project Benefits](#project-benefits)
- [Data Understanding](#data-understanding)
  - [Sumber Data](#sumber-data)
  - [Deskripsi Fitur](#deskripsi-fitur)
  - [Penjelasan Kontekstual Fitur](#penjelasan-kontekstual-fitur)
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Modeling & Evaluation](#modeling--evaluation)
- [Kesimpulan & Insight](#kesimpulan--insight)

---

## Domain Proyek: Sumber Daya Manusia (HR)
Proyek ini berfokus pada **prediksi kemungkinan karyawan keluar (attrition)** dari perusahaan berdasarkan berbagai faktor seperti kepuasan kerja, gaji, dan performa.

### Referensi
- Dataset: IBM HR Analytics Employee Attrition & Performance
- Sumber: [Kaggle Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

---

## Business Understanding

### Problem Statements
Perusahaan mengalami tingkat turnover tinggi dan membutuhkan model untuk memprediksi karyawan yang berpotensi resign.

### Goals
Membangun model klasifikasi untuk memprediksi probabilitas attrition dan menemukan faktor dominan yang memengaruhinya.

### Solution Statements
Menggunakan algoritma machine learning seperti **Logistic Regression, Random Forest, dan LightGBM** untuk menemukan model terbaik dengan metrik **AUC** tertinggi.

### Project Benefits
- Membantu HR mengidentifikasi risiko attrition dini.  
- Menyediakan insight bagi strategi retensi karyawan.  

---

## Data Understanding

### Sumber Data
Data berasal dari dataset IBM HR Analytics (Kaggle) dengan 1470 observasi dan 35 variabel.

### Deskripsi Fitur
Menjelaskan setiap fitur seperti:
- `Age`: Umur karyawan  
- `JobRole`: Jabatan karyawan  
- `MonthlyIncome`: Gaji bulanan  
- `Attrition`: Target variabel (Yes/No)

### Penjelasan Kontekstual Fitur
Fitur numerik dan kategorikal dianalisis untuk memahami pola distribusi dan korelasi antar variabel.

### Exploratory Data Analysis (EDA)
- Visualisasi distribusi dan outlier  
- Analisis missing value  
- Korelasi antar fitur  
- Analisis proporsi karyawan yang keluar

---

## Modeling & Evaluation
Model yang digunakan:
- Logistic Regression  
- Random Forest  
- LightGBM  
- XGBoost  

Evaluasi dilakukan menggunakan metrik:
- Accuracy  
- Precision, Recall, F1-Score  
- ROC-AUC  

Model terbaik: **LightGBM dengan AUC = 0.83**

---

## Kesimpulan & Insight
- Faktor paling berpengaruh terhadap attrition adalah *JobSatisfaction*, *MonthlyIncome*, dan *YearsAtCompany*.  
- Perusahaan dapat mengurangi attrition dengan memperbaiki kompensasi dan engagement karyawan.

---

📊 *Project dibuat untuk tugas mata kuliah Statistical Machine Learning A (2025).*
