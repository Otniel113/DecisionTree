# DecisionTree
Memprediksi apakah pelanggan pada dealer mobil tertarik untuk membeli mobil baru atau tidak

# Dataset
Dataset didapatkan dari Telkom University berupa Ms. Excel <img src = 'https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white' /> yang sudah dipisah menjadi data train dan data test dengan ukuran masing-masing 285831x12 dan 47639x11 dengan keterangan masing-masing kolom sebagai berikut:

id --> Nomor ID<br>
Jenis_Kelamin --> Berupa Pria/Wanita<br>
SIM	--> 0 : Tidak punya SIM 1 : Punya SIM<br>
Kode_Daerah --> Kode area tempat tinggal pelanggan<br>
Sudah_Asuransi --> 1 : Pelanggan sudah memiliki asuransi kendaraan, 0 : Pelanggan belum memiliki asuransi kendaraan<br>
Umur_Kendaraan --> Umur kendaraan<br>
Kendaraan_Rusak --> 1 : Kendaraan pernah rusak sebelumnya. 0 : Kendaraan belum pernah rusak.<br>
Premi --> Jumlah premi yang harus dibayarkan per tahun.<br>
Kanal_Penjualan --> Kode kanal untuk menghubungi pelanggan (email, telpon, dll)<br>
Lama_Berlangganan	--> Sudah berapa lama pelanggan menjadi klien perusahaan<br>
Tertarik --> 1 : Pelanggan tertarik, 0 : Pelanggan tidak tertarik<br>

Perbedaan data test dengan data train adalah tidak ada kolom id pada data test

# Formulasi Masalah
Masalah yang akan diselesaikan adalah pada toko dealer mobil. Toko dealer tersebut memiliki data-data pelanggan yang mencakup ID, jenis kelamin, umur, sudah memiliki SIM atau belum, kode daerah, sudah pernah asuransi atau belum, umur kendaraan, kendaran pernah rusak atau tidak, premi, kanal penjualan, lama berlangganan dan tertarik atau tidak.<br><br>
Untuk itu, dilakukan prediksi untuk mengetahui pelanggan pada dealer mobil tersebut tertarik untuk membeli mobil baru atau tidak berdasarkan data-data pelanggan yang dimiliki oleh toko dealer mobil. Untuk itu dibangun model klasifikasi Decision Tree yang merupakan contoh dari Supervised Learning. Data-data tersebut memiliki label kelas tertarik atau tidak yang akan diprediksi.

# Data Exploration
Melakukan eksplorasi data dengan visualisasi<br><br>
Untuk data bernilai numerikal
![Distplot](https://drive.google.com/uc?id=1632wKguwXOUQR-Guahzw-esLont2UYKp)
![Boxtplot](https://drive.google.com/uc?id=1Lo3F30KeSfBaT8WZdJD55SA3HFrAeQu-)
<br><br>
Untuk data bernilai kategorikal
![Barplot](https://drive.google.com/uc?id=1yGCZ_9TXaUfMWd_P1efNjZPYhzSwHTk8)

# Data Preprocessing
Praproses yang dilakukan
1. Categorical Encoding --> Dengan label encoding
2. Feature Selection --> Memilih 4 fitur paling relevan dengan Korelasi yaitu Umur, Sudah_Asuransi, Umur_Kendaraan, Kendaraan_Rusak <br>
![Korelasi](https://drive.google.com/uc?id=1Cyg603ZhyMa8JOHWB2fy5xq2J5hMC6vE) <br>
3. Handling Missing Value --> Drop
4. Sampling --> Undersampling

# Modeling
Menggunakan Decision Tree dari library  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" /> yang sudah didapatkan dengan parameter optimal 
```python
from sklearn import tree

pohon = tree.DecisionTreeClassifier(criterion="entropy", max_depth=9)
pohon = pohon.fit(X_train,y_train)
predik = pohon.predict(X_test)
```

# Evaluasi
Menggunakan 4 metrik evaluasi akurasi, precision, recall, dan f1 score dengan nilais sebagai berikut:
| Metrik | Nilai |
| -- | -- |
| Akurasi | 80.1% |
| Precision | 33.1% | 
| Recall | 60.2% |
| F1 Score | 42.7% |
<br>
Atau bisa juga dilihat dengan Confusion Matrix sebagai berikut: <br>

![ConfusionMatrix](https://drive.google.com/uc?id=1PwGSAirwKzEirNtyOE4M_uuRJx1wF7u7)

# Lebih lengkap
Untuk informasi lebih langkap ada di laporan pada file [Laporan_DT.pdf](https://github.com/Otniel113/DecisionTree/files/7811960/Laporan_DT.pdf) dan slide presentasi di [PPT_DT.pptx](https://github.com/Otniel113/DecisionTree/files/7811964/PPT_DT.pptx)

# Video Presentasi
Video presentasi dapat dilihat dibawah (dengan klik gambar) <br>

[![video](https://img.youtube.com/vi/skGCBnNzlwM/0.jpg)](https://youtu.be/skGCBnNzlwM)
