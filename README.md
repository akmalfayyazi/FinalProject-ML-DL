# Final Project - Machine Learning & Data Mining

## Author
| Nama              | NRP        |
|-------------------|------------|
| Seifeldein Akbar            | 5054241032      |
| Mohammad Akmal Fayyazi            | 5054241045      |
| Rasya Audrea Bramantya Wijaya            | 5054241034      |
| Ahnaf Tsabit Attaqi            | 5054231012      |

## Deskripsi Proyek
Proyek ini membandingkan performa berbagai model machine learning dengan menggunakan ekstraksi fitur dari arsitektur deep learning EfficientNet dan ResNet pada dataset gambar.

## Struktur Direktori

```
FinalProject-ML-DM/
├── dataset/                    # Dataset gambar asli
├── Dataset-CSV/               # Hasil ekstraksi fitur dalam format CSV
├── Dataset-Split/             # Dataset yang telah di-split untuk training/testing
├── Data-Split(80-20).ipynb   # Notebook untuk splitting data
├── Ekstraksi-fitur-Non-Normalized.ipynb  # Ekstraksi fitur tanpa normalisasi
├── Ekstraksi-fitur-Normalized.ipynb      # Ekstraksi fitur dengan normalisasi
├── Skenario-1.ipynb          # Perbandingan ML dengan EfficientNet
├── Skenario-2.ipynb          # Perbandingan ML dengan ResNet
├── Skenario-3-Efficientnet.ipynb  # Perbandingan scaling/normalisasi (EfficientNet)
├── Skenario-3-Resnet.ipynb        # Perbandingan scaling/normalisasi (ResNet)
├── Skenario-4.ipynb          # Perbandingan EfficientNet vs ResNet
└── requirements.txt          # Dependencies proyek
```

## Alur Kerja Proyek

### 1. Ekstraksi Fitur
Proses ekstraksi fitur dilakukan menggunakan dua arsitektur pre-trained model:
- **EfficientNet**: Model yang efisien dengan performa tinggi
- **ResNet**: Model dengan arsitektur residual connection

Ekstraksi dilakukan dalam dua varian:
- **Normalized**: Fitur hasil ekstraksi dinormalisasi
- **Non-Normalized**: Fitur hasil ekstraksi tanpa normalisasi

**Output**: Dataset dalam format CSV disimpan di folder `Dataset-CSV/`

### 2. Data Splitting
File `Data-Split(80-20).ipynb` digunakan untuk membagi data hasil ekstraksi menjadi:
- Training set (80%)
- Testing set (20%)

Proses splitting dilakukan pada 4 dataset hasil ekstraksi (EfficientNet & ResNet, masing-masing normalized dan non-normalized), menghasilkan **8 file CSV**.

**Output**: Dataset yang telah di-split disimpan di folder `Dataset-Split/`

### 3. Skenario Eksperimen

#### Skenario 1: Perbandingan Model ML dengan Ekstraksi Fitur EfficientNet
Membandingkan performa berbagai algoritma machine learning menggunakan fitur yang diekstraksi dari EfficientNet.

**Model yang dibandingkan:**
- Support Vector Machine (SVM)
- Random Forest
- K-Nearest Neighbors (KNN)
- Logistic Regression
- Neural Network
- dll.

#### Skenario 2: Perbandingan Model ML dengan Ekstraksi Fitur ResNet
Membandingkan performa berbagai algoritma machine learning menggunakan fitur yang diekstraksi dari ResNet.

**Model yang dibandingkan:** (sama seperti Skenario 1)

#### Skenario 3: Perbandingan Scaling dan Normalisasi
Membandingkan pengaruh scaling dan normalisasi dalam proses training model:
- `Skenario-3-Efficientnet.ipynb`: Eksperimen dengan fitur EfficientNet
- `Skenario-3-Resnet.ipynb`: Eksperimen dengan fitur ResNet

**Aspek yang dibandingkan:**
- Performa dengan normalisasi vs tanpa normalisasi
- Pengaruh preprocessing terhadap akurasi model
- Waktu training dan konvergensi

#### Skenario 4: Perbandingan EfficientNet vs ResNet
Membandingkan secara langsung performa ekstraksi fitur antara EfficientNet dan ResNet pada model machine learning yang sama.

## Cara Menjalankan Proyek

### Instalasi Dependencies
```bash
pip install -r requirements.txt
```

### Urutan Eksekusi

1. **Ekstraksi Fitur**
   ```bash
   # Jalankan salah satu atau kedua notebook berikut:
   jupyter notebook Ekstraksi-fitur-Normalized.ipynb
   jupyter notebook Ekstraksi-fitur-Non-Normalized.ipynb
   ```

2. **Split Data**
   ```bash
   jupyter notebook Data-Split(80-20).ipynb
   ```

3. **Jalankan Skenario Eksperimen**
   ```bash
   # Pilih skenario yang ingin dijalankan:
   jupyter notebook Skenario-1.ipynb
   jupyter notebook Skenario-2.ipynb
   jupyter notebook Skenario-3-Efficientnet.ipynb
   jupyter notebook Skenario-3-Resnet.ipynb
   jupyter notebook Skenario-4.ipynb
   ```

## Hasil dan Evaluasi

Setiap skenario menghasilkan metrik evaluasi yang mencakup:
- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Training Time

## Kesimpulan

Proyek ini memberikan insight komprehensif tentang:
- Performa berbagai algoritma ML pada fitur deep learning
- Pengaruh arsitektur ekstraksi fitur (EfficientNet vs ResNet)
- Pentingnya preprocessing (normalisasi) dalam pipeline ML
- Trade-off antara akurasi dan efisiensi komputasi