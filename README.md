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
Manajemen sumber daya manusia merupakan salah satu pilar utama dalam menjaga keberlanjutan dan daya saing sebuah perusahaan di era bisnis modern. Salah satu tantangan terbesar yang dihadapi organisasi adalah tingginya tingkat attrition atau employee turnover, yaitu kondisi ketika karyawan meninggalkan perusahaan baik secara sukarela maupun tidak. Fenomena ini menimbulkan berbagai konsekuensi, seperti meningkatnya biaya rekrutmen dan pelatihan, menurunnya produktivitas tim, serta terganggunya stabilitas operasional dan moral kerja di lingkungan perusahaan [1]. <br>
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
Dataset ini mencerminkan profil 1176 karyawan dari sebuah perusahaan. Karyawan memiliki usia rata-rata 37 tahun dan sebagian besar memiliki Job Level 1 hingga 3 (ditunjukkan oleh nilai kuartil). Mereka memiliki pengalaman kerja rata-rata sekitar 11.4 tahun dan telah bekerja di perusahaan ini selama sekitar 7 tahun.
Aktivitas kerja harian menunjukkan rata-rata Daily Rate (gaji harian) sekitar 804 dan rata-rata Hourly Rate (gaji per jam) sekitar 65. Meskipun sebagian besar karyawan berada pada Job Involvement level 3, ada variasi dalam Work-Life Balance (rata-rata 2.75 dari skala 1 hingga 4).
Rata-rata jarak tempuh ke rumah (DistanceFromHome) adalah 9.4 unit, namun ada juga karyawan yang tinggal hingga 29 unit jauhnya. Karyawan menghabiskan rata-rata 11.4 tahun bekerja secara total dan 4.2 tahun dalam peran saat ini, menunjukkan stabilitas manajer yang cukup baik dengan rata-rata 4.2 tahun bekerja dengan manajer saat ini.
Meskipun rata-rata hanya 2 kali menerima pelatihan tahun lalu, ada yang menerima hingga 6 kali. Rata-rata tingkat attrition (berhenti bekerja) pada dataset ini adalah 16.2%, dengan standar deviasi yang cukup tinggi (0.36), menunjukkan variasi signifikan dalam kecenderungan karyawan untuk keluar. Terdapat variasi dalam pengalaman kerja, kompensasi, dan keseimbangan hidup, yang merupakan faktor penting untuk prediksi attrition karyawan. <br>

- Statistika Deskriptif Kategorikal <br>
Karyawan yang keluar cenderung memiliki usia rata-rata yang lebih muda dibandingkan karyawan yang bertahan. Mereka memiliki gaji bulanan yang jauh lebih rendah (rata-rata 4843 vs. 6871) dan juga menerima Daily Rate yang lebih rendah (738 vs. 816). Mereka juga rata-rata memiliki Total Working Years dan Years At Company yang lebih singkat (masing-masing 8.05 tahun dan 4.9 tahun) dibandingkan rekan kerja yang bertahan (12.0 tahun dan 7.4 tahun).
Dalam hal komitmen dan kepuasan kerja, karyawan yang Keluar menunjukkan beberapa tanda risiko: <br>
Job Level mereka cenderung lebih rendah (1.66 vs. 2.15). <br>
Memiliki tingkat Environment Satisfaction, Job Satisfaction, dan Work-Life Balance yang sedikit lebih rendah. <br>
Rata-rata bekerja di lebih banyak perusahaan (2.96), menunjukkan kecenderungan job hopping yang lebih tinggi. <br>
Memiliki Years With Current Manager yang jauh lebih singkat (2.8 tahun) dibandingkan karyawan yang bertahan (4.4 tahun), menandakan hubungan manajerial yang kurang stabil.
Secara umum, karyawan yang Keluar menunjukkan profil yang lebih muda, berstatus kompensasi dan jabatan lebih rendah, serta memiliki tingkat kepuasan kerja dan stabilitas manajerial yang lebih pasif dibandingkan rekan kerja yang memilih untuk tetap bertahan. Pola ini sangat konsisten dengan risiko tinggi attrition pada karyawan yang lebih baru dan memiliki komitmen finansial/karir yang lebih rendah. <br>

