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

---

# Memahami Regresi Logistik
- Regresi logistik ini dipakai saat label output itu biner (0 atau 1), contohnya buat nentuin apakah sebuah gambar itu gambar kucing atau bukan.
- Tujuannya adalah buat ngebaca probabilitas (Y hat) bahwa output (Y) itu sama dengan satu, berdasarkan vektor fitur input (X).

### Peran Fungsi Sigmoid
- Gak kayak fungsi linier (W transpose X + B), regresi logistik pakai fungsi sigmoid supaya Y hat ada di antara 0 dan 1.
- Fungsi sigmoid itu didefinisiin sebagai \( \text{sigmoid}(Z) = \frac{1}{1 + e^{-Z}} \), di mana Z adalah kombinasi linier dari input dan parameter.

### Pembelajaran Parameter
- Tujuan di regresi logistik adalah belajar parameter W dan B biar Y hat bisa akurat mencerminkan probabilitas Y sama dengan satu.
- Ada banyak notasi yang dipakai, tapi di kursus ini, W dan B dianggap sebagai parameter yang terpisah supaya lebih jelas.

---

# Memahami Model Regresi Logistik
- Model ini bikin prediksi hasil dengan pakai parameter W (bobot) dan B (bias), dan prediksinya itu ditulis sebagai \( \hat{y} \) lewat fungsi sigmoid.
- Tujuannya adalah buat ngatur W dan B supaya \( \hat{y} \) mendekati label asli \( y \) di set pelatihan.

### Fungsi Kerugian dalam Regresi Logistik
- Fungsi kerugian ini ngukur seberapa baik prediksi model sesuai sama label yang bener, biasanya pakai bentuk yang ngehindarin masalah di optimisasi non-konveks.
- Fungsi kerugian yang dipilih adalah \( -y \log(\hat{y}) - (1 - y) \log(1 - \hat{y}) \), yang bikin prediksi yang bener untuk kedua kelas (0 dan 1) makin terdorong.

### Fungsi Biaya untuk Seluruh Set Pelatihan
- Fungsi biaya ngumpulin kerugian dari semua contoh pelatihan, jadi bisa dapet ukuran tunggal buat performa model.
- Ini didefinisiin sebagai rata-rata dari fungsi kerugian yang diterapin ke setiap contoh pelatihan, biar proses optimisasi bisa meminimalkan kesalahan keseluruhan.

---

# Memahami Turunan
- Turunan itu ngasih insight tentang gimana fungsi berubah, bikin kamu paham konsep laju perubahan di berbagai situasi.
- Gak perlu jadi jago matematika, punya intuisi dasar soal turunan udah cukup buat ningkatin skill kamu dalam jaringan saraf.

### Aplikasi dalam Jaringan Saraf
- Paham turunan dengan baik bisa bikin performa dan efisiensi jaringan saraf jadi lebih keren.
- Pengetahuan dasar ini bakal dibangun di pelajaran selanjutnya, biar kamu makin paham gimana turunan berfungsi dalam dunia deep learning.

---

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

---

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

---

# Apa Itu Vektorisasi?
- Vektorisasi tuh ngeganti kebutuhan `for loop` jadi nggak usah eksplisit lagi, jadi perhitungan lebih cepat di aplikasi deep learning.
- Contohnya, di regresi logistik, pakai operasi vektorisasi kayak `Z = np.dot(W, X) + B` tuh jauh lebih ngebut daripada harus ngiterin elemen pakai loop `for`.

### Perbandingan Kecepatan
- Ada contoh yang nunjukin kalo versi vektorisasi cuma makan waktu sekitar 1,5 milidetik, sementara versi non-vektorisasi pakai `for loop` bisa makan waktu 400-500 milidetik.
- Jadi keliatan banget kan, vektorisasi bisa bikin kode jalan 300 kali lebih cepat, penting banget buat latih model deep learning biar efisien.

### Maksimalin Hardware
- Baik CPU atau GPU bisa maksimalkan paralelisasi lewat SIMD (Single Instruction Multiple Data), yang bikin performa makin ngebut.
- Jadi, pakai fungsi bawaan bikin Python bisa optimasi perhitungan lebih baik, jadi hindarin deh `for loop` eksplisit kalau bisa.

---

# Ngerti Vektorisasi
- Vektorisasi bikin perhitungan lebih ngebut karena pakai fungsi bawaan, bukan `for-loop` manual. Ini penting banget pas coding neural network atau model regresi.
- Misalnya, buat ngaliin matriks \( A \) sama vektor \( v \), cukup pakai `u = np.dot(A, v)`, nggak perlu `for-loop` bertingkat yang lama banget!

### Optimasi Operasi dengan NumPy
- Buat operasi kayak fungsi eksponensial ke vektor, bisa satu baris aja pakai `u = np.exp(v)`, jadi lebih simpel tanpa `for-loop`.
- NumPy punya banyak fungsi bawaan buat operasi per elemen kayak `np.log(v)`, `np.abs(v)`, dan `v**2`, yang bikin performa makin kenceng.

### Ngebut Implementasi Regresi Logistik
- Di regresi logistik, makin sedikit `for-loop`, makin cepet jalanin kodenya. Pakai operasi vektorisasi bisa ganti banyak `for-loop` jadi satu langkah aja.
- Contohnya, daripada bikin turunan satu-satu dan diinisialisasi nol, bikin aja vektor `dw` terus update pakai vektorisasi. Jadi, prosesnya makin simpel dan cepat!

