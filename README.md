# uts-machine-learning-241011401508

Repositori ini berisi pengerjaan UTS Machine Learning mencakup implementasi manual algoritma **Linear Regression** dan **Logistic Regression** menggunakan **NumPy**, evaluasi model, eksperimen *threshold*, serta perbandingannya dengan **Scikit-Learn**.

## Identitas Mahasiswa
- **Nama**  : Alya Anjani Kasra
- **NIM**   : 241011401508
- **Kelas** : 05TPLM001



## Ringkasan Hasil tugas

### 1. Linear Regression (Prediksi Penjualan dari Biaya Iklan)
* **Tujuan**: Memprediksi angka penjualan berdasarkan biaya iklan yang dikeluarkan (`Ads_Data.csv`).
* **Rumus Persamaan Garis**: 
  > **Penjualan = 28.9945 + (9.0688 × Biaya Iklan)**
* **Artinya**: Setiap kali biaya iklan ditambah **1 juta Rupiah**, diperkirakan penjualan akan naik sebesar **9,0688 juta Rupiah**.
* **Seberapa Akurat Modelnya?**
  * Nilai **R2 Score = 0.9154** 
  * Rata-rata margin kesalahan (RMSE) hanya sekitar **8,28 juta Rupiah**.
* **Pilihan Learning Rate Terbaik**: Angka **`0.02`** adalah yang paling pas—proses belajarnya stabil dan cepat mencapai titik paling optimal.


### 2. Logistic Regression (Deteksi Email Spam)
* **Tujuan**: Membedakan mana email biasa (Normal) dan mana email sampah (`Email_Data.csv`).
* **Hasil Evaluasi**:
  * **Akurasi**: **100% (1.0000)** pada data *testing*.
  * **Precision & Recall**: **100%**.
  * Semua email berhasil ditebak dengan benar tanpa ada yang salah klasifikasi!
* **Mana Error yang Lebih Berbahaya? (FP vs FN)**
  * **False Positive (FP)** = Email penting/asli malah masuk ke folder Spam.
  * **False Negative (FN)** = Email spam lolos dan masuk ke Inbox utama.
  * **Kesimpulan**: **False Positive jauh lebih merugikan**, karena pengguna bisa ketinggalan informasi penting (seperti panggilan kerja/tagihan). Oleh karena itu, kita memilih *threshold* **0.5 - 0.7** agar email penting tidak salah terlempar ke spam.

### 3. Bonus: Perbandingan dengan Scikit-Learn
* **Linear Regression**: Hasil koefisien manual buatan sendiri dengan *scikit-learn* hasilnya **100% persis sama** ($m = 9.0688$, $b = 28.9945$).
* **Logistic Regression**: Ada sedikit perbedaan kecil pada angka koefisien karena *scikit-learn* secara otomatis memasang fitur penalti (*regularization L2*) untuk mencegah model terlalu 'menghafal' data, sedangkan model manual kita dibuat polos tanpa penalti.
