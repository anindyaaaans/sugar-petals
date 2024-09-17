## TUGAS 2

## 1. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
1. Membuat Proyek Django Baru:
   - Langkah pertama yang saya lakukan adalah membuat direktori baru untuk proyek ini, lalu menjalankan perintah `django-admin startproject myproject` untuk memulai proyek Django.
   - Saya juga menginisiasi repository Git pada direktori proyek dan membuat repository GitHub baru untuk menyimpan kode saya secara online. Setelah itu, saya mengunggah direktori lokal ke GitHub dengan perintah `git add`, `git commit`, dan `git push`.

2. Membuat Aplikasi dengan Nama main:
   - Untuk membuat aplikasi main di dalam proyek, saya menjalankan perintah `python manage.py startapp main`. Ini membuat struktur folder baru yang nantinya akan saya gunakan untuk mengelola fitur aplikasi ini.
   - Setelah itu, saya mendaftarkan aplikasi main di dalam file `settings.py` dengan menambahkan main pada daftar `INSTALLED_APPS`.

4. Routing Aplikasi main:
   - Dalam file `urls.py` proyek utama, saya menambahkan `path('', include('main.urls'))` agar semua routing yang ada di aplikasi main dapat diakses dari root aplikasi. Selain itu, saya juga membuat file `urls.py` di direktori main dan mengatur routing untuk menampilkan fungsi yang dibuat di views.py.

5. Membuat Model Product:
   - Saya membuat model dengan nama Product di file `models.py` dalam aplikasi main. Model ini memiliki atribut name (CharField), price (IntegerField), dan description (TextField). Saya juga menambahkan atribut sweet_level (IntegerField) sebagai tambahan, seperti yang diinginkan.
   - Setelah model selesai, saya menjalankan perintah `python manage.py makemigrations` dan `python manage.py migrate` untuk membuat serta menerapkan perubahan di database.

6. Membuat Fungsi pada views.py dan Template HTML:
   - Saya menambahkan fungsi di dalam file `views.py` untuk me-render halaman HTML. Fungsi ini mengembalikan nama aplikasi, nama saya, dan kelas saya ke dalam template HTML.
   - Pada template main.html, saya menampilkan variabel app_name, name, dan class menggunakan syntax Django templating.

7. Routing di urls.py untuk Views:
   - Pada file `urls.py` aplikasi main, saya menambahkan route untuk menghubungkan fungsi yang ada di `views.py` agar bisa diakses dari URL tertentu. 

8. Deployment ke PWS:
   - Saya men-deploy proyek ini ke platform PWS dengan mengikuti langkah-langkah untuk membuat deployment branch dan memastikan bahwa semua dependensi terinstal dengan benar.
   - Setelah proses deployment selesai, aplikasi saya bisa diakses oleh teman-teman saya melalui URL yang sudah diberikan oleh PWS.

9. README.md:
   - Di file README.md, saya menjelaskan langkah-langkah yang saya lakukan untuk menyelesaikan tugas ini, serta menambahkan link ke aplikasi yang sudah di-deploy di PWS.

