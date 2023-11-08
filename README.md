# tugas_list

1. Dalam konteks pengembangan aplikasi Flutter, terdapat perbedaan utama antara stateless widget dan stateful widget, yang berkaitan dengan bagaimana widget tersebut berinteraksi dengan data dan cara mereka memperbarui tampilan.

- Stateless Widget:

Stateless widget adalah widget yang tidak memiliki keadaan (state) internal yang dapat berubah.
Mereka hanya memiliki data yang diberikan saat widget dibuat (biasanya dalam konstruktor) dan tidak dapat diperbarui setelah itu.
Stateless widget sangat efisien karena mereka tidak perlu melacak perubahan keadaan internal.
Contoh penggunaan stateless widget adalah teks statis, ikon, gambar, dan widget lain yang tidak memerlukan pembaruan selama siklus hidup aplikasi.
Stateful Widget:

- Stateful widget adalah widget yang memiliki keadaan (state) internal yang dapat berubah sepanjang waktu.
Mereka menggunakan objek yang disebut "State" untuk mengelola dan memperbarui keadaan internal mereka.
Ketika keadaan internal berubah, stateful widget membangun ulang tampilan mereka untuk mencerminkan perubahan tersebut.
Stateful widget cocok untuk mengimplementasikan komponen yang perlu merespons perubahan data atau interaksi pengguna, seperti formulir, daftar, dan layar detail.

Perbedaan ini mencerminkan bagaimana Flutter mengelola pembaruan tampilan dan keadaan dalam aplikasi. Dalam pengembangan aplikasi Flutter, pemilihan antara stateless dan stateful widget bergantung pada kebutuhan aplikasi dan cara Anda ingin mengelola data dan pembaruan tampilan. Stateful widget digunakan ketika Anda memerlukan pembaruan dinamis dalam tampilan berdasarkan perubahan keadaan, sementara stateless widget digunakan untuk tampilan yang tetap dan tidak berubah sepanjang siklus hidup aplikasi.

2. Berikut adalah daftar widget yang digunakan dalam tugas 7 tersebut dan penjelasan fungsinya:

MaterialApp: MaterialApp adalah widget yang digunakan untuk mengkonfigurasi aspek-aspek utama aplikasi seperti tema, judul, dan banyak lagi. Anda menggunakan MaterialApp untuk mengatur tema aplikasi menjadi indigo.

Scaffold: Scaffold adalah widget yang menyediakan struktur dasar untuk halaman aplikasi. Ini termasuk AppBar dan body. Dalam tutorial, Anda menggunakan Scaffold untuk menyusun tampilan utama aplikasi.

AppBar: AppBar adalah bagian atas halaman yang biasanya berisi judul aplikasi. Anda menggunakannya untuk menampilkan judul "Shopping List" di aplikasi Anda.

Text: Widget Text digunakan untuk menampilkan teks. Anda menggunakannya untuk menampilkan teks "PBP Shop" di tengah aplikasi Anda.

Column: Column adalah widget yang digunakan untuk mengatur widget-widget anak secara vertikal. Anda menggunakannya untuk menyusun tampilan yang berisi judul "PBP Shop" dan kartu-kartu item.

GridView.count: GridView.count adalah widget yang digunakan untuk membuat grid dengan jumlah baris dan kolom yang ditentukan. Anda menggunakannya untuk membuat grid yang berisi kartu-kartu item yang dijual.

Padding: Padding adalah widget yang digunakan untuk menambahkan padding (margen) di sekitar widget anaknya. Anda menggunakannya untuk memberikan ruang di sekitar judul dan grid dalam Column.

ShopCard: Ini adalah widget yang Anda buat sendiri. Ini adalah widget stateless yang digunakan untuk menampilkan kartu item yang dijual. ShopCard memiliki sejumlah properti seperti item (objek ShopItem) dan menggunakan Material, InkWell, Container, Icon, Text, dan lain-lain untuk menampilkan kartu dengan ikon dan teks.

InkWell: InkWell adalah widget yang memberikan respons ketika ditekan, seperti menampilkan Snackbar. Anda menggunakannya di dalam ShopCard untuk menangani tindakan ketika kartu ditekan.

SnackBar: SnackBar adalah widget yang digunakan untuk menampilkan pesan singkat pada bagian bawah layar. Anda menggunakannya dalam InkWell untuk menampilkan pesan ketika kartu ditekan.

Icons: Icons adalah kumpulan ikon bawaan dalam Flutter yang digunakan untuk menampilkan ikon-ikon pada kartu item.

ListView: ListView adalah widget yang digunakan untuk membuat daftar gulir vertikal. Namun, dalam tutorial ini, Anda menggunakan SingleChildScrollView untuk memberikan kemampuan gulir pada tampilan Anda.

3. Berikut tahap-tahap step by step :
Tahap 1: Membuat Proyek Flutter
Buka Terminal atau Command Prompt.
Masuk ke direktori tempat Anda ingin menyimpan proyek Flutter.
Buat proyek Flutter baru dengan perintah flutter create tugas_list dan masuk ke direktori proyek tersebut.
Jalankan proyek Flutter dengan perintah flutter run.
Tahap 2: Merapikan Struktur Proyek
Buat file baru bernama "menu.dart" di direktori "tugas_list/lib" dan tambahkan import 'package:flutter/material.dart'; di baris pertama.
Pindahkan (cut) kode dari "main.dart" yang berisi class "MyHomePage" ke "menu.dart".
Tambahkan import 'package:tugas_list/menu.dart'; di awal "main.dart" untuk mengatasi error.
Jalankan proyek Anda untuk memastikan tidak ada masalah.
Tahap 3: Membuat Widget Sederhana pada Flutter
Buka "main.dart" dan ubah tema aplikasi menjadi indigo dengan mengubah kode pada bagian "colorScheme".
Ubah widget halaman menu menjadi stateless dengan menghapus "MyHomePage(title: 'Flutter Demo Home Page')" dan mengubah kode pada "menu.dart".
Tambahkan teks dan kartu item dengan mengdefinisikan tipe "ShopItem" dan menambahkan item ke dalam list.
Dalam widget "build", tambahkan tampilan tipe "Scaffold" yang berisi judul, teks, dan grid untuk menampilkan kartu item.
Buat widget stateless baru "ShopCard" untuk menampilkan kartu item dengan ikon dan teks, serta menampilkan pesan saat kartu ditekan.