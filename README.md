
# Laporan UTS Pengolahan Citra Digital A

Pada UTS praktikum ini, saya diminta untuk mendeteksi 3 warna pada citra yang saya ambil lalu mencari nilai ambang batas citra untuk menampilkan kategori warnanya.

1. Import library
Langkah pertama, saya mengimport 3 library yang diperlukan, yaitu 
- cv2: library untuk pengolahan citra.
- matplotlib: library untuk visualisasi.
- numpy: library untuk mengolah dan memanipulasi data dalam bentuk array.

2. Membaca gambar
Lalu, citra/gambar yang sudah dimasukkan, dibaca dengan fungsi imread dari cv2. Format gambar dari cv2  secara default adalah BGR (urutan warnanya tidak sesuai dengan urutan warna gambar asli), maka saya konversi ke RGB terlebih dahulu.

3. Pemurnian warna
Setelah itu, saya membuat baris dan kolom untuk proses pemurnian warna. Pada proses pemurnian warna ini, saya membuat proses untuk menghitung dua nilai maksimum dan indeksnya di setiap piksel citra. Ini dilakukan dengan menggunakan variabel max1 dan max2. Variabel imax1 dan imax2 menyimpan indeks dari nilai maksimum pertama dan kedua, yang digunakan untuk menentukan komponen warna mana yang memiliki nilai maksimum.

Setelah nilai maksimum dan indeksnya dihitung, saya mencari selisih antara nilai maksimum pertama dan kedua di setiap piksel citra. Jika selisih nilai maksimum melebihi ambang batas, yaitu 250, maka setiap komponen warna piksel, kecuali komponen warna dengan nilai maksimum, diatur menjadi 0.

4. Deteksi warna merah, hijau, dan biru pada citra.
Jika menggunakan img.shape, output yang akan dihasilkan adalah jumlah baris, jumlah kolom, dan jumlah saluran warna pada citra (jika gray = 1, biner = 2, berwarna = 3). Citra yang digunakan sudah dalam format RGB, maka [0,1,2] mewakili Red, Green, dan Blue. Dapat dilihat pada visualisasinya, ketika jumlah saluran warnanya diubah menjadi 0, maka warna merah pada citra akan terdeteksi (menjadi pudar/putih). Hal ini dikarenakan, pada citra grayscale, semakin berwarna putih, maka semakin tinggi intensitas warnanya (dalam hal ini merah). Hal yang sama berlaku pada warna hijau (1) dan warna biru (2).

5. Histogram tiap kategori warna pada citra.
Untuk histogram, saya membuat 4 baris dan 2 kolom dengan ukuran 12 x 15.
Pada keempat histogram tersebut, dapat dilihat distribusi intensitas piksel pada citra ada pada rentang 200 - > 250, yang artinya citra memiliki dominan warna putih.

6. Ambang batas untuk kategori warna pada citra.
Pertama-tama, saya mengonversi gambar ke citra grayscale terlebih dahulu karena akan menggunakan fungsi threshold untuk menentukan ambang batas. Saya mencoba-coba untuk mendapatkan ambang batasnya. Contohnya pada deteksi warna merah, ambang batasnya adalah 110 dan 255. Ini dikarenakan jika ambang batas bawah kurang dari 110, maka tulisan dengan warna merah akan kurang terlihat. Jika lebih dari 110, maka tulisan bukan dengan warna merah pun dapat terlihat. Hal yang sama berlaku pada ambang batas deteksi warna hijau dan biru. 

# Teori pendukung
Deteksi warna pada citra merupakan proses identifikasi dan pemisahan warna pada citra digital. Ini adalah langkah dasar penting dalam visi komputer dan pemrosesan citra digital, yang dapat digunakan untuk mendeteksi objek, mengklasifikasikan citra, atau menganalisis konten citra.

Teori deteksi warna terdiri dari beberapa langkah dasar:

- Pengambilan Citra: Citra diambil menggunakan kamera digital atau scanner. Citra dapat berwarna atau hitam-putih, tetapi dalam konteks deteksi warna, citra warna lebih relevan.

- Pemodelan Warna: Warna pada citra dapat dicatat dalam beberapa sistem pemodelan warna, seperti model RGB, HSV, atau CMYK. Model RGB umum digunakan dalam monitor komputer dan kamera digital. Dalam model RGB, setiap warna dibuat dari kombinasi tiga primaris: merah (Red), hijau (Green), dan biru (Blue).

- Deteksi Warna: Algoritma deteksi warna diterapkan pada citra untuk mengidentifikasi dan mengklasifikasikan warna. Ini biasanya melibatkan pengukuran intensitas merah, hijau, dan biru pada setiap pixel citra. Setelah itu, pixel dikelasifikasikan berdasarkan intensitas tersebut.

- Pengolahan Citra: Setelah warna dideteksi, proses pengolahan citra dapat dilakukan untuk mengubah atau meningkatkan citra. Ini dapat melibatkan operasi seperti filtering, thresholding, atau edge detection.

- Penginterpretasi Hasil: Hasil dari deteksi warna dan pengolahan citra dapat digunakan untuk mengambil keputusan atau mengklasifikasikan objek pada citra.

Beberapa teknik deteksi warna yang umum adalah:

- Histogram Warna: Menghitung jumlah pixel pada setiap nilai intensitas merah, hijau, dan biru.
- Segmentasi Warna: Memisahkan citra menjadi bagian-bagian berdasarkan warna.
- Deteksi Kontur Warna: Mendeteksi kontur atau garis pada citra berdasarkan perbedaan warna.





