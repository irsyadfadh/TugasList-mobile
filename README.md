# tugas_list (Tugas 7)

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

# Tugas 8 :
1. Navigator.push() dan Navigator.pushReplacement() adalah dua metode yang digunakan dalam Flutter untuk berpindah antar halaman (routes) di dalam aplikasi. Berikut adalah perbedaan utama antara keduanya:

Navigator.push():

Metode ini digunakan untuk menambahkan halaman baru di atas tumpukan (stack) navigasi.
Halaman yang baru ditambahkan akan menjadi bagian dari tumpukan, dan pengguna dapat kembali ke halaman sebelumnya dengan menekan tombol kembali.
Ini cocok digunakan ketika Anda ingin menambahkan halaman ke dalam tumpukan navigasi.
Contoh penggunaan Navigator.push():

onPressed: () {
  Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => HalamanBaru()),
  );
}
Navigator.pushReplacement():

Metode ini digunakan untuk menambahkan halaman baru di atas tumpukan dan pada saat yang bersamaan menggantikan halaman yang saat ini ditampilkan dengan halaman baru.
Ini berguna ketika Anda ingin mengganti halaman saat ini dengan halaman yang baru dan menghapus halaman sebelumnya dari tumpukan.
Misalnya, digunakan ketika Anda ingin mengganti halaman login dengan halaman utama setelah pengguna berhasil login.
Contoh penggunaan Navigator.pushReplacement():

onPressed: () {
  Navigator.pushReplacement(
    context,
    MaterialPageRoute(builder: (context) => HalamanUtama()),
  );
}
Dalam contoh di atas, HalamanBaru() dan HalamanUtama() adalah widget yang mewakili halaman baru yang akan ditampilkan setelah tombol ditekan. Pilihan antara Navigator.push() dan Navigator.pushReplacement() tergantung pada kebutuhan navigasi aplikasi.

2. Di Flutter, tentunya ada beberapa layout widget yang memungkinkan mengatur tata letak (layout) dari elemen-elemen UI dalam aplikasi . Berikut adalah beberapa layout widget yang umum digunakan beserta konteks penggunaannya:

- Container:

Container adalah widget yang dapat mengandung widget lainnya dan memberikan kontrol yang sangat baik terhadap properti-properti seperti padding, margin, dan dekorasi.
Cocok digunakan untuk mengelompokkan widget lainnya dan memberikan tata letak dasar.
Contoh penggunaan Container:

Container(
  padding: EdgeInsets.all(16.0),
  margin: EdgeInsets.symmetric(vertical: 8.0),
  decoration: BoxDecoration(
    color: Colors.blue,
    borderRadius: BorderRadius.circular(8.0),
  ),
  child: Text('Ini adalah Container'),
)
- Row dan Column:

Row digunakan untuk menempatkan widget dalam satu baris secara horizontal, sedangkan Column digunakan untuk menempatkan widget dalam satu kolom secara vertikal.
Cocok digunakan untuk menyusun widget-widget dalam susunan baris atau kolom.
Contoh penggunaan Row:

Row(
  children: [
    Icon(Icons.star),
    Text('Bintang'),
  ],
)
Contoh penggunaan Column:

Column(
  children: [
    Text('Baris 1'),
    Text('Baris 2'),
  ],
)
- ListView:

ListView adalah widget untuk menampilkan daftar item secara bergulir (scrollable).
Cocok digunakan ketika Anda memiliki daftar item yang mungkin memerlukan pengguliran.
Contoh penggunaan ListView:

ListView(
  children: [
    ListTile(
      title: Text('Item 1'),
    ),
    ListTile(
      title: Text('Item 2'),
    ),
    // ...
  ],
)

- Stack:

Stack digunakan untuk menempatkan widget di atas satu sama lain.
Cocok digunakan ketika Anda ingin menumpuk widget dan mengontrol penempatan relatif mereka.
Contoh penggunaan Stack:

Stack(
  children: [
    Positioned(
      left: 10.0,
      top: 10.0,
      child: Text('Atas Kiri'),
    ),
    Positioned(
      right: 10.0,
      bottom: 10.0,
      child: Text('Bawah Kanan'),
    ),
  ],
)

- Expanded dan Flexible:
Expanded dan Flexible digunakan untuk mengontrol ruang yang diambil oleh widget di dalam Row atau Column.
Cocok digunakan ketika Anda ingin memberikan bobot atau proporsi tertentu pada widget di dalam tata letak.
Contoh penggunaan Expanded:

Row(
  children: [
    Expanded(
      child: Container(color: Colors.red),
    ),
    Expanded(
      child: Container(color: Colors.blue),
    ),
  ],
)
Contoh penggunaan Flexible:

