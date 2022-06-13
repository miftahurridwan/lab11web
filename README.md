# Lab11Web
# Praktikum 11 PHP Framework (Codeigniter) 

### MIFTAHURRIDWAN [311910315]

### TI.19.A.2


## Laporan Praktikum
### Persiapan
Mengaktifkan beberapa ekstensi php, diantaranya:
- php-json ekstension untuk bekerja dengan JSON;
- php-mysqlnd native driver untuk MySQL;
- php-xml ekstension untuk bekerja dengan XML;
- php-intl ekstensi untuk membuat aplikasi multibahasa;
- libcurl (opsional), jika ingin pakai Curl</br>
![mengaktifkan ekstensi_L01](https://user-images.githubusercontent.com/56252129/122025647-b6a5d380-cdf3-11eb-96a9-7e710acaddec.PNG)

Pada bagian extension, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

![hilangkan titik koma](https://user-images.githubusercontent.com/56252129/122025706-c6bdb300-cdf3-11eb-97a6-34e5cb426bb5.PNG)

## Instalasi CodeIgniter 4
- Codeigniter dapat didownload dari website https://codeigniter.com/download
- Extrak file zip Codeigniter ke direktori htdocs/lab11_php_ci.
- Ubah nama direktory framework-4.x.xx menjadi ci4.
- Buka browser dengan alamat http://localhost/lab11_php_ci/ci4/public/
![instalasi codeigniter_l03](https://user-images.githubusercontent.com/56252129/122025788-d806bf80-cdf3-11eb-8495-06ba1bdd1738.PNG)

## Menjalankan CLI (Command Line Interface) 
Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/htdocs/lab11_ci/ci4/)  
Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:`php spark`
![L04](https://user-images.githubusercontent.com/56252129/122025882-efde4380-cdf3-11eb-9acf-224f227d5876.PNG)

<br>Codeigniter juga menyediakan mode debugging/development yang dapat menampilkan error/kesalahan dalam kode program. Cara mengaktifkannya dengan mengubah nama file `env` menjadi `.env` kemudian buka filenya dan ubah nilai <b>CI_ENVIRONMENT</b> menjadi <b>development</b>.
![P_CI=development](https://user-images.githubusercontent.com/56252129/123894766-f094df00-d988-11eb-9d1f-e06f6b1515c8.PNG)

Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file
app/Controller/Home.php hilangkan titik koma pada akhir kode`(disini sebenarnya saya masih gagal mengubah <b>CI_ENVIRONMENT</b> menjadi <b>development</b> jadi tampilan nya menjadi seperti ini)`.
![P_ErorPage](https://user-images.githubusercontent.com/56252129/123894817-0bffea00-d989-11eb-99a9-76c0d2ce9564.PNG)

### Langkah 1 - Membuat Route
- Router terletak pada file app/config/Routes.php
- Untuk mengetahui route yg ada atau telah berjalan dapat menggunakan perintah `php spark routes`!
![L1](https://user-images.githubusercontent.com/56252129/122029861-73e5fa80-cdf7-11eb-8bad-4d42bd2cdc50.PNG)

- Selanjutnya mencoba akses route yang telah dibuat dengan mengakses 
http://localhost:8080/about
![L2](https://user-images.githubusercontent.com/56252129/122029933-86603400-cdf7-11eb-9851-92083a7c9916.PNG)

Ketika diakses itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page. 

### Langkah 2 - Membuat Controller
- Membuat file <b>page.php</b> di dalam direktori Controller (/app/Controllers)
![L3](https://user-images.githubusercontent.com/56252129/122030084-a98ae380-cdf7-11eb-9f36-5a9020118553.PNG)

- Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaitu halaman sudah dapat diakses. 
![L4 ](https://user-images.githubusercontent.com/56252129/122030423-f5d62380-cdf7-11eb-98eb-d1c8c0464963.png)

- Menambahkan method baru pada controller page.
![L5](https://user-images.githubusercontent.com/56252129/122031009-7b59d380-cdf8-11eb-95fc-d24c9efee5ba.PNG)
- Method ini hanya dapat diakses dengan menggunakan alamat: http://localhost:8080/page/tos karena belum ada pada routing.
![L6 ](https://user-images.githubusercontent.com/56252129/122031282-c247c900-cdf8-11eb-86e3-c56ba3a3dd51.png)

### Langkah 3 - Membuat View
- Membuat file <b>about.php</b> di dalam direktori View (/app/view/about.php)
![L7](https://user-images.githubusercontent.com/56252129/122033078-667e3f80-cdfa-11eb-95a5-fa894d8a95ab.PNG)

- Ubah method about pada class Controller Page menjadi seperti berikut: 
![L8](https://user-images.githubusercontent.com/56252129/122033253-8f063980-cdfa-11eb-8c1c-539245806563.PNG)
- Berikut hasilnya : 
![L9](https://user-images.githubusercontent.com/56252129/122033304-99283800-cdfa-11eb-9a0c-dc4d9e982af6.png)

### Langkah 4 - Membuat Layout Web dengan CSS
- Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout).
![L10](https://user-images.githubusercontent.com/56252129/122034283-8eba6e00-cdfb-11eb-960f-986c611789b4.PNG)

- Kemudian buat folder template pada direktori view, lalu buat file <b>header.php</b> dan <b>footer.php</b>.
![L11](https://user-images.githubusercontent.com/56252129/122035870-1e145100-cdfd-11eb-92b8-b9c8c4621bc8.PNG)
![L12](https://user-images.githubusercontent.com/56252129/122035929-2e2c3080-cdfd-11eb-8833-ec7ff7b9151c.PNG)

- Kemudian ubah file about.php (/app/view/about.php) seperti berikut.
![L13](https://user-images.githubusercontent.com/56252129/122036235-8a8f5000-cdfd-11eb-96c6-ef32f7d30b33.PNG)

- Selanjutnya refresh tampilan pada alamat http://localhost:8080/about.
![L14](https://user-images.githubusercontent.com/56252129/122036402-b7dbfe00-cdfd-11eb-9fb5-540cf56ea3e3.png)

## Pertanyaan dan Tugas
Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

## Hasil tugas
- Tampilan page about
![L15](https://user-images.githubusercontent.com/56252129/122036577-ece85080-cdfd-11eb-84a4-370426f83efe.png)

- Tampilan page artikel
![L16](https://user-images.githubusercontent.com/56252129/122036909-451f5280-cdfe-11eb-99fb-32b97114602a.png)

- Tampilan page kontak
![L17](https://user-images.githubusercontent.com/56252129/122036974-54060500-cdfe-11eb-9d00-31fd3fced009.png)
.

# Praktikum 12 (Framework Lanjutan - CRUD)

### MIFTAHURRIDWAN [311910315]

### TI.19.A.2

## Laporan Praktikum
### Persiapan
Pastikan MySQL server sudah berjalan dan buat sebuah database sebagai berikut:
![Ss_00](https://user-images.githubusercontent.com/56252129/122942623-8c7a8580-d3a0-11eb-8e68-6bef18be5257.PNG)

### Langkah 1 - Konfigurasi Database
Membuat konfigurasi hubungan ke database server dengan menggunakan file `.env`.
![Ss_01](https://user-images.githubusercontent.com/56252129/122943935-a2d51100-d3a1-11eb-9c31-7738395e79b8.PNG)

### Langkah 2 - Membuat Model
Buat file baru pada direktori /app/Models dengan nama ArtikelModel.php
![Ss_02](https://user-images.githubusercontent.com/56252129/122944656-3575b000-d3a2-11eb-9009-23b58b6fe97a.PNG)

### Langkah 3 - Membuat Controller
Buat Controller baru dengan nama Artikel.php pada direktori /app/Controllers. 
![Ss_03](https://user-images.githubusercontent.com/56252129/122945756-fdbb3800-d3a2-11eb-8732-926e349c1c66.PNG)

### Langkah 4 - Membuat View
Buat direktori baru dengan nama <b>artikel</b> pada direktori /app/Views, kemudian buat file baru dengan nama <b>index.php</b>.
![Ss_04](https://user-images.githubusercontent.com/56252129/122946775-d7e26300-d3a3-11eb-8b3b-9750a701e121.PNG)

Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel
![Ss_05](https://user-images.githubusercontent.com/56252129/122951050-2d6c3f00-d3a7-11eb-9f97-4a49ea548757.PNG)

Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada database agar dapat ditampilkan datanya. 
![Ss_06](https://user-images.githubusercontent.com/56252129/122951471-81772380-d3a7-11eb-9837-f0df4de39d22.PNG)

Refresh kembali browser, sehingga akan ditampilkan hasilnya. 
![Ss_07](https://user-images.githubusercontent.com/56252129/122951763-baaf9380-d3a7-11eb-969e-587fa546d0a5.PNG)

### Langkah 5 - Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda.
Tambahkan sebuah fungsi baru pada <b>Controller Artikel</b> (/app/Controllers/Artikel.php) dengan nama <b>view()</b>.
![Ss_08](https://user-images.githubusercontent.com/56252129/122953545-ff87fa00-d3a8-11eb-8858-86b4ff5897c8.PNG)

### Langkah 6 - Membuat View Detail
Buat file baru dalam folder artikel <b>(/app/Views/artikel/)</b> dengan nama <b>detail.php</b> untuk menampilkan halaman detail.
![Ss_09](https://user-images.githubusercontent.com/56252129/122954310-83da7d00-d3a9-11eb-997a-9e8f44ef8691.PNG)

### Langkah 7 - Membuat Route
Buka Kembali file app/config/Routes.php, kemudian tambahkan routing untuk artikel detail.
`$routes->get('/artikel/(:any)', 'Artikel::view/$1');`
![Ss_10](https://user-images.githubusercontent.com/56252129/122955267-2a268280-d3aa-11eb-91ea-82156b1d8654.PNG)

Maka akan tampil halaman dari artikel yang diklik.
![Ss_11](https://user-images.githubusercontent.com/56252129/122955499-5d691180-d3aa-11eb-8ac5-15448a0a68a2.PNG)

### Langkah 8 - Membuat Menu Admin
Menu admin adalah untuk proses CRUD data artikel.</br>
Buat method atau fungsi baru pada <b>Controller Artikel</b> dengan nama <b>admin_index()</b>.
![Ss_12](https://user-images.githubusercontent.com/56252129/122957279-fb111080-d3ab-11eb-964c-493d642f3bf4.PNG)

Kemudian buat file <b>admin_index.php</b> dalam folder <b>(/app/Views/artikel/)</b> untuk tampilan halaman admin.
![Ss_13](https://user-images.githubusercontent.com/56252129/122961229-66f47880-d3ae-11eb-8027-461666140f6c.PNG)

Kemudian tambahkan routing untuk menu admin sebagai berikut:
![Ss_14](https://user-images.githubusercontent.com/56252129/122962066-3cef8600-d3af-11eb-9972-537e6e90b8cb.PNG)

Menu admin dapat diakses dengan alamat http://localhost:8080/admin/artikel
![Ss_15](https://user-images.githubusercontent.com/56252129/122962328-8049f480-d3af-11eb-8391-e39a5121ed31.PNG)

### Langkah 9 - Menambah Data Artikel
Tambahkan fungsi/method baru pada <b>Controller Artikel</b> dengan nama <b>add()</b>.
![Ss_16](https://user-images.githubusercontent.com/56252129/122964417-732e0500-d3b1-11eb-8797-9f36ab420162.PNG)

Kemudian buat view untuk form tambah dengan nama <b>form_add.php</b> dalam folder <b>(/app/Views/artikel/)</b>.
![Ss_17](https://user-images.githubusercontent.com/56252129/123026893-207f3800-d407-11eb-88d9-750d1c69ede9.PNG)

Berikut tampilan form untuk menambah data artikel.
![Ss_18](https://user-images.githubusercontent.com/56252129/123027002-4f95a980-d407-11eb-8b06-22f3a27ac094.PNG)

### Langkah 10 - Mengubah Data
Tambahkan fungsi/method baru pada <b>Controller Artikel</b> dengan nama <b>edit()</b>.
![Ss_19](https://user-images.githubusercontent.com/56252129/123027419-0134da80-d408-11eb-9cf1-fc49e6c7ea84.PNG)

Kemudian buat view untuk form tambah dengan nama <b>form_edit.php</b> dalam folder <b>(/app/Views/artikel/)</b>.
![Ss_20](https://user-images.githubusercontent.com/56252129/123027825-b1a2de80-d408-11eb-86f7-7267b4df2d8c.PNG)

Berikut tampilan form untuk mengubah data artikel.
![Ss_21](https://user-images.githubusercontent.com/56252129/123027974-d9924200-d408-11eb-91c4-e5aaf9b14847.PNG)

### Langkah 11 - Menghapus Data
Tambahkan fungsi/method baru pada <b>Controller Artikel</b> dengan nama <b>delete()</b>.
![Ss_22-](https://user-images.githubusercontent.com/56252129/123028467-94badb00-d409-11eb-8eae-220b5c931bbf.PNG)
