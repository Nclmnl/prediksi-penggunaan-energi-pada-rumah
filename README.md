## prediksi-penggunaan-energi-pada-rumah
tugas mata kuliah sains data rekayasa oleh Nawi rastoko dan elisabeth manalu

## Domain Projek
Projek prediksi penggunaan energi pada rumah adalah upaya untuk mengembangkan model atau sistem yang dapat memprediksi seberapa banyak energi yang akan digunakan oleh sebuah rumah dalam periode waktu tertentu.
pengunaan energi pada suatu rumah bergantung pada beberapa faktor seperti temperatur ruangan, kelembapan ruangan, pencahayaan ruangan, dan lain sebagainya. Oleh karena itu, dengan mempertimbangkan faktor-faktor tersebut, yang juga tersedia pada dataset, maka dapat diestimasi pengunaan energi rumah tersebut dan melihat seberapa besar korelasi pengaruh faktor-faktor tersebut.

## Business Understanding
Tujuan utama dari proyek ini adalah untuk membantu pemilik rumah atau penyedia layanan energi dalam mengoptimalkan penggunaan energi, mengurangi biaya energi, dan meningkatkan efisiensi energi secara keseluruhan.

# Problem Statements
* Berdasarkan eksplorasi dataset, fitur apa saja yang mempengaruhi dalam menentukan estimasi penggunaan energi pada rumah?
* Bagaimana mengolah dataset agar dapat dibuat model prediksi penggunaan energi pada rumah?
* Bagaimanna cara meningkatkan nilai perfoma model prediksi penggunaan energi pada rumah?
  
# Goals
* Mengeksplorasi semua fitur yang tersedia pada dataset kemudian membuat melihat korelasi dari semua fitur yang sedia untuk melihat faktor apa saja yang paling berpengaruh sampai paling kurang berpengaruh terhadap penggunaan energi pada rumah
* Melakukan proses data wragling dan data preparation terhadap dataset agar dapat dibuat model predksi penggunaan energi pada rumah
* Melakukan beberapa variasi model untuk mendapatkan model yang paling baik dari beberapa model yang telah dibuat untuk prediksi penggunaan energi pada rumah
  
# Solution statements
Untuk eksplorasi fitur dilakukan Analisis Univariat dan Analisis Multivariat. Analisis Univariat dilakukan untuk mengeksploasi data numerik dan data kategorik. Analisis Multivariat dilakukan untuk melihat hubungan antar fitur. Teknik yang digunakan adalah menggunakan catplot, pairplot, dan heatmap untuk melihat Correlation Matrix dari fitur-fitur yang dimiliki.
Agar didapatkan model prediksi yang baik maka dilakukan proses Data Wragling yang meliputi Data Gathering, Data Assessing, dan Data Cleaning.
Untuk mengetahui perfoma model dilakukan pengecekan performa dengan metrik evaluasi.

## Data Understanding
Data yang digunakan dalam pembuatan model merupakan data sekunder. Data diambil dari Kaggle dengan nama dataset yaitu _Appliances energy prediction Data Set_
URL : https://archive.ics.uci.edu/ml/datasets/Appliances+energy+prediction
Berikut merupakan detail dari dataset yang digunakan untuk pembuatan model:
* Dataset berupa CSV
* Dataset terdiri dari 19735 records dengan 20 buah fitur yang diukur.
* Dataset terdiri dari 20 data numerik.
* Dataset tidak memiliki missing value.
  
## Variabel-variabel pada dataset adalah sebagai berikut:
* Appliances, energy use in Wh (target variable for prediction)
* lights, energy use of light fixtures in the house in Wh
* T1, Temperature in kitchen area, in Celsius
* RH_1, Humidity in kitchen area, in %
* T2, Temperature in living room area, in Celsius
* RH_2, Humidity in living room area, in %
* T3, Temperature in laundry room area
* RH_3, Humidity in laundry room area, in %
* T4, Temperature in office room, in Celsius
* RH_4, Humidity in office room, in %
* T5, Temperature in bathroom, in Celsius
* RH_5, Humidity in bathroom, in %
* To, Temperature outside (from Chievres weather station), in Celsius
* Pressure (from Chievres weather station), in mm Hg
* RH_out, Humidity outside (from Chievres weather station), in %
* Wind speed (from Chievres weather station), in m/s
* Visibility (from Chievres weather station), in km
* Tdewpoint (from Chievres weather station), Â°C
* rv1, Random variable 1, nondimensional
* rv2, Random variable 2, nondimensional

Untuk memahami data lebih lanjut, dilakukan Analisis Univariat dan Analisis Multivariat, serta Visualisasi Data

