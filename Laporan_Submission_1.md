# Laporan Proyek Pertama Machine Learning Terapan - Muhammad Makarim
---
## Domain Proyek
Proyek Machine Learning ini mengangkat domain sosial dan psikologi, dengan fokus pada Prediksi Kepribadian. Dataset yang digunakan mencakup tanggapan individu mengenai perilaku sosial dan karakteristik kepribadian, yang membedakan antara introvert dan extrovert. Melalui analisis ini, kami bertujuan untuk memahami bagaimana kepribadian mempengaruhi keterlibatan sosial, ketakutan akan panggung, dan kecenderungan individu untuk berbagi pengalaman secara online.

## Latar Belakang
Masalah kepribadian dan pengaruhnya terhadap perilaku sosial semakin menarik perhatian di berbagai kalangan. Penelitian menunjukkan bahwa kepribadian dapat mempengaruhi interaksi sosial individu. Berdasarkan dataset yang dianalisis, perbedaan signifikan terlihat antara individu yang berkepribadian introvert dan extrovert dalam hal kehadiran di acara sosial dan pengalaman setelahnya. Individu introvert cenderung lebih memilih waktu sendirian dan merasa lebih lelah setelah berinteraksi dengan banyak orang, sementara individu extrovert lebih aktif dalam menghadiri acara sosial dan energik setelahnya. Selain itu, penelitian oleh McCrae dan Costa (2008) menunjukkan hubungan yang kuat antara sifat kepribadian dan keterlibatan dalam aktivitas sosial, yang mendasari pentingnya memahami karakteristik ini dalam konteks sosial yang beragam.

<br/>

Dalam era digital, pemanfaatan teknologi menjadi penting untuk memahami dan menganalisis perilaku sosial berdasarkan kepribadian. Dengan kemampuan analisis data yang cepat dan akurat, teknologi dapat membantu dalam mengidentifikasi pola perilaku dan rekomendasi untuk meningkatkan keterlibatan sosial. Mengingat hal tersebut, kami berusaha memberikan wawasan yang berguna untuk individu dan organisasi dalam mendesain program yang mendukung semua tipe kepribadian, serta mengoptimalkan interaksi sosial dalam konteks kesehatan mental. Penelitian oleh Cain (2013) menekankan bahwa inovasi teknologi dapat berfungsi sebagai solusi untuk meningkatkan kesadaran dan partisipasi dalam kesehatan mental.

## Business Understanding

## Problem Statements
Berdasarkan latar belakang yang telah disampaikan, terdapat beberapa rumusan masalah yang akan diselesaikan pada proyek ini:
1. Faktor apa saja yang mempengaruhi tingkat aktivitas sosial individu berdasarkan kepribadian?
2. Bagaimana cara membangun model machine learning untuk melakukan klasifikasi tingkat aktivitas sosial berdasarkan kepribadian?
3. Bagaimana cara memilih model machine learning dengan akurasi, precision, recall, dan F1-score terbaik untuk masalah prediksi kepribadian?

### Goals
Proyek ini dibangun dengan tujuan:
1. Mengidentifikasi variabel dan fitur yang mempengaruhi tingkat keterlibatan sosial individu berdasarkan kepribadian.
2. Mengembangkan model machine learning untuk melakukan klasifikasi tingkat keterlibatan sosial individu berdasarkan data.
3. Menentukan model terbaik untuk memprediksi tingkat keterlibatan sosial, berdasarkan hasil perbandingan metrik evaluasi seperti akurasi, precision, recall, dan F1-score.

### Solution Statements
Untuk mencapai tujuan dalam studi kasus ini, dilakukan beberapa tahapan solusi sebagai berikut:
1. Melakukan eksplorasi dan analisis data untuk memahami karakteristik data dan mengidentifikasi fitur-fitur yang paling relevan untuk menganalisis kepribadian individu. Analisis ini meliputi pembersihan data, visualisasi, dan pengujian korelasi antar fitur dalam dataset untuk mengungkap pola yang berkaitan dengan kepribadian introvert dan ekstrovert.
2. Membangun model machine learning klasifikasi untuk memprediksi tipe kepribadian individu. Beberapa model akan digunakan berdasarkan performanya dalam menangani kasus klasifikasi:
    - **K-Nearest Neighbors (KNN)**: Mengklasifikasikan kepribadian berdasarkan kedekatan dengan data lainnya.
    - **Random Forest**: Menggunakan beberapa *decision tree* untuk meningkatkan akurasi dan stabilitas klasifikasi.
    - **Boosting**: Mengkombinasikan model-model sederhana untuk memperbaiki kesalahan prediksi dan meningkatkan performa.
