## Info
Dataset yang kami pilih adalah dataset Hotel Booking Cancellation. Dataset ini terdiri atas 119.390 baris dan 36 kolom.

Terdapat 4 kolom yang memiliki missing value atau nilai kosong yaitu :
1. `Children` : 4 baris atau 0.003%
2. `Country` : 488 baris atau  0.409%
3. `Agent` : 16.340 baris atau  13.686 %
4. `Company` : 112.593 baris atau 94.307%

Terdapat sedikit keanehan dari summary statistics dataset Hotel Booking, yaitu :
1. Nilai minimal `adult` 0, tidak mungkin babies/children check in sendiri tanpa adanya orang yang lebih dewasa
2. Nilai minimal `adr` negatif

## Univariate Analysis

Untuk univariate analysis, kami menggunakan boxplot dan distribution plot. Dari kedua plot tersebut, kami dapat mengambil beberapa insight, yaitu :
1. Boxplot, Semua kolom kecuali kolom `agent` dan `company` memiliki outlier maka akan dilakukan proses penghapusan outlier
2. Distribution plot, Semua kolom bernilai negatif skewed, maka perlu dilakukan normalisasi agar distribusinya menjadi normal

## Multivariate Analysis

Untuk multivariate analysis, kami menggunakan correlation heatmap dan category plot, kami mendapatkan beberapa insight, yaitu :
1. Semua data relevan, sehingga tidak ada data yang di drop kecuali kolom yang membuat multicollinearity
2. Kolom `stays_in_week_nights` dan `stays_in_weekend-nights` yang memiliki nilai korelasi 0,5 yang menyebabkan multicollinearity, sehingga salah satu dari kolom akan di drop
3. Kolom `arrival_date_year` dan `arrival_date_week_number` yang memiliki nilai korelasi -0,54 yang menyebabkan multicollinearity, sehingga salah satu dari kolom akan di drop
4. Kolom `is_canceled` punya korelasi yang kuat dengan kolom `lead_time`
