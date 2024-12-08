# Submission-1-Prediktif-Analitik-Inflasi-dan-Pengangguran.

# Bab 1. Domain Proyek
Proyek ini berfokus pada analisis hubungan antara inflasi dan tingkat pengangguran, yang merupakan dua indikator penting dalam ekonomi makro. Inflasi, sebagai kenaikan umum harga barang dan jasa, dapat memengaruhi daya beli masyarakat, sementara tingkat pengangguran mengukur kesehatan pasar tenaga kerja. Pemahaman tentang hubungan antara dua indikator ini penting bagi pembuat kebijakan dan analis ekonomi untuk menyusun kebijakan yang seimbang antara pertumbuhan ekonomi dan stabilitas harga. Melalui analisis data historis, proyek ini berusaha memberikan wawasan berbasis data mengenai pola dan hubungan antara kedua indikator tersebut.

# Bab 2. Business Understanding
Problem Statements
1. Bagaimana performa model Linear Regression dalam memprediksi tingkat pengangguran berdasarkan tingkat inflasi dibandingkan dengan Random Forest?
2. Model manakah yang memiliki performa lebih baik berdasarkan metrik Mean Squared Error (MSE) pada dataset yang digunakan?
   
Goals
1. Membandingkan performa prediktif antara Linear Regression dan Random Forest menggunakan dataset yang tersedia.
2. Menentukan model terbaik untuk memprediksi tingkat pengangguran berdasarkan hasil evaluasi MSE pada data uji.


# Bab 3. Data Understanding
Dataset yang digunakan adalah "Inflation, Interest and Unemployment Rate" yang diunduh dari Kaggle. Dataset ini terdiri dari beberapa fitur, tetapi fokus proyek adalah pada dua variabel:
•	Inflation Rate: Tingkat kenaikan harga dalam periode tertentu.
•	Unemployment Rate: Persentase individu yang menganggur dari total angkatan kerja.
Dataset mencakup:
•	Jumlah data: 1066 
•	Jumlah variabel: 13 kolom, termasuk tahun dan negara. Data yang digunakan hanya data inflasi dan pengangguran
•	Kondisi data: Beberapa data hilang (missing values) ditemukan dan diatasi menggunakan penghapusan data kosong.
•	Distribusi variabel: Inflasi memiliki distribusi dengan outliers yang diatasi menggunakan metode IQR.

# Bab 4. Data Preparation
Proses persiapan data dilakukan secara sistematis:
1.	Menangani Missing Values: Data hilang dihapus untuk mencegah distorsi dalam analisis.
2.	Menghilangkan Outliers: Menggunakan metode Interquartile Range (IQR).
3.	Standarisasi Data: Menggunakan z-score normalization untuk skala data yang konsisten.
4.	Train-Test Split: Dataset dibagi menjadi data pelatihan (80%) dan pengujian (20%).
Langkah ini memastikan data siap digunakan dalam proses pemodelan.

# Bab 5. Modeling
Dua model machine learning digunakan:
1.	Linear Regression: Model ini memprediksi hubungan linier antara inflasi dan tingkat pengangguran. Parameter standar digunakan.
2.	Random Forest: Sebagai model ensemble, Random Forest menggabungkan prediksi beberapa decision tree untuk menangani hubungan non-linier.
Parameter default digunakan dalam eksperimen awal, sementara kinerja model dinilai menggunakan data pengujian dan cross-validation.

# Bab 6. Evaluation
Metrik evaluasi yang digunakan adalah Mean Squared Error (MSE), yang mengukur rata-rata kesalahan prediksi kuadrat. Hasilnya adalah:
•	Linear Regression: 
o	Test MSE: 28.3020
o	Cross-validation MSE: 30.1179
•	Random Forest: 
o	Test MSE: 41.0832
o	Cross-validation MSE: 43.1988
Hasil menunjukkan bahwa Linear Regression memiliki kinerja lebih baik dibandingkan Random Forest berdasarkan metrik MSE. Visualisasi distribusi MSE untuk setiap fold dalam cross-validation juga menunjukkan bahwa Linear Regression lebih stabil.

Daftar Referensi
•	Gelman, A., & Hill, J. (2007). Data analysis using regression and multilevel/hierarchical models. Cambridge University Press.
•	Hastie, T., Tibshirani, R., & Friedman, J. (2009). The elements of statistical learning: Data mining, inference, and prediction. Springer.
•	IBM. (n.d.). What is EDA? Retrieved from https://www.ibm.com/blog/what-is-eda/
•	James, G., Witten, D., Hastie, T., & Tibshirani, R. (2013). An introduction to statistical learning: With applications in R. Springer.
•	Tukey, J. W. (1977). Exploratory data analysis. Pearson.
•	VanderPlas, J. (2016). Python data science handbook. O’Reilly Media.

