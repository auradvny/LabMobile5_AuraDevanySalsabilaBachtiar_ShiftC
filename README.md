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
   
   ![Lampiran Register Page](registrasi_page.png)
   ![Lampiran Register Form](registrasi_form.png)
   
2. Respon Berhasil/Gagal
   
   ![Lampiran Register Berhasil](registrasi_sukses.png)
   ![Lampiran Register Gagal](registrasi_gagal.png)

### Proses Tambah Data Produk
1. Menginputkan Kode Produk, Nama Produk, dan Harga

   ![Lampiran Tambah Produk](produk_tambah.png)
   ![Lampiran Form Tambah Produk](produk_tambahform.png)
   
2. Respon Berhasil/Gagal

   ![Lampiran Tambah Produk Berhasil](produk_tambahberhasil.png)
   ![Lampiran Form Tambah Produk Gagal](produk_tambahgagal.png)

   (input harga harus angka)

### Proses Tampil Data Produk

1. Menampilkan Tampil Data Produk (Nama dan Harga Produk)

   ![Lampiran Tampil Produk](produk_tambahberhasil.png)
   
2. Menampilkan Detail Data Produk (Kode Produk, Nama Produk, dan Harga)

   ![Lampiran Detail Produk](produk_detail.png)

### Proses Edit Data Produk

1. Menampilkan dan Menginputkan Kode Produk, Nama Produk, dan Harga

   ![Lampiran Edit Produk](produk_edit.png)
   ![Lampiran Detail Produk Berhasil](produk_editform.png)
   
3. Respon Berhasil/Gagal

   ![Lampiran Detail Produk Berhasil](produk_editberhasil.png)
   ![Lampiran Detail Produk Gagal](produk_editgagal.png)

### Proses Delete Data Produk

1. XXX

### Proses Logout

1. XXXX
