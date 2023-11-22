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

# Tugas 9
1. Ya, bisa saja melakukan pengambilan data JSON tanpa membuat model terlebih dahulu. Ini sering disebut sebagai "parsing JSON secara dinamis" atau "dynamic JSON parsing". Dalam Flutter, kita dapat menggunakan tipe data yang dinamis seperti Map<String, dynamic> atau List<dynamic> untuk menangani objek JSON tanpa membuat model khusus.

Namun, apakah lebih baik atau tidak membuat model tergantung pada kompleksitas data yang diambil dan bagaimana data tersebut akan digunakan dalam aplikasi Anda. Berikut beberapa pertimbangan:

Kelebihan Penggunaan Model:
Struktur yang Jelas: Membuat model memberikan struktur yang jelas dan terdokumentasi untuk data yang diharapkan. Ini membuat kode lebih mudah dimengerti oleh pengembang lain yang bekerja pada proyek tersebut.

Validasi Tipe Data: Model memungkinkan validasi tipe data, sehingga jika struktur JSON tidak sesuai dengan yang diharapkan, kita dapat dengan mudah menangkap kesalahan tersebut pada waktu kompilasi atau runtime.

Auto-completion dan Refactoring: Dengan model, Anda dapat memanfaatkan fitur auto-completion dan refactoring dari editor kode Anda (seperti VS Code atau Android Studio). Ini dapat membuat pengembangan lebih efisien.

Kelebihan Pengambilan Tanpa Model:
Fleksibilitas: Jika struktur data sering berubah atau tidak terlalu kompleks, bisa lebih fleksibel untuk melakukan parsing dinamis tanpa model. Ini mengurangi overhead dalam pembuatan model baru setiap kali struktur data berubah.

Pengembangan Cepat: Pada beberapa situasi, terutama dalam pengembangan prototipe atau proyek kecil, pengambilan tanpa model bisa mempercepat pengembangan.

Kapan Memilih Salah Satu Pendekatan:
Gunakan Model Jika Struktur Data Tetap Stabil: Jika struktur data yang diambil dari server stabil dan cenderung tidak berubah sering, membuat model biasanya merupakan pilihan yang lebih baik.

Gunakan Pengambilan Tanpa Model Jika Struktur Data Dinamis: Jika struktur data bisa berubah secara dinamis atau jika hanya membutuhkan beberapa atribut dari data yang diambil, bisa lebih praktis untuk melakukan parsing dinamis.

Kombinasikan Kedua Pendekatan: Kadang-kadang, bisa menjadi pilihan terbaik untuk menggunakan model untuk bagian inti aplikasi yang membutuhkan data terstruktur dan menggunakan parsing dinamis untuk kasus-kasus khusus atau data tambahan yang mungkin berubah.

Pilihan antara keduanya tergantung pada kebutuhan spesifik proyek dan preferensi pengembang. Yang penting adalah memilih pendekatan yang paling sesuai untuk kebutuhan aplikasi dan memastikan keterbacaan dan keberlanjutan kode.

2. CookieRequest adalah kelas yang bertanggung jawab untuk mengelola permintaan HTTP, terutama terkait dengan autentikasi dan pengelolaan cookies. Fungsi utama dari CookieRequest dalam konteks tutorial yang diberikan adalah untuk menangani proses autentikasi dengan backend Django. Berikut adalah beberapa fungsi utama dari CookieRequest:

Autentikasi:

CookieRequest mengelola permintaan login dan logout ke server Django. Saat pengguna melakukan login, CookieRequest membuat permintaan ke endpoint login Django untuk memverifikasi kredensial dan memperoleh cookies sesi. Saat pengguna logout, CookieRequest mengirim permintaan logout ke server Django.
Cookies:

CookieRequest menyimpan dan memperbarui cookies sesi yang diperoleh dari server Django. Cookies ini kemudian digunakan untuk otentikasi setiap permintaan ke endpoint yang memerlukan autentikasi. Memastikan bahwa cookies sesi disimpan dan diperbarui adalah kunci untuk mempertahankan keadaan autentikasi pengguna di seluruh sesi aplikasi.
Permintaan HTTP:

