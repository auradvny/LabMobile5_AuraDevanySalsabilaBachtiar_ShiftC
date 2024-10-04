# Tugas Pertemuan 5

Nama : Aura Devany Salsabila Bachtiar

NIM : H1D022015

Shift Baru: Shift C

## Penjelasan Langkah-Langkah

### Proses Login
1. Menginputkan Email dan Password

   ![Lampiran Login Page](login_page.png)
   ![Lampiran Login Form](login_form.png)
   - Form login terdiri dari dua field utama:

     - Email: Pengguna diminta mengisi email dengan format yang benar

     - Password: Pengguna diminta mengisi password dengan minimal 6 karakter.
   - Tombol Login

     Setelah mengisi email dan password, pengguna dapat menekan tombol Login untuk memulai proses autentikasi.

     Ketika tombol Login ditekan, aplikasi akan melakukan validasi form dan memproses login menggunakan `LoginBloc`.
   - Proses login dan validasi

     Aplikasi mengirim data login (email dan password) ke server menggunakan `LoginBloc` dan memeriksa apakah login berhasil atau gagal.
     
     `LoginBloc`: Mengatur logika proses autentikasi, melakukan request ke server, dan mengembalikan hasil login.

  
2. Respon Berhasil/Gagal

   ![Lampiran Login Berhasil](produk_page.png)
   ![Lampiran Login Gagal](login_gagal.png)
   - Respon Berhasil/Gagal
     - Login Berhasil: Pengguna akan diarahkan ke halaman `ProdukPage`.
     - Login Gagal: Dialog peringatan muncul, memberitahukan bahwa login gagal.

### Proses Register

1. Menginputkan Nama, Email, dan Password
   
   ![Lampiran Registrasi Page](registrasi_page.png)
   ![Lampiran Registrasi Form](registrasi_form.png)

   - Tampilan Halaman Registrasi
     - Pada bagian ini, kita menggunakan `TextFormField` untuk input data, yang mencakup input Nama, Email, Password, dan Konfirmasi Password. Setiap field disertai dengan validasi, sehingga data yang dimasukkan memenuhi syarat yang telah ditentukan (contoh: panjang minimal untuk nama adalah 3 karakter dan password adalah 6 karakter).
     - Tombol Registrasi
       Tombol ini akan memvalidasi form dan jika valid, akan memanggil fungsi `submit` untuk memproses registrasi.
   - Memproses Input Data
     - Jika tombol registrasi diklik, data akan dikirimkan ke server melalui `RegistrasiBloc` yang melakukan request ke API. `RegistrasiBloc` bertanggung jawab untuk mengirim data ke server menggunakan method post dari helper Api.
     - Fungsi `_submit` akan mengirim data ke server dan menampilkan dialog sukses atau gagal. 
   
2. Respon Berhasil/Gagal
   
   ![Lampiran Registrasi Berhasil](registrasi_sukses.png)
   ![Lampiran Registrasi Gagal](registrasi_gagal.png)
   ![Lampiran Data Register Tidak Sesuai](registrasi_datasalah.png)

   - Menampilkan hasil berupa dialog sukses atau gagal.
     - Jika registrasi berhasil, dialog sukses akan ditampilkan
     - Jika registrasi gagal, dialog gagal akan muncul.
     - Jika penginputan data tidak sesuai ketentuan, warning untuk validasi di form akan muncul

### Proses Tambah Data Produk
1. Menginputkan Kode Produk, Nama Produk, dan Harga

   ![Lampiran Tambah Produk Page](produk_tambah.png)
   ![Lampiran Tambah Produk Form](produk_tambahform.png)

   - Tampilan Halaman Tambah Produk
     - Pada bagian ini, kita menggunakan `TextFormField` untuk input data, yang mencakup input Kode Produk, Nama Produk, dan Harga. Setiap field inputan untuk kode produk dan nama produk berupa teks biasa, serta harga berupa angka.
   - Tombol Submit
     - Tombol Submit untuk mengirimkan data. Tombol ini akan memvalidasi inputan sebelum menyimpan. Jika form valid, akan memanggil fungsi `simpan()`. Fungsi `simpan()` akan embuat objek produk baru dengan mengisi data dari text field, mengirim data ke server menggunakan `ProdukBloc.addProduk`, dan menampilkan dialog sukses atau gagal berdasarkan hasil pengiriman data.
     - Di bagian ini, kita menggunakan `ProdukBloc` untuk melakukan interaksi dengan API backend. Metode `addProduk()` mengirim data ke server.
   