## 2. Buatlah bagan yang berisi request client ke web aplikasi berbasis Django beserta responnya dan jelaskan pada bagan tersebut kaitan antara urls.py, views.py, models.py, dan berkas html
![Untitled design](https://github.com/user-attachments/assets/ad5fc895-6867-474f-a174-be8810fc168a)
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


## TUGAS 3

## 1. Jelaskan mengapa kita memerlukan data delivery dalam pengimplementasian sebuah platform?
Data delivery memastikan bahwa berbagai bagian dari sebuah sistem (atau antar sistem) dapat berkomunikasi dengan efektif. Hal ini memungkinkan platform untuk bertukar informasi antara frontend dan backend, atau antar layanan, sehingga data dapat diakses dan digunakan.

## 2. Menurutmu, mana yang lebih baik antara XML dan JSON? Mengapa JSON lebih populer dibandingkan XML?
Menurut saya JSON lebih baik karena lebih sederhana, lebih populer, dan mudah dibaca dibandingkan XML. Format pasangan key-value JSON lebih mudah diolah di sebagian besar programming environments, terutama JavaScript, sehingga menjadi pilihan utama untuk API dan web services.

## 3. Jelaskan fungsi dari method is_valid() pada form Django dan mengapa kita membutuhkan method tersebut?
Method `is_valid()` digunakan untuk memeriksa apakah data dalam form sesuai dengan aturan validasi yang telah ditentukan. Hal ini memastikan bahwa hanya data yang valid yang diproses dan disimpan, sehingga mencegah terjadinya kesalahan atau masalah keamanan.

## 4. Mengapa kita membutuhkan csrf_token saat membuat form di Django? Apa yang dapat terjadi jika kita tidak menambahkan csrf_token pada form Django? Bagaimana hal tersebut dapat dimanfaatkan oleh penyerang?
 `csrf_token` adalah langkah keamanan untuk melindungi aplikasi dari serangan Cross-Site Request Forgery (CSRF). Tanpa token ini, penyerang dapat menipu pengguna untuk mengirimkan form berbahaya di situs kita. Token ini memastikan bahwa pengiriman form benar-benar berasal dari sumber yang terpercaya.

## 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
1. Membuat Input Form untuk Menambahkan Objek Model
- Saya membuat form di Django menggunakan `ModelForm` untuk model Product. Form ini didefinisikan di file `forms.py`, dan di dalamnya saya menyertakan field yang relevan dari model Product.
- Di `views.py`, saya membuat fungsi yang menangani request untuk menambahkan objek Product. Fungsi ini memvalidasi form, dan jika valid, data baru akan disimpan ke database. Jika tidak valid, form akan ditampilkan kembali dengan pesan error.
- Saya membuat template HTML yang menampilkan form tersebut, dimana pengguna dapat mengisi data dan mengirimkannya melalui metode POST.
- Terakhir, saya menambahkan path di `urls.py` untuk menghubungkan URL ke view yang menangani form, sehingga pengguna dapat mengakses form melalui browser.

2. Menambahkan 4 Fungsi Views untuk Menampilkan Data dalam Format XML, JSON, XML by ID, dan JSON by ID
- Saya membuat fungsi di `views.py` yang mengambil semua data objek Product dari database menggunakan query seperti `Product.objects.all()`, kemudian mengonversinya menjadi format XML dan mengembalikan hasilnya dalam `HttpResponse`.
- Saya membuat fungsi serupa untuk menampilkan data Product dalam format JSON.
- Saya membuat fungsi yang mengambil data Product berdasarkan ID menggunakan query `Product.objects.filter(pk=id)` dan mengembalikan hasilnya dalam format XML.
- Fungsi ini mirip dengan yang menampilkan data XML berdasarkan ID, namun hasilnya dikembalikan dalam format JSON.

3. Membuat Routing URL untuk Masing-masing Views
- Saya menambahkan path di `urls.py` untuk menghubungkan URL ke masing-masing fungsi view yang sudah dibuat.
URL untuk menampilkan data dalam format XML
URL untuk menampilkan data dalam format JSON
URL untuk menampilkan data XML berdasarkan ID
URL untuk menampilkan data JSON berdasarkan ID

## Mengakses keempat URL di poin 2 menggunakan Postman, membuat screenshot dari hasil akses URL pada Postman, dan menambahkannya ke dalam README.md.
![Screenshot 2024-09-17 211810](https://github.com/user-attachments/assets/d69c4878-02b4-45c![Screenshot 2024-09-17 211833](https://github.com/user-attachments/assets/a03cda96-9cd4-4f26-a173-6be5337f7a04)
6-87e4-dc44c2905804)
![Screenshot 2024-09-17 211851](https://github.com/user-attachments/assets/eb02b667-2a9e-4e5f-8298-075b7ef33a35)
![Screenshot 2024-09-17 211916](https://github.com/user-attachments/assets/87a8d6b7-36ea-4a4e-8b34-c3bb3e0a5999)
