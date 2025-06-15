# Submission-2-MLT

# Laporan Proyek Machine Learning - Biki Nurul Af'ida

## Project Overview

Di era digital saat ini, akses terhadap buku semakin mudah berkat berbagai platform e-book dan aplikasi pembaca buku. Namun, dengan banyaknya pilihan buku yang tersedia, sering kali pengguna merasa kesulitan dalam memilih buku yang sesuai dengan minat mereka. Hal ini menciptakan tantangan besar dalam memfasilitasi pembaca yang ingin menemukan buku yang tepat tanpa harus menghabiskan banyak waktu untuk mencarikannya.

Salah satu masalah utama yang dihadapi adalah information overload, yaitu pengguna disajikan dengan banyak pilihan buku, tetapi kesulitan untuk menemukan buku yang benar-benar sesuai dengan minat mereka. Pembaca sering kali tidak tahu buku apa yang akan mereka nikmati selanjutnya, apalagi buku yang mungkin belum mereka temui sebelumnya. Oleh karena itu, sistem rekomendasi berbasis Content-Based Filtering menjadi solusi yang efektif untuk mempersonalisasi pengalaman pengguna berdasarkan kesamaan konten dari buku yang sudah mereka baca. Dengan menggunakan metode ini, buku direkomendasikan berdasarkan kemiripan konten seperti judul, penulis, bahasa, dan penerbit dari buku yang telah dibaca oleh pengguna (Safitri, Atina, & Farida, 2022; Reswara, Evanita, & Susanto, 2021).

Metode Content-Based Filtering bekerja dengan menganalisis peubah konten buku yang telah dipilih oleh pengguna, seperti title, author, language, dan publisher, kemudian memberikan rekomendasi berdasarkan kesamaan dari buku yang sudah dibaca. Dengan menggunakan algoritma seperti TF-IDF dan Cosine Similarity, sistem ini dapat menghitung kesamaan antar buku berdasarkan peubah-peubah tersebut, memberikan rekomendasi yang lebih personal dan relevan bagi pengguna (Safitri, Atina, & Farida, 2022; Reswara, Evanita, & Susanto, 2021).

