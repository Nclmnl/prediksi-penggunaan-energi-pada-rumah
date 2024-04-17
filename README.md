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

# Hasil Exploratory Data Analysis (EDA)

Untuk hasil EDA atau Exploratory Data Analysis, hanya dilakukan analisis terhadap data numerik, dikarenakan pada keseluruhan data, tidak ditemukan data yang bersifat kategorik. Sehingga, analisis Univariat dan Analisis Multivariat hanya dilakukan Analisis terhadap Data Numerik.
Berikut adalah hasil Exploratory Data Analysis (EDA), dimana Gambar 1 merupakan EDA Analisis Univariat dan Gambar 2 merupakan EDA Analisis Multivariat.

Gambar 1 EDA Univariat Numerik
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/afdeb649-55fe-41f0-922c-4810a0a9e82b)
Berdasarkan grafik analisis univariate diatas, dapat dilihat dari grafik tiap variabel, bahwa terdapat data yang terdistribusi normal, dan ada juga data yang terdistribusi merata, namun dari grafik analisis univariate tersebut, mayoritas data terdistribusi normal.

Gambar 2a. EDA Multivariat Numerik
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/8619bd42-dc66-4529-8432-b807bbc6a214)

Gambar 2b. Analisis Multivariat Numerik (Correlation Matrix)
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/51aa42b7-7299-4a1c-985e-938cc740ba19)

Melalui Grafik Analisis multivariate, kita bisa melihat korelasi dari setiap variabel, dimana variabel x yang tidak berkorelasi dengan y atau variabel target, dapat di hilangkan. 

Jika diamati, fitur 'T2' memiliki skor korelasi yang cukup besar (0.27) dengan fitur target 'Appliances'. Artinya, fitur 'Appliances' berkorelasi cukup tinggi dengan lima belas fitur tersebut. Sementara itu, fitur lainnya memiliki korelasi negatif sehingga, fitur tersebut dapat di-drop.

Dalam hal ini, jika diamati dari Analisis Multivariate tersebut, variabel rv1 dan rv2, yang merupakan random variabel, tidak berkorelasi dengan variabel y,  sehingga variabel rv1 dan rv2 dapat didrop atau dihilangkan.

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

$$ IQR = Q<sub>3</sub> - Q<sub>1</sub> $$

dimana
Q<sub>1</sub> adalah kuartil pertama dan Q<sub>3</sub> adalah kuartil ketiga.

Dengan menggunakan metode IQR, dapat ditentukan outlier melalui suatu nilai batas yang ditentukan. Setelah menggunakan metode IQR dimana dataset yang sebelumnya berjumlah 19735 menjadi 9160.

Semua proses ini diperlukan dalam rangka membuat model yang baik.

Untuk mereduksi jumlah fitur dilakukan proses PCA. Teknik reduksi ini adalah prosedur yang mengurangi jumlah fitur dengan tetap mempertahankan informasi pada data. PCA ini adalah teknik untuk mereduksi dimensi, mengekstraksi fitur, dan mentransformasi data dari “n-dimensional space” ke dalam sistem berkoordinat baru dengan dimensi m, di mana m lebih kecil dari n. Pada proyek ini, fitu 'housing_median_age', 'total_rooms', 'total_bedrooms', 'households' divisualisasikan untuk melihat hubungan di antara fitur-fitur tersebut. sperti yang terlihat pada Gambar 3 berikut.

Gambar 3 Visualisasi Hubungan antar Fitur sebelum Reduksi PCA
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/596421ae-9132-4df0-99c6-3e1808cc537e)

Berdasarkan hasil visualisasi dapat diketahui yang memiliki hubungan antar fitur ada 11 yaitu 'T1', 'T2', 'T3', 'T4', 'T5', 'RH_1', 'RH_2', 'RH_3', 'RH_4', 'Tdewpoint', 'T_out'.
Selanjutnya, 11 fitur ini dapat direduksi dengan PCA. Sebelum itu, cek proporsi informasi dari 11 komponen PCs tadi.

```
pca.explained_variance_ratio_.round(3)
```

