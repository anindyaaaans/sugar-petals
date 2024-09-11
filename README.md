## 1. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
1. Membuat Proyek Django Baru:
   - Langkah pertama yang saya lakukan adalah membuat direktori baru untuk proyek ini, lalu menjalankan perintah `django-admin startproject myproject` untuk memulai proyek Django.
   - Saya juga menginisiasi repository Git pada direktori proyek dan membuat repository GitHub baru untuk menyimpan kode saya secara online. Setelah itu, saya mengunggah direktori lokal ke GitHub dengan perintah `git add`, `git commit`, dan `git push`.

2. Membuat Aplikasi dengan Nama main:
   - Untuk membuat aplikasi main di dalam proyek, saya menjalankan perintah `python manage.py startapp main`. Ini membuat struktur folder baru yang nantinya akan saya gunakan untuk mengelola fitur aplikasi ini.
   - Setelah itu, saya mendaftarkan aplikasi main di dalam file `settings.py` dengan menambahkan main pada daftar `INSTALLED_APPS`.

3. Routing Aplikasi main:
   - Dalam file `urls.py` proyek utama, saya menambahkan `path('', include('main.urls'))` agar semua routing yang ada di aplikasi main dapat diakses dari root aplikasi. Selain itu, saya juga membuat file `urls.py` di direktori main dan mengatur routing untuk menampilkan fungsi yang dibuat di views.py.

4. Membuat Model Product:
   - Saya membuat model dengan nama Product di file `models.py` dalam aplikasi main. Model ini memiliki atribut name (CharField), price (IntegerField), dan description (TextField). Saya juga menambahkan atribut sweet_level (IntegerField) sebagai tambahan, seperti yang diinginkan.
   - Setelah model selesai, saya menjalankan perintah `python manage.py makemigrations` dan `python manage.py migrate` untuk membuat serta menerapkan perubahan di database.

5. Membuat Fungsi pada views.py dan Template HTML:
   - Saya menambahkan fungsi di dalam file `views.py` untuk me-render halaman HTML. Fungsi ini mengembalikan nama aplikasi, nama saya, dan kelas saya ke dalam template HTML.
   - Pada template main.html, saya menampilkan variabel app_name, name, dan class menggunakan syntax Django templating.

6. Routing di urls.py untuk Views:
   - Pada file `urls.py` aplikasi main, saya menambahkan route untuk menghubungkan fungsi yang ada di `views.py` agar bisa diakses dari URL tertentu. 

7. Deployment ke PWS:
   - Saya men-deploy proyek ini ke platform PWS dengan mengikuti langkah-langkah untuk membuat deployment branch dan memastikan bahwa semua dependensi terinstal dengan benar.
   - Setelah proses deployment selesai, aplikasi saya bisa diakses oleh teman-teman saya melalui URL yang sudah diberikan oleh PWS.

8. README.md:
   - Di file README.md, saya menjelaskan langkah-langkah yang saya lakukan untuk menyelesaikan tugas ini, serta menambahkan link ke aplikasi yang sudah di-deploy di PWS.

## 2. Buatlah bagan yang berisi request client ke web aplikasi berbasis Django beserta responnya dan jelaskan pada bagan tersebut kaitan antara urls.py, views.py, models.py, dan berkas html
- ```urls.py``` bertugas untuk menentukan ke view mana request akan diarahkan.
- ```views.py``` berfungsi untuk menangani logika bisnis dan memutuskan bagaimana request diproses.
- ```models.py``` mengelola interaksi dengan database, bila ada data yang perlu diambil atau disimpan.
- Berkas HTML, atau template, digunakan untuk merender tampilan respons yang akan dikirimkan ke client.

## 3. Jelaskan fungsi git dalam pengembangan perangkat lunak!
- Git menyimpan semua perubahan yang dibuat, kita bisa melihat dan mengembalikan versi kode sebelumnya jika perlu.
- Banyak developer bisa bekerja bersama di proyek yang sama tanpa khawatir mengganggu kode orang lain.
- Git memudahkan developer membuat cabang terpisah untuk mengerjakan fitur baru atau memperbaiki bug tanpa memengaruhi kode utama. Cabang ini bisa digabungkan kembali nanti.
- Git juga berfungsi sebagai cadangan otomatis karena menyimpan semua perubahan.

## 4. Menurut Anda, dari semua framework yang ada, mengapa framework Django dijadikan permulaan pembelajaran pengembangan perangkat lunak?
- Django memiliki dokumentasi yang lengkap dan panduan langkah demi langkah yang cocok untuk pemula.
- Django sudah dilengkapi dengan berbagai fitur seperti autentikasi, manajemen database, dan sistem admin, sehingga pengembang tidak perlu memulai semuanya dari nol.
- Django menggunakan pola Model-View-Template (MVT) yang membuat kode lebih terstruktur dan mudah dipahami.
- Dengan banyak pengguna, tersedia banyak tutorial dan bantuan bagi pemula yang ingin belajar.

## 5. Mengapa model pada Django disebut sebagai ORM?
Model di Django disebut ORM (Object-Relational Mapping) karena memungkinkan pengembang berinteraksi dengan database tanpa menulis query SQL. ORM ini berfungsi sebagai jembatan antara kode Python dan database relasional.
- Pengembang cukup menggunakan objek Python tanpa harus menulis SQL langsung.
- Django ORM mendukung berbagai jenis database, sehingga jika ingin mengganti database, cukup ubah konfigurasi tanpa merombak kode model.
- ORM melindungi dari serangan SQL injection, karena query dibentuk secara otomatis oleh Django.