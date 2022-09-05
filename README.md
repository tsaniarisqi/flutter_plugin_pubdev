# flutter_plugin_pubdev

A new Flutter project.

## Langkah 1: Buat Project Baru
Membuat projek flutter baru dengan nama flutter_plugin_pubdev
![Screenshoot flutter_plugin_dev](images/01.png)

## Langkah 2: Menambahkan Plugin
Menambahkan plugin auto_size_text, menggunakan perintah "flutter pub add auto_size_text". Jika plugin berhasil ditambahaknan maka pada file pubspec.yaml bagian dependencies akan muncul nama dan versi dari plugin. Pada projek ini menggunakan versi 3.0.0
![Screenshoot flutter_plugin_dev](images/02.png)

## Langkah 3: Buat file red_text_widget.dart
Membuat file baru pada folder lib dengan nama red_text_widget.dart.
![Screenshoot flutter_plugin_dev](images/03.png)

## Langkah 4: Tambah Widget AutoSizeText
Untuk menggunakan plugin auto_size_text, maka perlu untuk merubah kode return Container() menjadi seperti berikut.
```
return AutoSizeText(
      text,
      style: const TextStyle(color: Colors.red, fontSize: 14),
      maxLines: 2,
      overflow: TextOverflow.ellipsis,
);
```
![Screenshoot flutter_plugin_dev](images/04.png)
Hasil dari penambahan code tersebut akan terjadi error. Hal tersebut dikarenakan variabel text belum didefinisikan pada class RedTextWidget.

## Langkah 5: Buat Variabel text dan parameter di constructor
Untuk menghilangkan error pada langkah 4 maka perlu menambahkan variabel text dan menambahkan parameter pada constructor sebagai berikut:
```
final String text;

const RedTextWidget({Key? key, required this.text}) : super(key: key);
```
![Screenshoot flutter_plugin_dev](images/05.png)

## Langkah 6: Tambahkan widget di main.dart
Menambahkan dua widget berikut pada file main.dart
```
Container(
   color: Colors.yellowAccent,
   width: 50,
   child: const RedTextWidget(
	text: 'You have pushed the button this many times:',
	),
),
Container(
    color: Colors.greenAccent,
    width: 100,
    child: const Text(
	'You have pushed the button this many times:',
	),
),
```
- Widget pertama menggunakan RedTextWidget, hasilnya yaitu tulisan yang meimliki background berwarna kuning
- Untuk widget kedua hanya menggunakan text saja, hasilnya yaitu tulisan yang memiliki background berwarna hijau
![Screenshoot flutter_plugin_dev](images/06.png)

# Tugas Praktikum
2. Jelaskan maksud dari langkah 2 pada praktikum tersebut! 
   - Jawab: Maksud dari langkah 2 yaitu untuk menambahkan plugin auto_size_text ke dalam projek.
3. Jelaskan maksud dari langkah 5 pada praktikum tersebut!
   - Jawab:
   Maksud dari langkah 5, kode baris pertama merupakan inisialisasi dari variable text.
	```
	final String text;
	```
   - Kode baris kedua merupakan konstruktor yang ditambahkan parameter required this.text. 
	```
	const RedTextWidget({Key? key, required this.text}) : super(key: key);
	```
4. Pada langkah 6 terdapat dua widget yang ditambahkan, jelaskan fungsi dan perbedaannya!
   - Widget pertama menggunakan RedTextWidget. Pada class RedTextWidget terdapat style untuk merubah warna dan ukuran text, maxLines untuk mengatur berapa jumlah maximum dari baris yang akan ditampilkan dan overflow digunakan untuk menangani kalimat yang tidak dapat tampil pada aplikasi contoh pada projek ini menggunakan ellipsis. Hasilnya yaitu tulisan yang meimliki background berwarna kuning
   - Untuk widget kedua hanya menggunakan text saja, hasilnya yaitu tulisan yang memiliki background berwarna hijau 
5. Jelaskan maksud dari tiap parameter yang ada di dalam plugin auto_size_text berdasarkan tautan pada dokumentasi ini !

	| Parameter  | Description |
	| ------------- | ------------- |
	| Key*  | Mengontrol bagaimana satu widget menggantikan widget lain di pohon.  |
	| textKey  | Mengatur key untuk widget Teks yang dihasilkan  |
	| style* | Jika bukan null, style digunakan untuk teks ini |
	| minFontSize | Batasan ukuran teks minimum yang akan digunakan saat mengubah ukuran teks secara otomatis.Diabaikan jika presetFontSizes diatur. |
	| maxFontSize | Batasan ukuran teks maksimum yang akan digunakan saat mengubah ukuran teks secara otomatis Diabaikan jika presetFontSizes diatur. |
	| stepGranularity | Ukuran langkah di mana ukuran font sedang disesuaikan dengan batasan. |
	| presetFontSizes | Mendefinisikan semua ukuran font yang mungkin. presetFontSizes harus dalam urutan menurun. |
	| group | Menyinkronkan ukuran beberapa AutoSizeTexts | 
	| textAlign* | Bagaimana teks harus disejajarkan secara horizontal. |
	| textDirection* | Arah  dari teks. Ini memutuskan bagaimana nilai textAlign seperti TextAlign.start dan TextAlign.end diinterpretasikan. |
	| locale* | Digunakan untuk memilih font ketika karakter Unicode yang sama dapat dirender secara berbeda, tergantung pada lokal. |
	| wrapWords | Ketika kata-kata yang tidak cocok dalam satu baris harus dibungkus. Default ke true untuk berperilaku seperti Teks. |
	| overflow* | Bagaimana visual overflow harus ditangani. |
	| overflowReplacement | Jika teks overflowing dan tidak sesuai dengan batasnya, widget ini akan ditampilkan sebagai gantinya. |
	| textScaleFactor* | Jumlah piksel font untuk setiap piksel logis. Juga memengaruhi minFontSize, maxFontSize, dan presetFontSizes. |
	| maxLines | Jumlah maksimum baris opsional untuk teks yang akan dibentangkan. |
	| semanticsLabel* | Label semantik alternatif untuk teks. |