--- 

# Vektorisasi di Regresi Logistik
- Vektorisasi bikin prediksi semua data latihan dihitung barengan, jadi lebih cepat banget.
- Nggak perlu looping tiap data, kamu bisa langsung hitung semua nilai Z (kombinasi linear dari input) dalam satu baris kode pakai operasi matriks. Satu kali klik, kelar!

### Hitung Aktivasi
- Setelah Z dapet, langsung bisa hitung aktivasi (A) semua data latihan pakai fungsi sigmoid yang udah tervektorisasi.
- Hasilnya? Variabel A besar yang isinya semua aktivasi, rapi satu paket.

### Keuntungan Vektorisasi
- Dengan vektorisasi, nggak perlu `loop` manual lagi, jadi implementasi regresi logistik makin simpel dan ngebut.
- Ngerti teknik ini bakal bantu banget buat aplikasiin trik serupa di neural network atau model machine learning lainnya.

---

### Apa Itu Broadcasting?

Broadcasting itu teknik yang bikin Python otomatis nyamain ukuran array yang lebih kecil biar bisa dihitung bareng sama yang lebih besar. Misalnya nih, kalau kita mau nambahin angka tunggal ke dalam vektor, si angka itu bakal otomatis dijumlahin ke setiap elemen di vektor tersebut. Simpel banget, kan? Bisa juga diterapin buat matriks, jadi kita bisa operasi antar elemen matriks meski dimensinya beda!

### Contoh Seru Broadcasting

Misalnya pas ngitung persentase kalori dari berbagai makanan. Dengan broadcasting, kita tinggal jumlahin kolom di matriks, terus bagi setiap elemen sama totalnya, dan voilà! Gak perlu pake loop sama sekali. Kodenya pun jadi lebih simpel dan rapi!

### Inti Penting

- **Simpel & Efisien:** Broadcasting bikin kodenya jadi lebih pendek, lebih rapi, dan tentunya lebih cepet!
- **Penting Banget:** Terutama buat yang mau mainan jaringan saraf tiruan atau aplikasi data lainnya di Python.

**INTRO:** Di materi ini kita akan bedah betapa pentingnya memahami operasi *broadcasting* di Python, khususnya di library NumPy. Bukan cuma punya keunggulan, tapi ada beberapa hal yang perlu diwaspadai biar enggak kejebak bug halus yang bisa bikin bingung.

---

# Mengenal Broadcasting di NumPy

- Dengan *broadcasting*, kita bisa operasiin array beda bentuk, jadi kodenya lebih ringkas. Tapi hati-hati, kadang malah bisa munculin bug halus kalau konsepnya belum paham bener.
- Contoh, pas nambahin *column vector* ke *row vector*, hasilnya bisa jadi matriks, bukan error! Ini bikin pemula suka kebingungan.

### Hindari Array *Rank* 1

- Array *rank* 1 (bentuknya kayak (5,)) kadang ngasih hasil yang enggak konsisten buat operasi matematika. Sebaiknya pakai bentuk (n,1) buat *column vector* atau (1,n) buat *row vector*.
- Kalau pakai bentuk yang konsisten, kamu bisa hindari hasil-hasil gak terduga, kayak hasil transposenya malah sama aja kayak array awal.

### Tips *Best Practices* Buat Debugging

- Pakai *assertion statement* buat ngecek dimensi array kamu. Ini enggak cuma buat ngecek, tapi juga bisa jadi dokumentasi biar kode lebih rapi.
- Kalau nemu array *rank* 1, *reshape* aja ke dimensi yang kamu mau, biar hasilnya selalu konsisten.

**INTRO:** Materi ini bakal ngebahas kenapa kita butuh *cost function* di *logistic regression*, dan gimana kaitannya sama probabilitas serta *maximum likelihood estimation* alias MLE.

---

# Kenalan Sama *Cost Function* di Logistic Regression

- Di *logistic regression*, prediksi \( \hat{y} \) dianggap sebagai probabilitas \( P(y = 1 | x) \), di mana nilai \( y \) bisa 0 atau 1.
- Nah, *cost function* ini diambil dari probabilitas dua kemungkinan itu dan dibikin jadi satu persamaan aja biar gampang nentuin \( P(y | x) \).

### *Loss Function* dan Fungsi Logaritmik

- Kenapa pakai log? Soalnya fungsi log itu monoton naik terus, jadi kita bisa maksimalkan log dari probabilitas, gak perlu probabilitasnya langsung.
- *Loss function* ini jadi \( -L(\hat{y}, y) \). Jadi, kalo kita minimalin *loss* ini, otomatis kita juga lagi maksimalkan kemungkinan data yang ada. Simpel, kan?


### *Overall Cost Function* dan MLE (Maximum Likelihood Estimation)

- Buat seluruh data training, *cost function* dibuat dari perkalian probabilitas yang diubah ke bentuk jumlah pakai logaritma.
- Dengan cara ini, kalau kita minimalin *cost function* \( J(w, b) \), kita kayak lagi ngelakuin MLE, anggepannya tiap data itu berdiri sendiri alias *IID*.