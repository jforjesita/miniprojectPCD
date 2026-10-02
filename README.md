NAMA    : JESITA APRIMESTI
NIM     : F1G124032
KELAS   : A

# miniprojectPCD

# Hasil Pengujian Deteksi Tanda Tangan:

Sistem diuji menggunakan citra beresolusi tinggi (2481x3506 piksel) yang merepresentasikan berbagai kondisi degradasi dokumen di dunia nyata.

Dari hasil eksekusi program, diperoleh data sebagai berikut:

01_HighQuality_Enhanced: 7.41% (PRESENT)

02_LowContrast: 7.50% (PRESENT)

03_Blurred: 11.69% (PRESENT)

04_HighNoise: 7.16% (PRESENT)

05_LowResolution_Upsampled: 9.20% (PRESENT)

06_Faded_Underexposed: 7.63% (PRESENT)

07_ColorShift_WarmTint: 7.52% (PRESENT)

08_JPEGCompression_Artifacts: 7.72% (PRESENT)

09_CombinedDegradation: 8.81% (PRESENT)


# Analisis
1. Mengapa thresholding diperlukan sebelum melakukan analisis keberadaan tanda tangan?

Thresholding diperlukan untuk memisahkan objek tanda tangan dari latar belakang pada citra. Pada gambar ijazah, tanda tangan biasanya berupa goresan atau piksel yang lebih gelap dibandingkan dengan latar belakang kertas yang relatif terang. Dengan thresholding, citra grayscale diubah menjadi citra biner yang hanya memiliki dua nilai, yaitu hitam dan putih. Dengan demikian, piksel yang dianggap sebagai bagian dari tanda tangan dapat dihitung dengan lebih mudah. Hasil thresholding kemudian dapat digunakan untuk menghitung jumlah piksel foreground dan rasio piksel tersebut terhadap seluruh area crop. Rasio inilah yang digunakan untuk membantu menentukan apakah pada area tersebut terdapat tanda tangan atau tidak.

2. Apa masalah yang terjadi jika threshold terlalu tinggi atau terlalu rendah?

Jika nilai threshold terlalu tinggi, terlalu banyak bagian gambar yang dianggap sebagai objek atau foreground. Akibatnya, noise, tulisan lain, bayangan, dan bagian latar belakang dapat ikut terdeteksi sebagai tanda tangan. Hal ini dapat menyebabkan false positive, yaitu sistem menyatakan terdapat tanda tangan padahal sebenarnya tidak ada. Sebaliknya, jika threshold terlalu rendah, goresan tanda tangan yang tipis atau samar dapat dianggap sebagai bagian dari background sehingga sebagian tanda tangan tidak terdeteksi. Hal ini dapat menyebabkan false negative, yaitu sistem menyatakan tidak terdapat tanda tangan padahal sebenarnya ada. Oleh karena itu, nilai threshold perlu dipilih dengan tepat agar tanda tangan dapat dipisahkan dari background secara optimal.