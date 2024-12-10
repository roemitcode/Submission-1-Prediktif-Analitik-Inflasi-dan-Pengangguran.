# Submission-1-Prediktif-Analitik-Inflasi-dan-Pengangguran.

# Bab 1. Domain Proyek
Proyek ini berfokus pada analisis hubungan antara inflasi dan tingkat pengangguran, yang merupakan dua indikator penting dalam ekonomi makro. Inflasi, sebagai kenaikan umum harga barang dan jasa, dapat memengaruhi daya beli masyarakat, sementara tingkat pengangguran mengukur kesehatan pasar tenaga kerja. Pemahaman tentang hubungan antara dua indikator ini penting bagi pembuat kebijakan dan analis ekonomi untuk menyusun kebijakan yang seimbang antara pertumbuhan ekonomi dan stabilitas harga. Melalui analisis data historis, proyek ini berusaha memberikan wawasan berbasis data mengenai model machine learning terbaik mana yang dapat mengenali pola hubungan antara kedua indikator tersebut.

# Bab 2. Business Understanding
Problem Statements
1. Apakah terdapat hubungan antara tingkat inflasi dan tingkat pengangguran?
   
Goals
1. Membangun model prediktif untuk memperkirakan hubungan tingkat pengangguran berdasarkan tingkat inflasi
   
# Bab 3. Data Understanding
Dataset yang digunakan adalah "Inflation, Interest and Unemployment Rate" yang diunduh dari Kaggle dengan link unduh :       https://www.kaggle.com/datasets/prasertk/inflation-interest-and-unemployment-rate. 

Dataset mencakup:
- Jumlah data: 1066
- Jumlah variabel: 13 kolom, termasuk tahun dan negara.
- Kondisi data: Beberapa data hilang (missing values) ditemukan dan diatasi menggunakan penghapusan data kosong.
- Distribusi variabel: Inflasi memiliki distribusi dengan outliers yang diatasi menggunakan metode IQR.

Dataset yang digunakan memiliki fitur yang tersebar dalam 13 kolom data yang terdiri atas:
1.  country   : Nama negara atau wilayah yang dianalisis ; jenis data object
2. year (integer) : Tahun saat data direkam ; jenis data integer
3. Inflation, consumer prices (annual percent %) : Persentase perubahan tahunan dalam tingkat harga barang dan jasa yang dikonsumsi oleh rumah tangga, yang mengukur inflasi dari perspektif konsumen ; jenis data float
4. Inflation, GDP deflator (annual percent %)): Persentase perubahan tahunan dalam deflator PDB, yang merupakan ukuran inflasi yang lebih luas yang mencakup semua barang dan jasa yang diproduksi dalam perekonomian, bukan hanya yang dikonsumsi oleh rumah tangga ; jenis data float
5. Real interest rate (%): Suku bunga nominal yang disesuaikan dengan inflasi, yang mencerminkan biaya pinjaman sebenarnya dan pengembalian riil atas tabungan ; jenis data float
6. Deposit rate (%): Suku bunga yang dibayarkan oleh lembaga keuangan atas simpanan, biasanya rekening tabungan atau dana lain yang dipegang bank ; jenis data float
7. Lending rate (%): Suku bunga yang digunakan bank untuk meminjamkan uang kepada peminjam, seperti individu atau bisnis ; jenis data float
8. Unemployment, total (% of total labor force) (national estimate): Persentase total angkatan kerja yang menganggur, berdasarkan estimasi nasional ; jenis data float
9. Unemployment, total (% of total labor force) (modeled ILO estimate) : Persentase angkatan kerja yang menganggur, berdasarkan estimasi dari Organisasi Perburuhan Internasional (ILO) ; jenis data float
10. iso3c: Kode ISO 3166-1 tiga huruf yang mengidentifikasi negara secara unik ; jenis data object
11. iso2c: Kode negara ISO 3166-1 dua huruf ; jenis data object
12. admin region: Wilayah administratif tempat negara tersebut berada ; jenis data object
13. income Level**: Klasifikasi pendapatan suatu negara, seperti "Pendapatan rendah", "Pendapatan menengah ke atas", dll ; jenis data object

Dataset ini terdiri dari beberapa fitur, tetapi fokus proyek adalah pada dua variabel yakni Inflation, GDP deflator (annual percent %)) : dan Unemployment, total (% of total labor force) (national estimate

# Bab 4. Data Preparation
Proses persiapan data dilakukan secara sistematis:
1.	Menangani Missing Values: Data hilang dihapus untuk mencegah distorsi dalam analisis.
2.	Menghilangkan Outliers: Menggunakan metode Interquartile Range (IQR).
3.	Train-Test Split: Dataset dibagi menjadi data pelatihan (80%) dan pengujian (20%).
4.	Standarisasi Data: Menggunakan z-score normalization untuk skala data yang konsisten.
Langkah ini memastikan data siap digunakan dalam proses pemodelan.

# Bab 5. Modeling
Dua model machine learning digunakan:
1.	Linear Regression: Model ini memprediksi hubungan linier antara inflasi dan tingkat pengangguran. Parameter standar digunakan.
2.	Random Forest: Sebagai model ensemble, Random Forest menggabungkan prediksi beberapa decision tree untuk menangani hubungan non-linier.
Parameter default digunakan dalam eksperimen awal, sementara kinerja model dinilai menggunakan data pengujian dan cross-validation.

# Bab 6. Evaluation
Metrik evaluasi yang digunakan adalah Mean Squared Error (MSE), yang mengukur rata-rata kesalahan prediksi kuadrat. Hasilnya adalah:
1. Linear Regression: 
- Test MSE: 28.3020
- Cross-validation MSE: 30.1179
2. Random Forest: 
- Test MSE: 41.0832
- Cross-validation MSE: 43.1988

Dari hasil MSE yang dihasilkan maka dipilih model Linear Regression untuk analisis statistika selanjutnya.

3. Hasil Kuantitatif Statistika dari model Linear Regression :
- R-squared (koefisien determinasi): 0.0003
- Koefisien inflasi: -0.0194
- Nilai p untuk inflasi: 5.3753e-01
- Hasil: Inflasi memiliki pengaruh yang signifikan terhadap tingkat pengangguran.

# Kesimpulan
1. Hasil ini menunjukkan bahwa Linear Regression memiliki kinerja lebih baik dibandingkan Random Forest berdasarkan metrik MSE. Visualisasi distribusi MSE untuk setiap fold dalam cross-validation juga menunjukkan bahwa Linear Regression lebih stabil.
2. Hasil nilai p yang dihasilkan menunjukkan bahwa Inflasi memiliki pengaruh terhadap tingkat pengangguran.



# Daftar Referensi
1. Gelman, A., & Hill, J. (2007). Data analysis using regression and multilevel/hierarchical models. Cambridge University Press.
2. Hastie, T., Tibshirani, R., & Friedman, J. (2009). The elements of statistical learning: Data mining, inference, and prediction. Springer.
3. IBM. (n.d.). What is EDA? Retrieved from https://www.ibm.com/blog/what-is-eda/
4. James, G., Witten, D., Hastie, T., & Tibshirani, R. (2013). An introduction to statistical learning: With applications in R. Springer.
5. Tukey, J. W. (1977). Exploratory data analysis. Pearson.
6. VanderPlas, J. (2016). Python data science handbook. O’Reilly Media.