CookieRequest mengatur dan mengirim permintaan HTTP dengan menyertakan cookies sesi pada setiap permintaan. Ini memastikan bahwa setiap permintaan ke server Django dilakukan dengan konteks autentikasi yang sesuai.
Mengapa instance CookieRequest perlu dibagikan ke semua komponen di aplikasi Flutter? Ini terkait dengan prinsip manajemen keadaan di Flutter. Saat kita ingin menyimpan dan berbagi keadaan (state) yang sama di antara beberapa widget atau bagian aplikasi, kita menggunakan mekanisme seperti Provider.

Berikut adalah alasan mengapa CookieRequest perlu dibagikan:

Global State:

CookieRequest menyimpan informasi autentikasi global yang dibutuhkan oleh seluruh aplikasi. Memiliki satu instance yang dibagikan memastikan bahwa keadaan autentikasi dapat diakses dan diperbarui secara konsisten di seluruh aplikasi.
Konsistensi Keadaan:

Dengan menggunakan satu instance CookieRequest, kita dapat memastikan bahwa keadaan autentikasi yang dikelola oleh CookieRequest konsisten di seluruh aplikasi. Jika ada perubahan keadaan, perubahan tersebut dapat segera terlihat di seluruh widget yang menggunakan instance yang sama.
Efisiensi dan Kode yang Bersih:

Dengan menggunakan Provider atau mekanisme serupa, kita dapat menghindari membuat instance CookieRequest baru di setiap widget yang membutuhkannya. Ini meningkatkan efisiensi dan menjadikan kode lebih bersih.
Pembaruan Otomatis Widget:

Widget yang menggunakan instance CookieRequest akan secara otomatis memperbarui tampilan mereka ketika keadaan autentikasi berubah. Ini karena widget tersebut menjadi pengamat (observer) terhadap perubahan pada instance yang dibagikan.
Contoh implementasi ini dapat ditemukan pada potongan kode di tutorial di mana Provider digunakan untuk menyediakan dan membagikan instance CookieRequest ke seluruh widget dalam pohon widget Flutter.

3. Pengambilan data dari JSON hingga ditampilkan pada Flutter melibatkan beberapa langkah. Dalam konteks tutorial yang telah diberikan, langkah-langkahnya dapat dijelaskan sebagai berikut:

Menentukan Endpoint dan Struktur JSON di Django:

Pada sisi server (Django), Anda perlu memiliki endpoint (URL) yang menyediakan data dalam format JSON. Pastikan struktur JSON yang dihasilkan oleh server sesuai dengan kebutuhan aplikasi Flutter.
Membuat Model Dart Sesuai dengan Struktur JSON:

Jika data yang diambil memiliki struktur yang tetap, sangat disarankan untuk membuat model Dart yang sesuai dengan struktur JSON. Ini dapat dilakukan dengan menggunakan alat pembuat kode seperti Quicktype atau secara manual sesuai dengan struktur JSON yang diperoleh dari server Django.
Menambahkan Dependensi HTTP pada Flutter:

Untuk melakukan permintaan HTTP ke server Django, Anda perlu menambahkan dependensi HTTP ke proyek Flutter. Dalam tutorial tersebut, dependensi yang digunakan adalah http. Anda dapat menambahkannya ke file pubspec.yaml:

yaml
Copy code
dependencies:
  http: ^0.14.0
Kemudian, jalankan perintah flutter pub get untuk mengunduh dependensi baru.

Membuat Fungsi untuk Mengambil Data dari Django:

Buatlah fungsi atau metode yang akan melakukan permintaan HTTP ke endpoint Django menggunakan package http. Fungsi ini akan mengambil data dalam format JSON dari server.

dart
Copy code
Future<"List<"Product>> fetchProduct() async {
    var url = Uri.parse('http://<"URL_APP_KAMU>/json/');
    var response = await http.get(url);

    if (response.statusCode == 200) {
        // Jika permintaan sukses, lakukan parsing JSON
        var data = jsonDecode(utf8.decode(response.bodyBytes));
        List<Product> productList = [];
        for (var item in data) {
            productList.add(Product.fromJson(item));
        }
        return productList;
    } else {
        // Jika permintaan gagal, lempar eksepsi atau tangani dengan cara lain
        throw Exception('Gagal mengambil data');
    }
}
Menampilkan Data dalam Widget Flutter:

