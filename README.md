# Praktikum.9
## Cara Penanganan Eksepsi di Python
Halo sahabat programmer kali ini kita akan membahas cara menangani eksepsi di python, seperti yang kita ketahui di dalam pemrograman kesalahan atau error adalah hal yang sering terjadi, tidak mungkin seorang programmer ketika membuat sebuah program tidak pernah mengalami hal ini. Bahkan programmer sering di sebut sebagai troble maker karena kegiatan programming memang tidak luput dari hal itu.

Kesalahan atau error bisa disebabkan beberapa hal seperti kesalahan pada penulisan kode sehingga program tidak dapat di eksekusi atau kesalahan juga bisa terjadi saat program sedang berjalan (run-time). Error karena kesalahan sintak mungkin cukup mudah untuk di deteksi tapi bagaimana jika kesalahan terjadi saat program telah berjalan??

Contoh misalnya kita membuat sebuah program utnuk menerima nilai yang di masukan dari pengguna dengan tipe integer, tetapi pengguna memasukan tipe karakter tentu ini akan menyebabkan error pada program yang sedang berjalan sehingga program akan dihentikan secara tidak normal.

Sebagai seorang programmer kita harus mampu mengantisipasi kejadian seperti ini agar program yang kita buat dapat berjalan dengan baik. Ketika ada peluang terjadinya kesalahan maka program mampu memberikan instruksi kepada pengguna tentang kesalahan yang terjadi sehingga program tetap berjalan dengan baik seakan-akan tidak terjadi sebuah kesalahan.

## Pengertian Eksepsi

Eksepsi (exception) merupakan suatu kesalahan (error) yang terjadi saat proses eksekusi program sedang berjalan, kesalahan ini akan menyebabkan program berakhir dengan tidak normal. Kesalahan-kesalahan ini dapat diidentifikasikan dengan nama tertentu dan direpresentasikan sebagai objek di dalam python.

## Contoh:
Perhatikan program berikut:
```
a = 1
b = 'X'
print(a+b)
```
Program ini mencoba untuk menjumlahkan variabel a+b namun variabel b memiliki tipe data string, sehingga hal ini akan memicu bangkitnya eksepsi karena akan terjadi error.

![image](https://user-images.githubusercontent.com/115862112/208221424-f04ba87a-5f9f-4fd8-a76a-160d96e62478.png)

Dalam kasus ini eksepsi yang dibangkitkan adalah TypeError dimana operan tidak didukung penjumlahan antara tipe integer dan string.
## Membangkitkan Eksepsi dengan raise
Di dalam python ada banyak tipe eksepsi di dalam python, yang semuanya bisa dibangkitkan baik pada saat penanganan kesalahan (error) atau bisa juga kita bangkitkan secara paksa dengan menggunakan perintah raise.

![image](https://user-images.githubusercontent.com/115862112/208221507-55874b0b-13a1-4445-bf71-8cb483b41d68.png)

Contoh di atas kita membangkitkan eksepsi dengan tipe TypeError menggunakan perintah raise, meskipun sebenarnya di dalam kode tersebut tidak ada kesalahan penggunaan tipe data yang tidak sesuai.
## Penanganan Eksepsi Menggunakan Blok try … except
Jika kalian pernah belajar C++ atau Java penanganan eksepsi menggunakan blok try … catch, sedikit berbeda namanya dengan python menggunakan blok try … except bentuk umumnya seperti berikut:Jika kalian pernah belajar C++ atau Java penanganan eksepsi menggunakan blok try … catch, sedikit berbeda namanya dengan python menggunakan blok try … except bentuk umumnya seperti berikut:
```
try:
    # kode
except TipeEksepsi:
    # Penanganan kesalahan
```
Setiap kode program yang memungkinkan terjadinya eksepsi, maka perlu untuk di tempatkan di dalam blok try. Ketika ada kesalahan maka kode di blok except akan dieksekusi , sebaliknya jika program tidak memiliki kesalahan maka blok except akan di abaikan.
## Contoh Blok try … except di python
Perhatikan program berikut:
```
import sys
try:
    a = int(input("Masukan nilai a : "))
    b = int(input("Masukan nilai b : "))
except ValueError:
    print("Nilai harus bertipe numerik")
    sys.exit()
hasil=a+b
print("Hasil Penjumlahan :",hasil)
```
Pada contoh program di atas kita akan menjumlahkan nilai a dan b yang akan di masukan oleh pengguna. Karena inputan dari pengguna memungkinkan terjadi kesalahan maka perintah tersebut kita tempatkan di dalam blok try, apabila terjadi eksepsi dengan tipe ValueError maka kode di dalam blok except akan di eksekusi.

Tipe eksepsi ValueError adalah eksepsi untuk menangani kesalahan konversi tipe data. ketika pengguna memasukan nilai selain integer maka eksepsi ini akan dibangkitkan. Selain itu kita juga menggunakan perintah exit() di dalam modul sys untuk menghentikan eksekusi program yang sedang berjalan saat terjadi eksepsi.

Apabila tidak terjadi eksepsi maka kode di dalam blok except tidak akan di eksekusi oleh program dan langsung melompat ke perintah program selanjutnya.
## Menambahkan Klausa else dalam Blok try … except
```
try:
    a = int(input("Masukan nilai a : "))
    b = int(input("Masukan nilai b : "))
except ValueError:
    print("Nilai harus bertipe numerik")
else: 
    hasil=a+b
    print("Hasil Penjumlahan :",hasil)
```
Pada contoh kedua kita menambahkan klausa else, dimana kode-kode yang berada pada bagian else hanya akan dieksekusi ketika tidak terjadi kesalahan saat mengeksekusi kode di bagian try, ini berarti jika terjadi eksepsi kode pada bagian else tidak akan di eksekusi.

Perbedaan program pertama dan kedua selain ada penambahan klausa else, pada program kedua kita sudah tidak menggunakan fungsi exit() dari modul sys karena program akan melompat ke bagian else saat tidak terjadi eksepsi.
## Menggunakan Perintah assert
Perintah assert merupakan bentuk sederhana untuk memeriksa suatu ekspresi bertipe boolean apakah bernilai benar (true) atau salah (false). Berikut ini adalah bentuk umumnya:
```
assert Ekspresi, Argumen
```
Jika ekspresi bernilai salah maka eksepsi akan di bangkitkan dengan tipe AssertionError.
```
a = int(input("Masukan nilai a : "))
assert a > 0, "Nilai harus lebih dari 0"
```
![image](https://user-images.githubusercontent.com/115862112/208221720-f77a9c6a-7dca-42ef-b7ea-7ff180f3f1c0.png)
Perintah assert biasanya digunakan untuk melacak kesalahan (debugging) di dalam kode program.
## Kesimpulan
Demikian artikel kali ini mengenai cara menangani eksepsi di python baik menggunakan blok try … except dan perintah assert, semoga artikel ini bermanfaat dan menambah wawasan teman-teman semua.
