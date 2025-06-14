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
Dataset personality yang digunakan pada proyek ini berjumlah 2838 baris dan 8 kolom yang diambil pada:
<br/>
https://www.kaggle.com/datasets/rakeshkapilavai/extrovert-vs-introvert-behavior-data
<br/>
### EDA - Deskripsi Variabel
## Deskripsi Dataset
Dataset ini terdiri dari respon-respon dari individu yang mencakup informasi mengenai perilaku sosial mereka serta tipe kepribadian. Respon ini menyangkut faktor-faktor seperti ketakutan berbicara di depan umum, kehadiran di acara sosial, dan bagaimana perasaan mereka setelah interaksi tersebut. Dataset tersebut berjumlah 2838 data dan 8 kolom dengan karakteristik yang bervariasi, memungkinkan analisis yang mendalam tentang bagaimana perbedaan tipe kepribadian (introvert dan extrovert) memengaruhi tingkat keterlibatan sosial mereka. Berikut adalah penjelasan masing-masing kolom:
- **Time_spent_Alone**: Waktu yang dihabiskan individu sendirian dalam sehari (dalam jam).
- **Stage_fear**: Faktor yang menunjukkan ketakutan individu saat berbicara di depan umum (Ya/Tidak).
- **Social_event_attendance**: Tingkat kehadiran individu di acara sosial (Ya/Tidak).
- **Going_outside**: Frekuensi individu keluar untuk bersosialisasi (skala 0-10).
- **Drained_after_social**: Apakah individu merasa lelah setelah berinteraksi sosial (Ya/Tidak).
- **Friends_circle_size**: Ukuran lingkaran sosial individu (jumlah teman).
- **Post_frequency**: Frekuensi individu membagikan pengalaman sosial secara online (skala 0-10).
- **Personality**: Tipe kepribadian individu, yang dibedakan menjadi "Introvert" dan "Extrovert".

Pada dataset ini terdapat missing values pada fitur:
   - Identifikasi missing values pada kolom-kolom:
       - Time_spent_Alone: 63
       - Stage_fear: 73
       - Social_event_attendance: 62
       - Going_outside: 66
       - Drained_after_socializing: 52
       - Friends_circle_size: 77
       - Post_frequency: 65

Selain missing values pada dataset juga terdapat 388 entri yang harus ditangani nantinya

### Variable - variable pada dataset
- Data Float = Time_spent_Alone, Going_outside, Friends_circle_size, Post_frequency.  
- Data Object = Stage_fear, Social_event_attendance, Drained_after_social, Personality.

### EDA - Univariate Analysis
Analisis univariat dilakukan untuk memahami distribusi masing-masing variabel secara individual. Beberapa temuan awal:

