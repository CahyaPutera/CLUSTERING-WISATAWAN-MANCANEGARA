# CLUSTERING-WISATAWAN-MANCANEGARA (WISMAN)

Tugas IYKRA Data MBA, Unsupervised Learning - Clustering. Menggunakan data Jakarta Open Data Jumlah Kunjungan Wisatawan Mancanegara.

Sumber Dataset : https://data.jakarta.go.id/dataset/data-jumlah-kunjungan-wisman-ke-indonesia-berdasarkan-pintu-masuk-di-dki-jakarta

Referensi : Buku Fundamental of Machine Learning with Python (by Teguh Wahyono)

Curated by : B. Ari Kuncoro (IYKRA)

## LATAR BELAKANG

Pemerintah Indonesia ingin mengetahui prioritas pembangunan dan penempatan tenaga kerja di bidang pariwisata. 
Untuk itu, mereka ingin mengelompokkan gerbang pintu masuk wisatawan mancanegara berdasarkan jumlah wisman yang berkunjung ke Indonesia.

## SUMMARY 

Untuk mempermudah proses clustering, maka dibuat columns baru yaitu **SUM_SMT1** yang merupakan kolom representasi penjumlahan pengunjung wisman pada semester 1, yaitu dari bulan Januari sampai Juni. 
Dan **SUM_SMT2**, representasi dari penjumlahan pengunjung wisman pada semester 2, yaitu dari bulan Juli sampai Desember.

Menggunakan metode **K-Means Clustering** kita dapat mengetahui bahwa terdapat 3 cluster dari gerbang pintu masuk wisatawan mancanegara berdasarkan jumlah wisman yang berkunjung ke Indonesia. 
**Cluster 0** merupakan cluster dengan jumlah pintu masuk yang cukup banyak, namun memiliki pengunjung wisman yang relatif lebih sedikit di bandingkan cluster yang lain, karena jika dilihat lebih detail, 
pintu - pintu yang termasuk dalam cluster ini sebagian besar berada di pelabuhan atau kota yang kemungkinan bukan menjadi alternatif dari tujuan wisman ke Indonesia. 
**Cluster 1** merupakan pintu masuk *Batam* dan bandar udara *Soekarno-Hatta*, yang jika kita perhatikan walaupun cluster ini berisi 2 pintu ini saja, 
tetapi cluster ini memiliki pengunjung wisman yang cukup jauh di bandingkan pintu - pintu pada cluster sebelumnya, dengan total sekitar 3,7 juta kunjungan wisman pada data tahun 2014 ini. 
Sedangkan **Cluster 2** berisi pintu masuk dari bandara *Ngurah Rai* di Bali. Sudah jelas jika pintu ini adalah pintu yang mungkin merupakan **pintu gerbang utama** bagi wisman dalam berkunjung ke Indonesia, 
mungkin karena memang Bali sudah terkenal di seluruh dunia. Insight lebih lanjut lagi dapat kita lihat bahwa kunjungan wisman memang banyak di lakukan pada semester ke 2, yaitu pada bulan Juli sampai Desember, 
dengan jumlah selisih lebih dari 300 ribu kunjungan total pada semester 2. 

Melihat hasil yang di lakukan dengan menggunakan metode **Hierarchical Clustering** / **Agglomerative Clustering** ini. 
Kita dapat menyimpulkan insight yang kurang lebih mirip dengan metode **K-Means Clustering** sebelumnya, hanya bedanya pintu masuk *Ngurah Rai* dijadikan satu cluster dengan *Soekarno-Hatta* dan *Batam*.

## MODEL EVALUATION

Indeks validitas **Davies-Bouldin (DB)** menghitung rata-rata nilai setiap titik pada himpunan data. 
Perhitungan nilai setiap titik adalah jumlah nilai compactness yang dibagi dengan jarak antara kedua titik pusat klaster sebagai separation. 
Jumlah cluster terbaik ditunjukkan dengan nilai DB yang semakin kecil.  

**K-MEANS Davies Bouldin Score : 0.26033204614213545**

**HIERARCHICAL Davies Bouldin Score : 0.4033364447327529**

Melihat hasil DB Index, dalam hal ini metode K-Means Clustering lebih baik jika di bandingkan dengan metode Hierarchical / Agglomerative Clustering.
Artinya melalui **K-Means Clustering** dapat di simpulkan bahwa terdapat 3 cluster, yaitu *cluster 0, cluster 1, dan cluster2*. 
Sebagian besar wisatawan yang berkunjung ke Indonesia melewati pintu masuk dari bandara *Ngurah Rai* di Bali. 

Sehingga jika menjawab pertanyaan pada Latar Belakang masalah, sebaiknya prioritas pembangunan dan penempatan tenaga kerja di bidang pariwisata di fokuskan pada daerah Bali dan sekitarnya. 
Namun agak sulit untuk mengatakan bahwa cluster lainnya sebaiknya diabaikan, terlebih pada cluster 0. 
Karena memang sebagian besar kota kunjungan wisman pada cluster 0 ini bukan merupakan daerah pariwisata yang terkenal,
atau ada juga pada cluster ini yang merupakan kota kecil yang belum banyak di ketahui yang mungkin dapat menjadi pertimbangan dalam pembangunan untuk meningkatkan nilai jual pariwisata pada daerah sekitar cluster ini.