Potongan kode tersebut memberikan keluaran berupa array([0.572, 0.279, 0.069, 0.037, 0.017, 0.008, 0.008, 0.004, 0.003, 0.002, 0.001]). Dari output di atas 55.5% informasi pada ketiga fitur 'T1', 'T2', 'T3', 'T4', 'T5', 'RH_1', 'RH_2', 'RH_3', 'RH_4', 'Tdewpoint', 'T_out' terdapat pada PC pertama.
Berdasarkan hasil ini, reduksi fitur (dimensi) dan hanya mempertahankan PC (komponen) pertama saja. PC pertama ini akan menjadi fitur 'energy' menggantikan fitur lainnya ('T1', 'T2', 'T3', 'T4', 'T5', 'RH_1', 'RH_2', 'RH_3', 'RH_4', 'Tdewpoint', 'T_out'). Beri nama fitur ini 'energy'.

Setelah data dibersihkan, dataset dibagi menjadi data train dan data test untuk proses Modeling, dimana rasio pembagian data yang dipilih adalah 90:10 mengingat data test untuk rasio tersebut sudah terbilang cukup. 
Train-Test-Split Membagi dataset menjadi data latih (train) dan data uji (test) merupakan hal yang harus diakukan sebelum membuat model. Hal ini diperlukan untuk menguji seberapa baik generalisasi model terhadap data baru. Adapun detail dari dataset tersebut adalah:
* Total # of sample in whole *dataset*: 10525
* Total # of sample in train *dataset*: 9472
* Total # of sample in test *dataset*: 1053

## Modeling

Seperti yang dijelaskan di awal, model yang dipilih adalah model regresi karena merupakan salah satu algoritma yang paling umum digunakan dalam pembuatan model prediksi. Dalam bentuk yang sederhana, regresi terdiri dari intersep dan slope yang dituliskan dalam rumusan berikut:

$$ y = a + bX $$

dimana:
- y adalah variabel kriterium (variabel terikat yang digunakan untuk memprediksi)
- a adalah intersep (variabel konstan yang memiliki arti sebagai titik perpotongan suatu garis dengan sumbu Y),
- b adalah slope (nilai koefisien yang menyatakan ukuran kemiringan suatu garis), dan
- X adalah variabel prediktor (variabel yang digunakan untuk memprediksi atau menjelaskan variabel lain dalam suatu model)
  
Secara umum, regresi ini itu sendiri digunakan untuk meramalkan pengaruh variabel prediktor terhadap variabel kriterium atau membuktikan ada atau tidaknya hubungan fungsional antara variabel bebas (X) dengan variabel terikat (y).

Namun begitu terdapat kelebihan dan kekurangan dari model regresi, yaitu:

Kelebihan regresi:
- Kemudahan untuk digunakan
- Kekuatan Prediktor dalam mengidentifikasi sekuat apa pengaruh yang diberikan oleh variabel prediktor (variabel independen) terhadap variabel lainnya (variabel dependen).
- Dapat memprediksi nilai/tren di masa yang mendatang
  
Kelemahan dari model regresi adalah karena hasil ramalan dari analisis regresi merupakan nilai estimasi sehingga kemungkinan untuk tidak sesuai dengan data aktual tetaplah ada.

Pada proyek yang dikerjakan, algoritma regresi yang coba dibandingkan adalah regresi linear, regresi ridge, random forest regressor, dan random forest regressor dengan hyperparamter tuning. Regresi linear adalah teknik analisis data yang memprediksi nilai data yang tidak diketahui dengan menggunakan nilai data lain yang terkait dan diketahui dimana secara matematis dimodelkan sebagai persamaan linier, regresi ridge merupakan metode estimasi koefisien regresi yang diperoleh melalui penambahan konstanta bias c, dan random forest adalah suatu algoritma yang digunakan pada klasifikasi data dalam jumlah yang besar dimana teknik klasifikasi random forest dilakukan melalui penggabungan pohon dengan melakukan training pada sampel data yang dimiliki.

Untuk meningkatkan model, dilakukan hyperparamter tuning. Adapun paramater yang di-tuning antara lain n_estimators', 'max_depth', 'min_samples_split', dan 'min_samples_leaf. Untuk memudahkan proses tuning digunakan GridSearchCV. GridSearchCV itu sendiri merupakan bagian dari modul scikit-learn yang dapat digunakan untuk mendapatkan nilai hyperparameter secara otomatis. Grid Search adalah metode yang digunakan untuk mencari parameter yang paling tepat untuk meningkatkan performa model dengan mencoba seluruh kombinasi hyperparameter yang diberikan.

