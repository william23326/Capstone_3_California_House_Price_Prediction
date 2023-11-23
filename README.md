# Capstone_3_California_House_Price_Prediction

[Sumber data California House](https://drive.google.com/drive/folders/19YA_f36uGR86hTnZuX-Ech59s3AFzXXo)
### **Contents**

1. Business Problem Understanding
2. Data Understanding
3. Data Preprocessing
4. Modeling
5. Conclusion
6. Recommendation

****

### **Business Problem Understanding**
**Context**

Disclaimer: Data ini berisi informasi dari sensus California tahun 1990. Jadi, meskipun hal ini mungkin tidak membantu Anda dalam memprediksi harga rumah saat ini (2023), hal ini memberikan kumpulan data pengenalan yang dapat diakses untuk mengajari orang-orang tentang dasar-dasar pembelajaran machine learning.

Pasar properti, seperti di California, memberikan peluang menarik bagi para data analis untuk menganalisis dan memprediksi arah pergerakan harga properti. Prediksi harga properti menjadi semakin penting dan bermanfaat. Harga properti adalah indikator yang baik baik dari kondisi pasar secara keseluruhan maupun kesehatan ekonomi suatu negara. Dengan mempertimbangkan data yang disediakan, kita sedang mengelola kumpulan besar catatan penjualan properti yang tersimpan dalam format yang tidak diketahui dan dengan masalah kualitas data yang tidak diketahui.

**Problem Statement**

Dalam menghadapi dinamika pasar properti, khususnya di California, tantangan utama yang dihadapi adalah bagaimana memanfaatkan dataset sensus California tahun 1990 untuk mengembangkan model prediksi harga properti. Meskipun data ini tidak mencerminkan kondisi pasar saat ini (2023), pengembangan model prediksi memiliki potensi untuk memberikan wawasan berharga terkait faktor-faktor yang memengaruhi harga properti dan trennya.

Tujuan utama adalah **membangun model machine learning yang dapat memprediksi harga properti berdasarkan karakteristik tertentu, seperti lokasi geografis, umur rumah, jumlah kamar, pendapatan median, dan variabel lainnya yang terdapat dalam dataset**. Model ini diharapkan dapat memberikan pemahaman yang lebih dalam tentang faktor-faktor apa yang memiliki dampak signifikan terhadap harga properti.

**Goals**

Berdasarkan problem statement di atas, hasil dari model ini diharapkan dapat **memberikan wawasan strategis kepada para pemangku kepentingan di pasar properti, membantu pengambilan keputusan investasi, dan meningkatkan pemahaman tentang tren pasar properti di California**.

**Analytic Approach**

Agar dapat memperkirakan nilai pasar sebuah properti di California, informasi-informasi berikut ini diperlukan:

1. Karakteristik Kawasan dan Lingkungan:

- Jumlah Populasi (Population)
- Jumlah Rumah Tangga (Households)
- Usia Median Perumahan (Housing Median Age)
- Pendapatan Median (Median Income)

2. Kondisi Fisik Rumah:

- Koordinat Bujur (Longitude)
- Koordinat Lintang (Latitude)
- Proksimitas dengan Laut (Ocean Proximity)
- Total Ruangan (Total Rooms)
- Total Kamar Tidur (Total Bedrooms)

**Modelling**

Berikut teknik permodelan yang akan digunakan dalam analisis ini:
1. Linear Regression
2. Decission Tree Regressor
3. KNN Regressor
4. Random Forest
5. XGBoost Regressor

**Metric Evaluation**

Evaluasi metrik yang akan digunakan adalah sbb:
1. RMSE : nilai rataan akar kuadrat dari error
2. MAE  : rataan nilai absolut dari error
3. MAPE : rataan persentase error yang dihasilkan oleh model regresi, di mana RMSE adalah nilai rataan akar kuadrat dari error 

Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi harga properti sesuai dengan limitasi fitur yang digunakan. 

### **Conclusion**

Berikut adalah beberapa hal yang dapat disimpulkan:
1. Dari 5 model yang diuji, XGBoost merupakan algoritma permodelan yang paling baik dalam memprediksi nilai rumah dari dataset *data_california_house.csv*'
2. Fitur yang paling berpengaruh dalam menentukan prediksi harga rumah adalah posisinya dari laut (`ocean_proximity`) dan rata-rata pendapatan rumah tangga (`median_income`) dalam suatu blok.
3. Meskipun model yang dibangun sudah cukup baik dalam melakukan prediksi harga rumah di California dengan rentang nilai yang dilatih terhadap permodelan (masksimal harga rumah di $500.001), namun masih diperlukan optimalisasi lebih lanjut karena prediksinya masih dapat meleset ±$30.000 atau >17% nilai aktualnya.

### **Recomendation**

1. Melakukan evaluasi fitur serta menambahkan fitur yang relevan dan memiliki pengaruh yang cukup kuat terhadap harga rumah.
2. Dari grafik Actual vs. Prediction median_house_value, perusahaan dapat mempertimbangkan kemungkinan Over Prediction dan Under Prediction pada prediksi:
    - Under Prediction perlu mendapatkan perhatian serius dalam perhitungan pendapatan, terutama jika perusahaan menggunakan prediksi ini untuk mengevaluasi potensi pendapatan dari penjualan rumah. Kekurangan pendapatan dapat terjadi karena harga sebenarnya cenderung lebih tinggi daripada prediksi model, dan hal ini dapat memiliki dampak yang signifikan pada perencanaan keuangan perusahaan.
    - Di sisi lain, Over Prediction memerlukan perhatian khusus saat menetapkan harga rumah. Jika perusahaan mengantisipasi harga rumah yang lebih tinggi dari nilai sebenarnya, ini dapat mengakibatkan situasi di mana biaya aktual rumah melebihi perkiraan. Hal ini mungkin menyulitkan perusahaan untuk menarik pembeli karena harga yang lebih mahal dari yang diharapkan. Oleh karena itu, perusahaan perlu berhati-hati dalam menyesuaikan harga untuk menghindari over prediction yang dapat berdampak negatif pada penjualan dan reputasi perusahaan.
3. Menambah kompleksitas model dapat dilakukan dengan dua pendekatan: 
    1. Penambahan parameter saat proses tuning untuk meningkatkan fleksibilitas model
    2. Menggunakan algoritma yang lebih canggih yang memiliki kemampuan untuk menangani pola yang lebih kompleks dalam data.