Row(
  children: [
    Flexible(
      flex: 2,
      child: Container(color: Colors.red),
    ),
    Flexible(
      flex: 1,
      child: Container(color: Colors.blue),
    ),
  ],
)
Setiap layout widget di atas memiliki kegunaan dan konteks penggunaan yang spesifik tergantung pada desain UI yang diinginkan. Kombinasikan dan sesuaikan widget-widget ini sesuai dengan kebutuhan aplikasi Flutter Anda.

3. Dalam Tugas 8 kali ini, beberapa elemen input pada form yang saya gunakan yaitu:

TextFormField:

Penggunaan: Untuk memasukkan teks atau string, seperti nama produk, harga, dan deskripsi.
Contoh Penggunaan:

TextFormField(
  decoration: InputDecoration(
    hintText: "Nama Produk",
    labelText: "Nama Produk",
    border: OutlineInputBorder(
      borderRadius: BorderRadius.circular(5.0),
    ),
  ),
  onChanged: (String? value) {
    setState(() {
      _name = value!;
    });
  },
  validator: (String? value) {
    if (value == null || value.isEmpty) {
      return "Nama tidak boleh kosong!";
    }
    return null;
  },
)

ElevatedButton:

Penggunaan: Untuk membuat tombol yang memberikan umpan balik visual ketika ditekan.
Contoh Penggunaan:

ElevatedButton(
  onPressed: () {
    if (_formKey.currentState!.validate()) {
      // Tambahkan logika simpan data atau tampilkan pesan
    }
  },
  child: const Text(
    "Save",
    style: TextStyle(color: Colors.white),
  ),
)

AlertDialog:

Penggunaan: Untuk menampilkan dialog pop-up sebagai umpan balik setelah menekan tombol save.
Contoh Penggunaan:

showDialog(
  context: context,
  builder: (context) {
    return AlertDialog(
      title: const Text('Produk berhasil tersimpan'),
      content: SingleChildScrollView(
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text('Nama: $_name'),
            // TODO: Munculkan value-value lainnya
          ],
        ),
      ),
      actions: [
        TextButton(
          child: const Text('OK'),
          onPressed: () {
            Navigator.pop(context);
          },
        ),
      ],
    );
  },
);

Drawer:

Penggunaan: Untuk menampilkan menu drawer yang muncul dari sisi kiri layar.
Contoh Penggunaan:

Drawer(
  child: ListView(
    children: [
      const DrawerHeader(
        // TODO: Bagian drawer header
      ),
      // TODO: Bagian routing
    ],
  ),
)

ListView:

Penggunaan: Untuk menampilkan daftar item di dalam drawer.
Contoh Penggunaan:

ListView(
  children: [
    ListTile(
      leading: const Icon(Icons.home_outlined),
      title: const Text('Halaman Utama'),
      onTap: () {
        Navigator.pushReplacement(
          context,
          MaterialPageRoute(
            builder: (context) => MyHomePage(),
          ),
        );
      },
    ),
    // ...
  ],
)
Penggunaan elemen-elemen input ini mencakup berbagai jenis masukan yang umum digunakan dalam pengembangan aplikasi, seperti teks, tombol, dan menu navigasi. Elemen-elemen ini memberikan pengalaman interaktif dan responsif kepada pengguna dalam aplikasi Flutter

4. berikut adalah penerapan Clean Architecture dalam Flutter:

Entities (Domain):

Deskripsi: Berisi objek-objek dan aturan bisnis.
Implementasi:

// entities/product.dart
class Product {
  final String id;
  final String name;
  final double price;
  
  Product({required this.id, required this.name, required this.price});
}
Use Cases (Interactors):

Deskripsi: Berisi aturan bisnis aplikasi.
Implementasi:

// usecases/add_product_usecase.dart
import 'package:myapp/entities/product.dart';

class AddProductUseCase {
  void execute(Product product) {
    // Logika bisnis untuk menambahkan produk
  }
}
Interface Adapters (UI):

Deskripsi: Berisi implementasi UI dan koneksi ke Use Cases.
Implementasi:

// ui/product_list_screen.dart
import 'package:flutter/material.dart';
import 'package:myapp/entities/product.dart';
import 'package:myapp/usecases/add_product_usecase.dart';

class ProductListScreen extends StatelessWidget {
  final AddProductUseCase addProductUseCase;

  ProductListScreen(this.addProductUseCase);

  @override
  Widget build(BuildContext context) {
    // Implementasi UI untuk menampilkan daftar produk
  }
}
Frameworks & Drivers (Data):

Deskripsi: Berisi implementasi teknologi-spesifik seperti penyimpanan data.
Implementasi:

// data/product_repository.dart
import 'package:myapp/entities/product.dart';

