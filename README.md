# Clustering Untuk Data Numerik & Kategorik

Projek ini merupakan project kedua saya sebagai salah satu tim product di Algoritma Data Science Academy. Pada project ini saya melakukan clustering untuk data numerik dan data kategorik.

Link publikasi: https://rpubs.com/VicNP/clust-num-cat

## Tujuan Pembuatan

Tujuan pembuatan projek ini adalah untuk menjawab stigma yang melekat pada clustering yaitu hanya bisa digunakan untuk data-data numerik. Hal tersebut terjadi karena banyak sekali implementasi atau contoh dari clustering yang hanya menggunakan data numerik. Padahal clustering juga bisa digunakan terhadap data-data kategorikal, dan pada kesempatan kali ini kita akan mencoba menggunakan clustering untuk mengelompokan data kategorikal dan data numerik. 

## Input Variable

Projek ini menggunakan sumber data dari [kaggle](https://www.kaggle.com/datasets/shivam2503/diamonds).

| Variable             	| Detail                                                                           	|
|----------------------	|----------------------------------------------------------------------------------	|
| carat | Berat dari berliannya |
| cut | Kualitas dari potongan berliannya (Fair < Good < Very Good < Premium < Ideal) |
| color | Kualitas warna dari berlian tersebut (J < I < H < G < F < E < D) |
| clarity | Seberapa jernih berlian tersebut (I1 < SI2 < SI1 < VS2 < VS1 < VVS2 < VVS1 < IF) |
| depth | Persentase dari kedalaman berlian tersebut |
| table | Lebar maksimal dari atas berlian |
| x | Panjang dalam mm |
| y | Lebar dalam mm |
| z | Tinggi dalam mm |

## Machine Learning Model

Tipe algoritma yang akan kita gunakan nantinya bernama Partitioning Around Medoids dan metode perhitungan jarak yang akan digunakan adalah Gower Distance.

### PAM

Algoritma Partitioning Around Medoids(PAM) atau bisa disebut K-Medoids adalah sebuah metode pengelompokan non-hierarki yang masih menjadi keluarga dekat dari metode K-Means. Metode PAM atau K-Medoids ini akan mengelompokan sekumpulan n objek menjadi ke beberapa k cluster. Jika metode pengelompokannya seperti itu, apa bedanya dengan metode K-Means kalau begitu? Perbedaanya terdapat pada bagaimana melakukan pengelompokannya.

Pada metode K-Means, penentuan sebuah objek masuk ke sebuah cluster tertentu berdasarkan perhitungan rata-rata jarak ecluidean. Sedangkan cara kerja metode K-Medoids akan diawali dengan penentuan Medoids (sebuah objek yang letaknya terpusat di dalam suatu cluster). Dari gambar di bawah, kita dapat melihat bagaimana perbedaan antara metode K-Means & K-Medoids dalam menentukan sebuah objek lebih sesuai untuk masuk ke sebuah cluster tertentu.

![](https://github.com/VictorNugraha/clustering_for_numerical_categorical_data/blob/main/image/k-means-and-k-medoids.png)

Penentuan Medoids itu tidak dilakukan hanya sekali, melainkan berulang sampai Medoids itu tidak bisa bergerak lagi. Mengapa tidak hanya sekali, dikarenakan peletakan Medoids belum tentu posisi paling optimal. 

## Gower Distance

Pilihan paling populer untuk menghitung jarak adalah Euclidean, namun metode tersebut hanya berlaku untuk data numerik saja, oleh karena itu metode Euclidean tidak berlaku di sini. Ada satu metode yang dapat kita gunakan untuk kasus yang memiliki data campuran (data numerik dan data kategorikal), metode tersebut dinamakan Gower Distance.

Metode Gower Distance nantinya akan melakukan perbandingan pada setiap observasi data yang ada terhadap data-data yang lainnya, dengan cara melakukan perhitungan skala antara kedua observasi yang dibandingkan dengan rentan 0 sampai 1. Jika hasil dari perbandingannya mendekati 0 maka bisa dibilang kedua data tersebut identik atau jarak antara kedua observasi tersebut berdekatan, begitu juga sebaliknya, jika rentan perbandingannya mendekati 1 bisa dibilang kedua data tersebut tidak identik atau jarak antara kedua observasi tersebut berjauhan.
