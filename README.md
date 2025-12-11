# 📈 Forecasting Inflasi Indonesia

### *Wavelet Transform–based ARIMA–XGBoost Hybrid Model*

Repositori ini berisi kode, visualisasi, dan dokumentasi penelitian saya bersama rekan saya, mengenai peramalan inflasi Indonesia menggunakan pendekatan **hybrid Wavelet Transform–based ARIMA–XGBoost**. Penelitian ini dilakukan menggunakan data inflasi bulanan Indonesia periode **Desember 2002 – Agustus 2025** dari Bank Indonesia.

Bagi saya secara pribadi, proyek ini menjadi bagian penting dari portofolio magang karena menunjukkan kompetensi dalam:

* Statistical modeling (ARIMA, diagnostic checks, time-series stationarity)

* Machine learning regression

* Signal decomposition menggunakan wavelet transform

* Hybrid modeling untuk data ekonomi makro

* End-to-end workflow mulai dari pembersihan data, analisis, pemodelan, evaluasi, hingga visualisasi

Proyek ini merepresentasikan kemampuan saya dalam menggabungkan metode statistika dan teknik machine learning modern untuk menghasilkan solusi prediktif yang relevan bagi kebutuhan industri dan instansi pemerintah. Dengan dokumentasi lengkap dan reproducible workflow, penelitian ini saya sertakan sebagai salah satu proyek dalam portofolio magang saya di bidang data science, analytics, dan economic forecasting.

---

##  1. Latar Belakang Singkat

Inflasi merupakan indikator makroekonomi penting yang memengaruhi stabilitas harga, daya beli, dan kebijakan moneter. Data inflasi Indonesia menunjukkan:

* Pola tren jangka panjang yang stabil
* Fluktuasi acak jangka pendek
* Nilai ekstrem pada periode tertentu (2005, 2008, 2022)
* Ketidakstasioneran
* Autokorelasi residual pada model ARIMA

Model ARIMA mampu menangkap pola linear, tetapi masih menyisakan pola non-linear dan autocorrelation. Untuk itu digunakan pendekatan **Wavelet Transform–based ARIMA–XGBoost**, yakni model hybrid yang mampu menangkap:

* Tren jangka panjang (komponen low-frequency)
* Fluktuasi non-linear jangka pendek (high-frequency residuals)

Pendekatan ini menghasilkan prediksi yang lebih stabil, adaptif, dan akurat untuk data dengan dinamika multiskala seperti inflasi Indonesia.

---

## 2. Tujuan

* Membangun model hybrid **WT–ARIMA–XGBoost** untuk memprediksi inflasi Indonesia.
* Melakukan dekomposisi sinyal menggunakan **wavelet transform**.
* Memodelkan:

  * Komponen linear → ARIMA
  * Komponen non-linear → XGBoost
* Melakukan evaluasi akurasi menggunakan **RMSE, MAE, dan MAPE**.
* Menghasilkan multi-step forecasting yang berguna untuk kebijakan moneter.

---

## 3. Metodologi

### **3.1 Wavelet Transform**

* Melakukan dekomposisi sinyal inflasi menjadi beberapa level frekuensi:

  * **Approximation (A)** → tren jangka panjang
  * **Detail (D)** → fluktuasi jangka pendek
* Dekomposisi menggunakan wavelet (mis. *Daubechies db4*)
* Setiap komponen model dijalankan secara terpisah

### **3.2 ARIMA Modeling**

* Digunakan untuk komponen linear (A).
* Pemilihan model berdasarkan:

  * ACF & PACF
  * Uji Ljung–Box
  * Minimasi AIC/BIC

### **3.3 XGBoost Modeling**

* Digunakan untuk komponen nonlinear (D).
* Model dilatih menggunakan residual ARIMA atau komponen detail wavelet.
* Hyperparameter tuning menggunakan grid search.

### **3.4 Hybrid Forecasting**

Prediksi final dihitung dengan menjumlahkan prediksi ARIMA dan prediksi XGBoost dari masing-masing komponen wavelet.

---

## 4. Hasil (Ringkas)

Penelitian ini berhasil menerapkan model hybrid Wavelet–ARIMA–XGBoost untuk memprediksi inflasi bulanan di Indonesia dengan menggunakan data historis Januari 2002 hingga Agustus 2025. Melalui proses dekomposisi wavelet, deret waktu inflasi dipisahkan menjadi komponen linear dan non-linear sehingga masing-masing dapat dimodelkan secara optimal. Komponen linear dimodelkan menggunakan ARIMA(3,0,5), sementara komponen non-linear diestimasi melalui XGBoost. Integrasi kedua pendekatan ini menghasilkan model hybrid yang lebih representatif dibandingkan model tunggal.

Evaluasi performa menunjukkan hasil yang sangat baik, dengan RMSE = 0,0066, MAE = 0,0050, dan MAPE = 4,44% pada data uji selama 12 bulan. Nilai error yang rendah ini menunjukkan bahwa model hybrid mampu menghasilkan prediksi yang stabil dan akurat, baik untuk horizon jangka pendek maupun menengah. Kombinasi metode statistika dan machine learning ini terbukti mampu menangkap dinamika kompleks inflasi yang tidak sepenuhnya linear, sehingga memberikan peningkatan signifikan dibandingkan pemodelan tradisional.

Secara substantif, model ini memiliki potensi untuk mendukung proses pengambilan keputusan dalam kebijakan ekonomi nasional—terutama dalam penentuan suku bunga acuan, pengelolaan subsidi energi, dan perencanaan fiskal maupun moneter.

---

##  6. Referensi

Daftar referensi ilmiah yang digunakan antara lain:

* Mankiw (2021)
* Box & Jenkins (1970)
* Hyndman & Athanasopoulos (2018)
* Chen et al. (2016) — XGBoost
* Jiang Li et al. (2023) — WT-based Hybrid Model
* Bank Indonesia (2009, 2025)
  dan literatur terkait lainnya yang tercantum dalam laporan lengkap.

---

##  7. Kontak

Untuk pertanyaan:
**Nafalla – Statistics Student & Data Science Enthusiast**
Email: *afftanurrisma@gmail.com*

---
