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