3. Melakukan evaluasi model untuk memilih model terbaik berdasarkan metrik evaluasi yang sesuai, seperti akurasi, precision, recall, dan F1 score. Ini bertujuan untuk menentukan model yang paling efektif dalam mengklasifikasikan kepribadian individu berdasarkan data yang tersedia.

## Data Understanding
Dataset yang digunakan pada proyek ini diambil dari 
<br/>
https://www.kaggle.com/datasets/rakeshkapilavai/extrovert-vs-introvert-behavior-data
<br/>
### EDA - Deskripsi Variabel
## Deskripsi Dataset
Dataset ini terdiri dari respon-respon dari individu yang mencakup informasi mengenai perilaku sosial mereka serta tipe kepribadian. Respon ini menyangkut faktor-faktor seperti ketakutan berbicara di depan umum, kehadiran di acara sosial, dan bagaimana perasaan mereka setelah interaksi tersebut. Dataset tersebut mencakup 530 responden dengan karakteristik yang bervariasi, memungkinkan analisis yang mendalam tentang bagaimana perbedaan tipe kepribadian (introvert dan extrovert) memengaruhi tingkat keterlibatan sosial mereka. Berikut adalah penjelasan masing-masing kolom:
- **Time_spent_Alone**: Waktu yang dihabiskan individu sendirian dalam sehari (dalam jam).
- **Stage_fear**: Faktor yang menunjukkan ketakutan individu saat berbicara di depan umum (Ya/Tidak).
- **Social_event_attendance**: Tingkat kehadiran individu di acara sosial (Ya/Tidak).
- **Going_outside**: Frekuensi individu keluar untuk bersosialisasi (skala 0-10).
- **Drained_after_social**: Apakah individu merasa lelah setelah berinteraksi sosial (Ya/Tidak).
- **Friends_circle_size**: Ukuran lingkaran sosial individu (jumlah teman).
- **Post_frequency**: Frekuensi individu membagikan pengalaman sosial secara online (skala 0-10).
- **Personality**: Tipe kepribadian individu, yang dibedakan menjadi "Introvert" dan "Extrovert".

### Variable - variable pada dataset
- Data Float = Time_spent_Alone, Going_outside, Friends_circle_size, Post_frequency.  
- Data Object = Stage_fear, Social_event_attendance, Drained_after_social, Personality.

### Missing Value, Data Duplikat dan Outlier
1. Dataset ini memiliki beberapa nilai yang hilang pada kolom-kolom berikut:
   a. Time_spent_Alone: 63
   b. Stage_fear: 73
   c. Social_event_attendance: 62
   d. Going_outside: 66
   e. Drained_after_socializing: 52
   f. Friends_circle_size: 77
   g. Post_frequency: 65
   Penanganan nilai yang hilang perlu dilakukan, dengan metode menghapus baris yang memiliki nilai hilang.
3. Tidak ada outlier yang terdeteksi dalam dataset. Outlier dapat memengaruhi performa model prediksi dan perlu ditangani jika ada, namun dalam hal ini, data terlihat homogen dalam distribusinya.
4. Setelah pemeriksaan, tidak ditemukan data duplikat dalam dataset ini. Keberadaan data duplikat dapat mengubah hasil analisis, sehingga penting untuk memeriksanya sebelum melanjutkan ke tahap berikutnya.

### EDA - Univariate Analysis
Analisis univariat dilakukan untuk memahami distribusi masing-masing variabel secara individual. Beberapa temuan awal:

##### Kolom Categorical 
![Grafik Univariate Numeric Data](./gambar/univariate_categorical.png)
- Terdapat 4 kategori dalam fitur gender yang didominasi dengan kategori Male dan Female dengan perbandingan yang cukup seimbang. 
- Terdapat 4 kategori dalam fitur employment, secara berurutan dari yang paling banyak adalah employed, kemudian diikuti student, self emoployed, dan yang paling sedikit adalah unemployed.
- Terdapat 3 kategori dalam fitur work_environtment. secara berurutan dari yang paling banyak adalah onsite, Remote, dan Hybrid.
- Terdapat 2 kategori dalam fitur mental_health_history. dengan hampir 70% data memiliki value no yang berarti sebagian besar tidak memiliki riwayat penyakit mental.
- Terdapat 2 kategori dalam fitur seeks_treatment, yaitu yes dan no. dengan hampir 60% data menyatakan no yang artinya belum pernah mencari bantuan professional dalam masalah kesehatan mental.
- Terdapat 3 kategori dalam fitur mental_health_risk. Secara berurutan dari yang terbesar adalah medium sebesar 58,9% high sebesar 23,7%, dan low sebesar 17,4%.