Gunakan widget FutureBuilder untuk menangani proses asinkron dari pengambilan data. Widget ini memungkinkan Anda menangani kasus-kasus sukses, kegagalan, dan loading.

dart
Copy code
FutureBuilder(
  future: fetchProduct(),
  builder: (context, AsyncSnapshot snapshot) {
    if (snapshot.connectionState == ConnectionState.waiting) {
      // Tampilkan indikator loading jika masih dalam proses pengambilan data
      return CircularProgressIndicator();
    } else if (snapshot.hasError) {
      // Tangani error jika terjadi kesalahan dalam pengambilan data
      return Text('Error: ${snapshot.error}');
    } else {
      // Tampilkan data jika pengambilan data sukses
      List<"Product"> productList = snapshot.data;
      return ListView.builder(
        itemCount: productList.length,
        itemBuilder: (context, index) {
          return ListTile(
            title: Text(productList[index].name),
            subtitle: Text(productList[index].description),
            // Tambahan atribut lain sesuai kebutuhan
          );
        },
      );
    }
  },
)
Dengan langkah-langkah di atas, Anda dapat membuat aplikasi Flutter yang mengambil data dari Django melalui permintaan HTTP, memproses data JSON, dan menampilkannya dalam widget Flutter. Pastikan untuk menyesuaikan URL dan struktur data sesuai dengan proyek Django Anda.
4. Mekanisme autentikasi dari input data akun pada Flutter ke Django hingga tampilnya menu pada Flutter dapat diuraikan sebagai berikut:

Pada Bagian Django (Backend):

Pembuatan Aplikasi Authentication Django:

Buatlah sebuah aplikasi Django yang bertanggung jawab untuk menangani proses autentikasi. Dalam contoh ini, aplikasi tersebut dinamakan "authentication".
Konfigurasi Django untuk CORS:

Penggunaan library django-cors-headers dan konfigurasi di settings.py untuk mengizinkan permintaan lintas domain dari aplikasi Flutter.
Implementasi Fungsi Login:

Buatlah fungsi view pada authentication/views.py untuk menangani permintaan login dari Flutter.
Fungsi ini menerima data akun (username dan password) dari Flutter, menggunakan fungsi authenticate dari Django untuk memeriksa kredensial, dan jika berhasil, melakukan login menggunakan auth_login.
Implementasi Fungsi Logout:

Buatlah fungsi view untuk logout pada authentication/views.py yang akan memanggil fungsi auth_logout untuk melakukan proses logout.
Konfigurasi URL Routing:

Tambahkan URL routing untuk fungsi-fungsi login dan logout di authentication/urls.py.
CORS dan Pengaturan Keamanan:

Tambahkan pengaturan keamanan seperti CORS_ALLOW_ALL_ORIGINS, CSRF_COOKIE_SECURE, SESSION_COOKIE_SECURE, dan lainnya di settings.py untuk memastikan keamanan komunikasi antara Flutter dan Django.
Pada Bagian Flutter (Frontend):

Integrasi dengan Django menggunakan Package pbp_django_auth:

Instalasi package pbp_django_auth melalui pubspec.yaml pada proyek Flutter.
Penggunaan provider untuk menyediakan instance CookieRequest ke semua komponen aplikasi.
Pembuatan Halaman Login Flutter:

Pembuatan halaman login.dart di Flutter yang menggunakan CookieRequest untuk mengirim permintaan login ke Django.
Penggunaan TextEditingController untuk mengambil input dari pengguna.
Penggunaan package http untuk melakukan permintaan HTTP ke Django.
Penanganan Respons dari Django:

Penggunaan FutureBuilder untuk menangani respons asinkron dari Django setelah proses login.
Menampilkan pesan sukses atau gagal menggunakan SnackBar dan melakukan redireksi ke halaman yang sesuai setelah login berhasil.
Integrasi dengan Menu Flutter:

Pembuatan menu pada aplikasi Flutter yang dapat diakses setelah login.
Penambahan fungsi dan UI untuk melakukan logout dari aplikasi.
Pembuatan Model:

Penggunaan situs web Quicktype atau pendekatan lainnya untuk membuat model Dart yang sesuai dengan struktur JSON yang diberikan oleh Django.
Pengambilan dan Penampilan Data:

Penggunaan package http untuk mengambil data produk dari Django setelah login.
Penggunaan FutureBuilder untuk menangani respons asinkron dan menampilkan data produk pada halaman yang sesuai.
Penggunaan Form Flutter:

Penggunaan form Flutter untuk menambahkan produk baru dengan mengirimkan data ke Django menggunakan permintaan POST.
Penggunaan SnackBar untuk memberikan umpan balik setelah produk berhasil atau gagal disimpan.
Dengan cara ini, aplikasi Flutter dan Django saling berinteraksi melalui mekanisme autentikasi, dan data dapat diambil dan ditampilkan pada aplikasi Flutter sesuai dengan otorisasi pengguna.

5. Berikut adalah daftar widget yang digunakan dalam tugas tersebut beserta penjelasan fungsinya:

Pada Bagian Flutter (Frontend):
MyApp Widget:

Fungsi: Merupakan widget utama yang membungkus seluruh aplikasi Flutter.
Penjelasan: MaterialApp adalah widget utama yang menyediakan elemen-elemen dasar seperti tema, judul, dan navigasi.
Provider Widget:

Fungsi: Membungkus aplikasi dengan Provider untuk menyediakan instance CookieRequest ke semua child widgets.
Penjelasan: Provider adalah bagian dari package provider yang digunakan untuk mengelola state dan menyediakan objek tertentu (dalam hal ini, CookieRequest) ke dalam widget-tree.
LoginApp dan LoginPage Widgets:

Fungsi: Mewakili aplikasi login dan halaman login.
Penjelasan: MaterialApp, Scaffold, dan TextFormField adalah widget untuk membangun antarmuka pengguna login. Provider.of<CookieRequest>(context) digunakan untuk mendapatkan instance CookieRequest dari Provider.
FutureBuilder Widget:

Fungsi: Menangani data yang berasal dari proses asinkron (seperti permintaan HTTP).
Penjelasan: Menggunakan FutureBuilder untuk menampilkan respons setelah login. Memberikan indikator progres selama data diambil.
ProductPage Widget:

Fungsi: Menampilkan daftar produk.
Penjelasan: MaterialApp, Scaffold, dan FutureBuilder digunakan untuk menampilkan daftar produk dari Django. Produk ditampilkan dalam ListView.builder.
LeftDrawer Widget:

Fungsi: Menampilkan drawer dengan menu navigasi.
Penjelasan: Drawer adalah widget yang menyediakan navigasi menu kiri. ListTile digunakan untuk menambahkan opsi navigasi, seperti "Daftar Produk".
ListTile Menu:

Fungsi: Mewakili item menu dalam drawer.
Penjelasan: ListTile berisi ikon dan teks untuk setiap opsi navigasi. Digunakan untuk membuka halaman produk atau melakukan logout.
ElevatedButton:

Fungsi: Tombol untuk memulai proses login.
Penjelasan: Menggunakan ElevatedButton untuk memulai permintaan login ke Django. Menggunakan CookieRequest untuk berinteraksi dengan backend.
TextFormField:

Fungsi: Widget input untuk memasukkan username dan password.
Penjelasan: Digunakan untuk mengambil input pengguna (username dan password) saat login.
Pada Bagian Django (Backend):
login Function View:

Fungsi: Memproses permintaan login dari Flutter.
Penjelasan: Menerima data akun (username dan password) dari Flutter, menggunakan fungsi authenticate dari Django untuk memeriksa kredensial, dan memberikan respons JSON.
logout Function View:

Fungsi: Memproses permintaan logout dari Flutter.
Penjelasan: Menggunakan fungsi auth_logout untuk melakukan proses logout dan memberikan respons JSON.
create_product_flutter Function View:

Fungsi: Memproses permintaan penambahan produk dari Flutter.
Penjelasan: Menerima data produk, membuat objek Product baru, dan menyimpannya ke dalam database.
URL Routing:

Fungsi: Menyusun URL routing untuk fungsi-fungsi view.
Penjelasan: URL routing pada Django untuk menghubungkan endpoint dengan fungsi-fungsi view yang sesuai.
Semua widget dan fungsi ini bekerja bersama untuk mengimplementasikan integrasi autentikasi Django-Flutter beserta fitur lainnya seperti penambahan produk dan logout.

6. Implementasi Checklist pada Django:

Buatlah django-app authentication:

Gunakan perintah python manage.py startapp authentication.
Tambahkan authentication ke INSTALLED_APPS pada settings.py:

Buka settings.py pada proyek Django dan tambahkan 'authentication' pada variabel INSTALLED_APPS.
Instalasi dan konfigurasi CORS Headers:

Install library dengan perintah pip install django-cors-headers.
Tambahkan 'corsheaders' ke INSTALLED_APPS.
Tambahkan corsheaders.middleware.CorsMiddleware ke MIDDLEWARE.
Tambahkan variabel-variabel CORS pada settings.py.
Buat view untuk login:

Buat file views.py dalam folder authentication dan buat view login sesuai dengan yang dijelaskan.
Pastikan view tersebut di-dekorasi dengan @csrf_exempt.
Buat file urls.py pada folder authentication:

Buat file baru dengan nama urls.py dalam folder authentication dan tambahkan routing untuk view login.
Tambahkan path untuk authentication.urls di shopping_list/urls.py:

Buka urls.py pada proyek utama dan tambahkan path untuk authentication.urls.
Implementasi Checklist pada Flutter:

Instalasi Package Flutter:

Jalankan perintah flutter pub add provider dan flutter pub add pbp_django_auth untuk menginstal package yang diperlukan.
Modifikasi root widget untuk menyediakan CookieRequest:

Buka file main.dart dan ubah widget MyApp untuk menyediakan instance CookieRequest melalui Provider.
Buat file login.dart dalam folder screens:

Buat file login.dart yang berisi widget untuk halaman login sesuai dengan yang dijelaskan.
Hubungkan login.dart dengan CookieRequest:

Pastikan file login.dart menggunakan CookieRequest dari Provider menggunakan context.watch<CookieRequest>().
Tambahkan routing untuk ProductPage:

Ubah perintah Navigator.pushReplacement pada login.dart untuk mengarahkan ke halaman ProductPage.
Buat halaman ProductPage dan LeftDrawer:

Buat file list_product.dart dalam folder screens untuk menampilkan daftar produk.
Buat file left_drawer.dart dalam folder widgets untuk membuat drawer dengan menu navigasi.
Tambahkan path untuk list_product.dart di left_drawer.dart:

Di dalam left_drawer.dart, tambahkan path untuk ProductPage sehingga menu "Daftar Produk" dapat memicu navigasi.
Tambahkan dependensi HTTP:

Jalankan perintah flutter pub add http untuk menambahkan package http.
Buat file list_product.dart untuk fetch data dari Django:

Buat file list_product.dart dalam folder screens untuk menampilkan data produk dari Django.
Tambahkan path untuk create_product_flutter di main/urls.py di Django:

Di Django, buat view create_product_flutter dan tambahkan path-nya ke dalam urls.py.
Hubungkan shoplist_form.dart dengan Django:

Hubungkan form Flutter dengan Django untuk membuat produk baru.
Implementasi Fitur Logout:

Di Django, buat view untuk logout dan tambahkan pathnya ke dalam urls.py.
Di Flutter, tambahkan fungsi untuk logout pada file shop_card.dart.
Pastikan Anda menggantikan placeholder seperti <APP_URL_KAMU> dengan URL atau nama proyek Anda. Periksa instruksi pada tutorial untuk rincian lebih lanjut dan pastikan mengikuti setiap langkah dengan teliti. Selain itu, pastikan bahwa semua dependensi dan package terinstal dengan benar pada proyek Flutter Anda.