2. Respon Berhasil/Gagal

   ![Lampiran Tambah Produk Berhasil](produk_tambahberhasil.png)
   ![Lampiran Tambah Produk Gagal](produk_tambahgagal.png)

   - Menampilkan hasil berupa dialog sukses atau gagal.
     - Jika produk berhasil ditambahkan, pengguna akan diarahkan kembali ke halaman list produk.
     - Jika gagal, akan muncul dialog error, karena tidak sesuai syarat yang ditentukan.

### Proses Tampil Data Produk

1. Menampilkan Tampil Data Produk (Nama dan Harga Produk)

   ![Lampiran List Produk](produk_tambahberhasil.png)

   - Menampilkan Daftar Produk (Nama dan Harga Produk)
     - Pada file `produk_page.dart`, terdapat kelas `ProdukPage` yang berfungsi untuk menampilkan daftar produk. Di sini, kita menggunakan widget `FutureBuilder` untuk mendapatkan data produk dari API melalui `ProdukBloc.getProduks()`.
     - Pada `FutureBuilder`, jika data produk sudah berhasil diambil (snapshot memiliki data), komponen `ListProduk` akan dirender. Jika belum, akan menampilkan `CircularProgressIndicator` untuk memberi tahu pengguna bahwa data sedang diambil. Kelas `ListProduk` menerima data produk dalam bentuk list dan menampilkannya dalam bentuk daftar menggunakan `ListView.builder`.
     - Pada setiap elemen list, kita menggunakan widget `ItemProduk` yang akan menampilkan nama dan harga dari produk menggunakan widget `ListTile`.
     - Setiap item produk dapat diklik. Saat item diklik, pengguna akan diarahkan ke halaman detail produk (`ProdukDetail`)
  
2. Menampilkan Detail Data Produk (Kode Produk, Nama Produk, dan Harga)

   ![Lampiran Detail Produk](produk_detail.png)

   - Setelah pengguna mengklik sebuah produk, mereka akan diarahkan ke halaman `ProdukDetail` (dengan menampilkan Kode Produk, Nama Produk, dan Harga Produk)
   - Di bagian bawah halaman detail produk, terdapat dua tombol untuk mengedit (akan membawa pengguna ke form untuk mengedit data produk melalui navigasi ke `ProdukForm`) dan menghapus produk (akan mengonfirmasi penghapusan produk. Jika pengguna memilih untuk melanjutkan, produk akan dihapus menggunakan `ProdukBloc.deleteProduk`)

### Proses Edit Data Produk

1. Menampilkan dan Menginputkan Kode Produk, Nama Produk, dan Harga

   ![Lampiran Edit Produk](produk_edit.png)
   ![Lampiran Form Edit Produk](produk_editform.png)
   
3. Respon Berhasil/Gagal

   ![Lampiran Detail Produk Berhasil](produk_editberhasil.png)
   ![Lampiran Detail Produk Gagal](produk_editgagal.png)

### Proses Delete Data Produk

1. Menampilkan Pop Up Delete
   
    ![Lampiran Delete Produk](produk_hapus.png)

2. Respon Berhasil/Batal

   ![Lampiran Delete Produk Batal](produk_detail.png)
   ![Lampiran Delete Produk Berhasil](produk_page.png)

### Proses Logout

1. Menampilkan Sidemenu Logout

   ![Lampiran Logout](logout.png)

2. Respon Berhasil

   ![Lampiran Logout Berhasil](login_page.png)
   