##### Kolom Categorical 
![Grafik Univariate Categorical Data](https://raw.githubusercontent.com/MuhammadMakarim/Predictive-Analytics/43efc1bfa71c02f6dace16cffcdcb327cf9741c7/Gambar/Uni_Categorical%20Feature.png) 

Pada kolom kategorikal, visualisasi berikut digunakan untuk menunjukkan frekuensi dari masing-masing kategori:
- Terdapat dua kategori dalam fitur Stage_fear, di mana jumlah individu yang tidak mengalami ketakutan berbicara di depan umum (No) hampir seimbang dengan mereka yang mengalami ketakutan (Yes). Ini menunjukkan bahwa populasi dalam dataset ini memiliki proporsi yang hampir sama antara individu yang merasa nyaman untuk berbicara di depan umum dan yang tidak.
- Terdapat dua kategori dalam fitur Personality, yang dibagi menjadi Extrovert dan Introvert, dengan hampir setengah dari populasi termasuk dalam masing-masing kategori. Ini menunjukkan adanya keseimbangan antara kepribadian extrovert dan introvert, yang bisa berpengaruh dalam interaksi sosial dan preferensi individu.

##### Kolom Numerik
![Grafik Univariate Numeric Data](https://raw.githubusercontent.com/MuhammadMakarim/Predictive-Analytics/43efc1bfa71c02f6dace16cffcdcb327cf9741c7/Gambar/Uni_Numerical%20Feature_Histogram.png)

Pada kolom numerik, visualisasi berikut digunakan untuk menunjukkan frekuensi dari masing-masing kategori:
- Distribusi waktu yang dihabiskan sendirian Time_spent_Alone menunjukkan variasi yang signifikan, dengan mayoritas individu menghabiskan antara 0 hingga 5 jam sendirian. Ini mungkin menunjukkan kecenderungan bahwa individu lebih suka sosial dibandingkan menghabiskan waktu sendiri, setidaknya dalam konteks ini.
- Distribusi kehadiran di acara sosial Social_event_attendance menunjukkan bahwa kebanyakan individu tidak terlalu terlibat dalam acara sosial, dengan frekuensi rendah di atas 5. Ini dapat menunjukkan tendensi sifat introverted dalam populasi ini, di mana individu merasa kurang terpanggil untuk menghadiri banyak acara sosial.
- Frekuensi keluar bersosialisasi Going_outside menunjukkan bahwa banyak individu memiliki frekuensi rendah dalam bersosialisasi di luar rumah, terutama di bawah nilai 5. Angka ini mencerminkan kurangnya interaksi sosial yang aktif di luar lingkungan rumah atau yang lebih dikenal, mungkin sesuai dengan karakteristik introvert.
- Ukuran lingkaran teman Friends_circle_size menunjukkan bahwa sebagian besar individu memiliki lingkaran sosial yang kecil, dengan mayoritas berada di bawah angka 6. Ini menunjukkan bahwa individu cenderung memiliki relasi sosial yang lebih dalam dengan jumlah teman yang terbatas.
- Frekuensi berbagi pengalaman secara online Post_frequency juga menunjukkan mayoritas individu memiliki nilai rendah, menunjukkan kecenderungan untuk tidak aktif sharing di media sosial. Hal ini bisa terkait erat dengan kepribadian introvert, di mana mereka kurang merasa nyaman untuk membagikan pengalaman pribadi secara publik.

### EDA - Multivariate Analysis

##### Kolom Categorical
![Grafik Multivariate Categorical Data](https://raw.githubusercontent.com/MuhammadMakarim/Predictive-Analytics/ccd7627641ae70edf33cfa07ddfcbf3f43eda995/Gambar/Multi_Korelasi%20Semua%20Variabel%20dengan%20Personality.png)

- Introvert: Cenderung memiliki nilai tinggi pada Time_spent_Alone dan Stage_fear, serta rendah pada Social_event_attendance dan Going_outside. Mereka juga sering merasa drained setelah bersosialisasi. Dikenali dengan ukuran Friends_circle_size yang lebih kecil dan rendahnya frekuensi posting di media sosial.
- Extrovert: Menunjukkan waktu yang lebih rendah untuk dihabiskan sendirian dan lebih aktif dalam Social_event_attendance dan Going_outside. Memiliki ukuran Friends_circle_size yang lebih besar dan lebih aktif dalam membagikan pengalaman mereka di media sosial.

<br/>

##### Kolom Numerik
![Grafik Multivariate Categorical Data](https://raw.githubusercontent.com/MuhammadMakarim/Predictive-Analytics/43efc1bfa71c02f6dace16cffcdcb327cf9741c7/Gambar/Multi_Korelasi%20Variabel%20Numerik.png)

- Time_spent_Alone: Mengukur waktu yang dihabiskan sendirian setiap hari dalam jam. Terdapat korelasi positif yang signifikan dengan Drained_after_socializing (nilai: 0.87), yang menunjukkan bahwa semakin banyak waktu dihabiskan sendirian, semakin besar kemungkinan individu merasa lelah setelah bersosialisasi.
- Social_event_attendance: Mengukur seberapa sering individu menghadiri acara sosial. Korelasi negatif yang signifikan dengan Stage_fear (nilai: -0.85) mengindikasikan bahwa individu yang merasa takut berbicara di depan umum juga kurang memiliki frekuensi kehadiran di acara sosial, serta menunjukkan hubungan positif dengan Friends_circle_size (nilai: 0.73).
- Going_outside: Mengukur frekuensi keluar untuk bersosialisasi, dinilai dari 0 hingga 10. Memiliki korelasi positif dengan Social_event_attendance (nilai: 0.74). individu yang sering keluar cenderung menghadiri lebih banyak acara sosial. Ini biasanya lebih banyak terlihat pada extrovert.
- Drained_after_socializing: Menunjukkan apakah individu merasa lelah setelah bersosialisasi. Korelasi positif dengan Time_spent_Alone (nilai: 0.87) menunjukkan bahwa individu yang menghabiskan lebih banyak waktu sendirian lebih cenderung merasa lelah setelah bersosialisasi.
- Friends_circle_size: Mengukur jumlah teman dekat yang dimiliki individu. Memiliki korelasi positif dengan Social_event_attendance (nilai: 0.73), dimana individu dengan lingkaran teman yang lebih besar cenderung lebih aktif dalam menghadiri acara sosial.
- Post_frequency: Mengukur seberapa sering individu membagikan pengalaman sosial secara online. Terdapat korelasi negatif dengan Time_spent_Alone (nilai: -0.73), mengindikasikan bahwa individu yang menghabiskan lebih banyak waktu sendiri biasanya lebih sedikit membagikan pengalaman mereka di media sosial.


## Data Preparation
Bagian ini menjelaskan tahapan persiapan data yang telah dilakukan sebelum melakukan pemodelan. Proses ini penting untuk memastikan bahwa data yang digunakan berkualitas dan siap untuk analisis lebih lanjut. Berikut adalah tahapan yang diambil:
1. Penanganan Missing Values:
   - Identifikasi missing values pada kolom-kolom:
       - Time_spent_Alone: 63
       - Stage_fear: 73
       - Social_event_attendance: 62
       - Going_outside: 66
       - Drained_after_socializing: 52
       - Friends_circle_size: 77
       - Post_frequency: 65
   - Membersihkan dataset dari entri yang tidak lengkap untuk meningkatkan kualitas data. Penanganan nilai yang hilang perlu dilakukan, dengan metode menghapus baris yang memiliki nilai hilang menggunakan teknik _.dropna()_.

2. Penanganan Data Duplikat
   - Jumlah data duplikat terdeteksi: 388 entri
   - Metode Penanganan: Menggunakan _.drop_duplicates()_ untuk menghapus baris duplikat
   Penanganan data duplikat ini berguna untuk mencegah bias dalam model akibat data yang berulang

3. Penanganan Outliers
   - Metode Deteksi: Menggunakan Interquartile Range (IQR)
   - Hasil Analisis: Tidak ditemukan outliers signifikan dalam dataset
   - Catatan: Distribusi data terlihat homogen, tidak memerlukan perlakuan khusus
4. Encoding Variabel Kategorikal
   - Teknik Preprocessing Manual:
       - Mapping manual untuk kolom Stage_fear dan Drained_after_socializing
   - Metode Encoding:
       - Menggunakan pd.get_dummies() untuk kolom:
           - Post_frequency
           - Personality  
   Mengubah variabel kategorikal menjadi format numerik yang dapat diproses model
5. Pembagian Data
   - Metode: train_test_split dari sklearn
   - Proporsi Pembagian: 80% data training, 20% data testing
   - Stratifikasi: Mempertahankan distribusi label pada kedua subset
6. Standardisasi Fitur
   - Metode: StandardScaler dari sklearn
   - Tujuan: Normalisasi skala fitur untuk algoritma yang sensitif terhadap skala
   - Proses: Menstandarisasi fitur numerik agar memiliki mean 0 dan standar deviasi 1
7. Reduksi Dimensi
   - Mengurangi dimensi fitur
   - Menjaga informasi penting
   - Mempercepat proses pelatihan model
   - Membantu visualisasi data
Setiap tahapan dirancang untuk mempersiapkan dataset secara optimal, memastikan model machine learning dapat mengekstrak pola dan memberikan prediksi yang akurat.

## Modeling
- K-Nearest Neighbors (KNN) adalah algoritma yang berbasis pada metode instance-based learning. Metode ini bekerja dengan cara mencari k tetangga terdekat dari data yang ingin diprediksi. Dalam implementasinya, KNN mengukur jarak antara titik data dan semua titik lainnya dalam dataset, kemudian memilih k titik terdekat untuk menentukan kelas dari titik yang sedang diprediksi. Dalam proyek ini, kita menerapkan KNN dengan parameter n_neighbors=5, yang berarti model akan mempertimbangkan lima tetangga terdekat. Kelebihan dari KNN adalah kesederhanaannya serta kemampuannya untuk bekerja dengan masalah non-linier, namun kekurangannya mencakup ketidakmampuannya dalam menangani multikolinearitas dan kecenderungannya terhadap outlier. Hasil evaluasi menunjukkan bahwa model KNN dapat mencapai akurasi tinggi, sehingga membuatnya menjadi pilihan kuat untuk klasifikasi kepribadian.

- Random Forest adalah metode ensemble yang terdiri dari banyak pohon keputusan. Setiap pohon menghasilkan suara, dan kelas yang paling banyak dipilih menjadi hasil akhir dari prediksi. Model ini sangat efektif untuk mengurangi risiko overfitting, yang sering kali menjadi masalah pada model pohon keputusan tunggal. Dalam proyek ini, Random Forest diterapkan dengan parameter n_estimators=100, digunakan untuk menentukan jumlah pohon keputusan yang akan dibuat. Kelebihan dari Random Forest termasuk mampu menangani dataset besar dengan baik dan tidak memerlukan pemilihan fitur yang begitu kritis. Namun, model ini bisa menjadi lebih sulit untuk diinterpretasikan dibandingkan dengan model yang lebih sederhana. Hasil evaluasi menunjukkan bahwa meskipun akurasinya sedikit lebih rendah ketimbang KNN, Random Forest tetap memberikan hasil yang solid dan konsisten dalam klasifikasi tipe kepribadian.

- AdaBoost, atau Adaptive Boosting, adalah algoritma ensemble lain yang mengkombinasikan beberapa klasifikator lemah untuk membentuk klasifikator yang lebih kuat. Proses ini bekerja dengan cara memberikan bobot lebih pada titik data yang keliru diprediksi oleh model sebelumnya, sehingga fokus untuk memperbaiki kesalahan adalah utama. Dalam implementasi di proyek ini, kita menggunakan n_estimators=50, yang menyatakan jumlah iterasi yang akan dilakukan. Kelebihan dari AdaBoost terletak pada kemampuannya untuk meningkatkan kinerja klasifikasi pada dataset yang tidak seimbang, terutama dalam situasi di mana kelas mayoritas dan minoritas sangat berbeda. Namun, ia juga rentan terhadap noise di data. Hasil evaluasi menunjukkan bahwa AdaBoost memberikan akurasi tertinggi di antara ketiga model, menjadikannya model yang paling efektif untuk kasus ini.

## Evaluasi

Dalam tahap evaluasi, kinerja setiap model yang diterapkan dalam proyek ini akan dianalisis secara komprehensif menggunakan beberapa metrik evaluasi yang relevan. Metrik yang digunakan adalah akurasi, precision, recall, dan F1 score, yang semuanya penting untuk memahami bagaimana baiknya model dalam mengklasifikasikan kepribadian individu sebagai introvert atau extrovert. (catatan: )

![Grafik Akurasi Model](https://raw.githubusercontent.com/MuhammadMakarim/Predictive-Analytics/43efc1bfa71c02f6dace16cffcdcb327cf9741c7/Gambar/Akurasi%20KNN.png)
- KNN adalah algoritma klasifikasi berbasis instance learning yang mengklasifikasikan data berdasarkan kedekatan jarak dengan tetangga terdekatnya. Dalam konteks klasifikasi kepribadian, model ini mencapai akurasi 91.4% dengan mekanisme penentuan kelas melalui mayoritas dari k-tetangga terdekat. Metode ini menunjukkan kemampuan yang solid dalam membedakan antara tipe kepribadian introvert dan extrovert, dengan kemampuan mengidentifikasi 184 individu introvert dan 236 individu extrovert secara akurat. Kelebihan utama KNN terletak pada kesederhanaan algoritmanya dan tidak memerlukan asumsi distribusi data, namun memiliki kelemahan dalam hal kompleksitas komputasi yang tinggi untuk dataset besar dan sensitifitas terhadap fitur yang tidak seimbang. Precision untuk kelas introvert mencapai 0.88, sementara recall sebesar 0.93, dan precision untuk kelas ekstrovert mencapai 0.94 serta recall sebesar 0.90. Menunjukkan keseimbangan yang baik antara ketepatan dan kelengkapan prediksi.

![Grafik Akurasi Model](https://raw.githubusercontent.com/MuhammadMakarim/Predictive-Analytics/43efc1bfa71c02f6dace16cffcdcb327cf9741c7/Gambar/Akurasi%20Random%20Forest.png)
- Random Forest adalah metode ensemble berbasis pohon keputusan yang menghasilkan multiple decision tree dan mayoritas untuk klasifikasi akhir. Dalam analisis kepribadian, model ini mencapai akurasi 88.0%, yang merupakan performa terendah di antara ketiga model yang diuji. Metode ini berhasil mengklasifikasikan 184 individu introvert dan 236 individu extrovert, dengan kemampuan menangani fitur non-linier dan toleran terhadap missing values. Kelebihan utama Random Forest adalah kemampuannya mencegah overfitting melalui agregasi multiple tree dan dapat mengestimasi pentingnya fitur dalam klasifikasi. Namun, kompleksitas modelnya yang tinggi membuat interpretasi hasil menjadi lebih sulit. Precision untuk kelas introvert adalah 0.87 dengan recall 0.85, dan precision untuk kelas ekstrovert mencapai 0.89 serta recall sebesar 0.90. Menunjukkan performa yang solid namun tidak sebaik AdaBoost dan KNN. Kelemahan utama model ini terletak pada komputasi yang intensif dan penurunan kinerja pada dataset dengan noise tinggi.

![Grafik Akurasi Model](https://raw.githubusercontent.com/MuhammadMakarim/Predictive-Analytics/43efc1bfa71c02f6dace16cffcdcb327cf9741c7/Gambar/Akurasi%20AdaBoost.png)
- AdaBoost (Adaptive Boosting) merupakan algoritma ensemble learning canggih yang secara adaptif meningkatkan performa klasifikasi dengan fokus pada sampel-sampel yang salah diklasifikasi pada iterasi sebelumnya. AdaBoost menunjukkan performa superior dengan akurasi tertinggi 93.0% (0.930952380952381), secara signifikan unggul dibandingkan model lainnya. Model ini berhasil mengklasifikasikan 184 individu introvert dan 236 individu extrovert dengan presisi yang tinggi. Mekanisme kerjanya melibatkan kombinasi beberapa weak learner yang diboost untuk membentuk sebuah strong classifier, yang memungkinkannya menangkap pola kompleks dalam data kepribadian. Keunggulan AdaBoost terletak pada kemampuannya mengurangi bias dan variance, serta robust terhadap overfitting. Precision untuk kelas introvert mencapai 0.91 dengan recall 0.94, dan precision untuk kelas ekstrovert mencapai 0.95 serta recall sebesar 0.92. Menunjukkan akurasi prediksi yang sangat baik. Meskipun demikian, model ini memiliki kompleksitas komputasi yang tinggi dan sensitif terhadap data outlier.

### Penyelesaian permasalahan
Dalam proyek ini berfokus pada analisis dan klasifikasi kepribadian individu berdasarkan aktivitas sosial mereka, dengan tujuan menjawab tiga rumusan masalah yang telah ditentukan sebelumnya.
1. Faktor yang Mempengaruhi Tingkat Aktivitas Sosial
   Untuk memahami faktor-faktor yang mempengaruhi tingkat aktivitas sosial individu, kami mengidentifikasi dan menganalisis variabel-variabel yang terkandung dalam dataset, seperti rasa takut di atas panggung, kehadiran dalam acara sosial, dan perasaan kelelahan setelah berinteraksi sosial. Data menunjukkan bahwa kepribadian (introvert vs. extrovert) memiliki dampak signifikan terhadap keterlibatan individu dalam aktivitas sosial. Individu yang dikategorikan sebagai extrovert cenderung lebih aktif dalam berpartisipasi dalam kegiatan sosial, sementara introvert menunjukkan partisipasi yang lebih rendah.
   
2. Pengembangan Model Machine Learning
   Setelah memahami faktor-faktor yang mempengaruhi, langkah selanjutnya adalah membangun model machine learning untuk melakukan klasifikasi. Tiga algoritma yang diterapkan adalah K-Nearest Neighbors (KNN), Random Forest, dan AdaBoost.
- K-Nearest Neighbors (KNN) diterapkan untuk mengeksplorasi pola klasifikasi dengan pendekatan berbasis tetangga terdekat. Dengan mengatur parameter n_neighbors=5, model ini menunjukkan akurasi yang tinggi, mencapai 91.4%.
- Random Forest menggunakan teknik ensemble dari berbagai pohon keputusan untuk memprediksi kepribadian. Meskipun akurasinya sedikit lebih rendah di 88.0%, model ini menawarkan kestabilan yang baik dan mengurangi risiko overfitting.
- AdaBoost, sebagai algoritma boosting yang mengoptimalkan klasifikasi melalui penguatan klasifikator lemah, mencapai akurasi tertinggi di 93.0%. Kekuatan AdaBoost terletak pada kemampuannya memperbaiki kesalahan dari model sebelumnya, membuatnya sangat efektif dalam menghadapi data yang tidak seimbang.

3. Pemilihan Model Terbaik Berdasarkan Metrik Evaluasi
   Dalam tahap terakhir, kami melakukan evaluasi terhadap ketiga model menggunakan metrik seperti akurasi, precision, recall, dan F1 score. Metrik ini memungkinkan kami untuk menentukan keandalan masing-masing model dalam mengklasifikasikan kepribadian. Hasil evaluasi menunjukkan bahwa:
- KNN memberikan akurasi tinggi namun dengan trade-off dalam beberapa metrik precision dan recall.
- Random Forest masih menunjukkan akurasi yang solid, meskipun sedikit lebih rendah dibanding KNN.
- AdaBoost berhasil menunjukkan performa terbaik dalam hal akurasi, precision, dan recall, menjadikannya model pilihan utama untuk klasifikasi kepribadian.

### Kesimpulan 
Proyek ini berhasil mengidentifikasi dan menganalisis hubungan antara kepribadian, yaitu introvert dan extrovert, dengan tingkat aktivitas sosial individu. Melalui proses pemodelan dengan tiga algoritma machine learning, yaitu K-Nearest Neighbors (KNN), Random Forest, dan AdaBoost. Serta telah menunjukkan bahwa masing-masing model memiliki kelebihan dan kelemahan tersendiri.
<br/>
Berdasarkan hasil evaluasi, KNN menghasilkan akurasi tertinggi, sementara AdaBoost menunjukkan kemampuan terbaik dalam mengatasi permasalahan klasifikasi tidak seimbang, diikuti oleh Random Forest yang memberikan stabilitas. Evaluasi menggunakan metrik akurasi, precision, recall, dan F1 score menyoroti kinerja setiap model dan membantu menentukan model terbaik untuk prediksi kepribadian.
<br/>
Hasil analisis ini memberikan pemahaman yang lebih dalam tentang bagaimana kepribadian mempengaruhi partisipasi sosial dan memperkuat argumen bahwa pendekatan machine learning dapat memberikan wawasan berharga dalam analisis perilaku manusia. Secara keseluruhan, implementasi metode ini dapat menjadi landasan untuk pengembangan lebih lanjut.

## Referensi
[1]: McCrae, R. R., Costa, P. T. (2008). A five-factor theory of personality. American Psychological Association. [Online]. Available: https://www.researchgate.net/publication/284978581_A_five-factor_theory_of_personality. [Accessed: May 24, 2025].

[2]: Cain, S. (2013). Quiet: The Power of Introverts in a World That Can't Stop Talking. New York: Crown Publishing Group.

[3]: McCrae, R. R. (2008). Cited by 8023 — The five-factor model (FFM) of personality is an empirical generalization about the covariation of personality traits.