##### Kolom Numerik
![Grafik Univariate Numeric Data](./gambar/univariate_numeric.png)
- Data pada kolom stress_level, age, physical_activity_days, anxiety_score, dan social_support_score cenderung memiliki persebaran yang merata.  
- Terdapat peningkatan jumlah yang signifikan pada data fitur depression_score pada nilai maksimal (30).  
- Terdapat peningkatan jumlah yang signifikan pada data fitur productivity_score pada nilai maksimal (100).  
- Data sleep_hours cenderung terdistribusi normal.

### EDA - Multivariate Analysis

##### Kolom Categorical
![Grafik Multivariate Categorical Data](./gambar/multivariate_categorical.png)

- Pada fitur gender, risiko kesehatan mental cenderung merata di semua gender dengan mayoritas berada pada risiko sedang.  
  Tidak ada kategori tertentu yang cenderung memiliki risiko kesehatan mental tinggi, sedang, maupun rendah.  
- Pada fitur employment_status, risiko kesehatan mental pada setiap kategori cenderung merata.  
  Tidak ada kategori tertentu yang cenderung memiliki risiko kesehatan mental tinggi, sedang, maupun rendah.  
- Pada fitur work_environment, risiko kesehatan mental pada setiap kategori juga cenderung merata.  
  Tidak ada kategori tertentu yang cenderung memiliki risiko kesehatan mental tinggi, sedang, maupun rendah.  
- Pada fitur mental_health_history, risiko kesehatan mental pada setiap kategori cenderung merata.  
  Tidak ada kategori tertentu yang cenderung memiliki risiko kesehatan mental tinggi, sedang, maupun rendah.  
- Pada fitur seeks_treatment, tidak ada kategori tertentu yang cenderung memiliki risiko kesehatan mental tinggi, sedang, maupun rendah.  

<br/>

- Fitur seeks_treatment menunjukkan hubungan yang signifikan secara statistik terhadap fitur mental_health_risk.  
  Hal ini dapat diartikan bahwa kecenderungan individu untuk mencari bantuan atau perawatan memiliki pengaruh yang signifikan  
  terhadap tingkat risiko kesehatan mental mereka.  
- Fitur lain seperti gender, employment_status, work_environment, dan mental_health_history tidak menunjukkan hubungan  
  statistik yang signifikan terhadap fitur mental_health_risk.  
  Hal ini dapat diartikan bahwa faktor-faktor tersebut tidak cukup kuat untuk membedakan tingkat risiko kesehatan mental pada individu.

##### Kolom Numerik
![Grafik Multivariate Categorical Data](./gambar/multivariate_numeric.png)
- Pada fitur age, tidak terdapat kalangan umur tertentu yang memiliki kecenderungan risiko kesehatan mental kategori high,  
  medium, maupun low.  
- Pada fitur stress_level, variasi stres pada setiap individu di dalam kategori mental_health_risk cenderung mirip,  
  namun tingkat stres secara umum (berdasarkan median) pada fitur mental_health_risk kategori low cenderung memiliki  
  tingkat stres yang lebih rendah.  
- Pada fitur sleep_hours, tidak terdapat waktu tidur tertentu yang memiliki kecenderungan kesehatan mental kategori  
  high, medium, maupun low.  
- Pada fitur physical_activity_days, individu dengan risiko kesehatan mental kategori high menunjukkan kecenderungan  
  memiliki tingkat aktivitas fisik yang lebih tinggi dibandingkan kategori lainnya. Individu dengan risiko kesehatan mental  
  high dan low memiliki median aktivitas fisik mingguan yang sama, yaitu sekitar 4 hari. Sementara itu, individu dengan  
  risiko kategori medium memiliki median aktivitas fisik yang lebih rendah, yaitu sekitar 3 hari.  
- Pada fitur depression_score, menunjukkan bahwa semakin tinggi risiko kesehatan mental seseorang, semakin tinggi pula  
  skor depresi yang dimilikinya. Ini menunjukkan bahwa kolom depression_score memiliki korelasi yang tinggi dengan  
  kolom mental_health_risk.  
- Pada fitur anxiety_score, menunjukkan bahwa semakin tinggi risiko kesehatan mental seseorang, semakin tinggi pula  
  anxiety_score yang dimilikinya. Ini menunjukkan bahwa kolom anxiety_score memiliki korelasi yang cukup tinggi dengan  
  kolom mental_health_risk.  
- Distribusi nilai pada fitur social_support terlihat relatif merata di setiap kategori mental_health_risk, tanpa adanya  
  perbedaan yang mencolok di antara kategori tersebut.  
