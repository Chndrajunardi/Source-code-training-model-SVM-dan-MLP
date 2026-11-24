# Source Code Training Model SVM dan MLP

## Deskripsi
Folder ini berisi source code yang digunakan dalam proses pengembangan, pelatihan, optimasi, dan evaluasi model Machine Learning untuk klasifikasi subtipe molekuler kanker payudara berdasarkan data ekspresi gen TCGA-BRCA.

Penelitian ini menggunakan dua algoritma klasifikasi utama, yaitu **Support Vector Machine (SVM)** dan **Multi-Layer Perceptron (MLP)**, dengan label klasifikasi berdasarkan sistem subtipe molekuler PAM50.

## Tujuan
Source code ini digunakan untuk:
- Melakukan preprocessing dan seleksi fitur data ekspresi gen.
- Membangun dan melatih model klasifikasi SVM dan MLP.
- Melakukan optimasi hyperparameter model.
- Mengevaluasi performa model menggunakan metrik klasifikasi.
- Melakukan interpretasi fitur gen berdasarkan model yang dikembangkan.
- Menyimpan model dan artefak preprocessing untuk kebutuhan implementasi lebih lanjut.

## Struktur Source Code

```text
Source-code-training-model-SVM-dan-MLP/
│
├── SVM/
│   └── Source code training dan evaluasi model SVM
│
├── MLP/
│   └── Source code training dan evaluasi model MLP
│
└── README.md
```

*Catatan: Struktur direktori dapat disesuaikan dengan susunan file aktual.*

## Dataset
Dataset yang digunakan berasal dari **The Cancer Genome Atlas (TCGA-BRCA)** melalui UCSC Xena.

Data terdiri atas:
- Data ekspresi gen kanker payudara.
- Data klinis untuk memperoleh informasi subtipe molekuler PAM50.

Lima kelas klasifikasi yang digunakan:
1. Basal-like
2. HER2-enriched
3. Luminal A
4. Luminal B
5. Normal-like

Dataset akhir penelitian terdiri atas 844 sampel setelah proses integrasi, penyaringan, dan seleksi berdasarkan ketersediaan label PAM50.

## Tahapan Pemodelan

### 1. Preprocessing Data
- Integrasi data ekspresi gen dan data klinis.
- Seleksi sampel berdasarkan jenis jaringan dan ketersediaan label PAM50.
- Penanganan data yang tidak valid.
- Pembagian dataset menjadi data latih dan data uji dengan proporsi 80:20.
- Seleksi 2.000 gen berdasarkan variansi tertinggi.
- Standardisasi fitur menggunakan StandardScaler.

### 2. Pelatihan Model SVM
Model Support Vector Machine dikembangkan menggunakan pendekatan klasifikasi multikelas dengan kernel linear.

Tahapan yang dilakukan:
- Pelatihan model awal.
- Optimasi hyperparameter.
- Evaluasi menggunakan Stratified K-Fold Cross-Validation.
- Evaluasi menggunakan Nested Cross-Validation.
- Pengujian pada data uji.
- Analisis kepentingan gen berdasarkan nilai absolut koefisien model.

### 3. Pelatihan Model MLP
Model Multi-Layer Perceptron dikembangkan menggunakan arsitektur jaringan saraf tiruan untuk klasifikasi lima subtipe PAM50.

Tahapan yang dilakukan:
- Penyusunan arsitektur jaringan saraf.
- Pelatihan model menggunakan data latih.
- Validasi selama proses pelatihan.
- Optimasi parameter pelatihan.
- Evaluasi menggunakan data uji.
- Penyimpanan model dalam format `.keras`.

### 4. Evaluasi Model
Evaluasi performa model dilakukan menggunakan metrik:
- Accuracy
- Balanced Accuracy
- Macro Precision
- Macro Recall
- Macro F1-Score
- Macro ROC-AUC
- Matthews Correlation Coefficient (MCC)

## Teknologi dan Library
Source code dikembangkan menggunakan Python dengan beberapa library berikut:

- Python
- NumPy
- Pandas
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
- Joblib
- XGBoost (jika digunakan pada eksperimen pembanding)

## Artefak Model
Model dan komponen preprocessing yang telah dilatih disimpan untuk kebutuhan penggunaan kembali.

Artefak model MLP meliputi:
- `tuned_mlp_final.keras` — model MLP hasil pelatihan.
- `standard_scaler.joblib` — objek standardisasi fitur.
- `selected_gene_names.json` — daftar gen terpilih beserta urutannya.
- `label_mapping.json` — pemetaan label kelas.

Artefak model SVM disimpan sesuai dengan format serialisasi yang digunakan pada proses pelatihan.

## Catatan Penggunaan
1. Pastikan Python dan seluruh library yang dibutuhkan telah terpasang.
2. Sesuaikan lokasi dataset dengan direktori penyimpanan pada source code.
3. Jalankan source code sesuai urutan preprocessing, pelatihan, dan evaluasi.
4. Pastikan urutan fitur gen pada data pengujian sama dengan urutan fitur saat pelatihan.
5. Gunakan objek scaler dan pemetaan label yang sama dengan proses pelatihan ketika melakukan prediksi menggunakan model tersimpan.

## Keterangan
Source code ini merupakan bagian dari penelitian skripsi berjudul:

**"Dashboard Klasifikasi Subtipe Molekuler Kanker Payudara Berdasarkan Ekspresi Gen TCGA-BRCA Menggunakan Machine Learning."**

Seluruh hasil pemodelan digunakan untuk kepentingan penelitian akademik dan bukan sebagai alat diagnosis klinis.
