# Praktikum 1: Aplikasi Kamera Flutter

## Deskripsi
Aplikasi ini merupakan implementasi kamera pada Flutter yang memungkinkan pengguna untuk mengambil foto menggunakan kamera perangkat.

## Screenshot Hasil
![Screenshot aplikasi kamera](assets/hasil.jpg)

## Screenshot running take picture (belum mengambil gambar)
![Screenshot aplikasi kamera](assets/take-picture.jpg)

## Screenshot running display picture (sudah mengambil gambar)
![Screenshot aplikasi kamera](assets/display-picture.jpg)

## Penjelasan
Dalam aplikasi ini saya mengimplementasikan:
1. Penggunaan plugin camera untuk mengakses kamera perangkat
2. Implementasi preview kamera secara realtime
3. Fungsi untuk mengambil foto

## Penggunaan Void async 
Pada kode program di praktikum 1, terdapat fungsi:
Future<void> main() async {
Fungsi ini menggunakan dua kata kunci penting, yaitu async dan Future<void>.

## 1. Apa itu async?
Kata kunci async digunakan untuk menandakan bahwa fungsi ini berjalan secara asinkron. Maksudnya, program tidak harus menunggu satu tugas selesai sebelum menjalankan tugas lainnya.
Misalnya, dalam kode ini ada perintah:
### final cameras = await availableCameras();
Perintah ini membutuhkan waktu untuk mendapatkan daftar kamera yang tersedia di perangkat. Jika program tidak menggunakan async, maka program akan berhenti sejenak hingga kamera ditemukan, yang bisa menyebabkan aplikasi terasa lambat atau tidak responsif.
Dengan adanya async, program bisa tetap berjalan sambil menunggu proses tersebut selesai.

## 2 Apa itu Future<void>?
•	Future berarti bahwa fungsi ini akan mengembalikan sesuatu di masa depan (setelah beberapa waktu).

•	void berarti fungsi ini tidak mengembalikan nilai apa pun, hanya menjalankan tugas-tugas yang ada di dalamnya.

## 3 Kenapa Harus Menggunakan async dan await?
Jika tidak menggunakan async, program akan mengalami error saat mencoba menggunakan await. Kata kunci await hanya bisa digunakan di dalam fungsi yang diberi tanda async.
Jadi, fungsi main() ditulis seperti ini karena ada proses yang membutuhkan waktu, seperti mengambil daftar kamera yang tersedia. Dengan async, program tetap berjalan dengan lancar tanpa harus menunggu proses tersebut selesai secara langsung.

## Penggunaan @immutable dan @override dalam Flutter
Dalam Flutter, terdapat dua anotasi yang sering digunakan, yaitu @immutable dan @override.

## Anotasi @immutable digunakan untuk menandakan bahwa sebuah class tidak dapat diubah setelah objeknya dibuat.

### Manfaat @immutable:
  -  Membantu menjaga stabilitas aplikasi.
  - Mencegah perubahan data yang tidak disengaja.
  - Berguna dalam manajemen state agar data tetap konsisten.
### Contoh Penggunaan @immutable:

import 'package:flutter/foundation.dart';

@immutable
class Person {
  final String name;
  final int age;

  Person(this.name, this.age);
}

Pada contoh di atas, setelah objek Person dibuat, nilai name dan age tidak dapat diubah lagi. Jika ada usaha untuk mengubahnya, Dart akan memberikan peringatan atau error.

## Anotasi @override digunakan saat ingin mengganti (override) sebuah method dari class induk (parent class) di dalam subclass.

### Manfaat @override:
  -  Memastikan bahwa method benar-benar menggantikan method dari parent class.
  -  Menghindari kesalahan jika terjadi perubahan di parent class.

### Contoh Penggunaan @override:
class Animal {
  void makeSound() {
    print("Animal makes a sound");
  }
}

class Dog extends Animal {
  @override
  void makeSound() {
    print("Dog barks");
  }
}

void main() {
  Dog myDog = Dog();
  myDog.makeSound(); // Output: Dog barks
}
Pada contoh di atas:

makeSound() di class Dog menggantikan method yang sama dari class Animal.
Dengan menambahkan @override, kita memastikan bahwa method tersebut benar-benar mengganti method dari class induknya.
