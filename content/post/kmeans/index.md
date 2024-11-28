---
title: Pemetaan Kemiskinan di Jawa Tengah dengan Algoritma K-Means
summary:
date: 2021-11-03

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: "Image credit: [**Freepik**](https://www.freepik.com)"

authors:
  - admin

tags:
  - clustering
  - K-Means
  - R
---

Klastering adalah metode analisis data yang populer dan memainkan peran penting dalam data mining. Klastering merupakan sebuah teknik unsupervised learning karena tidak adanya target label dalam prosesnya, yang bertujuan untuk mengelompokkan data ke dalam beberapa kelompok atau klaster sehingga data dalam satu kelompok memiliki tingkat kemiripan yang maksimum dan data antar kelompok memiliki tingkat kemiripan yang minimum.

## Algoritma K-Means

Menurut Han dan Kamber (Han, Kamber, and Pei 2012)terdapat banyak algoritma klastering, tetapi secara umum metode-metode utama dalam analisis klaster dapat dikelompokkan berdasarkan metode partisi, metode hirarki, metode berbasis densitas dan metode berbasis grid. Metode klastering yang paling populer adalah metode hirarki dan metode partisi (A. T. de Carvalho, Lechevallier, and Melo 2012). Metode Hirarki mengelompokkan data menjadi seperti struktur pohon (Krishnasamy, Kulkarni, and Paramesran 2014) dengan cara membuat dekomposisi atau pemecahan objek secara hirarki dengan memisahkan data menjadi subset yang lebih kecil. Metode ini dapat diklasifikasikan menjadi dua, yaitu metode agglomerative dan metode devisive. Metode agglomerative atau disebut juga dengan pendekatan bottom-up, dimulai dengan setiap titik data membentuk kelompok atau klaster yang terpisah. Kemudian secara berturut-turut menggabungkan data yang mempunyai kemiripan hingga semua data berada dalam klaster yang sama. Sedangkan metode devisive atau disebut juga dengan pendekatan top-down, dimana proses pengelompokkan dimulai dengan semua titik data berada dalam satu klaster, kemudian membagi klaster ke dalam klaster yang lebih kecil. Kelebihan metode hirarki adalah tidak membutuhkan informasi jumlah klaster dan juga penentuan nilai-nilai awal sehingga hasil klastering selalu sama , namum membutuhkan waktu komputasi tinggi pada dataset yang besar daripada metode partisi.

K-means merupakan salah satu metode hard partition yang banyak digunakan untuk pengelompokan data. Algoritma K-means adalah dasar pengelompokan metode partisi yang dipublikasikan oleh Lloyd dari Bell Telephone Laboratories pada tahun 1957. Penelitian pada K-means dapat ditelusuri kembali ke pertengahan abad yang lalu, yang dilakukan oleh berbagai peneliti diseluruh disiplin ilmu yang berbeda terutama oleh Lloyd (1957), Forgey (1965), Friedman dan Robin (1967) dan MacQueen (1967). K-means dapat didefinisikan sebagai algoritma klastering yang mengelompokan data ke dalam k klaster berdasarkan jarak terdekat data dengan pusat klaster. Algoritma K-means sangat efisien untuk mengelompokan dataset yang besar, kemudahan dalam pengaplikasiannya dan metode yang efisien dalam hal komputasi, menjadi alasan utama popularitas K-means, meskipun telah diusulkan lebih dari 50 tahun yang lalu.

Algoritma K-means mengelompokan objek ke dalam kelompok sehingga objek dalam satu klaster memiliki kemiripan yang tinggi dibandingkan dengan objek di dalam klaster yang berbeda. K-means dimulai dengan menentukan jumlah klaster sebanyak k, kemudian membangkitkan k pusat klaster secara acak. Selanjutnya setiap objek akan dikelompokan berdasarkan jarak terdekat dengan pusat klaster, pusat klaster diperbaharui berdasarkan titik data dalam setiap klaster. Proses ini diulangi sampai kriteria konvergen terpenuhi. Berikut ini adalah tahapan dari algoritma K-means:

1. Menentukan nilai k sebagai jumlah klaster yang dibentuk.
2. Memilih k pusat klaster secara acak untuk menjadi pusat klaster awal.
3. Alokasikan semua data ke pusat klaster terdekat dengan matrik jarak.
4. Hitung kembali pusat klaster baru berdasarkan data yang mengikuti klaster masing-masing.
5. Ulangi langkah 3 dan 4 hingga kondisi konvergen tercapai atau tidak ada data yang berpindah dari satu klaster ke klaster yang lainnya.

## Eksperimen Algoritma K-Means

Pada eksprimen ini algoritma K-Means akan digunakan untuk mengelompokan data kemiskinan di Jawa Tengah yang diambil dari website Tim Percepatan Penanggulangan Kemiskinan [TNP2K](https://www.tnp2k.go.id/)

### Read Data
