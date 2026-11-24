# Source Code Training Model SVM dan MLP

## Deskripsi

Repositori ini berisi source code penelitian mengenai klasifikasi subtipe molekuler kanker payudara berdasarkan data ekspresi gen TCGA-BRCA menggunakan pendekatan Machine Learning.

Penelitian ini mengembangkan dan membandingkan dua algoritma klasifikasi, yaitu **Support Vector Machine (SVM)** dan **Multi-Layer Perceptron (MLP)**, dengan menggunakan sistem klasifikasi subtipe molekuler PAM50.

## Struktur Repositori

```text
Source-code-training-model-SVM-dan-MLP/
│
├── Dataset/
│   └── Dataset yang digunakan dalam penelitian
│
├── new.ipynb
│   └── Notebook preprocessing, pelatihan,
│       optimasi, dan evaluasi model
│
└── README.md
    └── Dokumentasi repositori
```

## Dataset

Dataset penelitian diperoleh dari **The Cancer Genome Atlas (TCGA-BRCA)** melalui UCSC Xena.

Dataset mencakup:
- Data ekspresi gen kanker payudara.
- Data klinis pasien untuk memperoleh informasi subtipe molekuler PAM50.

Penelitian menggunakan lima kelas subtipe molekuler PAM50:
1. Basal-like
2. HER2-enriched
3. Luminal A
4. Luminal B
5. Normal-like

Dataset akhir penelitian terdiri atas 844 sampel setelah proses integrasi dan seleksi data.

## Metode Penelitian

### 1. Preprocessing Data
- Integrasi data ekspresi gen dan data klinis.
- Seleksi sampel berdasarkan jenis jaringan.
- Seleksi sampel dengan label PAM50 yang valid.
- Pembagian data latih dan data uji.
- Seleksi fitur berdasarkan variansi gen.
- Standardisasi data ekspresi gen.

### 2. Support Vector Machine (SVM)

Model SVM digunakan untuk melakukan klasifikasi multikelas berdasarkan pola ekspresi gen.

Tahapan pengembangan meliputi:
- Pelatihan model awal.
- Optimasi hyperparameter.
- Stratified K-Fold Cross-Validation.
- Nested Cross-Validation.
- Evaluasi menggunakan data uji.
- Interpretasi kepentingan gen berdasarkan nilai absolut koefisien model.

### 3. Multi-Layer Perceptron (MLP)

Model MLP dikembangkan menggunakan jaringan saraf tiruan untuk mengklasifikasikan lima subtipe molekuler PAM50.

Tahapan pengembangan meliputi:
- Perancangan arsitektur jaringan.
- Pelatihan model.
- Validasi model.
- Optimasi parameter pelatihan.
- Evaluasi performa model.
- Penyimpanan model terlatih.

## Evaluasi Model

Kinerja model dievaluasi menggunakan beberapa metrik klasifikasi:

- Accuracy
- Balanced Accuracy
- Macro Precision
- Macro Recall
- Macro F1-Score
- Macro ROC-AUC
- Matthews Correlation Coefficient (MCC)

## Teknologi dan Library

Penelitian ini menggunakan beberapa teknologi dan library berikut:

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
- Joblib

## Cara Menjalankan Source Code

1. Clone repositori GitHub:

```bash
git clone <URL-REPOSITORY>
```

2. Masuk ke direktori repositori:

```bash
cd Source-code-training-model-SVM-dan-MLP
```

3. Instal library yang diperlukan:

```bash
pip install numpy pandas scikit-learn tensorflow matplotlib joblib
```

4. Buka notebook `new.ipynb` menggunakan Jupyter Notebook atau Visual Studio Code.

5. Sesuaikan lokasi dataset apabila diperlukan.

6. Jalankan setiap cell secara berurutan sesuai tahapan penelitian.

## Keterangan Penelitian

Source code ini merupakan bagian dari penelitian skripsi dengan judul:

**"Klasifikasi Subtipe Molekuler Kanker Payudara Berdasarkan Ekspresi Gen TCGA-BRCA Menggunakan Machine Learning."**

Seluruh proses pemodelan dan hasil evaluasi ditujukan untuk kepentingan penelitian akademik, bukan sebagai alat diagnosis klinis.