Proyek ini menggunakan dataset Goodreads Books yang tersedia di platform Kaggle (https://www.kaggle.com/datasets/jealousleopard/goodreadsbooks/data). Dataset ini mencakup berbagai informasi tentang buku, seperti judul, penulis, penerbit, dan bahasa. Dengan dataset ini, sistem rekomendasi dapat memberikan saran buku yang lebih akurat sesuai dengan preferensi pengguna. Diharapkan bahwa sistem rekomendasi ini dapat memperkaya pengalaman membaca dan mengurangi waktu yang dibutuhkan untuk memilih buku yang tepat, serta membantu pengguna menemukan buku yang relevan dengan minat mereka lebih efisien.

## Business Understanding

### Problem Statements

Di dunia digital yang serba cepat dan penuh dengan informasi, terutama di platform literasi seperti Goodreads, pengguna sering kali merasa kewalahan dengan banyaknya pilihan buku yang tersedia. Hal ini menciptakan tantangan besar, di mana pengguna kesulitan untuk menemukan buku yang sesuai dengan minat dan kebutuhan mereka, yang dikenal dengan istilah information overload.

Dalam konteks ini, sistem rekomendasi buku menjadi sangat penting untuk memecahkan masalah tersebut. Sistem ini bertujuan untuk mengurangi kebingungannya dengan menyediakan saran yang relevan berdasarkan minat dan preferensi pengguna, berdasarkan informasi yang ada tentang buku yang mereka baca sebelumnya.

Beberapa masalah utama yang dihadapi oleh pengguna adalah sebagai berikut:

- Kesulitan dalam memilih buku yang sesuai dengan preferensi pribadi: Pengguna sering kali merasa kebingungan dalam memilih buku karena banyaknya pilihan yang tersedia, namun tanpa sistem yang dapat membantu mereka menemukan buku yang tepat.
- Kurangnya personalisasi dalam rekomendasi buku: Banyak sistem yang memberikan rekomendasi secara umum tanpa memperhatikan selera pribadi pengguna, yang mengarah pada saran buku yang kurang relevan.
- Kurangnya keterlibatan pengguna: Pengguna cenderung tidak kembali ke platform jika mereka merasa rekomendasi yang diberikan tidak sesuai dengan kebutuhan atau minat mereka, yang berisiko mengurangi loyalitas dan penggunaan layanan lebih lanjut.

### Goals

Proyek ini bertujuan untuk mengembangkan sistem rekomendasi buku yang dapat memberikan rekomendasi yang personal dan relevan bagi pengguna, dengan menggunakan Content-Based Filtering. Tujuan utama proyek ini adalah:

- Meningkatkan Pengalaman Pengguna: Memberikan pengalaman yang lebih personal dengan menyarankan buku yang sesuai dengan preferensi pengguna berdasarkan buku yang pernah mereka baca sebelumnya.
- Mengurangi Information Overload bagi Pengguna: Dengan hanya menampilkan buku yang memiliki kemiripan tinggi dengan buku yang sudah dibaca pengguna, sistem ini dapat meminimalkan kebingungannya dalam memilih buku.
- Meningkatkan Keterlibatan Pengguna: Sistem ini bertujuan untuk meningkatkan interaksi pengguna dengan platform dengan memberikan rekomendasi yang lebih relevan dan menarik.
- Meningkatkan Retensi Pengguna: Dengan rekomendasi yang lebih sesuai dengan keinginan dan preferensi pengguna, diharapkan pengguna akan lebih sering kembali menggunakan platform dan lebih loyal.

    ### Solution statements

    Untuk mencapai tujuan tersebut, pendekatan yang digunakan dalam proyek ini adalah Content-Based Filtering. Sistem rekomendasi ini akan memberikan saran buku berdasarkan kemiripan konten, dengan memperhitungkan beberapa peubah buku seperti judul, penulis, bahasa, dan penerbit.

    1. Penerapan Content-Based Filtering:
        - Data buku akan dianalisis berdasarkan kemiripan peubah-peubah seperti judul, penulis, dan penerbit.
        - Teknik TF-IDF (Term Frequency-Inverse Document Frequency) akan digunakan untuk menghasilkan vektor peubah, yang menggambarkan representasi numerik dari setiap buku berdasarkan frekuensi kata-kata yang ada pada judul, penulis, dan penerbit. Ini akan menghasilkan representasi fitur buku dalam ruang vektor berdimensi tinggi.

    2. Rekomendasi Berdasarkan Kemiripan:
        - Setelah proses TF-IDF menghasilkan vektor untuk setiap buku, Cosine Similarity akan digunakan untuk menghitung kemiripan antara buku yang telah dibaca oleh pengguna dan buku lainnya di dalam dataset.
        - Buku yang memiliki skor kemiripan tinggi dengan buku yang sudah dibaca oleh pengguna akan diprioritaskan untuk direkomendasikan sebagai bacaan berikutnya.

    3. Proses Alur Rekomendasi:
        - Pengguna memasukkan preferensi atau memilih buku yang sudah dibaca.
        - Data buku yang telah dibaca dianalisis menggunakan TF-IDF untuk mendapatkan vektor konten.
        - Kemudian, sistem akan menghitung Cosine Similarity antara buku yang sudah dibaca dengan buku lainnya.
        - Rekomendasi buku yang memiliki skor kemiripan tertinggi akan disarankan kepada pengguna sebagai buku berikutnya untuk dibaca.

## Data Understanding

Data yang digunakan dalam proyek ini berasal dari dataset Goodreads Books, yang tersedia di platform Kaggle (https://www.kaggle.com/datasets/jealousleopard/goodreadsbooks/data). Dataset ini mencakup berbagai informasi mengenai buku yang terdaftar di Goodreads, seperti judul, penulis, penerbit, rating, jumlah halaman, dan banyak peubah lainnya yang dapat digunakan untuk membangun sistem rekomendasi berbasis Content-Based Filtering. Dataset terdiri dari 11 kolom dengan 11.1119 baris berdasarkan output data.shape. Tidak terdapat missing values pada data.

Peubah-peubah pada dataset adalah sebagai berikut:
- title: Nama buku yang terdaftar di platform Goodreads. Peubah ini adalah data kategorikal yang menyimpan informasi tentang judul buku.
- authors: Nama penulis buku. Peubah ini juga kategorikal yang mencatat nama penulis buku.
- average_rating: Rata-rata rating buku berdasarkan penilaian pengguna di Goodreads. Peubah ini berupa data kontinu yang mencerminkan popularitas atau kualitas buku.
- isbn: Nomor ISBN buku yang digunakan untuk identifikasi unik. Ini adalah data kategorikal.
- isbn13: Nomor ISBN-13 buku, versi terbaru dari ISBN. Ini juga data kategorikal.
- language_code: Kode bahasa buku (misalnya "eng" untuk Bahasa Inggris). Ini adalah data kategorikal.
- num_pages: Jumlah halaman dalam buku. Peubah ini adalah data kontinu yang mengindikasikan panjang buku.
- ratings_count: Jumlah total rating yang diterima oleh buku. Peubah ini berupa data kontinu.
- text_reviews_count: Jumlah ulasan teks yang ditulis oleh pengguna. Peubah ini berupa data kontinu.
- publication_date: Tanggal penerbitan buku. Peubah ini kategorikal yang mencatat tanggal publikasi.
- publisher: Nama penerbit buku. Ini adalah data kategorikal yang menyimpan informasi tentang penerbit.

## Exploratory Data Analysis
Berdasarkan analisis awal terhadap data, berikut beberapa hal yang ditemukan:

- Jumlah Buku Unik: Dataset ini memiliki 10.344 judul buku yang berbeda. Ini menunjukkan keberagaman pilihan buku yang tersedia dalam dataset.
- Jumlah Penulis: Terdapat 6.635 penulis yang berbeda di dalam dataset, yang mencerminkan beragamnya kontribusi penulis dalam literatur yang tersedia di Goodreads.
- Rating Buku: Rating buku berkisar dari 0 hingga 5, dengan rata-rata rating 3.93, menunjukkan adanya variasi dalam penerimaan buku oleh pengguna.
- Jumlah Halaman Buku: Buku dalam dataset ini bervariasi dari 0 hingga 6.576 halaman, dengan rata-rata 336 halaman, yang mencerminkan variasi dalam panjang buku.
- Jumlah Rating dan Ulasan: Ada buku yang mendapatkan rating lebih dari 4 juta kali, sementara beberapa buku lainnya tidak mendapatkan rating sama sekali. Ini menunjukkan perbedaan dalam popularitas dan visibilitas buku.
- Bahasa Buku: Dataset ini mencakup 27 kode bahasa yang berbeda, dengan mayoritas buku menggunakan bahasa Inggris.

## Visualisasi Data
Untuk mendapatkan pemahaman yang lebih baik mengenai distribusi dan karakteristik data, dilakukan beberapa visualisasi:

- Top 10 Judul Buku
  ![top 10 judul](https://github.com/user-attachments/assets/0f0a61a6-46dc-4947-9c40-be3cbd1836d7)

Barchart ini menunjukkan 10 judul buku yang paling sering ditemukan dalam dataset. Judul buku yang paling sering muncul adalah The Brothers Karamazov dan The Iliad, masing-masing dengan frekuensi 9 kali. Diikuti oleh beberapa judul lain seperti 'Salem's Lot dan The Odyssey yang muncul sebanyak 8 kali. Barchart ini menggambarkan popularitas berbagai buku dalam koleksi data yang digunakan.

- Top 10 Authors
  ![top 10 authors](https://github.com/user-attachments/assets/e6a97385-c35b-4d2a-9973-c6c59f31a154)

Barchart di atas menampilkan 10 penulis yang paling sering muncul dalam dataset. Penulis yang paling sering ditemukan adalah Stephen King dan P.G. Wodehouse, masing-masing dengan 40 kali kemunculan. Penulis lainnya seperti Rumiko Takahashi dan Orson Scott Card juga sering muncul dalam dataset, dengan frekuensi 39 dan 35, masing-masing. Barchart ini menggambarkan dominasi penulis tertentu dalam koleksi buku yang dianalisis.

- Distribusi Peubah Average Rating
![distribution of average ratings](https://github.com/user-attachments/assets/f4768786-f47b-471e-a5a7-b28254d9e371)

Grafik di atas menunjukkan distribusi rating rata-rata dari buku-buku dalam dataset. Sebagian besar buku memiliki rating antara 3 hingga 4, dengan frekuensi tertinggi di sekitar 4. Hal ini menunjukkan bahwa sebagian besar buku mendapatkan penilaian yang baik. Namun, ada juga buku dengan rating yang lebih rendah, meskipun jumlahnya lebih sedikit.
  
- Distribusi Peubah Language Code
![language code](https://github.com/user-attachments/assets/0ea1395c-4df0-4f0b-83b9-cb49eadad66d)

Grafik ini menggambarkan jumlah buku berdasarkan kode bahasa yang terdaftar dalam dataset. Buku dalam bahasa Inggris (kode bahasa eng) mendominasi dengan jumlah yang sangat tinggi, yaitu 8906 buku. Bahasa lainnya seperti Spanyol (spa) dan Inggris (kode en-US dan en-GB) juga memiliki jumlah yang cukup signifikan, meskipun jauh lebih sedikit dibandingkan bahasa Inggris.
  
- Distribusi Peubah Num Pages
![distribution of number of pages](https://github.com/user-attachments/assets/5a61079e-c302-4a3a-856c-b16b004b341e)

Grafik ini menunjukkan distribusi jumlah halaman buku. Sebagian besar buku memiliki jumlah halaman antara 100 hingga 400 halaman, dengan puncaknya pada sekitar 200 halaman. Buku dengan jumlah halaman lebih sedikit atau lebih banyak sangat jarang ditemukan.

- Distribusi Peubah Rating Count
  ![distribution of ratings count](https://github.com/user-attachments/assets/7475f220-5c8c-4509-8ba7-3b63b4387483)

Grafik ini menggambarkan distribusi jumlah rating yang diterima oleh buku. Kebanyakan buku memiliki jumlah rating yang rendah, dengan sedikit buku yang memiliki ribuan rating. Ini menunjukkan bahwa sebagian besar buku hanya menerima sedikit ulasan atau rating dari pembaca.

- Distribusi Peubah Text Review Count
![distribution of text review count](https://github.com/user-attachments/assets/4b42ad68-da12-4429-92a7-2bef3e851f63)

Grafik ini menunjukkan distribusi jumlah ulasan teks untuk buku-buku dalam dataset. Sebagian besar buku memiliki ulasan teks yang sedikit, dengan jumlah ulasan yang lebih tinggi secara signifikan pada beberapa buku yang lebih populer. Hal ini mencerminkan bahwa buku dengan ulasan teks lebih banyak cenderung lebih dikenal atau lebih banyak dibaca.

- Distirbusi Peubah Publication Date
![distribution of publication year](https://github.com/user-attachments/assets/169c4371-c7a8-4d31-b21c-e7b0db6ac2ef)

Grafik ini menunjukkan distribusi tahun publikasi buku. Sebagian besar buku diterbitkan antara tahun 2000 hingga 2020, dengan puncaknya terjadi pada tahun 2000. Hal ini menunjukkan bahwa dataset ini didominasi oleh buku-buku yang diterbitkan pada abad ke-21.
  
- Top 10 Publisher
![top 10 publisher](https://github.com/user-attachments/assets/98d4b784-7ead-4fe4-8094-158fc712b908)

Barchart di atas menampilkan 10 penerbit buku yang paling sering muncul dalam dataset. Penerbit yang paling sering ditemukan adalah Vintage dengan 318 buku, diikuti oleh Penguin Books dan Penguin Classics. Barchart ini menunjukkan penerbit-penerbit besar yang memiliki kontribusi signifikan terhadap koleksi buku yang dianalisis.

## Data Preparation

- Menyiapkan data untuk analisis rekomendasi. peubah yang digunakan adalah title, authors, language code, dan publisher yang relevan dan merepresentasikan isi dan karakteristik buku.
- Terdapat duplikasi data sehingga duplikasi data tersebut dihapus.
- Menggabungkan empat peubah yang digunakan menjadi satu kolom untuk memudahkan dalam mengubahnya menjadi vector.
- TF-IDF Vectorizer: Setelah menggabungkan peubah-peubah buku, langkah selanjutnya adalah mengubah data teks menjadi representasi numerik menggunakan TF-IDF Vectorizer. TF-IDF (Term Frequency-Inverse Document Frequency) adalah teknik yang digunakan untuk mengukur relevansi kata dalam dokumen. TF-IDF memberikan bobot pada kata-kata berdasarkan frekuensinya dalam dokumen dan frekuensinya dalam seluruh koleksi data. Dengan menggunakan TF-IDF, kita dapat memetakan setiap buku dalam ruang vektor yang menggambarkan karakteristik konten buku tersebut.

## Modeling
Pendekatan Content-Based Filtering
Content-Based Filtering adalah pendekatan dalam sistem rekomendasi yang menggunakan informasi tentang item (dalam hal ini buku) untuk memberikan rekomendasi. Dalam konteks ini, buku akan dianalisis berdasarkan peubah-peubah kontennya, seperti judul, penulis, penerbit, dan bahasa. Prosesnya melibatkan analisis peubah yang ada pada buku dan kemudian membandingkan kemiripan antara buku yang telah dibaca pengguna dengan buku lainnya menggunakan teknik-teknik pengolahan bahasa alami (NLP) 
Langkah-langkah yang dilakukan:

1. Menghitung Cosine Similarity:
Setelah memperoleh representasi numerik dari setiap buku menggunakan TF-IDF, kita menghitung Cosine Similarity untuk mengukur kemiripan antara buku yang satu dengan yang lainnya.Cosine Similarity mengukur kesamaan antara dua vektor dengan menghitung kosinus sudut di antara keduanya. Nilai cosine similarity berkisar antara 0 (tidak mirip) hingga 1 (mirip sekali).

2. Membangun DataFrame untuk Cosine Similarity:
Matriks yang dihasilkan dari Cosine Similarity kemudian dimasukkan ke dalam sebuah DataFrame dengan judul buku sebagai indeks dan kolom.

3. Membangun fungsi rekomendasi buku 
Fungsi ini akan mengembalikan buku-buku yang paling mirip dengan buku yang sudah dibaca oleh pengguna berdasarkan Cosine Similarity yang dihitung sebelumnya.
    
4. Mencari Indeks Kemiripan:
Fungsi akan mencari kemiripan antara buku yang diberikan dengan buku lainnya menggunakan Cosine Similarity yang sudah dihitung sebelumnya.

5. Membuat Daftar Rekomendasi
Buku-buku yang paling mirip akan diambil dan diprioritaskan untuk direkomendasikan kepada pengguna.

Kelebihan Content Based Filtering:
- Personalisasi yang Tinggi
Content-Based Filtering dapat memberikan rekomendasi yang sangat personal karena didasarkan pada preferensi konten yang sudah diketahui dari pengguna. Sistem ini menganalisis peubah-peubah dari item yang telah berinteraksi dengan pengguna, seperti genre, topik, atau kategori. Sistem ini sangat efektif ketika pengguna memiliki preferensi yang jelas, seperti genre buku atau tipe artikel yang sering dibaca.

- Tidak Bergantung pada Data Pengguna Lain
Content-Based Filtering tidak memerlukan informasi tentang pengguna lain untuk membuat rekomendasi. Ini menghindari masalah terkait dengan cold start (dimana sistem tidak memiliki cukup data tentang pengguna baru atau item baru). Sistem dapat bekerja dengan baik meskipun pengguna baru belum banyak berinteraksi dengan sistem.

- Dapat Beradaptasi dengan Perubahan Preferensi Pengguna
Karena rekomendasi didasarkan pada peubah konten, jika preferensi pengguna berubah (misalnya, mereka mulai tertarik pada genre baru), sistem dapat menyesuaikan dengan cepat tanpa memerlukan data pengguna lain.

- Tidak Memerlukan Interaksi Sosial
Tidak seperti Collaborative Filtering, Content-Based Filtering tidak memerlukan interaksi sosial atau data dari pengguna lain, sehingga bisa lebih terfokus pada preferensi individu.

Kekurangan Content Based Filtering:
- Keterbatasan Variasi Rekomendasi
Content-Based Filtering hanya dapat merekomendasikan item berdasarkan peubah yang diamati. Jika semua item dalam sistem memiliki peubah yang serupa, rekomendasi yang diberikan mungkin kurang beragam. Misalnya, jika seorang pengguna hanya pernah membaca buku fiksi ilmiah, sistem hanya akan merekomendasikan lebih banyak buku fiksi ilmiah meskipun mereka mungkin tertarik pada genre lain.

- Ketergantungan pada Peubah yang Tersedia
Sistem ini bergantung pada kualitas dan keberagaman peubah yang tersedia dalam data. Jika peubah yang relevan tidak ada atau tidak cukup, maka rekomendasi yang diberikan mungkin tidak tepat. Misalnya, jika buku hanya memiliki informasi judul dan penulis, maka rekomendasi akan terbatas dan kurang akurat jika dibandingkan dengan model yang juga menggunakan informasi lain seperti sinopsis atau review.

- Tidak Memperhitungkan Preferensi Pengguna yang Tidak Diketahui
Jika seorang pengguna belum menunjukkan minat dalam kategori atau genre tertentu, sistem mungkin kesulitan untuk merekomendasikan item baru yang mereka sukai (misalnya, sistem mungkin tidak bisa mendeteksi minat tersembunyi atau minat baru).

- Overfitting pada Preferensi Pengguna
Sistem dapat cenderung mengandalkan preferensi masa lalu pengguna dan memberikan rekomendasi yang terlalu mirip dengan buku-buku sebelumnya, sehingga kurang memberikan kesempatan untuk eksplorasi genre atau topik baru.

**Top 20 Rekomendasi**

Judul Buku: Paint it Black

Penulis: Janet Fitch

Berikut Top 20 Hasil Rekomendasi

# Daftar Buku

Berikut adalah daftar buku yang dipublikasikan dengan detail penulis, penerbit, dan kode bahasa.

| No  | **Book Title**                                    | **Author**                    | **Language Code** | **Publisher**                |
|-----|---------------------------------------------------|-------------------------------|-------------------|------------------------------|
| 1   | White Oleander                                    | Janet Fitch                   | eng               | Back Bay Books               |
| 2   | White Oleander                                    | Janet Fitch                   | eng               | Little Brown and Company     |
| 3   | White Oleander                                    | Janet Fitch                   | eng               | Back Bay Books               |
| 4   | White Oleander                                    | Janet Fitch                   | eng               | Little Brown and Company     |
| 5   | Nine Stories                                      | J.D. Salinger                 | eng               | Little Brown and Company     |
| 6   | The Terror                                        | Dan Simmons                   | eng               | Little Brown and Company     |
| 7   | Black Veil: A Memoir with Digressions              | Rick Moody                    | eng               | Little Brown and Company     |
| 8   | The Harry Bosch Novels Volume 1: The Black Echo   | Michael Connelly              | eng               | Little Brown & Company       |
| 9   | Skylight Confessions                              | Alice Hoffman                 | eng               | Little Brown and Company     |
| 10  | The Beach House                                   | James Patterson/Peter de Jonge | eng               | Grand Central Publishing     |
| 11  | The Beach House                                   | James Patterson/Peter de Jonge | eng               | Little Brown and Company     |
| 12  | The Night Gardener                               | George Pelecanos              | eng               | Little Brown and Company     |
| 13  | Body Surfing                                      | Anita Shreve                  | eng               | Little Brown and Company     |
| 14  | The Quickie                                       | James Patterson/Michael Ledwidge | eng             | Little Brown and Company     |
| 15  | Roses Are Red (Alex Cross #6)                     | James Patterson               | eng               | Headline                     |
| 16  | Roses Are Red (Alex Cross #6)                     | James Patterson               | eng               | Little Brown and Company     |
| 17  | Mythology                                         | Edith Hamilton/Steele Savage  | eng               | Little Brown and Company     |
| 18  | School's Out—Forever (Maximum Ride #2)            | James Patterson               | eng               | Little Brown and Company     |
| 19  | Judge & Jury                                      | James Patterson/Andrew Gross  | eng               | Little Brown and Company     |
| 20  | Consider the Lobster and Other Essays             | David Foster Wallace          | eng               | Little Brown and Company     |

## Evaluation
Setelah membangun model rekomendasi, langkah selanjutnya adalah mengevaluasi kinerjanya. Untuk mengevaluasi Content-Based Filtering, kita menggunakan metrik Precision@k, metrik evaluasi yang digunakan untuk mengukur akurasi dari sistem rekomendasi, dengan fokus pada seberapa banyak rekomendasi yang diberikan benar-benar relevan dengan preferensi pengguna. Dalam konteks sistem rekomendasi buku berbasis Content-Based Filtering, Precision mengukur persentase buku yang relevan di antara buku-buku yang direkomendasikan.

Rumus:

$$
\text{Precision@k} = \frac{\text{Jumlah rekomendasi relevan pada k teratas}}{k}
$$

Di mana:
- Precision@k adalah ukuran presisi pada jumlah rekomendasi 𝑘
- Jumlah rekomendasi relevan adalah jumlah buku yang relevan (sesuai dengan preferensi pengguna) yang muncul dalam 20 rekomendasi teratas.
- 𝑘 adalah jumlah rekomendasi yang diberikan oleh sistem, misalnya 20 rekomendasi teratas (Precision@20).

Cara kerja metrik precision:
- Relevansi dalam sistem rekomendasi dihitung berdasarkan kesamaan peubah antara buku yang sudah dibaca oleh pengguna dan buku yang akan direkomendasikan. Content-Based Filtering mengandalkan atribut seperti judul, penulis, bahasa, dan penerbit untuk menilai kesamaan antara buku-buku.
- Sistem akan menghitung kesamaan antara buku yang telah dibaca dan buku lainnya dalam database menggunakan teknik seperti Cosine Similarity atau Euclidean Distance.
- Buku-buku yang memiliki kesamaan tinggi (nilai kesamaan mendekati 1) dianggap relevan dan masuk dalam rekomendasi.
- Precision@k mengukur berapa persen buku yang relevan di dalam 𝑘 rekomendasi teratas. Misalnya, jika ada 5 buku relevan dari 20 buku yang direkomendasikan, maka Precision@20 adalah 5/20=0,25 atau 25%.

Sistem yang memiliki Precision tinggi berarti sebagian besar rekomendasi yang diberikan sesuai dengan preferensi pengguna, yang meningkatkan kepuasan pengguna. Metrik ini sangat penting dalam sistem rekomendasi berbasis Content-Based Filtering karena dapat membantu mengevaluasi apakah sistem berhasil menyesuaikan rekomendasi dengan minat pengguna berdasarkan atribut buku yang ada.

Interpretasi Hasil Evaluasi dengan Metrik Precision@k
Hasil Precision@20 = 1.00 pada peubah gabungan (judul, penulis, bahasa, dan penerbit) berarti bahwa sistem sangat baik dalam memberikan rekomendasi yang relevan, dengan semua buku yang direkomendasikan memiliki kemiripan tinggi dengan buku yang diberikan berdasarkan gabungan berbagai peubah. Ini menunjukkan bahwa sistem sangat efisien dan akurat dalam menyarankan buku-buku yang paling mirip dengan buku yang diberikan oleh pengguna.

Pada setiap peubah yang dievaluasi, yaitu book_title, book_author, language_code, dan publisher, nilai Precision@20 yang diperoleh adalah 1.00. Ini menunjukkan bahwa semua buku yang direkomendasikan berada dalam kategori yang relevan dengan buku yang diberikan, sesuai dengan peubah yang digunakan untuk menghitung kemiripan.

Precision@20 adalah metrik evaluasi yang mengukur sejauh mana rekomendasi yang diberikan relevan dengan item yang seharusnya relevan berdasarkan urutan kemiripan yang dihitung oleh sistem. Precision@20 dihitung dengan membandingkan 20 rekomendasi teratas dengan buku-buku yang relevan. Nilai 1.00 menunjukkan bahwa semua 20 rekomendasi teratas adalah relevan menurut kriteria peubah yang diuji (judul, penulis, kode bahasa, dan penerbit).

## Daftar Pustaka
Safitri, A. D., Atina, V., & Farida, A. (2022). Sistem rekomendasi buku menggunakan metode content-based filtering. Jurnal Teknologi dan Sistem Informasi, 12(1), 45-59.

Reswara, R. H. D., Evanita, & Susanto, A. (2021). Implementasi Content-Based Filtering pada Sistem Rekomendasi Buku Perpustakaan. Jurnal Teknik Informatika, Universitas Muria Kudus.