- Missing Value dan Outlier <br>
Kemudian, dilakukan deteksi outlier menggunakan metode Interquartile Range (IQR) untuk setiap fitur numerik. Hasil analisis menunjukkan bahwa beberapa variabel yang berkaitan dengan rating dan riwayat pelatihan memiliki jumlah outlier yang sangat signifikan : <br>
1. PerformanceRating menunjukkan jumlah outlier tertinggi (185 outlier), mengindikasikan adanya evaluasi kinerja yang ekstrem (sangat tinggi atau sangat rendah). <br>
2. TrainingTimesLastYear juga memiliki jumlah outlier yang tinggi (174 outlier), menunjukkan adanya variasi ekstrem dalam frekuensi pelatihan yang diikuti karyawan. <br>
3. Variabel yang berkaitan dengan target, Attrition (sebagai variabel biner 0/1 yang dianalisis sebagai outlier), memiliki 190 outlier. Dalam konteks data biner, ini secara sederhana merefleksikan jumlah aktual kasus attrition (Kelas 1), menyoroti sifat data yang tidak seimbang (imbalance). <br>
4. Keberadaan outlier yang tinggi pada fitur-fitur seperti PerformanceRating dan TrainingTimesLastYear mengindikasikan adanya variasi ekstrem dalam evaluasi dan investasi perusahaan terhadap karyawan. Beberapa fitur lain, meskipun dalam jumlah yang lebih rendah, juga menunjukkan adanya pencilan yang signifikan dalam konteks total sampel 1176 : <br>
YearsSinceLastPromotion (85 outlier),
MonthlyIncome (86 outlier), dan
StockOptionLevel (66 outlier).
Sementara itu, variabel yang berkaitan dengan stabilitas kerja, seperti YearsWithCurrManager (10 outlier) dan YearsInCurrentRole (16 outlier), memiliki jumlah outlier terendah di antara fitur-fitur yang terdeteksi, menandakan distribusi nilai yang relatif stabil untuk fitur-fitur yang mengukur komitmen peran dan manajerial saat ini. <br>

Visualisasi melalui boxplot semakin memperjelas sebaran data dan keberadaan outlier di setiap fitur. Fitur seperti MonthlyIncome, TotalWorkingYears, dan YearsAtCompany tampak memiliki sebaran yang lebar dengan banyak data berada di luar whisker (batas IQR), yang mengindikasikan variasi nilai ekstrim dalam kompensasi dan riwayat kerja.
MonthlyIncome menunjukkan outlier yang signifikan pada kuartil atas, menandakan adanya segmen karyawan dengan gaji yang jauh lebih tinggi dari rata-rata.
TotalWorkingYears dan YearsAtCompany memiliki banyak outlier pada nilai yang tinggi (di atas 30 tahun), menunjukkan adanya veteran perusahaan dalam jumlah yang substansial.
Fitur-fitur seperti NumCompaniesWorked, YearsSinceLastPromotion, dan YearsInCurrentRole juga memiliki banyak titik data yang tersebar luas di atas whisker atas, menyoroti adanya job hopper dan karyawan dengan masa promosi/peran yang sangat panjang atau sangat singkat.
Meskipun demikian, outlier tidak dihapus dari dataset. Hal ini dilakukan untuk menjaga keutuhan informasi, mengingat data pencilan tersebut mencerminkan kondisi nyata seperti profil karyawan senior (veteran) atau karyawan yang sangat sering pindah kerja (job hopper). <br>

Menghilangkan outlier justru berisiko menghilangkan pola penting dalam konteks analisis attrition karyawan. Sebagai langkah mitigasi terhadap pengaruh outlier, model machine learning yang digunakan adalah model berbasis tree (XGBoost, LightGBM, Random Forest), sehingga lebih robust terhadap outlier karena keputusan split didasarkan pada ambang batas (nilai kuartil) dan bukan pada nilai absolut atau jarak rata-rata.

