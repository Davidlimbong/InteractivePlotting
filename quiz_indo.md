# Kuis Interactive Plotting

Kuis ini merupakan bagian dari proses penilaian *Algoritma Academy*. Selamat anda sudah menyelesaikan materi *Interactive Plotting and Web Dashboard*! Kami akan melakukan penilaian berupa kuis untuk menguji materi yang sudah dipelajari. Pengerjaan Kuis diharapkan dapat dilakukan di dalam kelas, silakan hubungi tim instruktur kami jika Anda melewatkan kesempatan untuk mengambilnya di kelas.

## Memeriksa Data set

Kita akan menggunakan dataset video trending di YouTube yang disimpan di file `youtube.csv`. Data tersebut terdiri dari seluruh video trending di Amerika Serikat dari November 2017 hingga Januari 2018 dengan total 2986 observasi dan 9 variabel. Silakan gunakan glosarium berikut sebagai referensi:
 * `trending_date`: Tanggal video trending
 * `title`: Judul video
 * `channel_title`: Nama saluran (*channel*) YouTube
 * `category_id`: Kategori video
 * `publish_time`: Tanggal video dipublikasikan
 * `views`: Jumlah penonton pada video
 * `likes`: Jumlah penonton yang menyukai video
 * `dislikes`: Jumlah penonton yang tidak menyukai video
 * `comment_count`: Jumlah komentar pada video

Baca dataset tersebut dan simpan kedalam objek dengan nama `youtube`:

```{r}
# Your code here
```

Anda bekerja sebagai konsultan analis tren untuk saluran/channel YouTube. Anda mencoba untuk mendapatkan channel YouTube dengan peringkat teratas pada kategori musik (**Music**). Ukuran yang Anda gunakan untuk menilai setiap channel adalah rasio antara *likes* dan *views* (*likes ratio*) dari channel tersebut.

Ambil 10 saluran YouTube teratas berdasarkan *likes ratio* tertinggi dengan melengkapi kode di bawah ini:

```{r}
library(dplyr)
youtube %>% 
   ___(category_id == "Music") %>% 
   group_by(channel_title) %>% 
   ___(likes_ratio = mean(likes/views)) %>% 
   ___(desc(likes_ratio)) %>% 
   head(10)
```
___

1. Fungsi `dplyr` mana yang sesuai untuk mengisi kode di atas?  
  - [ ] filter, summarise, arrange
  - [ ] select, pivot, order
  - [ ] filter, mutate, order
  - [ ] select, summarise, arrange
___

## Membangun Aplikasi Dashboard

Berdasarkan channel YouTube yang telah Anda ekstrak, Anda berencana untuk membuat prototipe *dashboard* untuk klien Anda menggunakan flexdashboard. Anda membuat mockup dengan desain berikut:

![](assets/mockup.png)
___
2. Untuk menghasilkan tata letak (*layout*) seperti di atas menggunakan *template* dari flexdashboard, bagaimana seharusnya tata letak disusun?
  - [ ] orientation: rows ; 2 header pada bagian pertama, 1 header pada bagian kedua
  - [ ] orientation: columns ; 2 header pada bagian pertama, 1 headers pada bagian kedua
  - [ ] orientation: columns ; 1 header pada bagian pertama, 2 header pada bagian kedua
  - [ ] orientation: rows ; 1 header pada bagian pertama, 2 header pada bagian kedua

*Referensi Opsi Bahasa Inggris:*
  - [ ] orientation: rows ; 2 headers in first section, 1 headers in the second section
  - [ ] orientation: columns ; 2 headers in first section, 1 headers in the second section
  - [ ] orientation: columns ; 1 headers in first section, 2 headers in the second section
  - [ ] orientation: rows ; 1 headers in first section, 2 headers in the second section
___

Sekarang perhatikan plot kanan atas. Plot menunjukkan *likes ratio* dan *dislikes ratio* dari video trending pada kategori Musik. Bila Anda ingin menambahkan fitur interaktif yang menarik dimana pengguna dapat memilih kategori yang mereka inginkan dan plot akan berubah sesuai dengan kategori tersebut.
___
3. Manakah dari jenis masukan (*input type*) di bawah ini yang sesuai untuk jenis pilihan di atas?
  - [ ] selectInput()
  - [ ] sliderInput()
  - [ ] numericInput()
  - [ ] passwordInput()
___
  
Masih di plot yang sama, Anda juga ingin memiliki plot yang dapat menampilkan setiap judul video untuk analisis lebih lanjut. Karena Anda menyadari bahwa menambahkan geom_text dapat membuat plot menjadi terlalu penuh (tidak rapih), Anda berencana untuk membuat object *plotly* yang menampilkan judul video dengan mengarahkan kursor pada bagian tertentu pada plot.
___
4. Manakah dari kode berikut yang merupakan pasangan yang tepat antara fungsi render dan output untuk membuat plotly pada Shiny Dashboard?
  - [ ] output$plot1 <- renderPlot({}) ; plotlyOutput("plot1")
  - [ ] output$plotly1 <- renderPlotly({}) ; plotOutput("plotly1")
  - [ ] output$plot1 <- renderPlot({}) ; plotOutput("plot1")
  - [ ] output$plot1 <- renderPlotly({}) ; plotlyOutput("plot1")
 ___
