# Pembuktian Citra Digital sebagai Susunan Angka Menggunakan Python

Nama : M Said Hibban Muttaqien
NIM : 24260016
Prodi : Teknik Informatika

## 1. Deskripsi Proyek

Proyek ini dibuat untuk membuktikan bahwa citra digital bukan hanya sebuah gambar yang dapat dilihat oleh manusia, tetapi juga merupakan kumpulan data numerik yang dapat dibaca dan diolah oleh komputer.

Pembuktian dilakukan menggunakan bahasa pemrograman Python melalui Google Colab. Gambar yang digunakan akan diubah menjadi array numerik sehingga nilai setiap piksel dapat ditampilkan dan dianalisis.

Melalui eksperimen ini, dapat diketahui bagaimana komputer merepresentasikan warna gambar menggunakan angka serta bagaimana data numerik tersebut dapat digunakan untuk membentuk kembali gambar.

## 2. Tujuan

Tujuan dari proyek ini adalah:

1. Memahami konsep citra digital dan piksel.
2. Membuktikan bahwa citra digital tersusun dari data numerik.
3. Mengetahui cara membaca nilai piksel menggunakan Python.
4. Memahami representasi warna RGB dan citra grayscale.
5. Menampilkan matriks angka yang membentuk citra digital.
6. Membuktikan bahwa data numerik dapat direkonstruksi menjadi gambar kembali.
7. Memanfaatkan GitHub sebagai tempat penyimpanan kode dan dokumentasi tugas.

## 3. Teknologi yang Digunakan

Proyek ini menggunakan beberapa teknologi berikut:

- **Python:** bahasa pemrograman untuk mengolah dan menganalisis citra digital.
- **Google Colab:** lingkungan pemrograman berbasis cloud untuk menjalankan kode Python tanpa instalasi lokal.
- **NumPy:** library untuk mengubah gambar menjadi array numerik dan melakukan operasi pada data piksel.
- **Pillow (PIL):** library untuk membaca, mengubah format, dan membuat gambar.
- **Matplotlib:** library untuk menampilkan gambar, matriks angka, dan visualisasi hasil eksperimen.

## 4. Konsep Dasar Citra Digital

Citra digital adalah representasi gambar dalam bentuk data yang dapat disimpan dan diproses oleh komputer. Citra tersusun dari elemen-elemen kecil yang disebut piksel (*picture element*).

Setiap piksel menyimpan informasi tertentu yang menentukan tampilan gambar pada posisi tersebut. Pada citra berwarna dengan format RGB, setiap piksel umumnya memiliki tiga nilai kanal warna:

- **Red (R):** tingkat warna merah.
- **Green (G):** tingkat warna hijau.
- **Blue (B):** tingkat warna biru.

Pada citra RGB 8-bit, setiap kanal memiliki rentang nilai 0 sampai 255. Kombinasi ketiga nilai tersebut menentukan warna piksel.

Sebagai contoh:

| Warna | Nilai RGB |
|---|---|
| Merah | (255, 0, 0) |
| Hijau | (0, 255, 0) |
| Biru | (0, 0, 255) |
| Putih | (255, 255, 255) |
| Hitam | (0, 0, 0) |

Dengan demikian, warna yang terlihat pada gambar merupakan hasil representasi nilai numerik pada setiap piksel.

## 5. Metode Pembuktian

Eksperimen dilakukan melalui beberapa tahapan berikut.

### 5.1 Membaca Gambar

Gambar diunggah ke Google Colab, kemudian dibaca menggunakan Pillow dan dikonversi ke format RGB. Tujuannya adalah memastikan gambar memiliki tiga kanal warna yang dapat dianalisis.

### 5.2 Mengubah Gambar Menjadi Array

Gambar yang telah dibaca diubah menjadi array menggunakan NumPy. Array tersebut menyimpan nilai numerik dari setiap piksel berdasarkan posisi dan kanal warnanya.

Untuk citra dengan tinggi H, lebar W, dan tiga kanal RGB, bentuk array adalah:

`(H, W, 3)`

Jumlah seluruh nilai kanal warna dihitung menggunakan rumus:

`Jumlah nilai = tinggi × lebar × 3`

Sebagai contoh, gambar berukuran 100 × 100 piksel memiliki 30.000 nilai kanal warna RGB.

### 5.3 Menganalisis Nilai Piksel

Program mengambil satu piksel dari gambar untuk menampilkan nilai merah, hijau, dan biru. Selain itu, sebagian matriks angka ditampilkan agar susunan nilai numerik pada gambar dapat diamati secara langsung.

### 5.4 Mengubah Gambar Menjadi Grayscale

Gambar RGB dikonversi menjadi grayscale atau citra keabuan. Dalam representasi grayscale 8-bit, setiap piksel memiliki satu nilai intensitas dari 0 sampai 255.

Nilai yang mendekati 0 menunjukkan warna gelap, sedangkan nilai yang mendekati 255 menunjukkan warna terang.

### 5.5 Rekonstruksi Citra

Array numerik digunakan untuk membentuk kembali gambar menggunakan Pillow. Selanjutnya, array gambar asli dibandingkan dengan array hasil rekonstruksi menggunakan fungsi `numpy.array_equal()`.

Jika hasil perbandingan bernilai `True`, berarti seluruh nilai piksel pada kedua array identik.

## 6. Hasil Eksperimen

Hasil eksperimen yang dihasilkan oleh program meliputi:

1. Tampilan gambar asli yang digunakan sebagai objek penelitian.
2. Informasi dimensi gambar, jumlah kanal, bentuk array, tipe data, dan jumlah nilai numerik.
3. Nilai RGB dari salah satu piksel.
4. Matriks angka RGB dari sebagian area gambar.
5. Visualisasi nilai pada kanal merah, hijau, dan biru.
6. Perbandingan citra RGB dengan citra grayscale.
7. Perbandingan gambar asli dan gambar hasil rekonstruksi.
8. Ringkasan hasil eksperimen dalam format JSON.

Hasil tersebut digunakan untuk menunjukkan hubungan antara gambar yang terlihat secara visual dengan data numerik yang disimpan dan diolah oleh komputer.

## 7. Analisis dan Pembahasan

Berdasarkan konsep dan pengujian yang dilakukan, citra digital dapat direpresentasikan sebagai kumpulan nilai numerik yang tersusun berdasarkan posisi piksel dan kanal warna.

Setiap piksel memiliki nilai yang berkontribusi terhadap tampilan warna gambar. Perubahan pada nilai tersebut dapat menyebabkan perubahan warna atau intensitas piksel.

Jumlah data numerik juga bergantung pada dimensi dan representasi citra. Citra RGB memiliki tiga nilai kanal per piksel, sedangkan citra grayscale 8-bit memiliki satu nilai intensitas per piksel.

Proses rekonstruksi menjadi bagian penting dalam eksperimen karena menunjukkan bahwa array numerik dapat dikonversi kembali menjadi gambar. Apabila hasil perbandingan menunjukkan nilai `True` dan selisih maksimum 0, seluruh nilai piksel pada gambar hasil rekonstruksi sama dengan gambar yang dianalisis.

Perlu diperhatikan bahwa eksperimen ini membuktikan representasi numerik citra dalam program, bukan berarti setiap format file gambar memiliki susunan penyimpanan internal yang sama.

## 8. Kesimpulan

Citra digital dapat direpresentasikan sebagai susunan data numerik yang tersimpan dalam bentuk array. Pada citra RGB 8-bit, setiap piksel memiliki tiga nilai kanal warna, yaitu merah, hijau, dan biru. Nilai-nilai tersebut dapat ditampilkan dalam bentuk matriks, dianalisis menggunakan Python, dan digunakan untuk merekonstruksi gambar.

Dengan demikian, eksperimen ini menunjukkan bahwa gambar digital tidak hanya berupa tampilan visual, tetapi juga merupakan data numerik yang dapat diproses oleh komputer.