- Pada fitur productivity_score menunjukkan korelasi yang kuat dengan fitur mental_health_risk, dimana risiko kesehatan  
  mental individu dengan kategori low memiliki tingkat produktivitas tertinggi dengan nilai median sekitar 95, kemudian  
  individu dengan risiko kesehatan mental kategori medium memiliki nilai median tingkat produktivitas yang lebih rendah  
  yaitu sekitar 80, dan yang terakhir adalah individu dengan tingkat risiko kesehatan mental kategori high memiliki  
  tingkat produktivitas terendah dengan median sekitar 60-an.


## Data Preparation
- Menghapus kolom yang tidak relevan. Beberapa kolom tersebut adalah 'gender', 'employment_status', 'work_environment', 'mental_health_history', 'age', 'stress_level', 'sleep_hours', dan 'social_support_score' dihapus karena tidak memiliki pengaruh yang signifikan terhadap tingkat resiko kesehatan mental (variabel target).
- Melakukan Label Encoding untuk seeks_treatment (data kategorikal non ordinal dengan 2 label memungkinkan untuk dilakukan label encoding) dan mental_health_risk adalah data ordinal sehingga encoder dilakukan dengan metode labeling.
- Melakukan spliting pada dataset dengan rasio pembagian 90% untuk data training dan 10% untuk data testing. Berdasarkan data yang berjumlah 10.000, rasio ini sudaha baik karena model memiliki cukup data untuk training dan cukup data untuk melakukan testing.
- Melakukan Scalling dengan StandardScaller untuk membuat data numerik berada pada rentang nilai yang sama. Hal ini dilakukan agar algoritma tidak bias, kecenderungan model seperti KNN menganggap kolom dengan rentang nilai yang tinggi adalah kolom yang penting. 

## Modeling
- KNN (K-Nearest Neighbor) adalah model machine learning yang bekerja dengan cara membandingkan jarak dari suatu sampel  
  ke sampel pelatihan yang lain dengan memilih sejumlah (k) tetangga terdekat. Dalam studi kasus ini,  
  model K-Nearest Neighbors (KNN) digunakan untuk mengklasifikasikan risiko kesehatan mental dengan parameter  
  n_neighbors=10, yang berarti setiap prediksi didasarkan pada 10 tetangga terdekat dalam data latih. KNN adalah  
  algoritma yang sederhana dan mudah dipahami, namun memiliki kelemahan seperti kurang efektif pada data berdimensi  
  tinggi (curse of dimensionality), sensitif terhadap outlier, dan performa yang menurun jika data tidak seimbang.  
  Selain itu, waktu prediksi bisa menjadi lambat pada dataset besar karena perlu menghitung jarak ke seluruh data latih.

- Random Forest adalah algoritma machine learning yang digunakan untuk menyelesaikan masalah klasifikasi dan regresi.  
  Random Forest adalah kumpulan dari beberapa model decision tree yang masing-masing memiliki hyperparameter berbeda dan  
  dilatih pada beberapa bagian data yang berbeda. Dengan melakukan beberapa keputusan sekaligus melalui beberapa pohon,  
  algoritma Random Forest sangat cocok digunakan pada kasus klasifikasi.  
  Random Forest merupakan metode ensemble yang menggabungkan hasil dari banyak pohon keputusan untuk meningkatkan  
  akurasi dan mengurangi risiko overfitting. Dalam studi kasus ini, model yang dibangun menggunakan n_estimators=50,  
  artinya 50 pohon dibangun, serta max_depth=16 yang membatasi kedalaman maksimal tiap pohon untuk mengontrol kompleksitas model.  
  Parameter random_state=55 digunakan agar hasil pelatihan konsisten dan dapat direproduksi. Sementara itu, n_jobs=-1  
  memungkinkan model memanfaatkan seluruh inti CPU yang tersedia untuk mempercepat proses pelatihan. Random Forest sangat kuat  
  dalam menangani data kompleks dan tahan terhadap noise, tetapi model ini sulit diinterpretasikan dan membutuhkan sumber daya  
  komputasi yang lebih besar.

