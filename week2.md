# Dasar-dasar pemrograman jaringan saraf, fokus ke teknik dan konsep penting yang bikin kamu paham tentang regresi logistik dan jaringan saraf.

### Memahami Jaringan Saraf
- Jadi, jaringan saraf ini biasanya memproses seluruh set pelatihan tanpa perlu loop yang ribet, jadi lebih efisien saat latihan.
- Perhitungannya dibagi jadi dua langkah utama: **forward propagation** (ngitung output) dan **backward propagation** (ngupdate bobot).

### Regresi Logistik untuk Klasifikasi Biner
- Regresi logistik itu buat klasifikasi biner, misalnya buat ngenalin gambar sebagai kucing (1) atau bukan kucing (0).
- Gambar-gambar itu direpresentasikan sebagai matriks untuk saluran warna merah, hijau, dan biru, terus diubah jadi vektor fitur.

### Pelatihan dan Notasi
- Contoh pelatihan ditulis sebagai pasangan (x, y), di mana x itu vektor fitur dan y itu label (0 atau 1).
- Set pelatihan terdiri dari banyak contoh, dan matriks dipakai buat ngatur input sama output ini biar lebih gampang dipakai di jaringan saraf.

# Memahami Regresi Logistik
- Regresi logistik ini dipakai saat label output itu biner (0 atau 1), contohnya buat nentuin apakah sebuah gambar itu gambar kucing atau bukan.
- Tujuannya adalah buat ngebaca probabilitas (Y hat) bahwa output (Y) itu sama dengan satu, berdasarkan vektor fitur input (X).

### Peran Fungsi Sigmoid
- Gak kayak fungsi linier (W transpose X + B), regresi logistik pakai fungsi sigmoid supaya Y hat ada di antara 0 dan 1.
- Fungsi sigmoid itu didefinisiin sebagai \( \text{sigmoid}(Z) = \frac{1}{1 + e^{-Z}} \), di mana Z adalah kombinasi linier dari input dan parameter.

### Pembelajaran Parameter
- Tujuan di regresi logistik adalah belajar parameter W dan B biar Y hat bisa akurat mencerminkan probabilitas Y sama dengan satu.
- Ada banyak notasi yang dipakai, tapi di kursus ini, W dan B dianggap sebagai parameter yang terpisah supaya lebih jelas.

# Memahami Model Regresi Logistik
- Model ini bikin prediksi hasil dengan pakai parameter W (bobot) dan B (bias), dan prediksinya itu ditulis sebagai \( \hat{y} \) lewat fungsi sigmoid.
- Tujuannya adalah buat ngatur W dan B supaya \( \hat{y} \) mendekati label asli \( y \) di set pelatihan.

### Fungsi Kerugian dalam Regresi Logistik
- Fungsi kerugian ini ngukur seberapa baik prediksi model sesuai sama label yang bener, biasanya pakai bentuk yang ngehindarin masalah di optimisasi non-konveks.
- Fungsi kerugian yang dipilih adalah \( -y \log(\hat{y}) - (1 - y) \log(1 - \hat{y}) \), yang bikin prediksi yang bener untuk kedua kelas (0 dan 1) makin terdorong.

### Fungsi Biaya untuk Seluruh Set Pelatihan
- Fungsi biaya ngumpulin kerugian dari semua contoh pelatihan, jadi bisa dapet ukuran tunggal buat performa model.
- Ini didefinisiin sebagai rata-rata dari fungsi kerugian yang diterapin ke setiap contoh pelatihan, biar proses optimisasi bisa meminimalkan kesalahan keseluruhan.

# Memahami Turunan
- Turunan itu ngasih insight tentang gimana fungsi berubah, bikin kamu paham konsep laju perubahan di berbagai situasi.
- Gak perlu jadi jago matematika, punya intuisi dasar soal turunan udah cukup buat ningkatin skill kamu dalam jaringan saraf.

### Aplikasi dalam Jaringan Saraf
- Paham turunan dengan baik bisa bikin performa dan efisiensi jaringan saraf jadi lebih keren.
- Pengetahuan dasar ini bakal dibangun di pelajaran selanjutnya, biar kamu makin paham gimana turunan berfungsi dalam dunia deep learning.

# Struktur dan cara kerja jaringan syaraf, khususnya tentang konsep forward dan backward pass dalam grafik komputasi.

**Memahami Forward Pass**
- Forward pass, atau biasa kita sebut propagasi maju, itu adalah proses menghitung output dari jaringan syaraf dengan cara memproses input lewat berbagai langkah.
- Misalnya, ada fungsi \( J = 3(a + bc) \) yang bisa kita gunakan buat ngitung output lewat variabel-variabel perantara.

**Grafik Komputasi**
- Grafik komputasi ini kayak peta visual yang nunjukin langkah-langkah buat ngitung suatu fungsi, jadi kita bisa lihat bagaimana input itu berhubungan sama output.
- Di contoh ini, variabel \( a, b, \) dan \( c \) menghasilkan perhitungan perantara \( u \) dan \( V \), dan akhirnya jadi output akhir \( J \).

**Backward Pass**
- Nah, backward pass atau backpropagation itu dipakai buat ngitung gradien atau turunan, yang penting banget buat optimasi jaringan syaraf.
- Proses ini melibatkan penelusuran grafik komputasi dari belakang ke depan buat dapetin nilai-nilai yang kita butuhin buat belajar.

# Cara hitung turunan buat nerapin gradient descent di regresi logistik, pakai grafik komputasi biar prosesnya lebih gampang dimengerti.

**Memahami Regresi Logistik**
- Prediksi di regresi logistik itu ditulis sebagai \( Y_{\text{hat}} \), yang dihitung dari jumlah tertimbang fitur-fitur ditambah bias.
- Fungsi loss itu buat ngukur seberapa beda output yang kita prediksi \( A \) dibandingkan dengan label aslinya \( Y \).

**Menghitung Turunan**
- Langkah pertama di backpropagation adalah hitung turunan dari loss terhadap output \( A \). Ini kita dapat rumusnya jadi \( \frac{dL}{dA} = -\frac{Y}{A} + \frac{1-Y}{1-A} \).
- Dengan aturan rantai, turunan loss terhadap \( Z \) disederhanakan jadi \( \frac{dL}{dZ} = A - Y \).

**Memperbarui Parameter**
- Turunan buat bobot \( W_1 \), \( W_2 \), dan bias \( B \) dihitung sebagai \( \frac{dW_1}{dL} = X_1 \cdot \frac{dL}{dZ} \), \( \frac{dW_2}{dL} = X_2 \cdot \frac{dL}{dZ} \), dan \( \frac{dB}{dL} = \frac{dL}{dZ} \).
- Gradient descent memperbarui parameter dengan cara ngurangin hasil kali antara learning rate dan turunan yang udah kita hitung.