Analisis Univariat merupakan bentuk analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel. Jenis visualisasi ini umumnya digunakan untuk memberikan gambaran terkait distribusi sebuah variabel dalam suatu dataset. Sedangkan, Analisis Multivariat tmerupakan jenis analisis data yang terdapat dalam lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data.

Selain melalui analisis, dilakukan juga Visualisasi Data. Memvisualisasikan data memberikan wawasan mendalam tentang perilaku berbagai fitur-fitur yang tersedia dalam dataset. Teknik visualisasi yang digunakan pada pembuatan model proyek ini adalah dengan menggunakan catplot yang digunakan untuk memplot distribusi data pada data kategori, pairplot yang digunakan untuk melakukan hubungan antar fitur dalam dataset, dan heatmap yang menampilkan korelasi antar fitur yang ada dalam dataset dalam bentuk matriks.

Berikut adalah hasil Exploratory Data Analysis (EDA)

Gambar 1 EDA Univariat Numerik
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/afdeb649-55fe-41f0-922c-4810a0a9e82b)


Gambar 2 EDA Multivariat Numerik
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/8619bd42-dc66-4529-8432-b807bbc6a214)

Gambar 3 Analisis Multivariat (Correlation Matrix)
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/51aa42b7-7299-4a1c-985e-938cc740ba19)

Jika diamati, fitur 'T2' memiliki skor korelasi yang cukup besar (0.27) dengan fitur target 'Appliances'. Artinya, fitur 'Appliances' berkorelasi cukup tinggi dengan lima belas fitur tersebut. Sementara itu, fitur lainnya memiliki korelasi negatif sehingga, fitur tersebut dapat di-drop.

##Data Preparation
Pada proses Data Preparation dilakukan kegiatan seperti Data Gathering, Data Assessing, dan Data Cleaning. Pada proses Data Gathering, data diimpor sedemikian rupa agar bisa dibaca dengan baik menggunakan dataframe Pandas. 

Untuk proses Data Assessing, berikut adalah beberapa pengecekan yang dilakukan:
* Duplicate data (data yang serupa dengan data lainnya)
* Missing value (data atau informasi yang "hilang" atau tidak tersedia)
* Outlier (data yang menyimpang dari rata-rata sekumpulan data yang ada)
  
Pada proses Data Cleaning, secara garis besar, terdapat tiga metode yang dapat digunakan antara lain seperti berikut:
* Dropping (metode yang dilakukan dengan cara menghapus sejumlah baris data)
* Imputation (metode yang dilakukan dengan cara mengganti nilai yang "hilang" atau tidak tersedia dengan nilai tertentu yang bisa berupa median atau mean dari data)
* Interpolation (metode menghasilkan titik-titik data baru dalam suatu jangkauan dari suatu data)

Pada kasus proyek ini tidak ditemukan data duplikat maupun data Missing Value. Namun, jika ditemukan data missing, dapat menerapkan imputation dimana data yang missing diganti dengan nilai mean. Untuk outlier sendiri dilakukan metode dropping menggunakan metode IQR. IQR sendiri didapatkan dengan cara mengurangi Q3 dengan Q1 sebagaimana rumusan berikut.
<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mi>I</mi>
  <mi>Q</mi>
  <mi>R</mi>
  <mo>=</mo>
  <mi>Q</mi>
  <mn>3</mn>
  <mo>&#x2212;</mo>
  <mi>Q</mi>
  <mn>1</mn>
</math>

dimana Q1 adalah kuartil pertama dan Q3 adalah kuartil ketiga.

Dengan menggunakan metode IQR, dapat ditentukan outlier melalui suatu nilai batas yang ditentukan. Setelah menggunakan metode IQR dimana dataset yang sebelumnya berjumlah 19735 menjadi 9160.

Semua proses ini diperlukan dalam rangka membuat model yang baik.

Untuk mereduksi jumlah fitur dilakukan proses PCA. Teknik reduksi ini adalah prosedur yang mengurangi jumlah fitur dengan tetap mempertahankan informasi pada data. PCA ini adalah teknik untuk mereduksi dimensi, mengekstraksi fitur, dan mentransformasi data dari “n-dimensional space” ke dalam sistem berkoordinat baru dengan dimensi m, di mana m lebih kecil dari n. Pada proyek ini, fitu 'housing_median_age', 'total_rooms', 'total_bedrooms', 'households' divisualisasikan untuk melihat hubungan di antara fitur-fitur tersebut. sperti yang terlihat pada Gambar 3 berikut.
