# Dimensionality Reduction - Week 21-22

Eksplorasi teknik dimensionality reduction untuk klasifikasi aktivitas (fall detection) menggunakan dataset sensor.

## Objective

Membandingkan performa Logistic Regression pada data full-feature vs data hasil reduksi dimensi, untuk dua target klasifikasi: **fall** dan **label**.

## Methods

| Metode | Deskripsi |
|--------|-----------|
| PCA | Principal Component Analysis, n_components=2 (visualisasi) dan n_components=8 (klasifikasi) |
| LDA | Linear Discriminant Analysis, n_components=2 |
| t-SNE | t-Distributed Stochastic Neighbor Embedding, untuk visualisasi |

## Results (Target: `label`)

| Setup | Accuracy | Avg Time |
|-------|----------|----------|
| Full features (scaled) | ≥ 0.7123 | ~2.27 ms |
| PCA 8 components | ≥ 0.7123 | ~908 μs |

## Project Structure

```
├── README.md
├── requirements.txt
├── Week21-22.ipynb
└── data/
    ├── Train.csv
    └── Test.csv
```

## Setup

```bash
pip install -r requirements.txt
jupyter notebook Week21-22.ipynb
```

## Notes

- `%%timeit` hanya mengukur `lr.score()`, bukan `fit()`, supaya waktu yang diukur representatif
- Visualisasi scatter plot menggunakan `tab10` palette untuk membedakan kelas dengan jelas