class ProductRepository {
  List<Product> getProducts() {
    // Logika untuk mengambil produk dari sumber data
  }

  void addProduct(Product product) {
    // Logika untuk menambahkan produk ke sumber data
  }
}
Dependency Rule:

Deskripsi: Aturan yang mengatur arah hubungan antar lapisan.
Implementasi:
Pastikan setiap lapisan hanya bergantung pada lapisan yang lebih dalam (Entities → Use Cases → Interface Adapters → Frameworks & Drivers).
Dependency Injection:

Deskripsi: Teknik menyediakan objek-objek yang dibutuhkan suatu kelas.
Implementasi:
Gunakan pustaka atau alat manajemen kebergantungan seperti get_it atau provider untuk mengimplementasikan dependency injection.
Dengan struktur ini, Anda dapat mengganti implementasi di satu lapisan tanpa memengaruhi lapisan lainnya, memudahkan pengujian, dan memastikan bahwa aturan bisnis tetap terisolasi di lapisan Use Cases. Semua ini membantu menciptakan proyek yang bersih, terstruktur, dan mudah dipelihara.

5. Berikut adalah panduan langkah-demi-langkah untuk mengimplementasikan checklist tutorial di atas:

- Membuat Drawer Menu (left_drawer.dart):
a. Buat File left_drawer.dart:
Buat berkas baru dengan nama left_drawer.dart dalam direktori widgets.

b. Tambahkan Kode untuk Drawer:
Tambahkan kode untuk membuat Drawer beserta isinya ke dalam berkas left_drawer.dart.

c. Impor Halaman yang Akan Diarahkan:
Impor halaman-halaman yang akan diarahkan pada bagian TODO: Impor halaman ShopFormPage jika sudah dibuat.

d. Tambahkan Routing ke Drawer:
Tambahkan routing untuk mengarahkan ke halaman-halaman yang diinginkan, seperti MyHomePage dan ShopFormPage.

e. Hiasi Drawer dengan Header:
Hiasi drawer dengan menambahkan dekorasi dan teks pada bagian TODO: Bagian drawer header.

f. Panggil Drawer di Halaman yang Diinginkan:
Panggil drawer yang telah dibuat di halaman yang ingin ditambahkan drawer, misalnya di menu.dart.

- Membuat Form dan Elemen Input (shoplist_form.dart):
a. Buat File shoplist_form.dart:
Buat berkas baru dengan nama shoplist_form.dart dalam direktori lib.

b. Buat Class ShopFormPage:
Buat class ShopFormPage yang merupakan StatefulWidget.

c. Tambahkan Form dan SingleChildScrollView:
Tambahkan widget Form dan SingleChildScrollView ke dalam build method.

d. Buat GlobalKey untuk Form:
Buat GlobalKey<'FormState'> sebagai atribut untuk form key.

e. Tambahkan TextFormField:
Tambahkan TextFormField untuk menerima input nama produk, harga, dan deskripsi.

f. Validasi Input:
Tambahkan validasi untuk memastikan input sesuai dengan kebutuhan, seperti tidak boleh kosong atau harus berupa angka.

g. Tambahkan Tombol Save:
Tambahkan tombol ElevatedButton untuk menyimpan data. Saat ditekan, validasi form akan dijalankan.

h. Tampilkan AlertDialog:
Jika form valid, tampilkan AlertDialog sebagai umpan balik, menampilkan data yang dimasukkan.

i. Reset Form Setelah Disimpan:
Reset form setelah data disimpan.

- Navigasi pada Tombol (menu.dart):
a. Modifikasi Widget ShopItem:
Modifikasi widget ShopItem pada menu.dart untuk menambahkan navigasi ke halaman yang sesuai saat tombol ditekan.

b. Gunakan Navigator.push:
Gunakan Navigator.push untuk melakukan navigasi ke ShopFormPage.

- Refactoring File (screens Folder):
a. Buat Folder screens:
Buat folder baru dengan nama screens dalam direktori lib.

b. Pindahkan File ke Folder screens:
Pindahkan file menu.dart dan shoplist_form.dart ke dalam folder screens. Gunakan fitur refactoring IDE atau text editor.

- Pemanggilan Drawer:
a. Panggil Drawer di Halaman yang Diinginkan:
Panggil drawer yang telah dibuat di halaman yang ingin ditambahkan drawer, misalnya di menu.dart.

- Menjalankan Aplikasi:
a. Jalankan Aplikasi:
Pastikan semua perubahan sudah disimpan dan jalankan aplikasi Flutter Anda untuk melihat hasilnya.

- Penyelesaian TODO:
a. Lengkapi TODO:
Pastikan untuk menyelesaikan semua bagian TODO yang dijelaskan dalam tutorial.