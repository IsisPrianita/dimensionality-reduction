# Dimensionality Reduction - Week 21-22

Eksplorasi teknik dimensionality reduction untuk klasifikasi aktivitas menggunakan dataset sensor gerak (accelerometer & gyroscope).

## Objective

Membandingkan performa Logistic Regression pada data full-feature vs data hasil reduksi dimensi, untuk dua target klasifikasi: **fall** (binary) dan **label** (13 kelas aktivitas).

## Dataset

- **Train**: 1428 sampel, 9 fitur sensor
- **Test**: 356 sampel
- **Fitur**: `acc_max`, `gyro_max`, `acc_kurtosis`, `gyro_kurtosis`, `lin_max`, `acc_skewness`, `gyro_skewness`, `post_gyro_max`, `post_lin_max`
- **Target `fall`**: binary (jatuh / tidak jatuh)
- **Target `label`**: 13 kelas aktivitas (FKL, SDL, BSC, FOL, WAL, SCH, CSI, STN, STD, JOG, STU, JUM, CSO)

## Methods

| Metode | Deskripsi |
|--------|-----------|
| StandardScaler | Normalisasi fitur sebelum reduksi dimensi |
| PCA | Principal Component Analysis, n_components=2 (fall) / n_components=8 (label) |
| LDA | Linear Discriminant Analysis, n_components=2 (supervised, untuk fall) |
| t-SNE | t-Distributed Stochastic Neighbor Embedding, n_components=2 |

## Results

### Target: `fall`

| Setup | Accuracy | Avg Time (%%timeit) |
|-------|----------|---------------------|
| Full features (scaled) | - | 17.9 ms |
| PCA (n=2) | 0.9522 | - |
| LDA (n=2) | 0.9747 | - |
| t-SNE (n=2) | - | 4.68 ms |

### Target: `label`

| Setup | Accuracy |
|-------|----------|
| PCA (n=8) | 0.7191 |

## Project Structure

```
├── README.md
├── Week21-22.ipynb
└── data/
    ├── Train.csv
    └── Test.csv
```

## Setup

```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
jupyter notebook Week21-22.ipynb
```
