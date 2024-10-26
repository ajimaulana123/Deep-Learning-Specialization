# Deep-Learning-Specialization

Deep learning itu intinya ngajarin jaringan saraf buatan gede buat tugas-tugas kaya nebak harga rumah berdasarkan banyak faktor.

# Apa itu Neural Network

Oke, jadi begini, bro! Neural Network itu semacam “otak buatan” yang diajarin buat ngambil keputusan atau ngenalin pola, mirip kayak otak kita sendiri yang bisa nyambung-nyambungin informasi. Bayangin aja kayak jaringan kabel-kabel (disebut *neuron*) yang tersambung rapet satu sama lain.

Nah, pas Neural Network ini dilatih, dia kayak dipoles atau dipasokin data biar makin pintar. Awalnya sih agak oon, tapi makin sering dia “latihan”, makin pinter juga buat ngenalin pola. Misal buat ngenalin foto kucing, si Neural Network ini bakal ngecek pola gambar dari banyak foto kucing sampai dia hapal betul bentuknya.

Secara teknis, Neural Network punya *layer* alias lapisan, kayak sandwich gitu. Ada tiga lapisan utama:
1. **Input layer** – tempat data mentah masuk (misalnya, gambar kucing).
2. **Hidden layers** – ini yang kerjanya ribet, lapisan ini ngolah data dari berbagai arah, nyari pola tertentu.
3. **Output layer** – lapisan ini yang kasih hasil akhirnya, misal bilang "ini kucing" atau "ini anjing."

Kuncinya adalah di hidden layers, karena di sana proses analisis dan “pembelajaran” terjadi. Makin banyak hidden layers, makin detail juga analisisnya. 

Tiap neuron di jaringan ini pake fungsi kayak ReLU (Rectified Linear Unit) buat ngolah input dan bikin output yang bener.

Singkatnya, Neural Network itu kayak jaringan otak buatan yang makin jago makin sering latihan, dan bisa bantu ngambil keputusan atau ngenalin sesuatu tanpa kita harus ngasih tahu aturan-aturan detailnya.

# Neural Network dengan Supervised learning

Supervised learning dengan Neural Network itu proses ngajarin jaringan biar bisa ngenalin pola dari data yang udah dikasih label atau jawaban benernya. 

1. **Data Latihan Berlabel**: Kita kasih data yang udah punya label (misal gambar kucing dengan label “kucing”).
2. **Training Process**: Neural Network bakal belajar pola dari data itu. Dia coba nebak output, lalu hasilnya dibandingin sama label yang benar.
3. **Error Calculation & Adjustment**: Kalau tebakannya salah, jaringan ini bakal ngitung error-nya. Lalu, bobot (weight) dalam hidden layers-nya di-adjust supaya prediksi berikutnya makin akurat.
4. **Iterasi**: Proses ini diulang terus-terusan sampai prediksi jaringan mendekati hasil yang benar.

Aplikasinya banyak, bro! Misalnya, buat iklan online neural network bisa nebak kemungkinan orang nge-klik iklan, atau di computer vision buat ngenalin gambar.

**Jenis-Jenis Neural Network**

- Berbagai arsitektur neural network cocok buat tugas tertentu: CNN (Convolutional Neural Network) buat gambar, dan RNN (Recurrent Neural Network) buat data urutan kayak audio atau bahasa.
- Aplikasi yang rumit, misal mobil otonom, biasanya butuh gabungan berbagai jenis neural network, alias arsitektur hibrida.

**Data Terstruktur vs. Tidak Terstruktur**

- Data terstruktur itu punya fitur yang jelas, misalnya atribut rumah, sementara data gak terstruktur kayak gambar dan audio susah diolah komputer.
- Neural network bikin pengolahan data gak terstruktur makin oke banget, kayak di pengenalan suara, gambar, sama pemrosesan bahasa alami.

# Faktor-faktor yang bikin deep learning makin sukses belakangan ini, terutama soal skala data, ukuran jaringan, dan inovasi algoritma.

### Peran Data dan Skala
- Kinerja algoritma tradisional sering mentok dengan data terbatas, sedangkan neural network yang lebih besar bisa terus berkembang dengan nambahnya data.
- Digitalisasi yang pesat bikin data melimpah ruah, dan deep learning bisa banget manfaatin data ini dengan efektif.

### Arsitektur Neural Network dan Performa
- Neural network yang lebih besar dengan banyak parameter cenderung lebih jago, terutama kalo didukung dataset yang gede.
- Hubungan antara ukuran dataset dan efektivitas algoritma berbeda-beda, tapi neural network biasanya unggul di dataset yang besar.

### Inovasi Algoritma dan Efisiensi Komputasi
- Inovasi algoritma, kayak ganti fungsi aktivasi dari sigmoid ke ReLU, bikin pelatihan makin cepet dan efisien.
- Komputasi yang lebih cepat bikin eksperimen bisa lebih banyak dan cepet juga, jadi praktisi bisa terus nyempurnain model mereka.

# Nasihat

- penting banget buat paham mekanisme belajar otak, dan dia usul kalau backpropagation bisa jadi perkembangan evolusioner yang logis.
- Terlibat sama konsep dan algoritma ini itu penting banget buat menguasai deep learning, dan semua pelajar didorong buat eksplorasi dan bertanya selama perjalanan belajar.

