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
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Modeling & Evaluation](#modeling--evaluation)
- [Business Result](#business--result)
- [Kesimpulan](#kesimpulan)

---

## Domain Proyek: Sumber Daya Manusia (HR) <br>
![hook](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/employee-attrition.jpg?raw-true) <br>
Manajemen sumber daya manusia merupakan salah satu pilar utama dalam menjaga keberlanjutan dan daya saing sebuah perusahaan di era bisnis modern. Salah satu tantangan terbesar yang dihadapi organisasi adalah tingginya tingkat attrition atau employee turnover, yaitu kondisi ketika karyawan meninggalkan perusahaan baik secara sukarela maupun tidak. Fenomena ini menimbulkan berbagai konsekuensi, seperti meningkatnya biaya rekrutmen dan pelatihan, menurunnya produktivitas tim, serta terganggunya stabilitas operasional dan moral kerja di lingkungan perusahaan [1]. <br> <br>
Beragam faktor dapat memengaruhi keputusan seorang karyawan untuk bertahan atau keluar, mulai dari karakteristik demografis, posisi jabatan, tingkat kepuasan kerja, beban kerja, hingga frekuensi lembur [2]. Pemahaman mendalam terhadap faktor-faktor ini memungkinkan perusahaan untuk mengambil langkah strategis dalam mempertahankan talenta terbaik, meningkatkan kesejahteraan karyawan, serta menciptakan lingkungan kerja yang lebih sehat dan produktif.
Proyek ini berada dalam domain People Analytics dan Human Resource Management (HRM), dengan fokus pada pengembangan model prediktif untuk mempelajari dan memprediksi perilaku employee attrition. Melalui pemanfaatan teknik data science dan machine learning, proyek ini bertujuan untuk: <br>
1. Mengidentifikasi variabel-variabel yang paling berpengaruh terhadap keputusan karyawan untuk keluar. <br>
2. Membangun model prediksi yang mampu mengestimasi kemungkinan attrition secara akurat meskipun menghadapi tantangan seperti ketidakseimbangan kelas dan interaksi fitur yang kompleks. <br>
3. Memberikan insight strategis yang dapat digunakan oleh manajemen untuk merancang kebijakan retensi karyawan yang lebih efektif. <br>
Dengan demikian, hasil analisis dari proyek ini diharapkan dapat membantu organisasi mengantisipasi potensi turnover lebih dini, meminimalkan biaya yang timbul akibat kehilangan karyawan berprestasi, serta meningkatkan keberlanjutan dan efisiensi operasional perusahaan secara keseluruhan.


### Referensi
[1] Kossivi, B., Xu, M., & Kalgora, B. (2016). Study on determining factors of employee retention. Open Journal of Social Sciences, 4(5), 261–268. https://doi.org/10.4236/jss.2016.45029 <br>
[2] Samuel, M. O., & Chipunza, C. (2009). Employee retention and turnover: Using motivational variables as a panacea. African Journal of Business Management, 3(8), 410–415. <br>
[3] @misc{tugas-1-sml-a-2025,
    author = {Muhammad Tsaqif},
    title = {Tugas 1 SML A 2025},
    year = {2025},
    howpublished = {\url{https://kaggle.com/competitions/tugas-1-sml-a-2025}},
    note = {Kaggle}
}

---

## Business Understanding

### Problem Statements
Dalam dunia bisnis modern, perusahaan menghadapi tantangan serius berupa meningkatnya jumlah karyawan yang meninggalkan organisasi (employee attrition). Tingginya tingkat turnover berdampak pada peningkatan biaya rekrutmen, turunnya produktivitas, serta gangguan terhadap stabilitas dan moral tim.
Berdasarkan latar belakang tersebut, pernyataan masalah yang diangkat dalam proyek ini adalah sebagai berikut: <br>
1. Bagaimana mengidentifikasi faktor-faktor penting yang memengaruhi keputusan karyawan untuk meninggalkan perusahaan? <br>
2. Bagaimana membangun model prediksi yang mampu memperkirakan kemungkinan seorang karyawan akan keluar dengan tingkat akurasi yang tinggi? <br>
3. Bagaimana menyusun strategi berbasis data yang dapat membantu manajemen dalam menurunkan tingkat attrition serta meningkatkan kepuasan dan retensi karyawan? <br>


### Goals
Untuk menjawab permasalahan di atas, tujuan proyek ini adalah: <br>
1. Melakukan eksplorasi dan analisis data karyawan untuk mengidentifikasi pola, hubungan antarvariabel, serta faktor-faktor utama yang berkontribusi terhadap turnover. <br>
2. Membangun model prediktif berbasis machine learning yang dapat menghitung probabilitas seorang karyawan akan keluar berdasarkan fitur-fitur yang tersedia. <br>
3. Memberikan rekomendasi strategis kepada manajemen berdasarkan hasil prediksi dan analisis fitur penting untuk meningkatkan retensi dan kesejahteraan karyawan.

### Solution Statements
Untuk mencapai tujuan-tujuan tersebut, solusi yang akan diimplementasikan meliputi: <br>
1. Eksperimen Berbagai Algoritma Klasifikasi <br>
Membangun dan membandingkan performa beberapa algoritma machine learning, seperti: <br>
a. Logistic Regression <br>
b. Random Forest <br>
c. XGBoost  <br>
d. LightGBM <br>

2. Optimasi Model dengan Hyperparameter Tuning
Menggunakan pendekatan seperti Bayesian Optimization (melalui Optuna) untuk menemukan kombinasi parameter model terbaik. <br>
3. Evaluasi Model dengan Metrik yang Relevan <br>
Menggunakan metrik evaluasi yang sesuai untuk kasus klasifikasi dengan kelas tidak seimbang, yaitu: <br>
a. Accuracy → untuk mengukur kinerja keseluruhan model. <br>
b. Precision, Recall, dan F1-Score → untuk menilai performa model khususnya pada kelas attrition. <br>
c. ROC-AUC → untuk mengukur kemampuan model dalam membedakan antara karyawan yang bertahan dan yang keluar. <br>
d. Confusion Matrix → untuk melihat distribusi hasil prediksi model.

4. Analisis Fitur dan Visualisasi <br>
Menyajikan analisis visual untuk memahami variabel-variabel yang paling berpengaruh terhadap turnover.

### Project Benefits
Dengan implementasi solusi ini, manfaat utama yang diharapkan antara lain: <br>
1. Efisiensi Biaya: Mengurangi biaya rekrutmen dan pelatihan dengan mempertahankan karyawan berpotensi tinggi. <br>
2. Peningkatan Retensi Karyawan: Mengidentifikasi dan memberikan intervensi tepat waktu kepada karyawan dengan risiko tinggi untuk keluar. <br>
3. Peningkatan Produktivitas dan Moral: Menurunkan tingkat pergantian tenaga kerja demi menjaga stabilitas dan kolaborasi tim. <br>
4. Pengambilan Keputusan Berbasis Data: Memberikan dasar analisis yang kuat bagi manajemen SDM dalam merancang kebijakan retensi dan kesejahteraan karyawan. <br>
5. Keberlanjutan Organisasi: Mendukung strategi jangka panjang perusahaan dengan menjaga stabilitas tenaga kerja yang berkualitas. <br>
  

---

## Data Understanding

### Sumber Data
Data berasal dari dataset Employee Attrition Prediction (Kaggle) yang dapat diakses pada Muhammad Tsaqif. Tugas 1 SML A 2025. https://kaggle.com/competitions/tugas-1-sml-a-2025, 2025. Kaggle dengan 1173 observasi dan 36 variabel di data training serta 294 observasi dan 36 variabel di data test.

### Deskripsi Fitur
| **Feature** | **Insight / Temuan Utama** |
|--------------|-----------------------------|
| **Age** | Karyawan yang keluar cenderung berusia lebih muda dibandingkan yang bertahan. |
| **DailyRate** | Tidak ada perbedaan berarti antara karyawan keluar dan bertahan. |
| **DistanceFromHome** | Karyawan yang tinggal lebih jauh dari kantor sedikit lebih sering keluar. |
| **Education** | Tingkat pendidikan tidak menunjukkan pengaruh signifikan terhadap attrition. |
| **EmployeeCount** | Nilai konstan di seluruh data. Tidak berpengaruh terhadap model. |
| **EmployeeNumber** | Hanya berfungsi sebagai ID unik, tidak memiliki makna analitis. |
| **EnvironmentSatisfaction** | Attrition lebih tinggi pada karyawan dengan kepuasan lingkungan kerja rendah. |
| **HourlyRate** | Tidak menunjukkan perbedaan mencolok antara yang keluar dan bertahan. |
| **JobInvolvement** | Karyawan dengan tingkat keterlibatan kerja rendah lebih sering keluar. |
| **JobLevel** | Attrition lebih sering terjadi pada level jabatan rendah. |
| **JobSatisfaction** | Kepuasan kerja rendah berasosiasi kuat dengan attrition tinggi. |
| **MonthlyIncome** | Rata-rata pendapatan karyawan yang keluar lebih rendah. |
| **MonthlyRate** | Tidak menunjukkan pola yang jelas terhadap attrition. |
| **NumCompaniesWorked** | Karyawan yang pernah bekerja di lebih banyak perusahaan cenderung lebih sering keluar. |
| **PercentSalaryHike** | Tidak ada perbedaan signifikan terhadap status attrition. |
| **PerformanceRating** | Mayoritas memiliki rating sama, tidak relevan untuk prediksi. |
| **RelationshipSatisfaction** | Nilai kepuasan hubungan yang rendah lebih sering ditemukan pada karyawan yang keluar. |
| **StandardHours** | Nilai konstan (umumnya 80) di seluruh data. Tidak informatif. |
| **StockOptionLevel** | Tidak menunjukkan pola jelas terhadap attrition. |
| **TotalWorkingYears** | Karyawan dengan pengalaman kerja lebih sedikit lebih sering keluar. |
| **TrainingTimesLastYear** | Karyawan dengan pelatihan lebih sedikit sedikit lebih sering keluar. |
| **WorkLifeBalance** | Karyawan dengan work-life balance buruk lebih sering keluar. |
| **YearsAtCompany** | Lama bekerja berbanding terbalik dengan attrition — semakin lama, semakin kecil peluang keluar. |
| **YearsInCurrentRole** | Karyawan baru di posisi saat ini lebih sering keluar. |
| **YearsSinceLastPromotion** | Attrition sedikit meningkat pada karyawan yang lama tidak dipromosikan. |
| **YearsWithCurrManager** | Karyawan yang baru bekerja dengan manajer lebih sering keluar. |
| **Over18** | Semua bernilai sama (“Y”), tidak berpengaruh terhadap model. |

---

Terdapat **36 fitur** meliputi:  
- `id` — ID unik karyawan untuk identifikasi.  
- `Age` — Usia karyawan.  
- `BusinessTravel` — Frekuensi perjalanan dinas karyawan (contoh: Non-Travel, Travel_Rarely, Travel_Frequently).  
- `DailyRate` — Gaji harian.  
- `Department` — Departemen tempat karyawan bekerja (contoh: Sales, Research & Development, Human Resources).  
- `DistanceFromHome` — Jarak tempat tinggal karyawan ke kantor.  
- `Education` — Tingkat pendidikan terakhir: 1 = Below College, 2 = College, 3 = Bachelor, 4 = Master, 5 = Doctor.  
- `EducationField` — Bidang studi terakhir karyawan (contoh: Life Sciences, Medical, Marketing).  
- `EmployeeCount` — Jumlah karyawan (selalu 1 dalam dataset).  
- `EmployeeNumber` — Nomor unik karyawan dalam sistem HR.  
- `EnvironmentSatisfaction` — Tingkat kepuasan terhadap lingkungan kerja: 1 = Low, 2 = Medium, 3 = High, 4 = Very High.  
- `Gender` — Jenis kelamin karyawan (Male/Female).  
- `HourlyRate` — Upah per jam.  
- `JobInvolvement` — Tingkat keterlibatan pekerjaan: 1 = Low, 2 = Medium, 3 = High, 4 = Very High.  
- `JobLevel` — Level jabatan karyawan.  
- `JobRole` — Posisi/jabatan spesifik karyawan (contoh: Sales Executive, Research Scientist).  
- `JobSatisfaction` — Tingkat kepuasan pekerjaan: 1 = Low, 2 = Medium, 3 = High, 4 = Very High.  
- `MaritalStatus` — Status pernikahan karyawan (Single, Married, Divorced).  
- `MonthlyIncome` — Gaji bulanan karyawan.  
- `MonthlyRate` — Tarif bulanan karyawan.  
- `NumCompaniesWorked` — Jumlah perusahaan tempat karyawan pernah bekerja sebelumnya.  
- `Over18` — Status usia di atas 18 tahun (selalu Y dalam dataset).  
- `OverTime` — Apakah karyawan sering lembur (Yes/No).  
- `PercentSalaryHike` — Persentase kenaikan gaji tahunan terakhir.  
- `PerformanceRating` — Penilaian kinerja terakhir: 1 = Low, 2 = Good, 3 = Excellent, 4 = Outstanding.  
- `RelationshipSatisfaction` — Tingkat kepuasan terhadap hubungan kerja: 1 = Low, 2 = Medium, 3 = High, 4 = Very High.  
- `StandardHours` — Jam kerja standar (selalu 80 dalam dataset).  
- `StockOptionLevel` — Level kepemilikan saham perusahaan.  
- `TotalWorkingYears` — Total tahun pengalaman kerja.  
- `TrainingTimesLastYear` — Jumlah pelatihan yang diikuti dalam setahun terakhir.  
- `WorkLifeBalance` — Tingkat keseimbangan kerja–hidup: 1 = Bad, 2 = Good, 3 = Better, 4 = Best.  
- `YearsAtCompany` — Total tahun bekerja di perusahaan saat ini.  
- `YearsInCurrentRole` — Total tahun di posisi/jabatan saat ini.  
- `YearsSinceLastPromotion` — Tahun sejak promosi terakhir.  
- `YearsWithCurrManager` — Tahun bekerja dengan manajer saat ini.  
- `Attrition` — Target: apakah karyawan keluar dari perusahaan (1 = Yes / 0 = No).  

### Exploratory Data Analysis (EDA)
- Statistika Deskriptif Numerik <br>
## Statistik Deskriptif Dataset Karyawan

| Statistik | Age | DailyRate | DistanceFromHome | Education | EmployeeCount | EmployeeNumber | EnvironmentSatisfaction | HourlyRate | JobInvolvement | JobLevel | ... | StandardHours | StockOptionLevel | TotalWorkingYears | TrainingTimesLastYear | WorkLifeBalance | YearsAtCompany | YearsInCurrentRole | YearsSinceLastPromotion | YearsWithCurrManager | Attrition |
|:-----------|:------:|:-----------:|:----------------:|:----------:|:--------------:|:----------------:|:--------------------------:|:-----------:|:---------------:|:-----------:|:---:|:---------------:|:------------------:|:----------------:|:---------------------:|:----------------:|:----------------:|:-------------------:|:--------------------------:|:---------------------:|:----------:|
| **count** | 1176.000 | 1176.000 | 1176.000 | 1176.000 | 1176.0 | 1176.000 | 1176.000 | 1176.000 | 1176.000 | 1176.000 | ... | 1176.0 | 1176.000 | 1176.000 | 1176.000 | 1176.000 | 1176.000 | 1176.000 | 1176.000 | 1176.000 | 1176.000 |
| **mean** | 36.998 | 803.991 | 9.358 | 2.906 | 1.0 | 1015.831 | 2.717 | 65.500 | 2.737 | 2.077 | ... | 80.0 | 0.791 | 11.365 | 2.760 | 2.758 | 7.050 | 4.231 | 2.183 | 4.196 | 0.162 |
| **std** | 9.178 | 401.339 | 8.180 | 1.028 | 0.0 | 599.657 | 1.089 | 20.373 | 0.704 | 1.092 | ... | 0.0 | 0.846 | 7.801 | 1.256 | 0.718 | 6.087 | 3.570 | 3.215 | 3.565 | 0.368 |
| **min** | 18.000 | 103.000 | 1.000 | 1.000 | 1.0 | 1.000 | 1.000 | 30.000 | 1.000 | 1.000 | ... | 80.0 | 0.000 | 0.000 | 0.000 | 1.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| **25%** | 30.000 | 467.750 | 2.000 | 2.000 | 1.0 | 487.750 | 2.000 | 48.000 | 2.000 | 1.000 | ... | 80.0 | 0.000 | 6.000 | 2.000 | 2.000 | 3.000 | 2.000 | 0.000 | 2.000 | 0.000 |
| **50%** | 36.000 | 799.500 | 7.000 | 3.000 | 1.0 | 1004.500 | 3.000 | 66.000 | 3.000 | 2.000 | ... | 80.0 | 1.000 | 10.000 | 3.000 | 3.000 | 5.000 | 3.000 | 1.000 | 3.000 | 0.000 |
| **75%** | 43.000 | 1157.000 | 14.000 | 4.000 | 1.0 | 1547.250 | 4.000 | 83.000 | 3.000 | 3.000 | ... | 80.0 | 1.000 | 15.000 | 3.000 | 3.000 | 10.000 | 7.000 | 3.000 | 7.000 | 0.000 |
| **max** | 60.000 | 1499.000 | 29.000 | 5.000 | 1.0 | 2062.000 | 4.000 | 100.000 | 4.000 | 5.000 | ... | 80.0 | 3.000 | 40.000 | 6.000 | 4.000 | 37.000 | 17.000 | 15.000 | 17.000 | 1.000 |

Dataset ini mencerminkan profil 1176 karyawan dari sebuah perusahaan. Karyawan memiliki usia rata-rata 37 tahun dan sebagian besar memiliki Job Level 1 hingga 3 (ditunjukkan oleh nilai kuartil). Mereka memiliki pengalaman kerja rata-rata sekitar 11.4 tahun dan telah bekerja di perusahaan ini selama sekitar 7 tahun. Aktivitas kerja harian menunjukkan rata-rata Daily Rate (gaji harian) sekitar 804 dan rata-rata Hourly Rate (gaji per jam) sekitar 65. Meskipun sebagian besar karyawan berada pada Job Involvement level 3, ada variasi dalam Work-Life Balance (rata-rata 2.75 dari skala 1 hingga 4). Rata-rata jarak tempuh ke rumah (DistanceFromHome) adalah 9.4 unit, namun ada juga karyawan yang tinggal hingga 29 unit jauhnya. Karyawan menghabiskan rata-rata 11.4 tahun bekerja secara total dan 4.2 tahun dalam peran saat ini, menunjukkan stabilitas manajer yang cukup baik dengan rata-rata 4.2 tahun bekerja dengan manajer saat ini. Meskipun rata-rata hanya 2 kali menerima pelatihan tahun lalu, ada yang menerima hingga 6 kali. Rata-rata tingkat attrition (berhenti bekerja) pada dataset ini adalah 16.2%, dengan standar deviasi yang cukup tinggi (0.36), menunjukkan variasi signifikan dalam kecenderungan karyawan untuk keluar. Terdapat variasi dalam pengalaman kerja, kompensasi, dan keseimbangan hidup, yang merupakan faktor penting untuk prediksi attrition karyawan. <br>

- **Statistika Deskriptif Kategorikal** <br>
## Description of Categorical Variables

### **id**
| ID | Count |
|:------|------:|
| WA862 | 2 |
| TP136 | 2 |
| BN287 | 2 |
| UF013 | 1 |
| BR784 | 1 |
| ... | ... |
| XI719 | 1 |
| AW894 | 1 |
| FE054 | 1 |
| DJ187 | 1 |
| OI063 | 1 |
| **Total Unique IDs** | **1173** |

---

### **BusinessTravel**
| Category | Count |
|:------------------|------:|
| Travel_Rarely | 828 |
| Travel_Frequently | 225 |
| Non-Travel | 123 |

---

### **Department**
| Department | Count |
|:-------------------------|------:|
| Research & Development | 764 |
| Sales | 364 |
| Human Resources | 48 |

---

### **EducationField**
| Education Field | Count |
|:----------------------|------:|
| Life Sciences | 479 |
| Medical | 364 |
| Marketing | 134 |
| Technical Degree | 115 |
| Other | 62 |
| Human Resources | 22 |

---

### **Gender**
| Gender | Count |
|:--------|------:|
| Male | 704 |
| Female | 472 |

---

### **JobRole**
| Job Role | Count |
|:-----------------------------|------:|
| Sales Executive | 273 |
| Research Scientist | 220 |
| Laboratory Technician | 215 |
| Manufacturing Director | 113 |
| Healthcare Representative | 108 |
| Manager | 83 |
| Research Director | 63 |
| Sales Representative | 60 |
| Human Resources | 41 |

---

### **MaritalStatus**
| Marital Status | Count |
|:---------------|------:|
| Married | 540 |
| Single | 373 |
| Divorced | 263 |

---

### **Over18**
| Category | Count |
|:----------|------:|
| Y | 1176 |

---

### **OverTime**
| Category | Count |
|:----------|------:|
| No | 836 |
| Yes | 340 |

Karyawan yang keluar cenderung memiliki usia rata-rata yang lebih muda dibandingkan karyawan yang bertahan. Mereka memiliki gaji bulanan yang jauh lebih rendah (rata-rata 4843 vs. 6871) dan juga menerima Daily Rate yang lebih rendah (738 vs. 816). Mereka juga rata-rata memiliki Total Working Years dan Years At Company yang lebih singkat (masing-masing 8.05 tahun dan 4.9 tahun) dibandingkan rekan kerja yang bertahan (12.0 tahun dan 7.4 tahun). <br> <br>
Dalam hal komitmen dan kepuasan kerja, karyawan yang Keluar menunjukkan beberapa tanda risiko: <br>
Job Level mereka cenderung lebih rendah (1.66 vs. 2.15). <br>
Memiliki tingkat Environment Satisfaction, Job Satisfaction, dan Work-Life Balance yang sedikit lebih rendah. <br>
Rata-rata bekerja di lebih banyak perusahaan (2.96), menunjukkan kecenderungan job hopping yang lebih tinggi. <br>
Memiliki Years With Current Manager yang jauh lebih singkat (2.8 tahun) dibandingkan karyawan yang bertahan (4.4 tahun), menandakan hubungan manajerial yang kurang stabil. <br> <br>
Secara umum, karyawan yang Keluar menunjukkan profil yang lebih muda, berstatus kompensasi dan jabatan lebih rendah, serta memiliki tingkat kepuasan kerja dan stabilitas manajerial yang lebih pasif dibandingkan rekan kerja yang memilih untuk tetap bertahan. Pola ini sangat konsisten dengan risiko tinggi attrition pada karyawan yang lebih baru dan memiliki komitmen finansial/karir yang lebih rendah. <br>

- **Missing Value dan Outlier** <br>
## Total Outliers per Feature (Based on IQR)

| Feature | Number of Outliers |
|:---------------------------|------------------:|
| MonthlyIncome | 86 |
| NumCompaniesWorked | 36 |
| PerformanceRating | 185 |
| StockOptionLevel | 66 |
| TotalWorkingYears | 52 |
| TrainingTimesLastYear | 174 |
| YearsAtCompany | 52 |
| YearsInCurrentRole | 16 |
| YearsSinceLastPromotion | 85 |
| YearsWithCurrManager | 10 |
| Attrition | 190 |

---

Kemudian, dilakukan deteksi outlier menggunakan metode Interquartile Range (IQR) untuk setiap fitur numerik. Hasil analisis menunjukkan bahwa beberapa variabel yang berkaitan dengan rating dan riwayat pelatihan memiliki jumlah outlier yang sangat signifikan : <br>
1. PerformanceRating menunjukkan jumlah outlier tertinggi (185 outlier), mengindikasikan adanya evaluasi kinerja yang ekstrem (sangat tinggi atau sangat rendah). <br>
2. TrainingTimesLastYear juga memiliki jumlah outlier yang tinggi (174 outlier), menunjukkan adanya variasi ekstrem dalam frekuensi pelatihan yang diikuti karyawan. <br>
3. Variabel yang berkaitan dengan target, Attrition (sebagai variabel biner 0/1 yang dianalisis sebagai outlier), memiliki 190 outlier. Dalam konteks data biner, ini secara sederhana merefleksikan jumlah aktual kasus attrition (Kelas 1), menyoroti sifat data yang tidak seimbang (imbalance). <br>
4. Keberadaan outlier yang tinggi pada fitur-fitur seperti PerformanceRating dan TrainingTimesLastYear mengindikasikan adanya variasi ekstrem dalam evaluasi dan investasi perusahaan terhadap karyawan. Beberapa fitur lain, meskipun dalam jumlah yang lebih rendah, juga menunjukkan adanya pencilan yang signifikan dalam konteks total sampel 1176 : <br>
YearsSinceLastPromotion (85 outlier),
MonthlyIncome (86 outlier), dan
StockOptionLevel (66 outlier).
Sementara itu, variabel yang berkaitan dengan stabilitas kerja, seperti YearsWithCurrManager (10 outlier) dan YearsInCurrentRole (16 outlier), memiliki jumlah outlier terendah di antara fitur-fitur yang terdeteksi, menandakan distribusi nilai yang relatif stabil untuk fitur-fitur yang mengukur komitmen peran dan manajerial saat ini. <br>

![Boxplot](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/boxplot%20outlier.png?raw=true) 
Visualisasi melalui boxplot semakin memperjelas sebaran data dan keberadaan outlier di setiap fitur. Fitur seperti MonthlyIncome, TotalWorkingYears, dan YearsAtCompany tampak memiliki sebaran yang lebar dengan banyak data berada di luar whisker (batas IQR), yang mengindikasikan variasi nilai ekstrim dalam kompensasi dan riwayat kerja.
MonthlyIncome menunjukkan outlier yang signifikan pada kuartil atas, menandakan adanya segmen karyawan dengan gaji yang jauh lebih tinggi dari rata-rata.
TotalWorkingYears dan YearsAtCompany memiliki banyak outlier pada nilai yang tinggi (di atas 30 tahun), menunjukkan adanya veteran perusahaan dalam jumlah yang substansial.
Fitur-fitur seperti NumCompaniesWorked, YearsSinceLastPromotion, dan YearsInCurrentRole juga memiliki banyak titik data yang tersebar luas di atas whisker atas, menyoroti adanya job hopper dan karyawan dengan masa promosi/peran yang sangat panjang atau sangat singkat.
Meskipun demikian, outlier tidak dihapus dari dataset. Hal ini dilakukan untuk menjaga keutuhan informasi, mengingat data pencilan tersebut mencerminkan kondisi nyata seperti profil karyawan senior (veteran) atau karyawan yang sangat sering pindah kerja (job hopper). <br>

Menghilangkan outlier justru berisiko menghilangkan pola penting dalam konteks analisis attrition karyawan. Sebagai langkah mitigasi terhadap pengaruh outlier, model machine learning yang digunakan adalah model berbasis tree (XGBoost, LightGBM, Random Forest), sehingga lebih robust terhadap outlier karena keputusan split didasarkan pada ambang batas (nilai kuartil) dan bukan pada nilai absolut atau jarak rata-rata. <br>

**Sementara itu, tidak ditemukan missing value pada seluruh variabel pada dataset sehingga tidak perlu dilakukan imputasi dan tidak ada data duplikat sehingga analisis dapat dilanjutkan.** <br>

- Proporsi Attrition Karyawan <br>
![Pie](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/pie%20chart%20attrition.png?raw=true)

Proporsi karyawan yang keluar (Attrition = 1) dalam dataset hanya sebesar 16.2%, sementara mayoritas karyawan bertahan (Attrition = 0), yaitu 83.8%. Angka ini jelas menunjukkan ketidakseimbangan kelas (class imbalance) yang signifikan.
Untuk mengatasi dominasi kelas mayoritas yang dapat membuat model bias dan buruk dalam memprediksi kasus Attrition yang langka, diterapkan beberapa strategi berikut: <br> 
1. Stratified K-Fold Cross Validation: Digunakan untuk memastikan proporsi Attrition tetap seimbang pada data pelatihan, validasi, dan pengujian, termasuk saat proses tuning hyperparameter, sehingga model tidak hanya belajar dari kelas mayoritas. <br>
2. Penyesuaian Bobot Kelas (Scale Pos Weight): Diberikan bobot yang jauh lebih tinggi pada kelas minoritas (Attrition = 1) (sekitar 5.2:1) di dalam model boosting (XGBoost/LightGBM). Ini membuat model lebih sensitif terhadap kesalahan klasifikasi pada kasus Attrition (kelas minoritas) yang berharga. <br>
3. Prediksi Probabilistik & Kalibrasi: Fokus diarahkan pada prediksi probabilitas Attrition, bukan hanya klasifikasi biner. Selain itu, kalibrasi prediksi diterapkan untuk menyesuaikan rata-rata probabilitas prediksi dengan proporsi nyata 16.2%, memastikan keputusan bisnis lebih akurat dan fleksibel. <br><br>

- Heatmap Variabel <br>
Analisis menggunakan Heatmap digunakan untuk melihat hubungan antara dua variabel numerik pada Dataset. <br>
![Heatmap](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/heatmap.png?raw=true) 
1. Age memiliki korelasi positif tinggi dengan TotalWorkingYears (0.69) dan MonthlyIncome (0.52), menunjukkan bahwa semakin lama pengalaman kerja seseorang, umumnya semakin tua dan pendapatannya lebih tinggi. <br>
2. JobLevel juga berkorelasi kuat dengan MonthlyIncome (0.95) dan TotalWorkingYears (0.77), menandakan bahwa karyawan dengan level jabatan lebih tinggi cenderung memiliki pengalaman dan pendapatan yang lebih besar. <br>
3. YearsAtCompany, YearsInCurrentRole, dan YearsWithCurrManager menunjukkan korelasi positif yang kuat (≥0.6), mengindikasikan bahwa lama bekerja dalam satu posisi biasanya sejalan dengan lamanya masa kerja dan hubungan dengan manajer yang sama. <br>
4. Attrition memiliki korelasi negatif moderat terhadap Age (-0.16), MonthlyIncome (-0.17), dan TotalWorkingYears (-0.17). Artinya, karyawan yang lebih muda, berpenghasilan rendah, dan memiliki pengalaman kerja lebih sedikit cenderung memiliki risiko keluar lebih tinggi. <br>
5. Korelasi antar variabel kompensasi seperti MonthlyIncome, JobLevel, dan TotalWorkingYears menunjukkan adanya redundansi informasi — misalnya, MonthlyIncome dan JobLevel sangat berkorelasi (0.95), sehingga salah satu dapat dihapus dalam analisis untuk menghindari multikolinearitas. <br>
6. Variabel seperti EnvironmentSatisfaction, JobSatisfaction, dan WorkLifeBalance memiliki korelasi sangat rendah antar variabel numerik lainnya, menandakan bahwa persepsi kepuasan kerja bersifat independen dari faktor demografis dan kompensasi. <br>

Secara lebih jelas, beberapa hubungan antara 2 variabel tersebut dapat divisualisasikan sebagai berikut: <br>
![Corr](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/hub%202%20var.png?raw=true) 

Menariknya, terlihat bahwa karyawan yang berhenti bekerja (Attrition = 1) umumnya memiliki usia dan masa kerja yang lebih pendek. Pada grafik pertama, titik oranye terkonsentrasi pada kelompok usia muda dengan masa kerja di bawah 10 tahun. Pola serupa muncul pada grafik kedua di mana karyawan dengan pendapatan bulanan rendah lebih sering mengalami attrition. Sementara itu, pada grafik ketiga, karyawan dengan masa kerja panjang tetapi jarang mendapat promosi juga menunjukkan kecenderungan keluar dari perusahaan. Hal ini menegaskan bahwa baik faktor ekonomi maupun stagnasi karier berperan dalam meningkatkan risiko attrition. <br>

- Rata-rata Fitur per Kategori Attrition <br>
## Average of Numerical Features per Attrition Category

| Feature | Attrition = 0 | Attrition = 1 |
|:---------------------------------|---------------:|---------------:|
| Age | 37.744422 | 33.126316 |
| DailyRate | 816.564909 | 738.742105 |
| DistanceFromHome | 9.046653 | 10.973684 |
| Education | 2.919878 | 2.836842 |
| EmployeeCount | 1.000000 | 1.000000 |
| EmployeeNumber | 1009.796146 | 1047.147368 |
| EnvironmentSatisfaction | 2.770791 | 2.436842 |
| HourlyRate | 65.673428 | 64.600000 |
| JobInvolvement | 2.775862 | 2.536842 |
| JobLevel | 2.156187 | 1.663158 |
| JobSatisfaction | 2.769777 | 2.457895 |
| MonthlyIncome | 6871.638945 | 4843.878947 |
| MonthlyRate | 14321.476673 | 14747.084211 |
| NumCompaniesWorked | 2.639959 | 2.968421 |
| PercentSalaryHike | 15.254564 | 15.163158 |
| PerformanceRating | 3.156187 | 3.163158 |
| RelationshipSatisfaction | 2.759635 | 2.631579 |
| StandardHours | 80.000000 | 80.000000 |
| StockOptionLevel | 0.843813 | 0.515789 |
| TotalWorkingYears | 12.002028 | 8.057895 |
| TrainingTimesLastYear | 2.781947 | 2.647368 |
| WorkLifeBalance | 2.782961 | 2.626316 |
| YearsAtCompany | 7.464503 | 4.900000 |
| YearsInCurrentRole | 4.492901 | 2.873684 |
| YearsSinceLastPromotion | 2.243408 | 1.868421 |
| YearsWithCurrManager | 4.460446 | 2.826316 |
| Attrition | 0.000000 | 1.000000 |

---

Karyawan yang keluar cenderung memiliki usia rata-rata yang lebih muda dibandingkan karyawan yang bertahan. Mereka memiliki gaji bulanan yang jauh lebih rendah (rata-rata 4843 vs. 6871) dan juga menerima Daily Rate yang lebih rendah (738 vs. 816). Mereka juga rata-rata memiliki Total Working Years dan Years At Company yang lebih singkat (masing-masing 8.05 tahun dan 4.9 tahun) dibandingkan rekan kerja yang bertahan (12.0 tahun dan 7.4 tahun). Dalam hal komitmen dan kepuasan kerja, karyawan yang Keluar menunjukkan beberapa tanda risiko: <br>
a. Job Level mereka cenderung lebih rendah (1.66 vs. 2.15). <br>
b. Memiliki tingkat Environment Satisfaction, Job Satisfaction, dan Work-Life Balance yang sedikit lebih rendah. <br>
c. Rata-rata bekerja di lebih banyak perusahaan (2.96), menunjukkan kecenderungan job hopping yang lebih tinggi. <br>
d. Memiliki Years With Current Manager yang jauh lebih singkat (2.8 tahun) dibandingkan karyawan yang bertahan (4.4 tahun), menandakan hubungan manajerial yang kurang stabil. <br>
Secara umum, karyawan yang Keluar menunjukkan profil yang lebih muda, berstatus kompensasi dan jabatan lebih rendah, serta memiliki tingkat kepuasan kerja dan stabilitas manajerial yang lebih pasif dibandingkan rekan kerja yang memilih untuk tetap bertahan. Pola ini sangat konsisten dengan risiko tinggi attrition pada karyawan yang lebih baru dan memiliki komitmen finansial/karir yang lebih rendah. <br>

- Distribusi Variabel Kategorik <br>
![DistK](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/plot%20var%20kat.png?raw=true)
**Distribusi Demografi dan Status Karyawan** <br><br>
a. Mayoritas karyawan adalah Laki-laki (sekitar 60%) berbanding Perempuan (sekitar 40%). Sebagian besar karyawan berstatus Menikah (sekitar 52%), diikuti oleh Lajang (sekitar 35%), dan Sisanya Bercerai.<br>
b. Dalam hal pendidikan dan jabatan, bidang studi yang dominan adalah Life Sciences dan Medical, diikuti oleh Marketing dan Technical Degree. Variabel JobRole menunjukkan sebaran yang cukup beragam, namun Sales Executive dan Research Scientist adalah peran dengan jumlah karyawan terbesar. <br><br>
**Distribusi Aktivitas dan Risiko** <br><br>
a. Variabel BusinessTravel menunjukkan bahwa mayoritas (sekitar 70%) adalah Travel Rarely, mengindikasikan bahwa perjalanan dinas yang intensif (Travel Frequently) hanya dialami oleh segmen kecil karyawan. <br>
b. Sebanyak 83.8% karyawan memiliki nilai Over18 'Y', dan fitur ini memiliki distribusi yang sangat tidak seimbang (hanya satu nilai dominan), sehingga tidak memberikan informasi prediktif. <br>
c. Variabel OverTime menunjukkan ketidakseimbangan kelas yang signifikan, dengan sekitar 70% karyawan tidak bekerja lembur (No) dan sisanya bekerja lembur (Yes). Proporsi 30% karyawan yang bekerja lembur ini merupakan risiko attrition yang tinggi dan perlu strategi manajemen beban kerja. <br><br>

  
- Perbandingan Proporsi Attrition Tiap Variabel Kategorik <br>
![Prop](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/dist%20kat%20based%20asstrition.png?raw=true)
1. BusinessTravel:
Karyawan yang sering bepergian dinas (Travel_Frequently) memiliki tingkat attrition tertinggi. Hal ini menunjukkan bahwa intensitas perjalanan bisnis yang tinggi dapat meningkatkan kelelahan kerja dan keinginan untuk keluar. <br>
2. Department:
Tingkat attrition tertinggi terdapat pada Sales dan Human Resources, sedangkan Research & Development relatif lebih stabil.  <br>
3. EducationField:
Latar belakang Human Resources dan Marketing memiliki proporsi keluar lebih besar dibandingkan bidang teknis seperti Life Sciences dan Technical Degree.  <br>
4. Gender:
Pria menunjukkan sedikit kecenderungan attrition lebih tinggi dibanding wanita, meskipun perbedaannya tidak mencolok.  <br>
5. JobRole:
Sales Representative dan Laboratory Technician menjadi dua posisi dengan tingkat attrition tertinggi, sedangkan Manager dan Research Director paling rendah. Hal ini menunjukkan perbedaan stabilitas karier anta level jabatan.  <br>
6. MaritalStatus:
Karyawan lajang (Single) paling rentan keluar dibanding yang menikah atau bercerai. Hal ini menunjukkan bahwa status pernikahan bisa jadi berkaitan dengan kebutuhan stabilitas finansial dan loyalitas kerja.  <br>
7. Over18:
Seluruh karyawan tercatat dalam kategori "Yes" (berusia di atas 18 tahun), sedangkan kategori "No" tidak muncul sama sekali pada grafik. Hal ini menandakan bahwa variabel Over18 bersifat konstan dalam dataset, sehingga tidak memberikan informasi pembeda terhadap attrition dan bisa dihapus dari analisis lebih lanjut.  <br>
8. OverTime:
Karyawan yang sering lembur (Yes) memiliki tingkat attrition jauh lebih tinggi dibanding yang tidak. Ini mengindikasikan bahwa kelelahan akibat lembur merupakan faktor penting penyebab turnover.  <br> <br>

- Distribusi Variabel Numerik <br>
![Dist1](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/plot%20var%20num.png?raw=true)
**Distribusi Karyawan dan Demografi** <br> <br>
- Age: Sebaran usia karyawan mendekati distribusi normal, dengan sebagian besar karyawan berada dalam rentang usia 28 hingga 40 tahun. <br>
- DistanceFromHome: Distribusi ini miring ke kanan (skewed to the right), menunjukkan bahwa sebagian besar karyawan tinggal relatif dekat (jarak tempuh 2-10 unit), namun terdapat ekor panjang yang mencapai 29 unit, menandakan adanya komuter jarak jauh. <br>
- Education, JobInvolvement, JobSatisfaction, EnvironmentSatisfaction, RelationshipSatisfaction, WorkLifeBalance: Semua fitur ini memiliki distribusi yang cenderung seragam atau bimodal dengan puncak pada nilai 3 atau 4 (rata-rata atau tinggi), mengindikasikan bahwa sebagian besar karyawan melaporkan tingkat kepuasan, keterlibatan, dan keseimbangan yang moderat hingga baik. <br>
- PerformanceRating: Fitur ini hampir konstan, menunjukkan bahwa mayoritas karyawan dinilai 3.0, dengan hanya sedikit yang dinilai 4.0 (hanya ada dua nilai unik: 3 dan 4). <br> <br>
**Distribusi Kompensasi dan Tenure** <br><br>
- MonthlyIncome, DailyRate, HourlyRate, MonthlyRate: Distribusi fitur kompensasi ini cenderung simetris atau sedikit miring ke kanan. <br>
- MonthlyIncome menunjukkan sebaran yang luas, dengan puncak yang jelas pada kuadran pendapatan rendah hingga menengah, namun terdapat ekor panjang yang mewakili segmen karyawan berpenghasilan sangat tinggi (terutama pada JobLevel tinggi). <br>
- TotalWorkingYears, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion, YearsWithCurrManager: Fitur tenure (masa kerja) ini semuanya memiliki sebaran yang miring kuat ke kanan. Hal ini wajar, menunjukkan bahwa sebagian besar karyawan memiliki masa kerja, peran, dan promosi yang singkat (0-5 tahun), sementara karyawan senior (> 20 tahun) menjadi minoritas. <br> <br>
**Distribusi Risiko dan Kepemilikan** <br><br>
- NumCompaniesWorked: Sebaran miring ke kanan yang ekstrem, dengan sebagian besar karyawan hanya bekerja di satu atau dua
perusahaan sebelum ini. Ini menyoroti bahwa job hopper (karyawan dengan 5 perusahaan) merupakan segmen kecil. <br>
- StockOptionLevel: Fitur ini menunjukkan sebaran miring ke kanan, dengan mayoritas karyawan berada pada level 0 atau 1. <br>
- Attrition: Distribusi ini sangat tidak seimbang (imbalanced), dengan 83.8% berada pada Kelas 0 (Bertahan) dan 16.2% berada pada Kelas 1 (Keluar), menegaskan pentingnya strategi class weighting dalam pemodelan. <br>


- **Perbandingan Proporsi Attrition Tiap Variabel Numerik** <br>
![Prop](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/dist%20num%20based%20attrition.png?raw=true)

## Feature Insights Summary

| **Feature** | **Insight / Temuan Utama** |
|--------------|-----------------------------|
| **Age** | Karyawan yang keluar cenderung berusia lebih muda dibandingkan yang bertahan. |
| **DailyRate** | Tidak ada perbedaan berarti antara karyawan keluar dan bertahan. |
| **DistanceFromHome** | Karyawan yang tinggal lebih jauh dari kantor sedikit lebih sering keluar. |
| **Education** | Tingkat pendidikan tidak menunjukkan pengaruh signifikan terhadap attrition. |
| **EmployeeCount** | Nilai konstan di seluruh data. Tidak berpengaruh terhadap model. |
| **EmployeeNumber** | Hanya berfungsi sebagai ID unik, tidak memiliki makna analitis. |
| **EnvironmentSatisfaction** | Attrition lebih tinggi pada karyawan dengan kepuasan lingkungan kerja rendah. |
| **HourlyRate** | Tidak menunjukkan perbedaan mencolok antara yang keluar dan bertahan. |
| **JobInvolvement** | Karyawan dengan tingkat keterlibatan kerja rendah lebih sering keluar. |
| **JobLevel** | Attrition lebih sering terjadi pada level jabatan rendah. |
| **JobSatisfaction** | Kepuasan kerja rendah berasosiasi kuat dengan attrition tinggi. |
| **MonthlyIncome** | Rata-rata pendapatan karyawan yang keluar lebih rendah. |
| **MonthlyRate** | Tidak menunjukkan pola yang jelas terhadap attrition. |
| **NumCompaniesWorked** | Karyawan yang pernah bekerja di lebih banyak perusahaan cenderung lebih sering keluar. |
| **PercentSalaryHike** | Tidak ada perbedaan signifikan terhadap status attrition. |
| **PerformanceRating** | Mayoritas memiliki rating sama, tidak relevan untuk prediksi. |
| **RelationshipSatisfaction** | Nilai kepuasan hubungan yang rendah lebih sering ditemukan pada karyawan yang keluar. |
| **StandardHours** | Nilai konstan (umumnya 80) di seluruh data. Tidak informatif. |
| **StockOptionLevel** | Tidak menunjukkan pola jelas terhadap attrition. |
| **TotalWorkingYears** | Karyawan dengan pengalaman kerja lebih sedikit lebih sering keluar. |
| **TrainingTimesLastYear** | Karyawan dengan pelatihan lebih sedikit sedikit lebih sering keluar. |
| **WorkLifeBalance** | Karyawan dengan work-life balance buruk lebih sering keluar. |
| **YearsAtCompany** | Lama bekerja berbanding terbalik dengan attrition — semakin lama, semakin kecil peluang keluar. |
| **YearsInCurrentRole** | Karyawan baru di posisi saat ini lebih sering keluar. |
| **YearsSinceLastPromotion** | Attrition sedikit meningkat pada karyawan yang lama tidak dipromosikan. |
| **YearsWithCurrManager** | Karyawan yang baru bekerja dengan manajer lebih sering keluar. |
| **Over18** | Semua bernilai sama (“Y”), tidak berpengaruh terhadap model. |

## Kesimpulan EDA

Karyawan yang keluar (**Attrition = 1**) memiliki profil risiko yang konsisten dan kontras dengan karyawan yang bertahan (**Attrition = 0**). Beberapa temuan utama dari analisis eksploratif adalah sebagai berikut:

### 🧩 **1. Usia dan Masa Kerja**
- Karyawan yang keluar cenderung **lebih muda** dengan rata-rata usia **33 tahun**, dibandingkan dengan **37 tahun** pada karyawan yang bertahan.  
- Mereka juga memiliki **masa kerja total** dan **lama bekerja di perusahaan** yang lebih singkat (sekitar **4.9 hingga 8.05 tahun**).  
➡️ *Menunjukkan bahwa pengalaman dan loyalitas meningkat seiring usia dan lama bekerja.*

---

### 💰 **2. Kompensasi dan Jabatan**
- Karyawan yang keluar memiliki **gaji bulanan jauh lebih rendah** (rata-rata **4.843** vs **6.871**).  
- Mereka juga umumnya berada pada **Job Level yang lebih rendah**.  
➡️ *Faktor ekonomi dan posisi jabatan menjadi indikator kuat terhadap risiko turnover.*

---

### 😊 **3. Kepuasan dan Stabilitas**
- Tingkat **kepuasan kerja, lingkungan, dan hubungan** sedikit lebih rendah pada karyawan yang keluar.  
- Mereka juga memiliki **masa kerja dengan manajer saat ini** yang lebih singkat.  
➡️ *Kepuasan kerja dan stabilitas hubungan manajerial berperan penting dalam mempertahankan karyawan.*

---

### 🌍 **4. Faktor Eksternal**
- Karyawan yang **sering melakukan perjalanan dinas (Travel_Frequently)** dan **sering lembur (OverTime = Yes)** memiliki risiko keluar lebih tinggi.  
➡️ *Mengindikasikan bahwa kelelahan dan beban kerja berlebih menjadi pemicu utama attrition.*

---

### 👥 **5. Status dan Peran**
- Karyawan dengan **status lajang (Single)** paling rentan mengalami attrition.  
- **Sales Representative** dan **Laboratory Technician** termasuk peran dengan tingkat keluar tertinggi.  
➡️ *Menunjukkan perlunya perhatian khusus terhadap kelompok dan jabatan dengan risiko tinggi.*

---

**📊 Kesimpulan Akhir:**  
Faktor yang paling berpengaruh terhadap attrition mencakup **usia, pendapatan, level jabatan, kepuasan kerja, beban kerja, dan status pernikahan**. Strategi retensi perlu difokuskan pada **peningkatan kesejahteraan, keseimbangan kerja, serta peluang karier bagi karyawan muda dan berpenghasilan rendah.**


## Modeling & Evaluation

### Data Preparation
**1. Penyebaran Atrrition Karyawan di Training dan Testing Data** <br>
#### 📊 Data Overview

- **Train set:** (1176, 36)  
- **Test set:** (294, 36)

#### 🔹 Distribusi Kelas (Attrition)

| Kelas | Jumlah | Persentase |
|:------|--------:|-----------:|
| 0 (Bertahan) | 986 | 83.8% |
| 1 (Keluar) | 190 | 16.2% |

**Rasio:** 5.2 : 1  
➡️ Terjadi *class imbalance*, di mana jumlah karyawan yang bertahan jauh lebih banyak dibanding yang keluar.

**2. Drop Variabel Konstan** <br>
Variabel yang hanya berisi satu nilai dihapus dari dataset karena tidak mengandung informasi apapun. Pada dataset ini ditemukan bahwa variabel EmployeeCount, Over18, dan StandardHours hanya memiliki satu nilai. Sehingga ketiga variabel tersebut akan dihapuskan. Selain itu, variabel id juga di drop karena merupakan nilai unik setiap karyawan yang tidak digunakan dalam analisis. <br>

**3. Splitting Dataset** <br>
Menetapkan stratify = y sehingga fungsi train_test_split memastikan bahwa proses pemisahan mempertahankan persentase yang sama dari setiap kelas target di set train dan test.
Dataset yang digunakan dalam analisis ini terdiri dari data pelatihan (train) dan data pengujian (test) dengan rincian sebagai berikut: <br>
- Ukuran data fitur (train): 1.176 observasi dengan 31 fitur.
- Ukuran data target (train): 1.176 observasi.
- Ukuran data fitur (test): 294 observasi dengan 31 fitur.
- Ukuran data target (test): 294 observasi.

**4. Feature Engineering** <br>
Preprocessing untuk Model Berbasis Tree
- Fitur Numerik:
Tidak akan dilakukan transformasi apa pun karena model berbasis tree tidak memerlukan feature scaling. <br>
- Fitur Kategorikal (Ordinal):
Akan diterapkan ordinal encoding untuk mempertahankan karakteristik ordinal. <br>
- Fitur Kategorikal (Nominal):
Akan diterapkan target encoding karena penggunaan one-hot encoding dapat merugikan model berbasis tree akibat sparse representation dan meningkatnya dimensi. <br>
- Fitur Gender: Akan diterapkan one-hot encoding karena fitur ini akan diubah menjadi variabel biner unik, sehingga tidak meningkatkan dimensi. <br>

Untuk mendapatkan informasi maksimal dari fitur yang tersedia, dilakukan feature engineering yang sudah terintegrasi dalam preprocessing dengan membuat fitur-fitur berikut: <br>

### 🔹 Fitur Rasio dan Indeks
1. `ExperienceRatio` = YearsAtCompany / (TotalWorkingYears + 1)  
   → Menggambarkan proporsi pengalaman kerja yang dihabiskan di perusahaan saat ini.

2. `CurrentRoleRatio` = YearsInCurrentRole / (YearsAtCompany + 1)  
   → Mengukur seberapa lama seseorang bertahan dalam peran saat ini dibanding total masa kerja di perusahaan.

3. `JobHoppingRate` = NumCompaniesWorked / (TotalWorkingYears + 1)  
   → Indikator mobilitas karier atau kecenderungan berpindah pekerjaan.

4. `ManagerStability` = YearsWithCurrManager / (YearsAtCompany + 1)  
   → Mengukur kestabilan hubungan dengan manajer langsung.

5. `IncomePerYear` = MonthlyIncome / (TotalWorkingYears + 1)  
   → Mengindikasikan pendapatan relatif terhadap pengalaman kerja.

6. `Commitment_Index` = YearsAtCompany / (NumCompaniesWorked + 1)  
   → Indeks loyalitas berdasarkan lama bekerja dan jumlah perusahaan sebelumnya.

7. `DailyRate_x_JobSat_Negative` = DailyRate × (5 - JobSatisfaction)  
   → Mendeteksi potensi ketidakpuasan pada karyawan dengan bayaran tinggi.

8. `MonthlyRate_Per_Hour` = MonthlyRate / (HourlyRate + 1)  
   → Mengevaluasi konsistensi struktur kompensasi antar level.

---

### 🔹 Fitur Biner (Kondisional)
9. `IsYoung` = 1 jika Age < 30  
10. `ShortTenure` = 1 jika YearsAtCompany < 2  
11. `TimeWithoutPromotion` = 1 jika YearsSinceLastPromotion > 3  
12. `LowJobLevel` = 1 jika JobLevel ≤ 1  
13. `LongCommute` = 1 jika DistanceFromHome > 15  
14. `PoorWorkLife` = 1 jika WorkLifeBalance ≤ 2  

---

### 🔹 Fitur Komposit dan Interaksi
15. `AvgSatisfaction` = Rata-rata dari EnvironmentSatisfaction, JobSatisfaction, RelationshipSatisfaction, dan WorkLifeBalance  
16. `LowSatisfaction` = 1 jika AvgSatisfaction < 2  
17. `HighRisk_Flag` = 1 jika OverTime = 1, JobSatisfaction ≤ 2, dan WorkLifeBalance ≤ 2  
18. `Career_Stagnation` = 1 jika YearsSinceLastPromotion > 5 dan YearsAtCompany > 10  
19. `Income_JobLevel` = MonthlyIncome × JobLevel  
20. `Age_Experience` = Age × TotalWorkingYears  
21. `Satisfaction_Performance` = AvgSatisfaction × PerformanceRating  

---

### 🔹 Fitur Komposit Utama
22. `AttritionRiskScore`  
   = (LowSatisfaction × 2.5) + (OverTime × 2.5) + (LongCommute × 1.0) +  
     (TimeWithoutPromotion × 2.0) + (ShortTenure × 1.5) + (JobHoppingRate × 12) +  
     (PoorWorkLife × 1.5) + (LowJobLevel × 1.0) − (Commitment_Index × 5) +  
     (HighRisk_Flag × 3.0) + (Career_Stagnation × 2.0)  
   → Skor gabungan yang memperkirakan tingkat risiko karyawan untuk keluar.

---

Hasil akhir:
- **Fitur awal:** 31 kolom  
- **Setelah rekayasa fitur:** bertambah menjadi **54 kolom**.  
- Seluruh kolom bersifat **numerik dan aman untuk perhitungan model machine learning.**

### Model Training, Comparison, Selection and Tuning

**1. Model Selection** <br>
Proses pelatihan model dilakukan menggunakan beberapa algoritma **tree-based classifier** .  Semua model dievaluasi dengan **K-Fold Cross Validation** untuk memastikan hasil yang stabil di data imbalance. <br>

| Model | Library | Deskripsi |
|--------|----------|-----------|
| **Random Forest** | `sklearn.ensemble` | Model berbasis ensemble dari banyak decision tree yang mengurangi overfitting dan meningkatkan akurasi. |
| **LightGBM (LGBMClassifier)** | `lightgbm` | Algoritma gradient boosting berbasis histogram, cepat dan efisien pada dataset besar. |
| **XGBoost (XGBClassifier)** | `xgboost` | Gradient boosting yang dioptimasi, kuat terhadap overfitting dan memiliki performa tinggi untuk prediksi biner seperti attrition. |

### Metode Evaluasi: K-Fold Cross Validation
Fungsi `classification_kfold_cv()` digunakan untuk melakukan **Stratified K-Fold CV**, yaitu pembagian data menjadi *k subset* dengan menjaga proporsi kelas (0 dan 1) tetap seimbang pada setiap fold.
#### Langkah-langkah:
1. **Membagi data** menjadi `n_folds` bagian (default = 5).  
2. Melatih model di `(n_folds - 1)` bagian, dan menguji di 1 bagian.  
3. Mengulangi proses untuk setiap fold dan menghitung rata-rata metrik.

### Metrik Evaluasi
| Metrik | Rumus | Interpretasi |
|---------|--------|--------------|
| **Accuracy** | `(TP + TN) / (TP + TN + FP + FN)` | Proporsi prediksi benar dari total prediksi. |
| **Recall (Sensitivity)** | `TP / (TP + FN)` | Kemampuan model mengenali karyawan yang benar-benar keluar (Attrition = 1). |
| **Specificity** | `TN / (TN + FP)` | Kemampuan model mengenali karyawan yang tetap bertahan. |
| **ROC AUC** | Luas di bawah kurva ROC | Ukuran keseluruhan kemampuan model membedakan kelas 0 dan 1. |

### Output
| Model | Val AUC | Val Accuracy | Val Recall | Val Specificity | Training Time (s) |
|--------|----------|--------------|-------------|------------------|-------------------|
| XGBoost | 0.795874 | 0.866491 | 0.357895 | 0.964498 | 0.218701 |
| Random Forest | 0.784152 | 0.862243 | 0.215789 | 0.986812 | 0.390005 |
| LightGBM | 0.802276 | 0.868179 |0.321053 | 0.973609 | 0.31981 |

![Perform](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/model%20perform.png?raw=true)

Dalam proses feature selection, model LightGBM dipilih karena menunjukkan performa rata-rata terbaik (Val AUC = 0.80; Val Accuracy = 0.87; Val Specificity = 0.97) dengan waktu pelatihan cukup cepat di antara ketiga model. Meskipun model mengalami indikasi overfitting (skor ROC-AUC sebesar 1 pada data pelatihan), hasil validasi tetap sangat tinggi (0,97), menunjukkan generalisasi yang kuat. Namun, karena perbedaan performa dengan XGBoost tidak terlalu signifikan, mempertimbangkan hasil keduanya dalam proses feature selection dapat dijadikan opsi untuk memastikan variabel penting yang dipilih bersifat stabil dan konsisten di berbagai algoritma. <br>

**2. Feature Selection** <br>
Langkah seleksi fitur sangat penting untuk meningkatkan kemampuan generalisasi model dan membuatnya lebih sederhana, sehingga menambah efisiensi komputasi. Mengingat terdapat 54 fitur, menyederhanakan model tanpa kehilangan performa adalah keuntungan yang sangat besar. Oleh karena itu, digunakanlah metode Random Forest untuk seleksi fitur. <br>
Random Forest dipilih sebagai metode seleksi fitur karena mampu menangani variabel numerik dan kategorik, tahan terhadap noise/outlier dan multikolinearitas, serta dapat memberikan interpretasi yang mudah dipahami melalui feature importance
Feature importance menampilkan seberapa besar kontribusi masing-masing fitur terhadap kemampuan model dalam membuat prediksi. Berdasarkan hasil dari model Random Forest, fitur-fitur seperti AttritionRiskScore, Age_Experience, dan Income_JobLevel memiliki pengaruh paling besar terhadap prediksi. 
Sebagai hasilnya, jumlah fitur berhasil dikurangi dari 54 menjadi **45 fitur paling penting**, yang secara signifikan mengurangi kompleksitas komputasi. <br>

Berikut adalah hasil pemeringkatan fitur berdasarkan nilai **feature importance** pada model prediksi *Employee Attrition*.  
Fitur diurutkan dari yang paling berpengaruh hingga yang paling rendah.

| Rank | Feature Name | Importance |
|------|---------------|------------|
| 1 | `AttritionRiskScore` | **0.0660** |
| 2 | `Age_Experience` | **0.0613** |
| 3 | `Income_JobLevel` | **0.0432** |
| 4 | `Age` | **0.0426** |
| 5 | `MonthlyIncome` | **0.0409** |
| 6 | `JobHoppingRate` | **0.0359** |
| 7 | `TotalWorkingYears` | **0.0325** |
| 8 | `IncomePerYear` | **0.0287** |
| 9 | `DailyRate` | **0.0284** |
| 10 | `MonthlyRate_Per_Hour` | **0.0269** |
| 11 | `AvgSatisfaction` | **0.0265** |
| 12 | `HourlyRate` | **0.0264** |
| 13 | `OverTime_Binary` | **0.0261** |
| 14 | `EmployeeNumber` | **0.0250** |
| 15 | `Satisfaction_Performance` | **0.0244** |
| 16 | `MonthlyRate` | **0.0241** |
| 17 | `DailyRate_x_JobSat_Negative` | **0.0240** |
| 18 | `Commitment_Index` | **0.0234** |
| 19 | `DistanceFromHome` | **0.0228** |
| 20 | `OverTime` | **0.0220** |
| 21 | `ManagerStability` | 0.0202 |
| 22 | `StockOptionLevel` | 0.0198 |
| 23 | `YearsAtCompany` | 0.0182 |
| 24 | `JobRole` | 0.0182 |
| 25 | `PercentSalaryHike` | 0.0168 |
| 26 | `ExperienceRatio` | 0.0153 |
| 27 | `MaritalStatus` | 0.0152 |
| 28 | `EnvironmentSatisfaction` | 0.0150 |
| 29 | `JobInvolvement` | 0.0144 |
| 30 | `YearsWithCurrManager` | 0.0144 |
| 31 | `NumCompaniesWorked` | 0.0140 |
| 32 | `CurrentRoleRatio` | 0.0133 |
| 33 | `WorkLifeBalance` | 0.0121 |
| 34 | `EducationField` | 0.0115 |
| 35 | `TrainingTimesLastYear` | 0.0113 |
| 36 | `RelationshipSatisfaction` | 0.0111 |
| 37 | `JobSatisfaction` | 0.0107 |
| 38 | `YearsInCurrentRole` | 0.0102 |
| 39 | `YearsSinceLastPromotion` | 0.0101 |
| 40 | `Education` | 0.0100 |
| 41 | `BusinessTravel` | 0.0083 |
| 42 | `HighRisk_Flag` | 0.0076 |
| 43 | `IsYoung` | 0.0072 |
| 44 | `Department` | 0.0069 |
| 45 | `LowJobLevel` | 0.0069 |

---

**3. Model Training & Evaluation Setup** <br>
Model diuji menggunakan tiga algoritma berbasis *ensemble learning* yaitu **XGBoost**, **LightGBM**, dan **Random Forest** — tanpa penerapan *oversampling* (SMOTE). Sebagai gantinya, dilakukan *class reweighting* untuk menyeimbangkan distribusi kelas secara proporsional.

#### 🔹 Handling Imbalanced Data
- Dataset memiliki ketidakseimbangan kelas dengan rasio **5.19 : 1** (kelas bertahan jauh lebih banyak daripada keluar).  
- Untuk mengatasinya:
  - **XGBoost & LightGBM:** menggunakan parameter `scale_pos_weight = 5.19`.
  - **RandomForest:** menggunakan `class_weight='balanced'`.

#### 🔹 Data Splitting
Data dibagi untuk keperluan tuning dan validasi:
| Dataset | Jumlah Data | Jumlah Fitur |
|:---------|-------------:|-------------:|
| Training (X_temp) | 940 | 45 |
| Validation (X_val) | 236 | 45 |

Proses pembagian dilakukan dengan *stratified sampling* untuk menjaga proporsi kelas yang seimbang di setiap subset.

#### 🔹 Cross-Validation Setting
- **Metode:** 5-Fold Stratified Cross-Validation  
- **Metric Evaluasi:** ROC-AUC  
- **Alasan Pemilihan Metric:** AUC lebih stabil untuk data tidak seimbang, fokus pada kemampuan model membedakan kelas *Attrition (1)* dan *Stay (0)*.

---

#### Model Performance 

| Model | Mean AUC (CV) | ± 2×Std | Catatan |
|:------|---------------:|--------:|:--------|
| **LightGBM** | **0.7838** | ± 0.0685 | Performa terbaik; mampu menangkap pola kompleks tanpa overfitting. |
| **XGBoost** | 0.7803 | ± 0.0728 | Hampir setara dengan LightGBM; stabil pada berbagai fold. |
| **Random Forest** | 0.7714 | ± 0.0748 | Masih kompetitif, namun cenderung kurang optimal pada data numerik tinggi. |

---

- Ketiga model menunjukkan performa **cukup baik (AUC ~0.77–0.78)** meskipun tanpa *oversampling*.  
- **LightGBM** sedikit unggul, menunjukkan efisiensi dalam menangani fitur hasil *feature engineering* yang beragam.  
- Pendekatan *class weight balancing* terbukti efektif menggantikan SMOTE dalam kasus ini, menjaga integritas data asli tanpa menambah observasi sintetis.  

**4. Hyperparameter Tuning** <br>
#### Dataset & Setting
- **Scale Pos Weight (Ratio 0/1):** 5.19  
- **Train–Validation Split:**  
  - Training (X_temp): 940 sampel  
  - Validation (X_val): 236 sampel  
- **CV Method:** 5-Fold Stratified Cross-Validation  
- **Scoring Metric:** ROC-AUC  

---

#### Hasil Cross-Validation

| Model | Mean AUC | ± 2×Std | Catatan Utama |
|:--|:--:|:--:|:--|
| **RandomForest** | **0.7714** | ±0.0748 | Performa stabil, namun masih di bawah versi Balanced. |
| **BalancedRF** | **0.7793** | ±0.0682 | Sedikit lebih baik karena teknik undersampling internal menangani imbalance. |
| **XGBoost** | **0.7803** | ±0.0728 | Kuat, manfaat dari `scale_pos_weight = 5.19` terlihat efektif. |
| **LightGBM** | **0.7838** | ±0.0685 | 🚀 **Model terbaik**; stabil dan efisien dengan penyeimbangan internal. |
| **GradientBoosting** | **0.7588** | ±0.0689 | Kurang optimal tanpa balancing internal. |
| **LogisticRegression** | **0.7530** | ±0.0802 | Performa terendah; linearitas membatasi kemampuan terhadap pola kompleks. |

---

1. **LightGBM** mencatat AUC tertinggi (**0.7838**), menandakan kemampuannya menangkap pola minoritas dengan baik.  
   - Penggunaan `scale_pos_weight` membantu menekan bias terhadap kelas mayoritas.  
   - Struktur leaf-wise meningkatkan efisiensi dan ketepatan prediksi.

2. **XGBoost** menempati posisi kedua (**0.7803**), dengan performa hampir identik dengan LightGBM.  
   - Lebih stabil tetapi cenderung lebih lama saat training.

3. **BalancedRandomForest** menunjukkan peningkatan dibanding **RandomForest standar**,  
   membuktikan efektivitas balancing internal berbasis undersampling.

4. **GradientBoosting** dan **LogisticRegression** tidak optimal karena tidak memiliki mekanisme balancing native.

### Tuning pada Model Terpilih
1. Tuning pada XGBoost <br>
Hasil pencarian parameter terbaik dengan **RandomizedSearchCV** (menggunakan 5-fold Stratified CV):

| Parameter | Nilai Terbaik |
|:--|:--:|
| `n_estimators` | **300** |
| `max_depth` | **6** |
| `learning_rate` | **0.2** |
| `subsample` | **0.8** |
| `colsample_bytree` | **0.9** |
| `reg_alpha` | **10** |
| `scale_pos_weight` | **5.19** *(rasio kelas dari data asli)* |

---

### Hasil Evaluasi Cross-Validation
- **Best CV AUC:** `0.8129`  
- **Data yang digunakan:** Tanpa SMOTE (data asli)  
- **Metode:** Stratified 5-Fold Cross-Validation  

---

2. Tuning pada LightGBM <br>
## ⚙️ Best Parameters

| Hyperparameter | Nilai Optimal | Penjelasan |
|:----------------|:--------------|:------------|
| `subsample` | **0.7** | Mengambil 70% data secara acak setiap iterasi untuk mencegah overfitting. |
| `reg_lambda` | **1.5** | Regularisasi L2 untuk menyeimbangkan kompleksitas model. |
| `reg_alpha` | **10** | Regularisasi L1 untuk menekan fitur yang tidak relevan. |
| `n_estimators` | **600** | Jumlah total pohon yang digunakan untuk boosting. |
| `max_depth` | **4** | Membatasi kedalaman tiap pohon untuk menjaga generalisasi. |
| `learning_rate` | **0.05** | Laju pembelajaran kecil agar model belajar lebih halus dan stabil. |
| `colsample_bytree` | **0.9** | Mengambil 90% fitur secara acak di setiap pohon untuk meningkatkan diversitas model. |

---
Didapatkan nilai Best CV AUC sebesar 0.8001  yang diukur dengan 5-fold Stratified Cross Validation pada data asli. <br>


**5. Final Ensemble Model — Soft Voting Classifier** <br>
Menggabungkan tiga model terbaik hasil tuning sebelumnya (XGBoost, LightGBM, dan Random Forest)  
ke dalam satu **ensemble classifier** berbasis **soft voting**, untuk memanfaatkan kekuatan kolektif masing-masing model.

---

## Model Penyusun Ensemble

| Model | Jenis | Penanganan Imbalance | Keterangan |
|:--|:--|:--|:--|
| **XGBoost** | Gradient Boosting Tree | `scale_pos_weight = 5.19` | Menggunakan hasil tuning terbaik (`best_params_`) |
| **LightGBM** | Gradient Boosting Framework | `scale_pos_weight = 5.19` | Menggunakan hasil tuning (`best_lgbm_params`) |
| **RandomForest** | Bagging Ensemble | `class_weight = 'balanced'` | Dikonfigurasi dengan `max_depth = 15` dan 200 estimator |

---

## Konfigurasi Ensemble

```python
ensemble_final = VotingClassifier(
    estimators=[
        ('xgb', xgb_tuned),
        ('lgb', lgbm_tuned),
        ('rf', rf_balanced)
    ],
    voting='soft',
    weights=[1, 2, 1],  # Bobot lebih besar untuk LightGBM karena performanya tertinggi
    n_jobs=-1
)
```
LightGBM diberi bobot lebih besar karena memiliki AUC tertinggi (0.7838) pada hasil cross-validation sebelumnya. Pendekatan ini memanfaatkan diversitas model di mana XGBoost unggul dalam fine-tuning fitur non-linear, LightGBM unggul dalam efisiensi dan generalisasi, RandomForest menambah robustness terhadap noise.

**6. Best Model** <br>
Langkah ini melibatkan **pelatihan ulang model terbaik** (hasil tuning) yaitu XGBoost dan LightGBM menggunakan seluruh data training (`X_sel`, `y_train`) untuk memaksimalkan pemanfaatan data tanpa pembagian ulang. Dua model digabung menggunakan rata-rata berbobot (weighted average) agar kontribusi tiap model sesuai performanya. Di mana pada model final ini diberikan bobot sebesar 0.83 pada LightGBM dan 0.17 pada XGBoost. Setelah digabung, dilakukan kalibrasi probabilitas agar rata-rata prediksi sesuai dengan proporsi aktual kelas positif (≈16.2%) pada data training.

## Model Testing & Evaluation

| Metric | Nilai | Penjelasan |
|:--|--:|:--|
| **Accuracy** | 0.8644 | Persentase prediksi yang benar dari seluruh data uji. Model memprediksi dengan benar sekitar **86%** dari total sampel. |
| **Precision** | 0.8750 | Dari seluruh data yang diprediksi **positif**, sebanyak **87.5%** benar-benar positif. Artinya model jarang salah mengidentifikasi kelas positif. |
| **Recall (Sensitivity)** | 0.1842 | Dari seluruh data yang sebenarnya **positif**, hanya **18.4%** yang berhasil dideteksi oleh model. Ini menunjukkan model masih kurang sensitif terhadap kelas positif. |
| **Specificity** | 0.9949 | Dari seluruh data yang sebenarnya **negatif**, sekitar **99.5%** berhasil diidentifikasi dengan benar. Model sangat baik dalam mengenali kelas negatif. |
| **F1-Score** | 0.3043 | Rata-rata harmonis antara precision dan recall. Nilai yang rendah menandakan ketidakseimbangan antara kemampuan mendeteksi dan ketepatan prediksi kelas positif. |
| **ROC AUC** | 0.7706 | Mengukur kemampuan model membedakan antara kelas positif dan negatif. Nilai **0.77** menandakan performa yang cukup baik secara keseluruhan. |

---

#### Confusion Matrix
| | **Predicted Positive** | **Predicted Negative** |
|:--|--:|--:|
| **Actual Positive** | 7 | 31 |
| **Actual Negative** | 1 | 197 |

**Interpretasi:**
- **True Positive (TP):** 7 → Kasus positif yang berhasil dideteksi dengan benar.  
- **False Negative (FN):** 31 → Kasus positif yang **gagal** dideteksi model.  
- **False Positive (FP):** 1 → Kasus negatif yang **salah diklasifikasikan** sebagai positif.  
- **True Negative (TN):** 197 → Kasus negatif yang diprediksi dengan benar.

---

**Plot Kurva ROC-AUC** <br>
![auc](https://github.com/andraekaaaa-beep/Analisis-Prediksi-Probabilitas-Attrition-SML-A/blob/main/image/roc%20auc.png?raw=true)

Model memiliki **akurasi tinggi** dan **spesifisitas sangat baik**, artinya kuat dalam mengenali kelas negatif.  Namun, **recall yang rendah (18%)** menunjukkan bahwa model **kurang mampu mendeteksi kelas positif**, yang mungkin merupakan kelas minoritas.  

### Save Best Model
filename = '../model/complete_model_package.pkl'

## Business Result
#### Estimasi Dampak Finansial Model terhadap Perusahaan (Kasus Attrition)

Untuk menunjukkan nilai tambah dari model prediksi ini, dilakukan estimasi dampak finansial berdasarkan **Confusion Matrix** hasil prediksi *Attrition* (karyawan keluar atau tidak).

### Confusion Matrix (Model Validation)

|                      | Predicted Attrition | Predicted Stay |
|----------------------|--------------------:|----------------:|
| **Actual Attrition** | 7 (TP) | 1 (FN) |
| **Actual Stay**      | 31 (FP) | 197 (TN) |

### Asumsi Dasar
- Rata-rata **biaya kehilangan karyawan (turnover cost)** adalah sekitar **30% dari gaji tahunan** (termasuk rekrutmen, pelatihan, dan kehilangan produktivitas).  Esrimasi 30% merupakan estimasi rata-rata dari biaya kehilangan karyawan menurut SHRM (Society for Human Resource Management) untuk posisi entry level
- **Biaya retensi** (misalnya bonus, pelatihan tambahan, atau promosi) untuk mencegah karyawan keluar diasumsikan **10% dari gaji tahunan**.
- Model digunakan untuk membantu tim HR dalam mengidentifikasi karyawan berisiko tinggi agar strategi retensi lebih efisien.

### Komponen Biaya & Manfaat

| Komponen | Penjelasan | Dampak Finansial |
|-----------|-------------|------------------|
| **True Positive (TP)** | Karyawan yang benar-benar akan keluar dan berhasil diidentifikasi oleh model → bisa ditindaklanjuti dengan program retensi. | *Manfaat:* Menghindari kehilangan 30% dari gaji tahunan. <br>  *Biaya:* Retensi 10% dari gaji. |
| **False Negative (FN)** | Karyawan yang keluar tapi tidak terdeteksi oleh model. |  *Kerugian:* Kehilangan 30% dari gaji. |
| **False Positive (FP)** | Karyawan yang diprediksi akan keluar tapi sebenarnya bertahan. | *Kerugian kecil:* Perusahaan mengeluarkan biaya retensi 10% tanpa perlu. |
| **True Negative (TN)** | Karyawan yang benar-benar bertahan dan tidak perlu biaya tambahan. |  *Netral / stabil.* |

### Ilustrasi Estimasi Dampak Finansial

Misalkan:
- Rata-rata gaji tahunan karyawan: **Rp120 juta**  
- Biaya turnover: **30% × 120 juta = Rp36 juta per orang**
- Biaya retensi: **10% × 120 juta = Rp12 juta per orang**

Dengan Confusion Matrix di atas:

| Komponen | Jumlah | Estimasi Dampak per Orang | Total Dampak |
|-----------|--------|---------------------------|---------------|
| **TP (7)** | 7 × (36 - 12) juta | = **Rp168 juta manfaat** |
| **FP (31)** | 31 × (−12 juta) | = **−Rp372 juta** |
| **FN (1)** | 1 × (−36 juta) | = **−Rp36 juta** |
| **TN (197)** | Tidak berdampak | = Rp0 juta |

📈 **Estimasi dampak bersih model: −Rp240 juta**

> ⚠️ Artinya, meskipun model membantu mendeteksi sebagian besar karyawan yang akan keluar, biaya retensi terhadap terlalu banyak *false positives* masih menyebabkan kerugian bersih.  
> Dengan penyesuaian ambang probabilitas (threshold) agar fokus pada karyawan dengan risiko tertinggi, potensi kerugian ini dapat berbalik menjadi keuntungan bersih.

## Kesimpulan <br>
- LightGBM menjadi model dengan performa paling konsisten (CV AUC tertinggi) dan memberikan kontribusi utama dalam ensemble. <br>
- Ensemble Voting (XGB + LGBM + RF) meningkatkan stabilitas prediksi dengan menjaga keseimbangan antara akurasi dan interpretabilitas. <br>
- Model menunjukkan akurasi tinggi (86%) namun recall rendah (18%), yang berarti masih cenderung lebih baik dalam mendeteksi karyawan yang bertahan daripada yang akan keluar. <br>
Untuk peningkatan ke depan, perlu dilakukan: <br>
1. Oversampling/undersampling yang lebih halus (misalnya SMOTE Tomek Links). <br>
2. Penyesuaian threshold probabilitas untuk meningkatkan recall. <br>
3. Penambahan fitur perilaku dan engagement karyawan agar model lebih sensitif terhadap sinyal keluar. <br>

Model ensemble menunjukkan kinerja yang stabil dan seimbang, terutama dalam mengenali karyawan yang tetap bertahan dengan tingkat kesalahan sangat rendah. Namun, recall yang rendah menunjukkan bahwa model masih berhati-hati dalam mendeteksi karyawan yang berpotensi keluar, kemungkinan akibat ketidakseimbangan kelas pada data. Model ensemble (LightGBM + XGBoost) yang telah dikalibrasi menghasilkan skor AUC 82.348% pada leaderboard Kaggle, yang menunjukkan bahwa pendekatan kombinasi model ini berhasil meningkatkan generalisasi dibandingkan model lain yang telah dicoba.

---

📊 *Project dibuat untuk tugas mata kuliah Statistical Machine Learning A (2025).*
