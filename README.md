# Game Store – Flutter

## 📝 Deskripsi Singkat

Game Store merupakan aplikasi berbasis Flutter yang menampilkan daftar game dari API FreeToGame. Aplikasi ini menyediakan halaman Home yang berisi daftar game lengkap dengan thumbnail, judul, dan genre, serta halaman Detail untuk menampilkan informasi lebih lengkap mengenai game yang dipilih.

Aplikasi menggunakan named route untuk navigasi antarhalaman, model Dart untuk mengelola data JSON, serta permintaan HTTP untuk mengambil data dari API eksternal secara dinamis.

## ✨ Fitur Utama

- **Daftar Game:** Menampilkan daftar game beserta gambar thumbnail, judul, dan genre.
- **Search Bar:** Menyediakan kolom pencarian pada halaman Home.
- **Detail Game:** Menampilkan informasi game, persyaratan sistem minimum, screenshot, dan deskripsi.
- **Integrasi API:** Mengambil data daftar dan detail game dari FreeToGame.
- **Navigasi Named Route:** Memungkinkan pengguna berpindah dari halaman Home ke halaman Detail.
- **Loading dan Error Handling:** Menampilkan indikator loading serta pesan kesalahan ketika pengambilan data mengalami kendala.
- **Tampilan Dinamis:** Menggunakan `FutureBuilder`, `ListView.builder`, `Card`, dan berbagai widget Flutter untuk menyusun antarmuka.

## 🛠️ Teknologi yang Digunakan

- **Flutter & Dart** – Pengembangan aplikasi.
- **Material Design** – Komponen antarmuka pengguna.
- **http** – Mengirim permintaan HTTP ke API.
- **json_annotation** – Mendukung anotasi model JSON.
- **json_serializable** – Menghasilkan kode konversi JSON secara otomatis.
- **build_runner** – Menjalankan proses pembuatan kode hasil generator.
- **readmore** – Menampilkan deskripsi panjang dengan opsi untuk memperluas atau meringkas teks.
- **FreeToGame API** – Sumber data game.

## 📂 Struktur Proyek

```text
game_app/
├── lib/
│   ├── main.dart
│   ├── model/
│   │   ├── game.dart
│   │   ├── detailgame.dart
│   │   └── detailgame.g.dart
│   ├── view/
│   │   ├── home.dart
│   │   └── detail.dart
│   └── viewmodel/
│       └── fetchgame.dart
├── pubspec.yaml
└── README.md
```

## 🔄 Cara Kerja Aplikasi

1. Aplikasi dimulai dari `main.dart`, yang mengatur konfigurasi aplikasi dan named route.
2. Halaman Home memanggil fungsi `fetchGames()` untuk mengambil daftar game dari API.
3. Data JSON diubah menjadi objek `Game`, kemudian ditampilkan menggunakan `ListView.builder`.
4. Pengguna memilih salah satu game untuk membuka halaman Detail melalui `Navigator.pushNamed()`.
5. ID game dikirim sebagai argumen dan diterima melalui `ModalRoute`.
6. Halaman Detail mengambil data berdasarkan ID game menggunakan `fetchDataFromAPI()`.
7. Data diubah menjadi objek `DetailGame`, lalu ditampilkan dalam bentuk gambar, informasi persyaratan sistem, screenshot, dan deskripsi.
8. Pengguna dapat kembali ke halaman Home melalui tombol kembali dengan `Navigator.pop()`.

## 🌐 API yang Digunakan

Aplikasi menggunakan FreeToGame API untuk memperoleh informasi game.

- **Daftar game:** `https://www.freetogame.com/api/games`
- **Detail game:** `https://www.freetogame.com/api/game?id=ID_GAME`

Data dari API diterima dalam format JSON, kemudian diproses menjadi objek Dart agar dapat digunakan pada antarmuka aplikasi.

## 📚 Konsep Flutter yang Dipelajari

- **Desain GUI:** Menyusun tampilan menggunakan widget Flutter.
- **Named Route:** Mengatur navigasi antarhalaman melalui properti `routes` pada `MaterialApp`.
- **Navigator.pushNamed():** Membuka halaman berdasarkan nama route dan mengirim argumen.
- **Navigator.pop():** Kembali ke halaman sebelumnya.
- **JSON Deserialization:** Mengubah data JSON menjadi objek Dart menggunakan `fromJson()`.
- **JSON Serialization:** Mengubah objek Dart menjadi JSON menggunakan `toJson()`.
- **FutureBuilder:** Menampilkan UI berdasarkan status proses asynchronous.
- **ListView.builder dan Card:** Menampilkan daftar game secara terstruktur.
- **Pemisahan Model, View, dan ViewModel:** Memisahkan pengelolaan data, antarmuka, dan logika pengambilan data.

## 🚀 Cara Menjalankan

1. Pastikan Flutter SDK dan editor kode telah terpasang.
2. Buka proyek `game_app` melalui VS Code atau Android Studio.
3. Pastikan dependency berikut tersedia di `pubspec.yaml`:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     http: ^1.1.0
     json_annotation: ^4.9.0
     readmore: ^2.2.0

   dev_dependencies:
     flutter_test:
       sdk: flutter
     build_runner: ^2.4.8
     json_serializable: ^6.7.1
   ```

4. Unduh dependency dengan menjalankan:

   ```bash
   flutter pub get
   ```

5. Buat kode hasil JSON serialization menggunakan:

   ```bash
   dart run build_runner build
   ```

6. Pastikan perangkat atau emulator terhubung dan koneksi internet tersedia.
7. Jalankan aplikasi:

   ```bash
   flutter run
   ```

## 📌 Kesimpulan

Aplikasi Game Store menerapkan desain GUI, navigasi named route, dan integrasi API dalam pengembangan Flutter. Penggunaan model JSON mempermudah pengolahan data game, sedangkan `FutureBuilder` membantu menampilkan hasil pengambilan data secara asynchronous. Pemisahan kode ke dalam folder model, view, dan viewmodel juga membuat struktur proyek lebih terorganisasi dan mudah dikembangkan.