- Boosting adalah metode klasifikasi yang menggabungkan banyak model sederhana secara bertahap untuk meningkatkan  
  akurasi dengan fokus memperbaiki kesalahan prediksi sebelumnya. Dalam studi kasus ini, AdaBoostClassifier digunakan  
  sebagai metode boosting, dengan learning_rate=0.05, yang menentukan seberapa besar kontribusi setiap model lemah dalam pembelajaran bertahap.  
  Model ini juga menggunakan random_state=55 untuk memastikan hasil yang konsisten. Boosting bekerja dengan memperbaiki  
  kesalahan model sebelumnya secara iteratif, sehingga meningkatkan performa keseluruhan. Namun, AdaBoost dapat menjadi  
  sensitif terhadap outlier dan noise, serta memiliki waktu pelatihan yang lebih lambat dibandingkan beberapa metode lain  
  karena proses pembelajarannya yang bertahap.

## Evaluasi
![Grafik Akurasi Model](./gambar/accuracy2.png)

Evaluasi model dilakukan menggunakan metric accuracy, precision, Recall, dan F1-score untuk mengukur performa dari 
masing-masing model yang digunakan yaitu KNN, Random Forest, dan Boosting Algorithm. 
Berdasarkan hasil akurasi didapatkan informasi sebagai berikut:
- Model terbaik model dengan algoritma random forest yang menghasilkan akurasi, precision, f1-score, dan recall tertinggi, 
yaitu seluruhnya sebesar 99,4%.

- Model kedua terbaik adalah KNN yang menghasilkan akurasi, precision, f1-score, dan recall tidak berbeda jauh dengan random 
forest yaitu semuanya sebesar 97,6%.

- Model terburuk untuk studi kasus ini adalah model yang dibangun dengan algoritma Boosting yang menghasilkan akurasi, 
precision, f1-score dan recall yang cukup rendah, yaitu secara berturut-turut 59,3%; 35,1%; 44,1%; dan 59,3%.

### Penyelesaian permasalahan
1. Setelah melakukan proses EDA, berhasil dilakukan identifikasi fitur-fitur penting dalam klasifikasi resiko kesehatan 
mental yaitu: seeks_treatment, physical_activity_days,	depression_score,	anxiety_score, dan	productivity_score
2. Didalam proyek ini telah dibangun  3 algoritma klasifikasi untuk melakukan prediksi klasifikasi resiko kesehatan mental.
3 model yang dibangun adalah : KNN, Random Forest, dan Boosting Algorithm. Penggunaan parameter seperti n_neighbors, 
n_estimators, dan learning_rate juga sudah dioptimalkan sesuai kebutuhan.
3. Dari evaluasi yang dilakukan, Random Forest terbukti sebagai model paling optimal, karena memiliki nilai tertinggi untuk semua 
metrik dibandingkan model lain. Meskipun KNN mencapai metrik yang hampir sama dengan Random Forest, semua metrik evaluasi 
yang dihasilkan masih lebih rendah. 

### Kesimpulan 
Analisis fitur mengungkapkan bahwa seeks_treatment, physical_activity_days, depression_score, anxiety_score, dan 
productivity_score merupakan variabel paling penting yang memengaruhi prediksi risiko kesehatan mental.
<br/>
Berdasarkan hasil evaluasi, model Random Forest merupakan model terbaik untuk prediksi klasifikasi risiko kesehatan 
mental pada studi kasus ini. Model ini menunjukkan performa tertinggi pada semua metrik evaluasi dibandingkan dengan 
model lainnya.
<br/>
Meskipun model KNN memiliki nilai akurasi, recall, precision, dan F1-score yang sedikit lebih rendah, selisihnya 
tidak signifikan sehingga model ini tetap dapat dipertimbangkan sebagai alternatif.
<br/>
Dengan tercapainya tujuan prediksi risiko kesehatan mental secara dini, diharapkan proyek ini dapat membantu 
meningkatkan kesadaran individu untuk lebih cepat mencari bantuan atau perawatan ketika terdapat indikasi risiko 
kesehatan mental yang dialami.
![Grafik Akurasi Model](./gambar/accuracy.png)
## Referensi

[1]: Kementerian Kesehatan Republik Indonesia, *Laporan Tematik Survei Kesehatan Indonesia Tahun 2023: Potret Indonesia Sehat*, Jakarta: Kementerian Kesehatan RI, 2024. Diterbitkan oleh Kementerian Kesehatan RI dan dikeluarkan oleh Badan Kebijakan Pembangunan Kesehatan. [Online]. Available: https://drive.google.com/file/d/1AnuDQgQufa5JSXEJWpBSv4r7v6d5YZm7/view. [Accessed: May 24, 2025].

[2]: Universitas Gadjah Mada, Universitas Sumatera Utara, Universitas Hasanuddin, The University of 
Queensland Australia, Johns Hopkins Bloomberg School of Public Health, and Kementerian Kesehatan Republik 
Indonesia, *I-NAMHS: Indonesia-National Adolescent Mental Health Survey*, 2022.
