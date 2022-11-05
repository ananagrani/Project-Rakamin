# Missing Value
Berikut adalah strategi kita mengatasi missing values pada setiap kolom.
* `children` : impute dengan nilai modus (0)
* `country` : impute dengan nilai modus (PRT)
* `agent` & `company` : missing value diganti menjadi 0 agar bisa dimaksimalkan saat feature engineering

# Duplicated Data
Tidak ada duplicated data didalam dataset ini

# Outlier
Outlier tidak di-handle karena akan fokus menggunakan model yang robust terhadap outlier

# Feature Transformation
Karena semua kolom mengalami skew kanan jadi kami mengubah distribusi nya ke distribusi normal dengan cara log transformation

# Feature Extraction
Kami membuat 5 fitur tambahan yaitu :
1. Country_type, fitur ini berasal dari kolom `country`. Apabila country menunjukkan PRT, di fitur country_type akan menjadi local dan country yang tidak menunjukkan PRT akan menjadi international.
2. Match_reserved_room_type, fitur ini berasal dari kolom `reserved_room_type` dan `assigned_room_type`. Apabila `reserved_room_type` sama dengan `assigned_room_type`, maka hasilnya akan 1 yang berarti room nya match dengan apa yang user book/reserve, dan begitupun sebaliknya. 
3. Book_type, fitur ini berasal dari `agent` dan `company`. Apabila `agent` atau `company` bernilai > 0 maka book_type akan menjadi ‘third_party’, tetapi apabila `agent` atau `company` bernilai = 0 book_type akan menjadi ‘self-booking’. 
4. Total_guest, fitur ini merupakan gabungan dari kolom `adults`, `childs`, dan `babies`. Fitur ini akan mempersingkat atau menyederhanakan dataset dengan menggabungkan `adults`, `childs`, dan `babies` menjadi total_guest
5. Total_stay, fitur ini merupakan gabungan dari kolom `stays_in_weekend_nights`, dan  `stays_in_week_nights`. Fitur ini akan mempersingkat atau menyederhanakan dataset dengan menggabungkan `stays_in_weekend_nights`, dan  `stays_in_week_nights` menjadi total_stay.

# Feature Encoding
Dalam tahap Feature Encoding, kami memilih one hots sebagai solusi, kolom `hotel`,  `meal`, `deposit_type`, `customer_type`, `market_segment`, `distribution_channel`, `book_type`, `match_reserved_room_type`, `country_type` menjadi target feature encoding kami. Sebelum melakukan feature encoding terdapat 35 kolom, setelah melakukan feature encoding menjadi 74 kolom. 

# Feature Selection
Setelah melakukan feature extraction dan feature encoding, kami memutuskan untuk menghapus 24 Kolom, yaitu :
1. Name : kolom berisi biodata yang mempunyai unique values yang sangat tinggi, sehingga tidak dapat membuat suatu pola atau ditarik kesimpulan
2. Email : kolom berisi biodata yang mempunyai unique values yang sangat tinggi, sehingga tidak dapat membuat suatu pola atau ditarik kesimpulan
3. Phone Number : kolom berisi biodata yang mempunyai unique values yang sangat tinggi, sehingga tidak dapat membuat suatu pola atau ditarik kesimpulan
4. Credit Card : kolom berisi biodata yang mempunyai unique values yang sangat tinggi, sehingga tidak dapat membuat suatu pola atau ditarik kesimpulan [kolom ini berisi nomor credit card dari user bukan cara payment type dari user, sehingga tidak dapat ditarik kesimpulan]
5. Reservation Status : isi kolom reservation status mempunyai informasi yang sama dengan kolom `is_canceled` jadi kolom reservation status akan kami drop
6. Adults : setelah membuat fitur baru, kolom asli adults akan di drop
7. Babies : setelah membuat fitur baru, kolom asli babies akan di drop
8. Children : setelah membuat fitur baru, kolom asli children akan di drop
9. Country : setelah membuat fitur baru, kolom asli country akan di drop
10. Assigned Room Type : setelah membuat fitur baru, kolom asli assigned room type akan di drop
11. Reserved Room Type : setelah membuat fitur baru, kolom asli reserved room type akan di drop
12. Agent : setelah membuat fitur baru, kolom asli agent akan di drop
13. Company : setelah membuat fitur baru, kolom asli company akan di drop
14. Stays in Weekend Nights : setelah membuat fitur baru, kolom asli stays in weekend nights akan di drop
15. Stays in Week Nights : setelah membuat fitur baru, kolom asli stays in week nights akan di drop
16. Hotel : setelah dilakukan feature encoding one hots, kolom asli hotel akan di drop
17. Meal : setelah dilakukan feature encoding one hots, kolom asli meal akan di drop
18. Distribution Channel :  setelah dilakukan feature encoding one hots, kolom asli distibution channel akan di drop
19. Deposit Type : setelah dilakukan feature encoding one hots, kolom asli deposit type akan di drop
20. Customer Type : setelah dilakukan feature encoding one hots, kolom asli customer type akan di drop
21. Market Segment : setelah dilakukan feature encoding one hots, kolom asli market segment akan di drop
22. Book Type : setelah dilakukan feature encoding one hots, kolom asli book type akan di drop
23. Match Reserved Room Type : setelah dilakukan feature encoding one hots, kolom asli match reserved room type akan di drop
24. Country Type : setelah dilakukan feature encoding one hots, kolom asli country type akan di drop