- Heatmap Variabel <br>
1. Age memiliki korelasi positif tinggi dengan TotalWorkingYears (0.69) dan MonthlyIncome (0.52), menunjukkan bahwa semakin lama pengalaman kerja seseorang, umumnya semakin tua dan pendapatannya lebih tinggi. <br>
2. JobLevel juga berkorelasi kuat dengan MonthlyIncome (0.95) dan TotalWorkingYears (0.77), menandakan bahwa karyawan dengan level jabatan lebih tinggi cenderung memiliki pengalaman dan pendapatan yang lebih besar. <br>
3. YearsAtCompany, YearsInCurrentRole, dan YearsWithCurrManager menunjukkan korelasi positif yang kuat (≥0.6), mengindikasikan bahwa lama bekerja dalam satu posisi biasanya sejalan dengan lamanya masa kerja dan hubungan dengan manajer yang sama. <br>
4. Attrition memiliki korelasi negatif moderat terhadap Age (-0.16), MonthlyIncome (-0.17), dan TotalWorkingYears (-0.17). Artinya, karyawan yang lebih muda, berpenghasilan rendah, dan memiliki pengalaman kerja lebih sedikit cenderung memiliki risiko keluar lebih tinggi. <br>
5. Korelasi antar variabel kompensasi seperti MonthlyIncome, JobLevel, dan TotalWorkingYears menunjukkan adanya redundansi informasi — misalnya, MonthlyIncome dan JobLevel sangat berkorelasi (0.95), sehingga salah satu dapat dihapus dalam analisis untuk menghindari multikolinearitas. <br>
6. Variabel seperti EnvironmentSatisfaction, JobSatisfaction, dan WorkLifeBalance memiliki korelasi sangat rendah antar variabel numerik lainnya, menandakan bahwa persepsi kepuasan kerja bersifat independen dari faktor demografis dan kompensasi. <br>

- Distribusi Fitur <br>
Menariknya, terlihat bahwa karyawan yang berhenti bekerja (Attrition = 1) umumnya memiliki usia dan masa kerja yang lebih pendek. Pada grafik pertama, titik oranye terkonsentrasi pada kelompok usia muda dengan masa kerja di bawah 10 tahun. Pola serupa muncul pada grafik kedua — karyawan dengan pendapatan bulanan rendah lebih sering mengalami attrition. Sementara itu, pada grafik ketiga, karyawan dengan masa kerja panjang tetapi jarang mendapat promosi juga menunjukkan kecenderungan keluar dari perusahaan. Hal ini menegaskan bahwa baik faktor ekonomi maupun stagnasi karier berperan dalam meningkatkan risiko attrition. <br>

- Rata-rata Fitur per Kategori Attrition <br>
Karyawan yang keluar cenderung memiliki usia rata-rata yang lebih muda dibandingkan karyawan yang bertahan. Mereka memiliki gaji bulanan yang jauh lebih rendah (rata-rata 4843 vs. 6871) dan juga menerima Daily Rate yang lebih rendah (738 vs. 816). Mereka juga rata-rata memiliki Total Working Years dan Years At Company yang lebih singkat (masing-masing 8.05 tahun dan 4.9 tahun) dibandingkan rekan kerja yang bertahan (12.0 tahun dan 7.4 tahun). Dalam hal komitmen dan kepuasan kerja, karyawan yang Keluar menunjukkan beberapa tanda risiko: <br>
a. Job Level mereka cenderung lebih rendah (1.66 vs. 2.15). <br>
b. Memiliki tingkat Environment Satisfaction, Job Satisfaction, dan Work-Life Balance yang sedikit lebih rendah. <br>
c. Rata-rata bekerja di lebih banyak perusahaan (2.96), menunjukkan kecenderungan job hopping yang lebih tinggi. <br>
d. Memiliki Years With Current Manager yang jauh lebih singkat (2.8 tahun) dibandingkan karyawan yang bertahan (4.4 tahun), menandakan hubungan manajerial yang kurang stabil. <br>
Secara umum, karyawan yang Keluar menunjukkan profil yang lebih muda, berstatus kompensasi dan jabatan lebih rendah, serta memiliki tingkat kepuasan kerja dan stabilitas manajerial yang lebih pasif dibandingkan rekan kerja yang memilih untuk tetap bertahan. Pola ini sangat konsisten dengan risiko tinggi attrition pada karyawan yang lebih baru dan memiliki komitmen finansial/karir yang lebih rendah.

- Proporsi Perbandingan Kategori Attrition
# 📊 Employee Attrition Feature Insights

Ringkasan temuan utama dari analisis fitur terhadap status *attrition* karyawan (apakah keluar atau bertahan).

---

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

💡 *Catatan:*  
Fitur-fitur seperti `EmployeeCount`, `StandardHours`, dan `Over18` sebaiknya dihapus sebelum pemodelan karena tidak memberikan informasi yang berguna (constant features).


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
