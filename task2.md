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

   ![](C:\Users\annis\Pictures\Screenshots\Screenshot (612).png)

   ![](C:\Users\annis\Pictures\Screenshots\Screenshot (613).png)

   ![](C:\Users\annis\Pictures\Screenshots\Screenshot (614).png)

   