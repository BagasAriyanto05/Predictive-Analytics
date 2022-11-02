# Laporan Proyek *Machine Learning* - Bagas Afza Joko Ariyanto
<hr style="border:1px solid gray">

## Domain Proyek
#### <div align="left"><span style="white-space: prewrap; font: normal 12pt Arial; line-height: 1.5;">Domain proyek yang dipilih dalam proyek machine learning ini adalah mengenai **pertanian** dengan judul proyek "Prediksi Strategis Pemilihan Jenis Tanaman untuk Lahan Pertanian Tertentu"</span></div>

![gambar 1](https://user-images.githubusercontent.com/92978028/199243621-3b1c36bc-419f-4a14-aaa3-e3e42f686fcd.jpg)

#### <div align="left"><span style="white-space: prewrap; font: normal 12pt Arial; line-height: 1.5;">**Latar Belakang**<br>Sektor pertanian di Indonesia hingga saat ini memegang peranan penting dalam perekonomian nasional dan pembangunan negara secara keseluruhan. Pertanian masih menjadi andalan sebagai sumber bahan pangan (Kusumaningrum, 2019) dan sumber mata pencaharian terbesar di Indonesia, bahkan hampir di setiap daerah di Indonesia terdapat lahan pertanian (Mulziatuddin & Aidar, 2018). Sebelum melakukan proses pertanian maka seorang petani harus mengumpulkan berbagai informasi yang dapat memengaruhi proses pertanian terlebih dahulu. Informasi yang diperlukan antara lain seperti karaktersistik, struktur dan tekstur lahan, jenis tanaman yang akan ditanam, dan target panen (Telaah et al., 2020). Namun, pada kenyataannya, dalam melakukan penanaman tanaman pada suatu lahan pertanian, tidak banyak petani yang memperhitungkan apakah lahan yang dimiliki cocok untuk ditanami jenis tanaman yang telah ditentukan atau tidak (Wiratama & Dewi, 2021). Keputusan seorang petani mengenai jenis tanaman apa yang akan ditanam di lahannya pada umumnya tergantung pada intuisi petani itu sendiri, petani akan lebih memilih tanaman yang sedang tren di wilayah sekitarnya dan biasanya mereka tidak memiliki pengetahuan yang cukup tentang kandungan nutrisi lahan seperti nitrogen, fosfor, kalium dalam lahan (Fatiharani, 2022). Sehingga, jika petani mengambil keputusan yang salah pada pemilihan tanaman maka hasil panen menjadi tidak optimal dan berpotensi mengalami kerugian yang cukup besar nantinya.<br><br>Berdasarkan permasalahan tersebut, maka pada proyek ini akan dibangun suatu model machine larning untuk memprediksi jenis tanaman yang cocok ditanam di lahan pertanian tertentu berdasarkan parameter kandungan N, P, K (Nitrogen, Fosfor, Kalium) pada lahan, curah hujan, suhu, kelembapan dan pH. Dengan adanya model machine learning ini, diharapkan dapat membantu dan memudahkan petani dalam mengambil keputusan tentang strategi pertanian khususnya dalam memilih jenis tanaman yang cocok untuk lahan mereka, sehingga dapat meminimalkan kesalahan penanaman serta dapat meningkatkan hasil produksi di sektor pertanian. Kemudian, untuk tahap pengembangan selanjutnya implementasi dari model ini dapat dijalankan pada sebuah aplikasi berbasis web ataupun mobile.</span></div>

# *Business Understanding*

### Problem Statements
Berdasarkan pada latar belakang di atas, permasalahan yang dapat diselesaikan pada proyek ini adalah sebagai berikut :

-   Bagaimana cara melakukan prapemrosesan data lahan sehingga dapat digunakan untuk membuat model yang baik?
-   Bagaimana cara membangun model _machine learning_ untuk mengklasifikasikan data lahan ke dalam jenis tanaman yang cocok ditanam pada lahan tersebut?


### Goals
Tujuan dibuatnya proyek ini adalah sebagai berikut :

-   Melakukan prapemrosesan data lahan agar dapat digunakan dalam membangun model.
-   Membangun model _machine learning_ untuk mengklasifikasikan jenis tanaman yang cocok ditanam pada lahan tertentu dengan tingkat akurasi > 98%.

### Solution statements
Solusi yang dapat dilakukan untuk memenuhi tujuan dari proyek ini diantaranya :

- **Pra-pemrosesan Data**. Pada prapemrosesan data dapat dilakukan beberapa tahapan, antara lain :
  
    -   Melakukan label encoding pada fitur target (label).
    -   Melakukan pembagian dataset.
    -   Mengatasi data _outliers_ pada data latih dengan metode LOF (_Local Outlier Factor_).
    -   Standardisasi data pada semua fitur numerik pada dataset.

- **Pembangunan Model**. Pada pembangunan model terdapat beberapa algorima yang digunakan, antara lain :

  - **K-Nearest Neighbor** 
    <br>K-Nearest Neighbor atau KNN adalah algoritma yang relatif sederhana dibandingkan dengan algoritma lain. Algoritma KNN menggunakan kesamaan fitur untuk memprediksi nilai dari setiap data yang baru. Dengan kata lain, setiap data baru diberi nilai berdasarkan seberapa mirip titik tersebut dalam set pelatihan. KNN bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah k-tetangga terdekat. KNN bisa digunakan untuk kasus klasifikasi dan regresi [[1](https://towardsdatascience.com/getting-acquainted-with-k-nearest-neighbors-ba0a9ecf354f)]. Cara kerja algoritma KNN adalah sebagai berikut (bersumber dari [[2](https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761)]) :
    
    -   Inisialisasi nilai K (jumlah tetangga)
    -   Hitung jarak antara data baru yang ditanyakan dengan seluruh sampel data pelatihan
    -   Urutkan seluruh jarak berdasarkan jarak minimum dan tetapkan jumlah tetangga (nearest neighbors) sesuai dengan nilai K
    -   Pilih sejumlah K data dengan jarak terdekat
    -   Kemudian tentukan kelas atau label dari data baru
    
    Kelebihan dan kekurangan algoritma K-Nearest Neighbor adalah sebagai berikut (bersumber dari [[2](https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761)]) :
    
    -   Kelebihan :
        -   Algoritma KNN merupakan algoritma yang sederhana dan mudah untuk diimplementasikan
        -   Dapat diimplementasikan pada beberapa kasus seperti klasifikasi, regresi dan pencarian
    -   Kekurangan :
        -   Algoritma KNN menjadi lebih lambat secara signifikan seiring meningkatnya jumlah sampel dan/atau variabel independen

  - **XGBoost Algorithm**
    <br> XGboost adalah algoritma yang merupakan implementasi lanjutan dari algoritma peningkatan gradien (Gradient Boosting). XGboost menggunakan priensemble, yaituyaitu menggabungkan beberapa set pembelajar (tree) yang lemah menjadi sebuah model yang kuat sehinga menghasilkan prediksi yang kuat. Kelebihan dari algoritma XGBoost adalah sebagai berikut (bersumber dari [[3](https://towardsdatascience.com/https-medium-com-vishalmorde-xgboost-algorithm-long-she-may-rein-edd9f99be63d)]) :
    
    -   Kelebihan :
        -   Dapat melakukan pemrosesan paralel yang dapat mempercepat komputasi
        -   Memiliki fitur regularisasi untuk mencegah overfitting
        -   Menangani berbagai jenis pola sparsity dalam data dengan lebih efisien
        -   Dilengkapi din cross cross cross validation
        
  - **Random Forest**
    <br> Random Forest (RF) adalah suatu algoritma yang digunakan pada klasifikasi data dalam jumlah yang besar. Klasifikasi random forest dilakukan melalui penggabungan pohon (tree) dengan melakukan training pada sampel data yang dimiliki. Penggunaan pohon (treesemakinsemakin banyamemengaruhingaruhi akurasi yang akan didapatkan menjadi lebih baik. Penentuan klasifikasi dengan random forest diambil berdasarkan hasil voting dari tree yang terbentuk. Pemenang dari tree yang terbentuk ditentukan dengan vote terbanyak. Proses klasifikasi pada random forest berawal dari memecah data sampel yake dalamkedalam decision tree secara acak. Setelah pohon terbentuk,maka akan dilakukan voting pada setiap kelas dari data sampel. Kemmengombinasikannasikan vote dari setiap kelas kemudian diambil vote yang paling banyak.Dengan menggunakan random forest pada klamaka,a maka,a maka, akan menghasilkan vote yang paling baik [[4](https://id.wikipedia.org/wiki/Random_forest)]. Kelebihan dan kekurangan algoritma Random Forest adalah sebagai berikut (bersumber dari [[5](https://medium.com/swlh/random-forest-classification-and-its-implementation-d5d840dbead0)]) :
    
    -   Kelebihan :
        -   Algoritma Random Forest merupakan algoritma dengan pembelajaran paling akurat yang tersedia. Untuk banyak kumpulan data, algoritma ini menghasilkan pengklasifikasi yang sangat akurat
        -   Berjalan secara efisien pada data besar
        -   Dapat menangani ribuan variabel input tanpa penghapusan variabel
        -   Memberikan perkiraan variabel apa yang penting dalam klasifikasi
        -   Memiliki metode yang efektif untuk memperkirakan data yang hilang dan menjaga akurasi ketika sebagian besar data hilang
    -   Kekurangan :
        -   Algoritma Random Forest overfiting untuk beberapa kumpulan datatugasan tugas klasifikasi/regresi yang bising/noise
        -   Untuk data yang menyertakan variabel kategorik dengan jumlah level yang berbeda, Random Forest menjadi bias dalam mendukung atribut dengan level yang lebih Oleh karena itu,,ena itu, skor kepentingan variabel dari Random Forest tidak dapat diandalkan untuk jenis data ini.

# *Data Understanding*

- **Informasi Dataset**
  <br> Dataset yang digunakan pyaituni, yaituni yaitu crop dataset, informasi lebih lanjut  mengenai dataset tersebut dapat lihat pada tabel 1 :
  
  Tabel 1. Informasi mengenai dataset yang dipakai

  | Jenis                   | Keterangan                                                                              |
  | ----------------------- | --------------------------------------------------------------------------------------- |
  | Sumber                  | Crop Dataset : [Kaggle](https://www.kaggle.com/datasets/siddharthss/crop-recommendation-dataset) |
  | Dataset Owner           | SIDDHARTH SHARMA                                                                          |
  | Lisensi                 | https://creativecommons.org/licenses/by/3.0/igo                                                                                 |
  | Kategori                | agriculture, sistem rekomendasi                                               |
  | Jenis dan Ukuran Berkas | CSV (150.03 kb)                                                                         |

  Setelah melakukan observasi pada dataset yang diunduh meyaituive, yaituive yaitu `Crop_prediction.csv`, didapatakan informasi sebagai berikut :
  
  - Terdapat  2200 baris (records atau jumlah pengamatan) yang berisi informasi mengenai data lahan pertanian
  yaituolom, yaituolom yaitu `N, P, K, temperature, humidity, ph, rainfall, dan label` yang merupakan veriabel - variabel pada data
  - Dari kolom-kolom tersebut terdapat 3 kolom numerik dengan tipe data int64, yaitu `N, P, K` dan terdapat 4 kolom numerik denganyaituat64, yaituat64 yaitu `temperature, humidity, ph dan rainfall` yang merupakan fitur numerik. 
  - Terdapat 1 koloyaitubject, yaitubject yaitu `label`, kolom ini merupakan _categorical featurnon-numerik)oddi manarik) dimana kolom ini merupakan target fitur
  - Tidak terdapat missing value pada dataset. 
  
  Untuk penjelasan mengenai variabel-variable pada crop dataset dapat dilihat pada poin-poin berikut ini:

  - `N` - rasio kandungan Nitrogen dalam tanah
  - `P` - rasio kandungan Fosfor dalam tanah
  - `K` - rasio kandungan Kalium dalam tanah
  - `temperature` - suhu dalam derajat Celcius
  - kelembapan - kelembaban relatif dalam %
  - `ph` - nilai ph tanah
  - `rainfall` - curah hujan dalam mm
  - `label` - label dari crop yang cocok untuk tumbuh di lahan pertanian berdasarkan variabel numeKKemudian,tas. Kemudian terdapat 22 label criini, yaituata ini yaitu `'rice', 'maize', 'chickpea', 'kidneybeans', 'pigeonpeas', 'mothbeans', 'mungbean', 'blackgram', 'lentil', 'pomegranate', 'banana', 'mango', 'grapes', 'watermelon', 'muskmelon', 'apple', 'orange', 'papaya', 'coconut', 'cotton', 'jute', 'coffee'`

- **Sebaran atau Distribusi Data pada Setiap Fitur**
  <br> Berikut merupakan visualisasi data yang menunjukkan sebaran/ distribusi data pada setiap fitur numerik (`N, P, K, temperature, humidity, ph, rainfall`) yang pada gambar 1 sampai gambar 7 :

![Submission 1 MLT - plt 1](https://user-images.githubusercontent.com/92978028/199244081-08f662c8-2415-4803-baed-db506ef9dcf9.png)

Gambar 1. Plt N

![Submission 1 MLT - plt 2](https://user-images.githubusercontent.com/92978028/199244101-221ff997-7a97-4c91-bb2a-d1813def0e2f.png)

Gambar 2. Plt P

![Submission 1 MLT - plt 3](https://user-images.githubusercontent.com/92978028/199244137-abd5395d-fc9d-4a3c-8355-0246369102f2.png)

Gambar 3. Plt K

![Submission 1 MLT - plt 4](https://user-images.githubusercontent.com/92978028/199244157-b484330d-9a34-4b55-81e2-66cf1d02b4f8.png)

Gambar 4. Plt temperature

![Submission 1 MLT - plt 5](https://user-images.githubusercontent.com/92978028/199244181-56972d2b-be07-407c-870b-fe0ba2b3c833.png)

Gambar 5. Plt humidity

![Submission 1 MLT - plt 6](https://user-images.githubusercontent.com/92978028/199244193-e308baf0-a0bd-4e4e-902c-e68094783342.png)

Gambar 6. Plt ph

![Submission 1 MLT - plt 7](https://user-images.githubusercontent.com/92978028/199244202-8081e6ab-2338-409e-8f9e-a868b0818c59.png)

Gambar 7. Plt rainfall

Berdasarkan hasil visualisasi data pada gambar 1 sampai gambar 7, dapat terlihat sebaran atau distribusi data yang ada pada setiap fitur. Termasuk nilai minimum, median, maksimum, Q1, Q3, batas atas dan SSelain itu,h. Selain itu dapat dilihat juga pada beberapa fitur masih terdapat nilai outliers.
  
 Visualisasi data yang menunjukkan sebaran/distribusi data pada fitur target (dditunjukkanang ditunjukan oleh gambar 8:


<img width="835" alt="Submission 1 MLT - Sebaran_distribusi data pada fitur target" src="https://user-images.githubusercontent.com/92978028/199244690-ea41731e-bb14-45d0-b30f-b145704a5efc.png">

Gambar 8. Sebaran/ distribusi data pada fitur target

Berdasarkan hasil visualisasi dari fitur target 'label' pada gambar 8 dapat memberikan informasi bahwa dataset sudah seimbang dengan jumlah sampel label, yaitsehinggampel, sehinggampel, sehingga tidak perlu menyeimbangkan data lagi.
  
- **Rata-Rata Nilai pada fitur Numerik di Setiap label**
  <br> Visualisasi rata-rata kandungan `N, P, K` terhadap setiap label ditujukan oleh gambar 9 sampai gambar 15 :
  
<img width="836" alt="Submission 1 MLT - Rata rata N terhadap label crop" src="https://user-images.githubusercontent.com/92978028/199244421-15ca2af3-75c7-4233-829e-afc6e385f1bc.png">

Gambar 9. Rata-rata N terhadap label crop

![Submission 1 MLT - Rata rata N terhadap label crop 2](https://user-images.githubusercontent.com/92978028/199245324-f83713aa-38ca-4287-b020-989445b8d36f.png)

Gambar 10. Rata-rata N terhadap label crop 2


<img width="835" alt="Submission 1 MLT - Rata rata P terhadap label crop" src="https://user-images.githubusercontent.com/92978028/199248151-fa273dfc-176c-4e08-86aa-173f204117f3.png">

Gambar 11. Rata-rata P terhadap label crop

![Submission 1 MLT - Rata rata P terhadap label crop 2](https://user-images.githubusercontent.com/92978028/199248175-15abfc19-e45b-417c-a324-19a1d878b7fd.png)

Gambar 12. Rata-rata P terhadap label crop 2

<img width="836" alt="Submission 1 MLT - Rata rata K terhadap label crop" src="https://user-images.githubusercontent.com/92978028/199248216-fde96557-7ce9-46cc-8a9b-66aa90617421.png">

Gambar 13. Rata-rata K terhadap label crop

![Submission 1 MLT - Rata rata K terhadap label crop 2](https://user-images.githubusercontent.com/92978028/199248241-a631ad28-f3dd-42b6-a4c8-9da04cfbb03e.png)

Gambar 14. Rata-rata K terhadap label crop 2

![Submission 1 MLT - Perbandiangan N, P, K pada label](https://user-images.githubusercontent.com/92978028/199248283-ff6c8747-5594-41e7-a6f5-740acca8ed54.png)

Gambar 15. Perbandingan N, P, L terhadap label crop

 Hasil visualisasi pada gambar 9 sampai gambar 15 memberikan informasi mengenai rata-rata kandungan N, P, K terhadap setiaDDi manal crop. Dimana dapat dilihat bahwa terdapat beberapa label crop yang membutuhkan lahan dengan kandungan N,P,K tinggi dan beberapa label membutuhkan lahan dengan kandungan N,P,K rendah.
  
  Visualisasi rata-rata tingkat `temperature, humidity dan rainfall` terhadadditunjukkanabel ditunjukan oleh gambar 16 sampai gambar 22 :
  
<img width="830" alt="Submission 1 MLT - Rata rata temperatur terhadap label crop" src="https://user-images.githubusercontent.com/92978028/199249418-537408b5-f448-489c-a220-a86fdc6d01e2.png">

Gambar 16. Rata-rata temperature terhadap label crop

![Submission 1 MLT - Rata rata temperatur terhadap label crop 2](https://user-images.githubusercontent.com/92978028/199249435-2467be20-ef5c-4020-9f1b-0b5438ed6682.png)

Gambar 17. Rata-rata temperature terhadap label crop 2

<img width="836" alt="Submission 1 MLT - Rata rata humidity terhadap label crop" src="https://user-images.githubusercontent.com/92978028/199249453-b7502515-7748-45a8-bc8c-7e88496b41c1.png">

Gambar 18. Rata-rata humidity terhadap label crop

![Submission 1 MLT - Rata rata humadity terhadap label crop 2](https://user-images.githubusercontent.com/92978028/199249473-e27e17a3-291f-4339-869f-9fc3a228a9e3.png)

Gambar 19. Rata-rata humidity terhadap label crop 2

<img width="836" alt="Submission 1 MLT - Rata rata rainfall terhadap label crop" src="https://user-images.githubusercontent.com/92978028/199249491-004c8cca-4146-4cad-8159-245bc4c2d2a6.png">

Gambar 20. Rata-rata rainfall terhadap label crop

![Submission 1 MLT - Rata rata rainfall terhadap label crop 2](https://user-images.githubusercontent.com/92978028/199249537-10134326-0be1-4eae-8efe-ae2d1b700e82.png)

Gambar 21. Rata-rata rainfall terhadap label crop 2

![Submission 1 MLT - Perbandiangan tingkat temperature, humadity, dan rainfall](https://user-images.githubusercontent.com/92978028/199249559-f3441e7f-984a-4767-8ed4-423a80073d6c.png)

Gambar 22. Perbandingan temperature, humidity, rainfall terhadap label crop

  Hasil visualisasi pada gambar 16 sampai gambar 22 memberikan informasi mengenai tingkat temperature, humidity dan rainfall terhadap setiDDi manael crop. Dimana dapat dilihat bahwa terdapat beberapa label crop yang membutuhkan lahan dengan tingkat temperature, humidity dan rainfall tinggi dan beberapa label membutuhkan lahan dengan tingkat temperature, humidity dan rainfall rendah.antar Fiturasi antar Fitur Numerik**
  <br> _Correantar fiturix_ antardditunjukkanerik ditunjukan pada gambar 23 :
  
 <img width="467" alt="Submission 1antar fiturlasi antar fitur numerik" src="https://user-images.githubusercontent.com/92978028/199249595-bf6e7a58-7bf8-4d94-8446-0b597fbfc3f5.pngAntarGambar 23. antar fiturtrik antar fitur numerik
  
  Dari dari gambar 23 dapat dilihat bahwa fitur P dan K memiliki korelasi yang sedikit tinggi.

# *Data Preparation*

Berikut ini merupakan tahapan-tahapaprapemrosesanan pra-pemrosesan data :
- **Melakukan label encoding pada fitur target (label)**
  <br> Sebelum masuk ke tahap pembagian dataset, terlabih dahulu melakukan pemisahan antara variabel independen (N, P, K, temperature, humidity, ph, rainfall) sebagai data `X` dan variabel dependen (label) sebagai data `y`. Karena fitur label pada datasetnon-numerikfitur non-numerik yang berarti nilai pada fitur tersebut adalah kategorikddimasukkansebelum dimasukan ke dalam data `y` telah dilakukan proses label encoding untuk fitur tersebut.  Label encoding merupakan teknik untuk mengubah jenis data kategorikal  menjadi data numerik yang dapat dipahami model. Pada proyek ini, label encoding dilakukan dengan menggunakan modul [LabelEncoder](https://scikitlearn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html) dari scikit-learn.
  
- **Melakukan pembagian dataset**
    <br> Untuk mengetahui kinerja model ketika dihadapkan pada data yang belusebelumnya makat sebelumnya maka perlu dilakukan pembagian dataset. Pada proyek ini dataset dibagi menjadi data latih dan data uji dengan rasio 80% untuk data latih dan 20% untuk data uji. Data latih merupakan data yang akan kita latih untuk membangun model _machine learning_, sedangkan data uji merupakan data yang belum pernah dilihat oleh model dan digunakan untuk melihat kinerja atau performa dari model yang dilatih.  Pembagian dataset dilakukan dengan modul [train_test_split](https://scikit-learn.org/0.24/modules/generated/sklearn.model_selection.train_test_split.html#sklearn.model_selection.train_test_split) dari scikit-learn. Setelah melakukan pembagian dataset, didapatkan jumlah llatih, yaitu data latih yaitu 1760 sampel dan jumlah uuji, yaituda data uji yaitu 440 sampel dari total juddataset, yaituada dataset yaitu 2200 sampel.

- **Mengatasi data _outliers_ pada data latih dengan metode LOF (_Local Outlier Factor_)**
   <br> Data pencilan (outliers) merupakan nilai yang tidak normal pada dataset. Adanya data outliers ini akan membuat analisis terhadap serangkaian data menjadi bias, atau tidak mencerminkan fenomena yang sebenarnya sehingga dapat menyebabkan pada pembuatan model menjadi kurang optimal [[5](https://statisticsbyjim.com/basics/remOleh karena itu,, Oleh karena itu, untuk menangani ouliers pada proyek ini menerapkan metode Local Outlier Factor untuk mengidentifikasi outliers dan kemudian menghapusnya dari data latih. [LocalOutlierFactor](https://scikit-learn.org/0.24/modules/generated/sklearn.neighbors.LocalOutlierFactor.html#sklearn.neighbors.LocalOutlierFactor), bekerja dengan cara menganalisis nilai lokalitas yang ada pada k-tetangga terdekat, yang jaraknya digunakan untuk memperkirakan kepadatan lokal. Dengan membandingkan kepadatan lokal sampel desehinggangganya, sehinggangganya, sehingga dapat mengidentifikasi sampel yang memiliki kepadatan jauh lebih rendah daripada tetangganya. Apabrendah makaannya rendah maka ini dianggap sebagai outliers.

- **Standardisasi data pada semua fitur numerik pada dataset**
  <br> Standardisasi merupakan teknik transforumum yang paling umum digunakan dalam tahap dSStandardisasiion. Standarisasi membantu untuk membuat semua fitur numerik berada dalam skala data yang sama dan membuat fitur data menjadi bentuk yang lebih mudah diolahStandardisasiini,sstandardisasiini, standarisasi data dilakukan dengan menerapkan teknik [StandarScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html) dari library Scikitlearn. StandardScaler sstandardisasioses standarisasi fitur dengan mengurangkan mean (nilai rata-rata) kemudian membaginya dengan standar deviasi untuk menggeser distribusi.  StandardScaler menghasilkan distribusi dengan standar deviasi sama dengan 1 dan mean sama dengan 0. Sekitar 68% dari nilai akan berada di antara -1 dan 1.
  
## Modeling
Pada proyek ini, model yang dibuat merupakan kyaitustugastion_, yaitustugastion_ yaitu tugas klasifikasi dengan lebih dari dua kelas atau banyak kelas yang mana menggunakan parameter unsur temperature, humidity, rainfall, rasio nitrogen, fosfor, kalium, nilai ph tanah terhadap beberapa label crop yang cocok untuk tumbuh di lahan pertanian tersebut. Parameter tersebut akan dipakai pada setiap model algoritmanya. Proses modeling dalam proyek ini menggunakan 3 alllearning_, yaitue learning_ yaitu `K-Nearest Neighbor`, `Random Forest` dan `XGBoost Algorithm` kemudian membandingkan performanya.

- **K-Nearest Neighbor**
  <br> Pada tahap ini pembuatan model dilakukan dengan menggunakan modul [KNeighborsClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html) dari library Scikitlearn denKKemudian,i k = 1. Kemudian proses selanjutnya melakukan prediksi menggunakan data uji dan melakukan pengujian. Hasil pengujian dari model dengan algoritma K-Nearest Neighbor dapat dilihat pada tabel 2 berikut :
  <p>Classification Report</p>

Tabel 2. Classification report k-nearest neighbor

|index|precision|recall|f1-score|support|
|---|---|---|---|---|
|rice|1\.0|1\.0|1\.0|18\.0|
|maize|1\.0|1\.0|1\.0|18\.0|
|chickpea|1\.0|1\.0|1\.0|22\.0|
|kidneybeans|1\.0|1\.0|1\.0|23\.0|
|pigeonpeas|1\.0|1\.0|1\.0|15\.0|
|mothbeans|1\.0|1\.0|1\.0|17\.0|
|mungbean|1\.0|1\.0|1\.0|16\.0|
|blackgram|1\.0|1\.0|1\.0|18\.0|
|lentil|0\.9047619047619048|0\.9047619047619048|0\.9047619047619048|21\.0|
|pomegranate|0\.9523809523809523|1\.0|0\.975609756097561|20\.0|
|banana|0\.9444444444444444|1\.0|0\.9714285714285714|17\.0|
|mango|1\.0|1\.0|1\.0|18\.0|
|grapes|1\.0|1\.0|1\.0|21\.0|
|watermelon|1\.0|0\.96|0\.9795918367346939|25\.0|
|muskmelon|1\.0|1\.0|1\.0|17\.0|
|apple|1\.0|1\.0|1\.0|23\.0|
|orange|1\.0|1\.0|1\.0|23\.0|
|papaya|1\.0|1\.0|1\.0|21\.0|
|coconut|1\.0|0\.9545454545454546|0\.9767441860465117|22\.0|
|cotton|1\.0|1\.0|1\.0|23\.0|
|jute|0\.92|0\.92|0\.92|25\.0|
|coffee|1\.0|1\.0|1\.0|17\.0|
|accuracy|0\.9863636363636363|0\.9863636363636363|0\.9863636363636363|0\.9863636363636363|
|macro avg|0\.9873448773448774|0\.9881503345139709|0\.987642557048602|440\.0|
|weighted avg|0\.9865981240981241|0\.9863636363636363|0\.9863742019264262|440\.0|
  
  Berdasarkan hasdditunjukkanan yang ditunjukan oleh tabel 2 dapat dilihat bahwa model dengan algoritma K-Nearest Neighboraakurasi, yaituilai akurasi yaitu sebesar 0.986364.

- **XGBoost Algorithm**
  <br> Pada tahap ini pembuatan model dilakukan dengan menggunakan modul [XGBClassifier](https://xgboost.readthedocs.io/en/latest/python/python_api.html) dariKKemudian, xgboost. Kemudian proses selanjutnya melakukan prediksi menggunakan data uji dan melakukan pengujian. Hasil pengujian dari model dengan XGBoost Algorithm dapat dilihat pada tabel 3 :
  <p>Classification Report</p>

Tabel 3. Classification report XGBoost Algorithm

|index|precision|recall|f1-score|support|
|---|---|---|---|---|
|rice|1\.0|1\.0|1\.0|18\.0|
|maize|1\.0|1\.0|1\.0|18\.0|
|chickpea|1\.0|1\.0|1\.0|22\.0|
|kidneybeans|1\.0|1\.0|1\.0|23\.0|
|pigeonpeas|1\.0|1\.0|1\.0|15\.0|
|mothbeans|1\.0|1\.0|1\.0|17\.0|
|mungbean|1\.0|1\.0|1\.0|16\.0|
|blackgram|1\.0|1\.0|1\.0|18\.0|
|lentil|0\.9545454545454546|1\.0|0\.9767441860465117|21\.0|
|pomegranate|1\.0|1\.0|1\.0|20\.0|
|banana|1\.0|0\.9411764705882353|0\.9696969696969697|17\.0|
|mango|1\.0|1\.0|1\.0|18\.0|
|grapes|1\.0|1\.0|1\.0|21\.0|
|watermelon|0\.9615384615384616|1\.0|0\.9803921568627451|25\.0|
|muskmelon|1\.0|1\.0|1\.0|17\.0|
|apple|1\.0|1\.0|1\.0|23\.0|
|orange|1\.0|1\.0|1\.0|23\.0|
|papaya|1\.0|0\.9523809523809523|0\.975609756097561|21\.0|
|coconut|1\.0|1\.0|1\.0|22\.0|
|cotton|1\.0|1\.0|1\.0|23\.0|
|jute|1\.0|1\.0|1\.0|25\.0|
|coffee|1\.0|1\.0|1\.0|17\.0|
|accuracy|0\.9954545454545455|0\.9954545454545455|0\.9954545454545455|0\.9954545454545455|
|macro avg|0\.996185632549269|0\.995161701044054|0\.9955655940319904|440\.0|
|weighted avg|0\.9956452638270821|0\.9954545454545455|0\.9954411027078242|440\.0|

Berdasarkan hasil pengujian yang ditujukan oleh tabel 3 dapat dilihat bahwa model dengan algoritma XGBoostaakurasi, yaituilai akurasi yaitu sebesar 0.995455.

- **Random Forest**
  <br> Pada tahap ini pembuatan model dilakukan dengan menggunakan modul [RandomForestClassifier](https://scikitlearn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html) dari libKKemudian,kitlearn. Kemudian proses selanjutnya melakukan prediksi menggunakan data uji dan melakukan pengujian. Hasil pengujian dari model dengan algoritma Random Forest dapat dilihat pada tabel 4 :
  <p>Classification Report</p>

Tabel 4. Classification report random forest

|index|precision|recall|f1-score|support|
|---|---|---|---|---|
|rice|1\.0|1\.0|1\.0|18\.0|
|maize|1\.0|1\.0|1\.0|18\.0|
|chickpea|1\.0|1\.0|1\.0|22\.0|
|kidneybeans|1\.0|1\.0|1\.0|23\.0|
|pigeonpeas|1\.0|1\.0|1\.0|15\.0|
|mothbeans|1\.0|1\.0|1\.0|17\.0|
|mungbean|1\.0|1\.0|1\.0|16\.0|
|blackgram|1\.0|1\.0|1\.0|18\.0|
|lentil|0\.9545454545454546|1\.0|0\.9767441860465117|21\.0|
|pomegranate|1\.0|1\.0|1\.0|20\.0|
|banana|1\.0|1\.0|1\.0|17\.0|
|mango|1\.0|1\.0|1\.0|18\.0|
|grapes|1\.0|1\.0|1\.0|21\.0|
|watermelon|1\.0|1\.0|1\.0|25\.0|
|muskmelon|1\.0|1\.0|1\.0|17\.0|
|apple|1\.0|1\.0|1\.0|23\.0|
|orange|1\.0|1\.0|1\.0|23\.0|
|papaya|1\.0|1\.0|1\.0|21\.0|
|coconut|1\.0|1\.0|1\.0|22\.0|
|cotton|1\.0|1\.0|1\.0|23\.0|
|jute|1\.0|0\.96|0\.9795918367346939|25\.0|
|coffee|1\.0|1\.0|1\.0|17\.0|
|accuracy|0\.9977272727272727|0\.9977272727272727|0\.9977272727272727|0\.9977272727272727|
|macro avg|0\.9979338842975206|0\.9981818181818182|0\.998015273762782|440\.0|
|weighted avg|0\.9978305785123968|0\.9977272727272727|0\.9977305086939638|440\.0|

Berdasarkan hasdditunjukkanan yang ditunjukan oleh tabel 4 dapat dilihat bahwa model dengan algoritma Random Forestaakurasi, yaituilai akurasi yaitu sebesar 0.997727.

# *Evaluation*

Pada proyek ini, model yang dibuat merupakan kasus _multiclass classification_ dan metrik evaluasi yang digunakan untukmmodel, yaituinerja model yaitu menggunakan metrik **akurasi, precision dan recall**. Pada klasifikasi dengan jumlah keluaran kelas ya(multi-class),dua (multi-class), cara menghitung akurasi, presisi dan recall dapat dilakukan dengan menghitung rata-rata dari nilai akurasi, presisi dan recall pada setiap kelas. Berikut merupakan formula untuk menghitung nilai akurasi, presisi dan recall dari smulti-classfikasi multi-class (bersumber dari [[6](https://achmatim.net/2017/03/19/mengukur-kinerja-algoritma-klasifikasi-dengan-confusion-matrix/)]) :

- Akurasi
  <br> Akurasi merupakan perbandingan antara data yang terklasifikasi benar dengan keseluruhan data. Nilai akurasi dapat diperoleh dengan persamaan berikut :
  
$$ \Large Akurasi = \frac{\sum\limits_{i=1}^{l} \frac{TP_i+TN_i}{TP_i+TN_i+FP_i+FN_i}}{l} * 100%$$

- Precision
  <br> Precision menggambarkan jumlah data kategori positif yang diklasifikasikan secara benar dibagi dengan total data yang diklasifikasi positif. Precision dapat diperoleh dengan persamaan berikut :
  
$$ \Large Presisi = \frac{\sum\limits_{i=1}^{l}TP_i}{\sum\limits_{i=1}^{l}(FP_i+TP_i)} * 100%$$

- Recall
  <br> Sementara itu, recall menunjukkan berapa persen data kategori positif yang terklasifikasikan dengan benar oleh sistem. Recall dapat diperoleh dengan persamaan berikut :
  
$$ \Large Recall = \frac{\sum\limits_{i=1}^{l}TP_i}{\sum\limits_{i=1}^{l}(TP_i+FN_i)} * 100%$$

Pada proyek ini, menghitung nilai akurasi, precsion dan recall dilakukan dengan menggunakan modul [accuracy_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html), [precision_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_score.html), [recall_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.recall_score.html) dari library Scikitlearn dan menambahkan parameter average = 'macro'.

Pada tabel 5 merupakan hasil pantar Model performa antar Model yang meliputi accuracy, precision, dan recal :

Tabel 5. Pantar model

|index|Accuracyodel

|index|Accuracy \(%\)|Precision \(%\)|Recall \(%\)|
|---|---|---|---|
|K-Nearest Neighbor|98\.64|98\.73|98\.82|
|XGBoost|99\.55|99\.62|99\.52|
|Random Forest|99\.77|99\.79|99\.82|

Dari tabel 5 dapat memberikan informasi bahwa ketiga model yang dibangun memiliki nilai DDi manai di atas 98%. Dimana dapat dilihat juga bahwa model dengan algoritma Random Forest memiliki performa (nilai akurasi, precision, dan recall) yang lebih baik dari model dengan algoritma K-Nearest Neighbor dan XGBoost. 

Pada Gambar 24 sampai gambar 26 menujukan confusion matrik pada setiap algoritmanya :

- **Algoritma K-NN**

Confusion Matrix <br>

<img width="590" alt="Submission 1 MLT - Confusion Matrix KNN" src="https://user-images.githubusercontent.com/92978028/199251458-29f467a9-e2f4-49b7-a0cd-b1ce770579c0.png">

Gambar 24. Confusion matrix k-nearest neighbor

- **Algoritma XGBoost**

 Confusion Matrix <br>

<img width="592" alt="Submission 1 MLT - Confusion Matrix XGB" src="https://user-images.githubusercontent.com/92978028/199251525-e2b6c35b-0f0c-468c-8a5e-d31155a502ab.png">

Gambar 25. Confusion matrix XGBoost Algorithm

- **Algoritma Random Forest**

 Confusion Matrix <br>

<img width="590" alt="Submission 1 MLT - Confusion Matrix Random Forest" src="https://user-images.githubusercontent.com/92978028/199251576-a5f33824-9fd1-428e-988a-3cd34f389a42.png">

Gambar 26. Confusion matric random forest

# *Conclusion*

Dadi atasyek penelitian diatas dapat diambil kesimpulan bahwa dari dataset yang dipakai/ data lahan yang dipakai dalam pembuatan model dapat digunakan dengan baik di 3 algoritma yang dipakai pada proyek penelitian kali ini. Dan dari hasil perbandindipakai, yaknima yang dipakai yakni K-Nearst Neighbor, algoritma XRBoost, dan algoritma Random Forest mendapatkan hasil accuracy, prdi atason, dan recall diatas 98%, namun dari ketiga algoritma yang digunaka nilai tertinggi accuracy, precission, dan recall didapatkan oleh algoritma Random Forest dengan rata-rata nilai 99,79%.

# Daftar Pustaka
[1] 	A. Raj, "Introduction to Classification Using K Nearest Neighbours," 8 April 2021.<br>
[2] 	O. Harrison, "Machine Learning Basics with the K-Nearest Neighbors Algorithm," 11 September 2018.<br>
[3] 	V. Morde, "XGBoost Algorithm: Long May She Reign!," 8 April 2019.<br>
[4] 	Wikipedia, "Random Forest," Wikipedia ensiklopedia bebas, 23 September 23. [Online]. Available: https://id.wikipedia.org/wiki/Random_forest. [Accessed 2 November 2022].<br>
[5] 	Prasetyo, Data Mining: Konsep dan Aplikasi menggunakan Matlab, Yogyakarta: Andi Offset, 2021.<br>
[6] 	L. Sokolova, "A systematic analysis of performance measures for classification tasks," Inf. Process. Manag., vol.45, no. 4, pp. 427-437, 2009.<br>