Berikut adalah nilai parameter *tuning*
```
params = {'n_estimators' : [50,80,100],
          'max_depth' : [3,5,10],
           'min_samples_split':[2,3,4],
            'min_samples_leaf': [2,3,4]}
```
Berdasarkan hasil pengujian, terpilih grid.best_params_ yaitu
```
{'max_depth': 10,
 'min_samples_leaf': 4,
 'min_samples_split': 2,
 'n_estimators': 100}
```
Parameter dengan nilai inilah yang kemudian dibuat sebagai model.

## Evaluation
Adapun metrik yang sebagai alat ukur perfoma model yang dibuat antara lain:
**MSE · MAE · R<sup>2</sup>**. 

Berikut merupakan rumus dari masing-masing metrik yang digunakan:

$$ MAE = (1/n) Σ |y<sub>i</sub> - ŷ<sub>i</sub>| $$

$$ MSE = (1/n) Σ (y<sub>i</sub> - ŷ<sub>i</sub>)<sup>2</sup> $$

$$ R<sup>2</sup> = 1 - (MSE / Var(y)) $$

y<sub>i</sub> mewakili nilai yang diamati,
ŷ<sub>i</sub> mewakili nilai prediksi,
n adalah jumlah titik data,
Var(y) mewakili varians dari nilai yang diamati.

Berikut merupakan penjelasan kegunaan dari masing-masing metrik yang digunakan:
- MAE menghitung rata-rata dari selisih absolut antara nilai prediksi dan nilai aktual. Semakin kecil nilai MAE, semakin baik kualitas model tersebut.
- MSE menghitung rata-rata dari selisih kuadrat antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin baik kualitas model tersebut.
- R2 digunakan untuk menilai seberapa besar pengaruh variabel independen tertentu terhadap variabel dependen.

Tabel 1 berikut merupakan perbandingan 4 buah model yang coba dibandingkan
|     |Model 1|Model 2|Model 3|Model 4|
|---|---|---|---|---|
|R<sup>2</sup>|-15822.820235231844|-15817.222070472248|-0.39805276219466124|-0.36461941323745206|
|MSE|2228.819631272838|2228.425339531574|20.949855654993556|20.697840062675287|
|MAE|2227.9828068264883|2227.5886009970973|15.656659388646288|15.21291054892845|

Tabel 1. Perbandingan Performa MAE, MSE, dan R2 Model

Berdasarkan Tabel 1, secara umum Model 3 (RF1) dan Model 4 (RF2) menampilkan hasil performa yang lebih baik dimana masing-masing memiliki nilai R^2 yaitu sebesar -0.39805276219466124 dan -0.36461941323745206.

Secara lebih jauh perbandingan Model 1, 2, 3, dan 4 bisa dilihat pada Gambar 4 berikut.

Gambar 4. Perbandingan Model berdasarkan Nilai Error (dalam 1e6)
![image](https://github.com/Nclmnl/prediksi-penggunaan-energi-pada-rumah/assets/165830533/b969279b-4212-421f-a20a-bb9770a881e7)

Berdasarkan Gambar 4 dapat terlihat bahwa nilai error train dan test dari Model 3 (RF1) dan Model 4 (RF2) jauh lebih baik dibandingkan model lainnya.

Selain itu dilakukan perbandingan nilai y_true terhadap nilai prediksi energi yang digunakan pada sebuah rumah atau bangunan, dari 4 buah model yang dibuat. Tabel 2 berikut merupakan hasil dari evaluasi model yang telah dibuat.

Tabel 2. Perbandingan Model
|     |y_true|prediksi_LR|prediksi_RR|prediksi_RF1|prediksi_RF2|
|---|---|---|---|---|---|
|6291|80|49.2 49.2|56.9|54.0|

Terlihat bahwa prediksi dengan Random Forest (RF), baik RF1 ataupun RF2 memberikan hasil yang paling mendekati y_true. dimana nilai y_true yaitu 80 dan nilai RF1 dan RF2 masing-masing yaitu 56.9 dan 54.0. Dengan demikian bisa disimpulkan bahwa model yang telah dikembangkan dapat memprediksi harga rumah dengan baik dengan menggunakan *Random Forest Regressor*.

 








