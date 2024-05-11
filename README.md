# UTS PCD

Nama  : Cynthia Maharani

Nim   : 202231046

Kelas : Pengolahan Citra Digital C

### 1. Mengimport Library

Library dalam Python adalah proses mengambil dan menggunakan kode yang telah ditulis sebelumnya dalam file atau paket lain. Dalam Python, library adalah kumpulan modul (file Python) yang menyediakan fungsionalitas tambahan yang dapat digunakan dalam pengembangan perangkat lunak.

### Mendeklarasikan Gambar

Dalam Python, konsep deklarasi gambar sedikit berbeda dibandingkan dengan deklarasi variabel biasa. Bahasa pemrograman Python tidak memiliki tipe data bawaan (seperti integer atau string) khusus untuk gambar. Oleh karena itu, untuk bekerja dengan gambar, Anda biasanya menggunakan library pihak ketiga seperti Pillow (sebelumnya dikenal sebagai PIL) atau OpenCV.

    histogram_biru = cv2.calcHist([b], [0], None, [256], [0, 256])
    histogram_hijau = cv2.calcHist([g], [0], None, [256], [0, 256])
    histogram_merah = cv2.calcHist([r], [0], None, [256], [0, 256])
    histogram_warna = cv2.calcHist([color_image], [0], None, [256], [0, 256])

    histogram_biru = cv2.calcHist([b], [0], None, [256], [0, 256]):

Baris ini menghitung histogram untuk saluran biru. Ini mengambil data saluran biru [b] sebagai input, menentukan nomor saluran [0] untuk fokus pada komponen biru, mengatur mask ke None (tanpa masking), menggunakan 256 bin untuk histogram, dan menetapkan rentang intensitas dari 0 hingga 255 (inklusif).

    histogram_hijau = cv2.calcHist([g], [0], None, [256], [0, 256]):

Serupa dengan baris sebelumnya, baris ini menghitung histogram untuk saluran hijau, menggunakan data saluran hijau [g], nomor saluran [0], tanpa masking, 256 bin, dan rentang intensitas dari 0 hingga 255.

    histogram_merah = cv2.calcHist([r], [0], None, [256], [0, 256]):

Baris ini menghitung histogram untuk saluran merah, menggunakan data saluran merah [r], nomor saluran [0], tanpa masking, 256 bin, dan rentang intensitas dari 0 hingga 255.

    histogram_warna = cv2.calcHist([color_image], [0], None, [256], [0, 256]):

Baris ini menghitung histogram untuk keseluruhan gambar berwarna. Ini mengambil seluruh data gambar berwarna [color_image], menentukan nomor saluran [0] untuk mempertimbangkan ketiga saluran, menggunakan tanpa masking, 256 bin, dan rentang intensitas dari 0 hingga 255.

Baris-baris tersebut menghasilkan empat histogram terpisah. Masing-masing satu untuk saluran biru, hijau, dan merah, dan satu untuk keseluruhan distribusi warna gambar. Histogram ini dapat divisualisasikan untuk menganalisis distribusi intensitas setiap komponen warna dan memperoleh wawasan tentang 

#### Teori Pendukung :

Citra warna digital umumnya direpresentasikan dalam model warna RGB (Red, Green, Blue). Setiap piksel dalam citra RGB memiliki tiga nilai yang mewakili intensitas warna merah, hijau, dan biru pada piksel tersebut. Memisahkan saluran warna berarti mengekstrak nilai individual untuk setiap komponen warna dari setiap piksel.

## Membagi Citra Warna

Ada banyak cara untuk membagi citra warna pada sebuah gambar diantaranya :

### 1. Membagi Berdasarkan Saluran Warna

Dimana dapat memisahkan citra warna menjadi saluran warna individualnya (merah, hijau, biru) menggunakan library Pillow atau OpenCV. Hal ini berguna untuk melakukan analisis gambar atau manipulasi warna. 

Dapat dituliskan seperti pada contoh berikut :

    r = color_image[:, :, 0]
    g = color_image[:, :, 1]
    b = color_image[:, :, 2]

Pada contoh di atas, dideklarasikan terlebih dahulu saluran warnanya masing-masing. Sehingga mudah untuk pemanggilannya nanti.

### 2. Membagi Berdasarkan Wilayah

Anda dapat membagi citra warna menjadi beberapa wilayah berdasarkan kriteria tertentu, seperti warna, tekstur, atau batas objek. Hal ini berguna untuk segmentasi gambar atau analisis region of interest (ROI).

### 3. Membagi Berdasarkan Grid

dapat membagi citra warna menjadi grid dengan ukuran yang sama, menghasilkan sub-gambar. Hal ini berguna untuk pemrosesan gambar paralel atau analisis lokal.

Diantara cara-cara di atas, sebenarnya masih banyak lagi cara untuk membagi saluran warna pada citra gambar.

#### Teori pendukung :

