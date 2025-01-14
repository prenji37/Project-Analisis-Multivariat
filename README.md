# Prediksi Kualitas Udara di Jakarta Berdasarkan Data ISPU

Proyek ini bertujuan untuk memprediksi kualitas udara di Jakarta berdasarkan data **Indeks Standar Pencemar Udara (ISPU)**. Dalam penelitian ini, dilakukan perbandingan dua metode klasifikasi, yaitu **Naive Bayes** dan **Ordinal Logistic Regression**, untuk menentukan model yang lebih akurat.

---

## 📋 Pendahuluan

Kualitas udara adalah aspek penting yang memengaruhi kesehatan manusia dan lingkungan. Dengan menggunakan data ISPU yang mencakup parameter seperti **PM10**, **PM2.5**, **SO2**, **CO**, **O3**, dan **NO2**, proyek ini bertujuan untuk:
1. Memprediksi kualitas udara di Jakarta.
2. Membandingkan kinerja **Naive Bayes** dan **Ordinal Logistic Regression**.

---

## 📂 Dataset

Dataset yang digunakan berasal dari **Portal Data Terbuka Indonesia**:
- **Sumber**: [Data ISPU Jakarta](https://katalog.data.go.id/dataset/data-indeks-standar-pencemar-udara-ispu-di-provinsi-dki-jakarta1)
- **Dimensi**: 1804 baris dan 11 kolom.
- **Fitur Utama**:
  - PM10, PM2.5, SO2, CO, O3, NO2.
  - Kategori kualitas udara: "Baik", "Sedang", "Tidak Sehat", dan "Sangat Tidak Sehat".

---

## 🔍 Metodologi

### 1. **Naive Bayes**
- **Gaussian Naive Bayes**: Untuk data kontinu dengan distribusi Gaussian.
- **Bernoulli Naive Bayes**: Untuk data biner.

### 2. **Ordinal Logistic Regression**
- Mempertimbangkan urutan kategori kualitas udara.
- Dua pendekatan:
  - **All-Threshold Variant**: Menggunakan threshold untuk setiap kategori.
  - **Immediate-Threshold Variant**: Menggunakan threshold langsung untuk semua kategori.

---

## 📊 Hasil Analisis

### Statistik Deskriptif
- **PM10**: Rata-rata 46.74 μg/m³, maksimum 163 μg/m³.
- **PM2.5**: Rata-rata 65.97 μg/m³, maksimum 287 μg/m³.
- **SO2**: Rata-rata 37.68 μg/m³.
- **CO**: Rata-rata 12.48 μg/m³.
- **O3**: Rata-rata 28.13 μg/m³.
- **NO2**: Rata-rata 17.35 μg/m³.


## 🔬 Uji Hipotesis

**Tujuan Uji Hipotesis:**  
Mengidentifikasi apakah variabel pencemar udara (PM10, PM2.5, SO2, CO, O3, NO2) memiliki pengaruh signifikan terhadap kategori kualitas udara.

### Langkah-Langkah Uji Hipotesis:
1. **Pernyataan Hipotesis:**
   - **H0 (Hipotesis Nol):** Tidak ada pengaruh signifikan dari variabel pencemar udara terhadap kategori kualitas udara.
   - **H1 (Hipotesis Alternatif):** Ada pengaruh signifikan dari variabel pencemar udara terhadap kategori kualitas udara.

2. **Metode Pengujian:**
   - **Tes ANOVA (Analysis of Variance):** Menguji signifikansi pengaruh variabel independen terhadap variabel dependen.
   - **P-Value:** Jika p-value < 0.05, maka H0 ditolak.

3. **Hasil Uji ANOVA:**
   - Semua variabel pencemar udara (PM10, PM2.5, SO2, CO, O3, NO2) memiliki nilai **p < 0.05**, menunjukkan bahwa mereka memiliki pengaruh signifikan terhadap kategori kualitas udara.

4. **Kesimpulan:**
   - **H0 ditolak**, sehingga variabel pencemar udara secara signifikan memengaruhi kategori kualitas udara.

### Interpretasi Hasil:
- **PM2.5** memiliki pengaruh paling signifikan berdasarkan Mutual Information Score.
- **O3** memiliki pengaruh paling rendah dibandingkan variabel lainnya.

### Perbandingan Model
| Model                                                | Akurasi | RMSE | MSE  |
|------------------------------------------------------|---------|------|------|
| Gaussian Naive Bayes                                 | 92%     | 0.38 | 0.15 |
| Bernoulli Naive Bayes                                | 78%     | 0.58 | 0.78 |
| Ordinal Logistic Regression (All-Threshold Variant)  | 46%     | 0.96 | 0.92 |
| Ordinal Logistic Regression (Immediate Threshold)    | 47%     | 1.25 | 1.58 |

### Kesimpulan
- **Gaussian Naive Bayes** lebih akurat dibandingkan **Bernoulli Naive Bayes dan Ordinal Logistic Regression (All-Threshold Variant) serta Ordinal Logistic Regression (Immediate Threshold) **.
- Model ini mampu menangani data kontinu dengan lebih baik.

---

## 📈 Visualisasi
- **Histogram dan Boxplot**: Memvisualisasikan distribusi data untuk PM10, PM2.5, SO2, CO, O3, dan NO2.
- **Correlation Heatmap**: Menunjukkan hubungan antar fitur polutan.

---

## 🚀 Cara Menggunakan

1. Clone repositori:
   ```bash
   git clone https://github.com/username/repo-name.git

2. Instal Dependensi
   `pip install -r requirements.txt`
