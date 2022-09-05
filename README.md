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