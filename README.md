# Prediksi Skor Ujian Mahasiswa Berdasarkan Gaya Hidup Menggunakan Model Deep Learning

Pencapaian akademik mahasiswa dipengaruhi oleh berbagai faktor internal dan eksternal, termasuk kebiasaan gaya hidup sehari-hari. Beberapa penelitian sebelumnya telah menunjukkan hubungan antara durasi belajar, waktu tidur, penggunaan media sosial, dan performa akademik. Dengan kemajuan teknologi kecerdasan buatan, khususnya deep learning, kini memungkinkan untuk menganalisis hubungan non-linear yang kompleks antar variabel untuk tujuan prediksi. Penelitian ini bertujuan untuk membangun model prediktif berbasis deep learning untuk mengestimasi skor ujian mahasiswa berdasarkan pola gaya hidup mereka.

## Informasi Dataset
Dataset yang digunakan merupakan data sintetik yang merepresentasikan 1.000 mahasiswa dengan 16 atribut, seperti umur, jenis kelamin, jam belajar, jam penggunaan media sosial, jam menonton Netflix, part-time job, persentase kehadiran, durasi tidur, kualitas diet, frekuensi olahraga, pendidikan orang tua, kualitas internet, kesehatan mental, partisipasi ekstrakurikuler, dan skor ujian akhir.

## Pra-pemrosesan Data
* Mengganti nilai koma (",") pada angka desimal menjadi titik (".")
* Menangani nilai hilang (missing values) dengan imputasi menggunakan nilai rata-rata/ modus
* Normalisasi fitur numerik menggunakan MinMaxScaler
* Encoding variabel kategorikal menggunakan One-Hot Encoding

## Arsitektur Model
Model yang digunakan adalah MLP (Multilayer Perceptron) dengan:
a. Input layer: sejumlah neuron sesuai jumlah fitur numerik dan hasil encoding
b. Hidden layers: 2 layer tersembunyi dengan aktivasi ReLU
c. Output layer: 1 neuron (prediksi skor ujian) dengan aktivasi linear
d. Optimizer: Adam
e. Loss function: Mean Squared Error (MSE)
f. Epoch: 100
g. Batch size: 32

## Evaluasi Model
Model dievaluasi dengan tiga metrik:
1. MAE (Mean Absolute Error)
2. RMSE (Root Mean Squared Error)
3. R-squared (Koefisien Determinasi)

## Hasil Evaluasi
### MAE = 5.52
### RMSE = 6.70
### R^2 = 0.8247
Hasil tersebut menunjukkan bahwa model mampu memprediksi skor ujian akhir dengan tingkat kesalahan rata-rata yang rendah. Skor R-squared yang tinggi menunjukkan bahwa lebih dari 82% variabilitas skor ujian dapat dijelaskan oleh variabel gaya hidup.

### Visualisasi Loss
Grafik menunjukkan bahwa training loss dan validation loss menurun secara signifikan hingga mendatar pada epoch ke-15, tanpa tanda overfitting. Hal ini menunjukkan model terlatih dengan baik dan mampu melakukan generalisasi terhadap data validasi.

### Interpretasi
Fitur yang paling berpengaruh terhadap skor ujian adalah jam belajar, kualitas tidur, kesehatan mental, dan kehadiran kelas. Sebaliknya, jam menonton Netflix dan penggunaan media sosial yang tinggi cenderung berkorelasi negatif dengan performa akademik.

## Kesimpulan
Model deep learning berbasis MLP dapat secara efektif memprediksi skor ujian mahasiswa berdasarkan data gaya hidup. Pendekatan ini menunjukkan potensi penggunaan AI dalam dunia pendidikan untuk memberikan wawasan preventif dan intervensi berbasis data terhadap performa akademik mahasiswa. Penelitian lanjutan dapat dilakukan menggunakan data aktual dan mempertimbangkan faktor-faktor tambahan seperti motivasi dan dukungan sosial.
