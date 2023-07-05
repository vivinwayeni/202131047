
# UAS PENGOLAHAN CITRA B
1.import cv2: cv2 adalah modul utama dalam OpenCV (Open Source Computer Vision Library). 

2.OpenCV adalah pustaka populer yang digunakan untuk pengolahan gambar dan komputer vision. Dengan mengimpor cv2, Anda dapat menggunakan berbagai fungsi dan metode yang disediakan oleh OpenCV, seperti membaca gambar, manipulasi gambar, deteksi objek, pelacakan, dan lainnya.

3.import numpy as np: numpy adalah pustaka populer untuk komputasi numerik dalam Python. Dengan mengimpor numpy dan memberikan alias np, Anda dapat menggunakan array multidimensi numpy yang efisien dan berbagai fungsi matematika yang kuat. Dalam konteks pengolahan gambar, numpy sering digunakan untuk memanipulasi dan memproses array gambar.

4.import matplotlib.pyplot as plt: matplotlib adalah pustaka visualisasi data yang populer dalam Python. Dengan mengimpor matplotlib.pyplot dan memberikan alias plt, Anda dapat membuat plot, grafik, dan visualisasi data secara umum. Dalam konteks pengolahan gambar, matplotlib.pyplot sering digunakan untuk menampilkan gambar, histogram, dan hasil pemrosesan gambar lainnya.
 
 5.image = cv2.imread("marka.jpg")` adalah untuk membaca sebuah gambar dari file dengan nama "marka.jpg" menggunakan modul `cv2` dari OpenCV. Fungsi `imread()` digunakan untuk membaca gambar dari file dalam format yang didukung (misalnya, JPEG, PNG, BMP, dll.) dan mengembalikan representasi gambar dalam bentuk objek matriks.

Dalam hal ini, gambar dengan nama "marka.jpg" akan dibaca dari file tersebut dan disimpan dalam variabel `image`. Variabel `image` akan berisi representasi matriks dari gambar, di mana setiap elemen matriks mewakili intensitas piksel dari gambar tersebut.

Setelah membaca gambar menggunakan `imread()`, Anda dapat melanjutkan untuk melakukan berbagai operasi pemrosesan gambar, seperti manipulasi, deteksi objek, segmentasi, dan lainnya menggunakan fungsi-fungsi yang disediakan oleh OpenCV.

6.image_asli = cv2.cvtColor(image, cv2.COLOR_BGR2RGB): Pernyataan ini digunakan untuk mengubah mode warna gambar dari BGR (Blue-Green-Red) ke RGB (Red-Green-Blue). Dalam OpenCV, gambar biasanya direpresentasikan dalam mode warna BGR, di mana setiap piksel diwakili oleh tiga komponen warna: biru (Blue), hijau (Green), dan merah (Red). Namun, dalam beberapa kasus, seperti saat menggunakan modul matplotlib.pyplot untuk menampilkan gambar, mode warna RGB lebih umum digunakan. Dengan menggunakan cv2.cvtColor() dengan parameter cv2.COLOR_BGR2RGB, gambar image diubah menjadi mode warna RGB dan disimpan dalam variabel image_asli.

7.blurred_frame = cv2.GaussianBlur(image, (5, 5), 0): Pernyataan ini digunakan untuk menerapkan filter Gaussian blur ke gambar image. Gaussian blur adalah teknik pemrosesan gambar yang digunakan untuk menghaluskan gambar dengan cara mengurangi detail dan mengaburkan noise atau gangguan. Fungsi cv2.GaussianBlur() menerima beberapa parameter, di antaranya gambar yang akan di-blur (image), ukuran kernel blur (dalam contoh ini, (5, 5) menunjukkan kernel dengan lebar dan tinggi 5), dan deviasi standar (0 dalam contoh ini menunjukkan deviasi standar dihitung secara otomatis berdasarkan ukuran kernel). Hasil dari proses Gaussian blur disimpan dalam variabel blurred_frame.

8.hsv = cv2.cvtColor(blurred_frame, cv2.COLOR_BGR2HSV): Pernyataan ini digunakan untuk mengubah mode warna gambar yang telah di-blur (blurred_frame) dari BGR ke HSV (Hue-Saturation-Value). Mode warna HSV lebih sering digunakan dalam pemrosesan gambar berdasarkan warna. Dalam mode warna HSV, komponen Hue mewakili informasi tentang warna, Saturation menggambarkan kecerahan warna, dan Value menggambarkan tingkat kecerahan keseluruhan gambar. Fungsi cv2.cvtColor() dengan parameter cv2.COLOR_BGR2HSV digunakan untuk mengubah gambar dari BGR menjadi HSV, dan hasilnya disimpan dalam variabel hsv.

9.lower_orange = np.array([5, 100, 100], dtype=np.uint8) dan upper_orange = np.array([15, 255, 255], dtype=np.uint8): Dalam konteks ini, variabel lower_orange dan upper_orange digunakan untuk menentukan rentang nilai HSV yang akan dianggap sebagai warna oranye, yang mewakili marka jalan. Nilai-nilai ini dapat disesuaikan sesuai dengan kebutuhan dan kondisi spesifik. np.array() digunakan untuk membuat array NumPy dengan elemen-elemen yang diberikan, dan dtype=np.uint8 menentukan tipe data dari array tersebut.

10.mask = cv2.inRange(hsv, lower_orange, upper_orange): Pernyataan ini digunakan untuk membuat sebuah mask (masker) dengan menggunakan fungsi cv2.inRange(). Masker ini digunakan untuk memisahkan piksel-piksel dalam gambar yang berada dalam rentang warna oranye yang ditentukan oleh lower_orange dan upper_orange. Piksel-piksel dalam rentang tersebut akan memiliki nilai 255 dalam masker, sedangkan piksel-piksel di luar rentang akan memiliki nilai 0. Hasil masker disimpan dalam variabel mask.

11.edges = cv2.Canny(mask, 74, 150): Pernyataan ini digunakan untuk mendeteksi tepi dalam gambar menggunakan metode Canny edge detection. Metode ini mengidentifikasi perubahan tajam dalam intensitas piksel untuk menemukan tepi objek dalam gambar. Fungsi cv2.Canny() menerima gambar yang akan diolah (mask) dan dua parameter ambang batas (threshold), yaitu nilai ambang bawah (74) dan nilai ambang atas (150). Tepi yang ditemukan akan disimpan dalam variabel edges.

12.lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 50, maxLineGap=50): Pernyataan ini menggunakan transformasi Hough untuk mendeteksi garis-garis dalam gambar. Fungsi cv2.HoughLinesP() menerima gambar tepi (edges) dan beberapa parameter, seperti resolusi jarak (1), resolusi sudut (np.pi / 180), ambang batas (50), dan maksimal jarak antara segmen garis untuk menghubungkan mereka menjadi satu garis (maxLineGap=50). Hasilnya, garis-garis yang terdeteksi akan disimpan dalam variabel lines.

if lines is not None:: Pernyataan ini memeriksa apakah garis-garis terdeteksi (lines) tidak kosong.

for line in lines:: Melalui perulangan for, program mengiterasi melalui setiap garis dalam lines.

x1, y1, x2, y2 = line[0]: Mendeklarasikan variabel x1, y1, x2, y2 yang mewakili titik-titik awal dan akhir garis.

`cv









## UAS 202131047 VIVIN MELANESYA WAYENI
