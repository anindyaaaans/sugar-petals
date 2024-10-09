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
![Screenshot 2024-09-17 211810](https://github.com/user-attachments/assets/d69c4878-02b4-45c6-87e4-dc44c2905804)
![Screenshot 2024-09-17 211833](https://github.com/user-attachments/assets/a03cda96-9cd4-4f26-a173-6be5337f7a04)
![Screenshot 2024-09-17 211851](https://github.com/user-attachments/assets/eb02b667-2a9e-4e5f-8298-075b7ef33a35)
![Screenshot 2024-09-17 211916](https://github.com/user-attachments/assets/87a8d6b7-36ea-4a4e-8b34-c3bb3e0a5999)

## TUGAS 4

## 1. Apa perbedaan antara `HttpResponseRedirect()` dan `redirect()`
- `HttpResponseRedirect()` adalah fungsi bawaan Django yang digunakan untuk mengarahkan pengguna ke URL tertentu dengan membuat objek HTTP response secara eksplisit. Fungsi ini memerlukan URL lengkap sebagai argumen dan biasanya dipakai ketika *developer* membutuhkan kontrol penuh atas URL tujuan. Misalnya, jika URL tujuan sudah diketahui atau ingin dihasilkan secara manual, `HttpResponseRedirect()` dapat digunakan untuk memberikan pengalihan yang jelas. Fungsi ini juga sering digunakan setelah suatu tindakan spesifik, misalnya setelah pengguna berhasil login atau mengirimkan formulir dengan memanfaatkan URL yang ditentukan.
- `redirect()` adalah fungsi *shortcut* di Django dengan cara lebih sederhana dan fleksibel. Selain dapat menerima URL lengkap, fungsi ini juga dapat menggunakan nama *view,* yang kemudian akan secara otomatis di-*resolve* menjadi URL yang benar. Hal ini mengurangi kerumitan penulisan URL secara manual dan mempermudah proses pengalihan, terutama ketika *developer* hanya perlu menyebutkan nama *view* atau objek yang terkait. Fungsi ini sangat berguna dalam berbagai situasi, seperti ketika ingin mengarahkan pengguna setelah tindakan tertentu tanpa harus mengetahui URL yang tepat, karena Django akan menangani pencarian rute tersebut.

## 2. Jelaskan cara kerja penghubungan model `Product` dengan `User`!
1. Relasi database yang terbentuk

Ketika saya menambahkan `ForeignKey` pada model `Product` yang merujuk ke model `User`, Django secara otomatis membuat relasi "many-to-one" di dalam database. Ini berarti bahwa banyak produk (`Product`) bisa dimiliki oleh satu pengguna (`User`). Di database, `ForeignKey` ini akan menjadi sebuah kolom di tabel `Product` yang menyimpan `primary key` dari tabel `User`.

2. Penambahan referensi pengguna di model Product

Setiap kali sebuah `Product` dibuat atau diakses, Django menggunakan referensi `ForeignKey` tersebut untuk menentukan pengguna mana yang terkait dengan produk tersebut. Misalnya, saat sebuah produk disimpan, Django akan memasukkan nilai `primary key` dari pengguna (biasanya `user.id`) ke kolom `user_id` di tabel `Product`. Ini menghubungkan produk tersebut dengan pengguna.

3. Cascading saat penghapusan data

Dengan parameter `on_delete=models.CASCADE`, jika sebuah pengguna dihapus, Django secara otomatis akan menghapus semua produk yang terkait dengan pengguna tersebut. Ini terjadi karena Django menjalankan perintah di level database untuk melakukan "cascade delete", yang memastikan tidak ada produk yang terlepas tanpa pemilik.

4. Akses data via query Django

Ketika saya melakukan query, seperti mengambil semua produk yang dimiliki oleh pengguna, Django memanfaatkan relasi tersebut untuk melakukan join antar tabel `Product` dan `User` di database. Django kemudian mengembalikan semua produk yang sesuai dengan pengguna yang diminta. Relasi ini memungkinkan pengambilan data yang efisien dan terstruktur, karena `ForeignKey` menghubungkan data antar model dengan cara yang sangat optimal di belakang layar.

## 2. Apa perbedaan antara *authentication* dan *authorization*, apakah yang dilakukan saat pengguna login? Jelaskan bagaimana Django mengimplementasikan kedua konsep tersebut.

*Authentication* (Autentikasi)

- *Authentication* adalah proses untuk memverifikasi siapa *user* yang melakukan login ke aplikasi. Tujuan utama autentikasi adalah memastikan bahwa pengguna yang mencoba mengakses aplikasi adalah individu yang mereka klaim.
- Di Django, autentikasi dapat dilakukan menggunakan `UserCreationForm` untuk membuat akun baru, dan `AuthenticationForm` untuk proses login. Saat pengguna memasukkan kredensial mereka, Django akan memverifikasi informasi tersebut.

*Authorization* (Otorisasi)

- *Authorization* adalah proses untuk memverifikasi bahwa pengguna memiliki akses ke sumber daya tertentu. Setelah pengguna berhasil diautentikasi, sistem akan memeriksa apakah pengguna memiliki hak akses untuk melakukan tindakan tertentu atau mengakses halaman tertentu dalam aplikasi.
- Di Django, otorisasi dapat dikelola menggunakan *decorator* seperti `@login_required`, yang memastikan bahwa hanya pengguna yang telah terautentikasi yang dapat mengakses tampilan tertentu.

Saat pengguna melakukan login, prosesnya adalah sebagai berikut:

- Pengguna mengisi formulir login dengan *username* dan *password*.
- Django menggunakan `AuthenticationForm` untuk memverifikasi kredensial pengguna.
- Jika autentikasi berhasil, Django akan memulai sesi untuk pengguna menggunakan `login()`.
- Setelah login, pengguna dapat diarahkan ke halaman utama jika otorisasi berhasil.

## 4. Bagaimana Django mengingat pengguna yang telah login? Jelaskan kegunaan lain dari *cookies* dan apakah semua cookies aman digunakan?

Django mengingat pengguna yang telah login menggunakan *session*. Saat pengguna login, Django membuat *session ID* yang unik dan menyimpannya dalam *cookies* di sisi klien. Informasi pengguna disimpan di server. Ketika pengguna berpindah halaman, *browser* mengirimkan *session ID* ke *server*, memungkinkan Django untuk mengenali pengguna dan menjaga sesi login tanpa meminta mereka untuk login ulang.

Selain menyimpan *session ID, cookies* memiliki beberapa kegunaan, yaitu:

- Menyimpan preferensi pengguna, seperti bahasa dan tema.
- Mengumpulkan data analitik tentang perilaku pengguna.
- Menyimpan informasi seperti item di keranjang belanja.
- Memungkinkan pengguna tetap login setelah menutup *browser*.

*Cookies* tidak selalu aman karena rentan terhadap serangan seperti *Cross-Site Scripting* (XSS), di mana skrip jahat dapat mengakses informasi dalam *cookies*. Untuk meningkatkan keamanan, *cookies* harus menggunakan atribut `Secure` agar hanya dikirim melalui HTTPS dan atribut SameSite untuk mencegah pengiriman dalam permintaan lintas situs atau  bisa dibilang melindungi dari *Cross-Site Request Forgery* (CSRF). Selain itu, *cookies* tanpa batas waktu dapat bertahan lebih lama dari yang diperlukan meningkatkan risiko jika menyimpan informasi sensitif.

## 5. Jelaskan bagaimana cara kamu mengimplementasikan *checklist* di atas secara *step-by-step* (bukan hanya sekadar mengikuti tutorial).

1. Mengimplementasikan fungsi registrasi, login, dan logout untuk memungkinkan pengguna untuk mengakses aplikasi sebelumnya dengan lancar.

Registrasi:

- Pertama, saya membuat form registrasi dengan menggunakan `UserCreationForm` dari Django.
- Kemudian, saya membuat view untuk menangani pendaftaran pengguna baru. Di sini, saya memeriksa apakah data form valid, lalu menyimpan data pengguna baru ke database.
- Setelah registrasi berhasil, pengguna bisa dialihkan ke halaman login atau langsung login.
- Saya juga menambahkan URL *routing* yang mengarah ke halaman registrasi.

Login:

- Untuk login, saya menggunakan `AuthenticationForm` yang disediakan oleh Django untuk memverifikasi kredensial pengguna (username dan password).
- Di dalam view login, saya memeriksa apakah form login valid, lalu mengautentikasi pengguna.
- Jika berhasil, saya mengarahkan pengguna ke halaman utama dan menyimpan informasi sesi pengguna.

Logout:

- Logout diimplementasikan menggunakan fungsi `logout(request)` dari Django. Fungsi ini menghapus sesi pengguna yang aktif.
- Setelah pengguna logout, saya mengarahkan mereka ke halaman login kembali atau halaman utama dengan status logout.

2. Membuat **dua** akun pengguna dengan masing-masing **tiga** *dummy data* menggunakan model yang telah dibuat pada aplikasi sebelumnya untuk setiap akun **di lokal**.

- Saya sudah membuat dua akun pengguna secara manual di database.
- Setelah akun dibuat, saya membuat beberapa dummy data produk terkait dengan setiap akun. Untuk setiap akun, saya membuat tiga entri produk menggunakan model Product.

3. Menghubungkan model `Product` dengan `User`.

- Saya menambahkan field `user` pada model Product dengan menggunakan ForeignKey yang mengacu pada model User. Ini menghubungkan setiap produk dengan pengguna yang membuatnya.
- Dalam view yang menangani penambahan produk, saya memastikan bahwa produk yang ditambahkan terkait dengan pengguna yang sedang login (request.user).
- Dengan menghubungkan produk dan pengguna, saya dapat melakukan *query* untuk mendapatkan semua produk yang dimiliki oleh pengguna tertentu.

4. Menampilkan detail informasi pengguna yang sedang *logged in* seperti *username* dan menerapkan `cookies` seperti `last login` pada halaman utama aplikasi.

- Pada halaman utama, saya menampilkan informasi pengguna yang sedang login dengan menggunakan `request.user`.
- Untuk menyimpan informasi tambahan, seperti waktu login terakhir, saya memanfaatkan fitur cookies dan `last_login` yang disimpan oleh Django secara otomatis di dalam middleware.
- Saya menambahkan logika di dalam view untuk memeriksa dan menampilkan cookie `last_login` pada halaman utama.
- Kemudian, saya mengupdate cookie setelah pengguna berhasil login.

## TUGAS 5

## 1. Jika terdapat beberapa CSS selector untuk suatu elemen HTML, jelaskan urutan prioritas pengambilan CSS selector tersebut!

1. **`!important`**: Aturan dengan `!important` selalu memiliki prioritas tertinggi, mengesampingkan semua aturan lain, meskipun memiliki spesifisitas lebih rendah.
2. **Inline styles**: Gaya yang didefinisikan langsung pada elemen HTML menggunakan atribut `style` memiliki prioritas tinggi.
3. **ID selector**: Selector yang menggunakan ID (`#id`) memiliki prioritas lebih tinggi daripada selector lainnya seperti *class* dan elemen.
4. **Class, attribute, dan pseudo-class selector**: Selector yang menggunakan *class* (`.class`), *attribute* (`[attr]`), atau *pseudo-class* (`:hover`, `:focus`) memiliki prioritas lebih rendah dibandingkan ID tetapi lebih tinggi dari selector elemen.
5. **Element dan pseudo-element selector**: Selector yang mengacu pada elemen (`p`, `h1`, `div`, dll.) atau *pseudo-element* (`::before`, `::after`) memiliki prioritas terendah.

## 2. Mengapa *responsive design* menjadi konsep yang penting dalam pengembangan aplikasi *web*? Berikan contoh aplikasi yang sudah dan belum menerapkan *responsive design*!

*Responsive design* sangat penting karena:

1. *User* dapat dengan mudah menjelajahi situs di perangkat apa pun tanpa perlu memperbesar atau menggeser layar, meningkatkan kenyamanan dan kepuasan.

2. Google dan *search engine* lainnya lebih menyukai situs web yang responsif karena memberikan pengalaman pengguna yang lebih baik, sehingga meningkatkan peringkat pencarian.

3. Dengan satu desain responsif, pengembang tidak perlu membuat versi terpisah untuk berbagai perangkat (misalnya, versi desktop dan mobile), sehingga lebih efisien dalam pengelolaan situs.

4. Dengan banyaknya perangkat baru yang muncul, desain responsif memastikan situs web tetap relevan dan berfungsi baik di masa depan tanpa perlu perubahan besar.

Contoh aplikasi yang sudah menerapkan *responsive design*:

- Instagram web

Contoh aplikasi yang belum menerapkan *responsive design:*

- Situs web lama atau aplikasi yang hanya dikembangkan untuk desktop

## 3. Jelaskan perbedaan antara *margin*, *border*, dan *padding*, serta cara untuk mengimplementasikan ketiga hal tersebut!
- *Margin*

*Margin* adalah ruang di luar elemen yang digunakan untuk mengatur jarak antar elemen. Margin bersifat transparan dan tidak terlihat. Contoh implementasi:

```jsx
<div style="margin: 10px;"> <!-- Margin sama untuk semua sisi -->
    Ini adalah elemen dengan margin 10px di semua sisi.
</div>

<div style="margin-top: 20px; margin-bottom: 15px; margin-left: 5px; margin-right: 5px;">
    Ini adalah elemen dengan margin yang berbeda untuk setiap sisi.
</div>
```

- *Border*

*Border* adalah garis yang mengelilingi elemen, terletak di antara *padding* dan *margin*. *Programmer* dapat mengatur warna, ketebalan, dan gaya *border*. Contoh implementasi:

```jsx
<div style="border: 3px solid black;"> <!-- Border solid hitam -->
    Ini adalah elemen dengan border solid hitam.
</div>

<div style="border: 2px dashed red;"> <!-- Border garis putus-putus merah -->
    Ini adalah elemen dengan border garis putus-putus merah.
</div>

<div style="border: 4px dotted blue; border-radius: 10px;"> <!-- Border garis titik biru dengan sudut bulat -->
    Ini adalah elemen dengan border titik biru dan sudut dibulatkan.
</div>
```

- *Padding*

*Padding* adalah ruang di dalam elemen antara konten dan *border*. Ini memberikan jarak agar konten tidak menempel pada batas elemen. Contoh implementasi:

```jsx
<div style="padding: 20px; border: 1px solid black;"> <!-- Padding sama untuk semua sisi -->
    Ini adalah elemen dengan padding 20px di semua sisi.
</div>

<div style="padding-top: 10px; padding-bottom: 20px; padding-left: 15px; padding-right: 15px; border: 1px solid black;">
    Ini adalah elemen dengan padding yang berbeda untuk setiap sisi.
</div>
```

| **Aspek** | ***Margin*** | ***Border*** | ***Padding*** |
| --- | --- | --- | --- |
| **Fungsi** | Jarak luar elemen | Garis pengeliling | Jarak dalam elemen |
| **Warna** | Transparan | Memiliki warna | Sesuai background |
| **Dampak** | Mempengaruhi jarak antar elemen | Tidak mempengaruhi tata letak | Mempengaruhi ukuran total elemen |

Contoh implementasi gabungan:

```jsx
<div style="margin: 30px; border: 2px solid gray; padding: 15px;">
    <p style="margin: 0;">Ini adalah konten di dalam elemen dengan margin, border, dan padding.</p>
</div>

<div style="margin: 20px; border: 3px dotted green; padding: 10px;">
    <h2 style="margin: 0;">Contoh Elemen dengan Border Dotted</h2>
    <p style="margin: 0;">Ini adalah teks di dalam elemen dengan border dotted hijau.</p>
</div>
```

## 4. Jelaskan konsep *flex box* dan *grid layout* beserta kegunaannya!

*Flexbox* dan g*rid layout* adalah dua cara untuk mengatur tampilan elemen di halaman web agar rapi dan responsif.

*- Flexbox*

- Mengatur elemen secara horizontal (baris) atau vertikal (kolom).
- Elemen bisa otomatis menyesuaikan ukuran dan posisi sesuai ruang yang tersedia.
- Tata letak sederhana seperti deretan kartu atau tombol.

*- Grid layout*

- Mengatur elemen dalam baris dan kolom.
- Bisa membuat layout yang lebih terstruktur, seperti tabel atau halaman dengan beberapa bagian berbeda.
- Cocok untuk halaman yang butuh desain lebih rumit dengan banyak area.

## 5. Jelaskan bagaimana cara kamu mengimplementasikan *checklist* di atas secara *step-by-step* (bukan hanya sekadar mengikuti tutorial)!

1. Mengimplementasikan fungsi edit dan hapus produk

- Saya sudah menambahkan fungsi `edit_product(request, id)` dan `delete_product(request, id)` di `views.py`.

- Kedua fungsi tersebut dirouting dengan menambahkan import dan path di `main/urls.py`.

- Tombol edit dan hapus produk juga sudah ditambahkan di `main.html`.

2. Pembuatan halaman dan template

- Template `edit_product.html` sudah saya buat sebagai halaman untuk mengedit produk.

- Pada setiap card produk di `main.html`, saya menambahkan tombol untuk mengedit dan menghapus, yang dihubungkan ke fungsi `edit_product` dan `delete_product`.

3. Kustomisasi tampilan template HTML

- Styling menggunakan Tailwind CSS, dengan menambahkannya di `base.html`.

- Saya sudah mendesain halaman login, register, tambah produk, dan edit produk menggunakan Tailwind agar tampilannya lebih menarik.

- Folder `static/image` dibuat untuk menyimpan foto yang digunakan di website.

- Saya juga melakukan konfigurasi `STATIC_URL`, `STATICFILES_DIRS`, dan `STATIC_ROOT` di `settings.py` agar file statis dapat diakses, serta menambahkan `{% load static %}` di halaman yang memerlukannya.

4. Card produk dan informasi store

- Untuk menampilkan daftar produk, saya membuat `card_product.html` sebagai template kartu produk, dan halaman daftar produk dibuat responsif dengan menggunakan Flexbox.

- Informasi nama, kelas, dan NPM saya tampilkan di `main.html` dengan menggunakan card `card_info.html`.

5. Membuat navigasi dan menjadikannya responsif

- Template navigation bar (`navbar.html`) sudah saya buat, dan saya menambahkannya ke dalam `{% block content %}` di setiap halaman yang memerlukan navigasi.

- Navigation bar dirancang agar responsif, menggunakan pengaturan `md:flex` untuk tampilan desktop dan `md:hidden` untuk tampilan mobile.

## TUGAS 6

## 1. Manfaat JavaScript dalam Web Development
JavaScript berperan penting dalam membuat halaman web menjadi lebih interaktif dan dinamis. Dengan menggunakan JavaScript, kita dapat menambahkan berbagai fitur menarik, seperti validasi form untuk memastikan data yang dimasukkan pengguna benar, serta animasi yang mempercantik tampilan situs. Selain itu, JavaScript memungkinkan pengambilan data dari server secara langsung tanpa perlu memuat ulang halaman, berkat teknik yang dikenal sebagai AJAX. Yang membuat JavaScript semakin menarik adalah dukungannya yang luas di hampir semua jenis browser, sehingga pengguna dapat mengakses aplikasi web dengan baik di berbagai perangkat.

## 2. Jelaskan fungsi dari penggunaan await ketika kita menggunakan fetch()! Apa yang akan terjadi jika kita tidak menggunakan await?
Kata kunci `await` digunakan untuk menunggu hasil dari fungsi `fetch()` sebelum melanjutkan ke baris kode berikutnya. Ini sangat penting karena jika kita tidak menggunakan `await`, kode akan terus berjalan tanpa menunggu respons dari server. Hal ini dapat menyebabkan error atau hasil yang tidak diinginkan, karena data yang ingin kita akses mungkin belum siap untuk digunakan. Dengan kata lain, `await` memastikan bahwa kita mendapatkan hasil dari `fetch()` sebelum melanjutkan dengan proses yang memerlukan data tersebut.

## 3. Mengapa kita perlu menggunakan decorator csrf_exempt pada view yang akan digunakan untuk AJAX POST?
Decorator `csrf_exempt` sangat penting ketika kita bekerja dengan permintaan AJAX POST, karena fungsinya adalah untuk menonaktifkan pemeriksaan token CSRF (Cross-Site Request Forgery). Token CSRF adalah mekanisme keamanan yang digunakan untuk mencegah serangan yang memanfaatkan sesi pengguna yang sah. Ketika permintaan AJAX tidak mengirimkan token CSRF yang valid, server akan menolak permintaan tersebut. Dengan menggunakan `csrf_exempt`, kita memastikan bahwa permintaan AJAX tetap bisa diproses meskipun tidak ada token yang dikirimkan, terutama dalam situasi tertentu di mana token tidak dapat disertakan.

## 4. Pada tutorial PBP minggu ini, pembersihan data input pengguna dilakukan di belakang (backend) juga. Mengapa hal tersebut tidak dilakukan di frontend saja?
Pembersihan data input pengguna di backend sangat penting untuk menjaga keamanan aplikasi. Meskipun validasi dan pembersihan dilakukan di frontend, data tetap dapat dimanipulasi oleh pengguna yang berpotensi berbahaya. Dengan melakukan pembersihan di backend, kita dapat memastikan bahwa semua input yang diterima diperiksa ulang untuk mencegah serangan seperti XSS (Cross-Site Scripting) dan SQL Injection. Ini berarti bahwa backend bertindak sebagai lapisan perlindungan tambahan yang sangat diperlukan untuk menjaga integritas dan keamanan aplikasi secara keseluruhan.

## 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)!
### 1. **AJAX GET**
- Saya mengubah kode agar bisa mengambil data mood milik pengguna yang login dengan menggunakan AJAX. 
- Saya menggunakan `fetch()` untuk mengirim permintaan GET ke endpoint yang disiapkan, memastikan hanya data pengguna yang diambil.

### 2. **AJAX POST**
- Di halaman utama, saya menambahkan tombol untuk membuka modal yang berisi form untuk menambah mood baru. Modal ini awalnya tersembunyi.
- Setelah pengguna mengisi form dan mengirimkan data, saya menggunakan `fetch()` dengan metode POST ke endpoint `/create-ajax/`. Setelah berhasil, modal ditutup dan form dibersihkan.

### 3. **Buat View untuk Menambah Mood**
- Saya membuat view baru di `views.py` untuk menangani permintaan POST, memvalidasi input dari form, dan menyimpan mood ke dalam database.

### 4. **Tambahkan Routing**
- Saya menambahkan jalur baru di `urls.py` yang mengarah ke view untuk memungkinkan akses dari frontend.

### 5. **Hubungkan Form ke Jalur**
- Saya memastikan form di modal terhubung dengan jalur `/create-ajax/` sehingga data bisa dikirim dengan benar saat disubmit.

### 6. **Refresh Asinkronus**
- Setelah mood berhasil ditambahkan, saya memanggil fungsi untuk memperbarui tampilan daftar mood di halaman utama tanpa memuat ulang seluruh halaman.