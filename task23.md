# TASK 2



1. buat database baru (tubes_pi)

2. ganti nama database pada file .env

3. buat tabel rss dan tabel news

   ```
   php artisan make:migration create_rss_table
   ```

   ```
   php artisan make:migration create_news_table
   ```

   

4. isi tabel rss dan news

   ```
   Schema::create('rss', function (Blueprint $table) {
               $table->id();
               $table->string('name');
               $table->string('url');
               $table->timestamps();
           });
   ```

   ```
   Schema::create('news', function (Blueprint $table) {
               $table->id();
               $table->string('title')->nullable();
               $table->string('img_url')->nullable();
               $table->text('description');
               $table->string('source_url');
   
               //foreign key
               $table->unsignedBigInteger('rss_id');
               $table->foreign('rss_id')->references('id')->on('rss');
               
               $table->timestamps();
           });
   ```



5. buat controller rss dan news

   ```
   php artisan make:model Rss --seed --controller
   ```

   ```
   php artisan make:model News --controller
   ```

   

6. seeder rss memiliki 3 link

7. isi dari controllers news adalah apa yang akan ditampilkan/isi dari halaman

8. ke routes, kemudian klik web.php. file ini untuk menambahkan bagian akhir dari link laravel. contoh 127.0.0.1:8000/aggregreate/1

9. hasil dari 3 link

   ![Screenshot (612)](https://user-images.githubusercontent.com/92453574/175778343-d3857532-e101-4b84-9f94-7bd748c25681.png)

   [Screenshot (613)](https://user-images.githubusercontent.com/92453574/175778331-642ee1b0-4433-43b5-91df-e4e531237bd7.png)

  ![Screenshot (614)](https://user-images.githubusercontent.com/92453574/175778333-7e635479-42ed-4cd5-a763-23dddf3778f1.png)
  
  
  # TUGAS BESAR
  Kumparan: [https://news.un.org/feed/subscribe/en/news/topic/health/feed/rss.xml](https://lapi.kumparan.com/v2.0/rss/)
  
  US: [https://news.un.org/feed/subscribe/en/news/region/asia-pacific/feed/rss.xml](https://abcnews.go.com/abcnews/usheadlines)
  
  Kesehatan: [https://news.un.org/feed/subscribe/en/news/region/europe/feed/rss.xml](https://www.healthcareitnews.com/home/feed)
  
  ![tubes](https://user-images.githubusercontent.com/92453574/178402665-49a49df6-64f1-4842-b001-e6fd81dca1cd.PNG)


   
