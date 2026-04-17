# Klasifikasi Bunga Oxford 17 dengan Random Forest

Proyek ini menggunakan algoritma **Random Forest** untuk mengklasifikasikan citra bunga dari dataset **Oxford 17 Flowers** berdasarkan ekstraksi fitur warna, tekstur (GLCM), dan bentuk.

---

## Dataset

- **Nama Dataset:** Oxford 17 Flowers (subset 3 kelas)
- **Jumlah Sampel:** 239 citra
- **Jumlah Fitur:** 16 fitur numerik (Color Moments, GLCM, Area, Perimeter)
- **Target:** 3 kelas bunga: `tigerlily`, `tulip`, `windflower`

**Link Dataset:**  
[Oxford 17 Flowers (Google Drive)](https://drive.google.com/drive/folders/1nEhxGUhYKvLsNrdPYplv2iKSjhJW1tqP?usp=sharing) 

---

## Metode yang Digunakan

- **Ekstraksi Fitur:**
  - Color Moments (mean, std, skewness untuk R, G, B) 9 fitur
  - GLCM Texture (contrast, dissimilarity, homogeneity, energy, correlation) 5 fitur
  - Shape Features (area & perimeter dari objek terbesar) 2 fitur
- **Preprocessing:** Tidak ada scaling, hanya pembersihan kelas "unknown"
- **Algoritma:** Random Forest dengan `n_estimators=100`, `random_state=42`
- **Evaluasi:** Accuracy, Precision, Recall, F1-Score, Confusion Matrix, Feature Importance

---

## Hasil Evaluasi

| Metrik | Nilai |
|--------|-------|
| **Akurasi** | 77.08% |
| **Precision (rata-rata)** | 0.78 |
| **Recall (rata-rata)** | 0.77 |
| **F1-Score (rata-rata)** | 0.77 |

**Classification Report per kelas:**

| Kelas       | Precision | Recall | F1-Score |
|-------------|-----------|--------|----------|
| tigerlily   | 0.83      | 0.62   | 0.71     |
| tulip       | 0.72      | 0.81   | 0.76     |
| windflower  | 0.78      | 0.88   | 0.82     |

**Top 3 Fitur Penting:** Area, G_mean, perimeter (berdasarkan feature importance dari Random Forest).

---