Pembagian citra warna, proses memisahkan citra berwarna menjadi saluran warna individualnya (merah, hijau, dan biru), memiliki dasar teori kuat yang membuatnya menjadi alat penting dalam berbagai aplikasi pengolahan citra digital. Berikut beberapa teori utama yang mendasari praktik ini:

1. Model Warna RGB:

Citra digital umumnya direpresentasikan dalam model warna RGB, di mana setiap piksel memiliki tiga nilai yang mewakili intensitas warna merah (R), hijau (G), dan biru (B) pada piksel tersebut. Model ini didasarkan pada persepsi warna manusia, di mana mata manusia memiliki tiga jenis sel kerucut yang peka terhadap panjang gelombang cahaya merah, hijau, dan biru.

2. Psikofisika Warna:

Penelitian dalam psikofisika warna menunjukkan bahwa manusia dapat membedakan dengan halus variasi intensitas warna merah, hijau, dan biru. Hal ini memungkinkan pemisahan saluran warna untuk mengekstrak informasi warna yang lebih rinci dari citra digital.

3. Analisis Spektral:

Analisis spektral melibatkan dekomposisi cahaya menjadi komponen warna-warnanya. Pembagian citra warna pada dasarnya adalah implementasi digital dari analisis spektral, memungkinkan analisis distribusi warna dalam citra.

## Histogram

Histogram adalah representasi visual dari distribusi data numerik. Ini digunakan untuk menunjukkan berapa banyak data yang termasuk dalam rentang nilai tertentu. Histogram biasanya berupa grafik batang yang:

Sumbu X (horizontal): Mewakili bin (interval) dari nilai data.
Sumbu Y (vertikal): Mewakili jumlah data point yang jatuh dalam setiap bin.
 
Python menyediakan library seperti matplotlib dan Seaborn untuk membuat histogram. Langkah-langkah umum:

1. Import library.
2. Siapkan data.
3. Tentukan jumlah bin.
4. Buat histogram menggunakan fungsi hist().
5. Tambahkan label sumbu dan judul.
6. Tampilkan histogram.

### Teori Pendukung :

Teori Pendukung Penggunaan Histogram dalam Pengolahan Citra Digital
Histogram merupakan alat visual fundamental dalam pengolahan citra digital yang digunakan untuk merepresentasikan distribusi intensitas piksel dalam sebuah gambar. Alat ini menyediakan wawasan penting tentang karakteristik pencahayaan, kontras, dan distribusi nilai intensitas dalam citra, memungkinkannya untuk digunakan dalam berbagai aplikasi pengolahan citra.

## Nilai Ambang batas

Dalam pengolahan citra digital, nilai ambang batas (threshold) adalah konsep penting yang digunakan untuk segmentasi citra, ekstraksi objek, dan melakukan berbagai tugas analisis citra. Ini melibatkan penetapan nilai ambang batas, yang bertindak sebagai titik keputusan untuk mengklasifikasikan piksel citra menjadi dua kategori:

1. Vordergrund (foreground): Piksel dengan nilai intensitas di atas ambang batas dianggap sebagai bagian dari foreground, biasanya mewakili objek atau daerah yang diminati dalam citra.

2. Latar Belakang (background): Piksel dengan nilai intensitas di bawah ambang batas dianggap sebagai bagian dari background, biasanya mewakili area sekitar atau bagian yang tidak relevan dari citra.

Pemilihan Nilai Ambang Batas:

Pemilihan nilai ambang batas secara signifikan memengaruhi hasil segmentasi dan keseluruhan keberhasilan tugas pengolahan citra. Pemilihan nilai ambang batas yang tepat bergantung pada faktor-faktor seperti:

Karakteristik citra: Kontras antara foreground dan background, keberadaan noise (gangguan), dan distribusi intensitas keseluruhan citra.

Aplikasi: Tugas pengolahan citra spesifik yang sedang dilakukan, seperti deteksi objek, deteksi tepi, atau ekstraksi fitur.

### Metode Thresholding Umum:

Thresholding Manual: Menetapkan nilai ambang batas secara manual berdasarkan inspeksi visual atau pengetahuan sebelumnya tentang konten citra.

Thresholding Global: Menggunakan nilai ambang batas tunggal untuk seluruh citra, dengan asumsi pencahayaan seragam dan properti objek yang konsisten.

Thresholding Adaptif: Menyesuaikan nilai ambang batas secara lokal berdasarkan variasi intensitas di dalam citra, beradaptasi dengan kondisi pencahayaan dan tampilan objek yang berbeda.

Metode Otsu: Metode thresholding otomatis yang mengoptimalkan nilai ambang batas dengan memaksimalkan varians antar-kelas, bertujuan untuk pemisahan yang jelas antara foreground dan background.

#### Teori Pendukung :

Thresholding adalah teknik fundamental dalam pengolahan citra digital yang digunakan untuk membagi citra menjadi dua atau lebih kelas berdasarkan nilai intensitas pikselnya. Teknik ini memiliki peran penting dalam berbagai aplikasi, seperti segmentasi citra, analisis tekstur, dan deteksi objek.

