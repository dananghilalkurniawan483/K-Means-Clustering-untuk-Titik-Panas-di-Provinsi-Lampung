🔥 K-Means Clustering untuk Titik Panas di Provinsi Lampung

Proyek ini merupakan analisis spasial terhadap **titik panas (hotspots)** di Provinsi **Lampung, Indonesia**, selama periode satu tahun. Analisis dilakukan menggunakan **metode K-Means Clustering** dengan visualisasi berbasis peta dan evaluasi metrik clustering.

## 📂 Dataset
- **Sumber**: Dataset `titik_panas_indonesia_1_tahun.csv` berisi koordinat (latitude, longitude), confidence level (`low`, `nominal`, `high`), dan FRP (*Fire Radiative Power*).
- **Filtering**: Data difilter berdasarkan batas geografis Provinsi Lampung.

## 🔧 Teknologi dan Library
- Python 3
- `pandas`, `numpy` untuk manipulasi data
- `matplotlib`, `seaborn` untuk visualisasi
- `geopandas`, `shapely` untuk analisis spasial
- `scikit-learn` untuk K-Means dan evaluasi klaster
- Shapefile dari [GADM](https://gadm.org) untuk peta administratif Indonesia

## 📊 Analisis yang Dilakukan

1. **Preprocessing:**
   - Konversi label confidence (`l`, `n`, `h`) menjadi numerik (0, 1, 2)
   - Standarisasi fitur: `latitude`, `longitude`, `confidence`, `frp`

2. **Pemilihan K Optimal:**
   - Metode **Elbow**
   - **Silhouette Score**
   - Evaluasi tambahan: *Davies-Bouldin Index*, *Calinski-Harabasz Score*

3. **Clustering:**
   - Algoritma **K-Means**
   - Visualisasi hasil klaster di peta Lampung
   - Plot sebaran FRP tiap klaster:
     ```python
     import seaborn as sns
     sns.boxplot(data=df_lampung, x='cluster', y='frp')
     plt.title("Sebaran FRP berdasarkan Cluster")
     plt.show()
     ```

4. **Visualisasi Peta:**
   - Titik panas dikelompokkan berdasarkan klaster
   - Peta administratif Provinsi Lampung sebagai latar belakang

## 🧪 Hasil Evaluasi
| Metrik Evaluasi        | Nilai |
|------------------------|-------|
| Silhouette Score       | 0.5057 |
| Davies-Bouldin Index   | 0.9769 |
| Calinski-Harabasz Score| 651.2065 |

> Nilai di atas bergantung pada hasil aktual model.

## 🗺️ Visualisasi

| Klaster Titik Panas di Lampung | Elbow Method | Silhouette Score |
|-------------------------------|--------------|------------------|
| ![map](https://github.com/user-attachments/assets/0ce9ff37-ae56-4292-ac48-bc2fdd7c1f40) | ![elbow](https://github.com/user-attachments/assets/5cc940ef-b2b8-49b8-a99f-a9d09da58b5e) | ![silhouette](https://github.com/user-attachments/assets/40bd6d36-1039-4011-ac68-d3699a3a37fd) |

## 📌 Tujuan Proyek
- Mengidentifikasi sebaran dan intensitas titik panas di Lampung
- Mendukung pengambilan keputusan dalam pengawasan kebakaran hutan/lahan
- Menunjukkan bagaimana machine learning dapat diterapkan untuk analisis geospasial

## 👤 Author
**Danang Hilal Kurniawan**  
Data Science | Geospatial | Machine Learning  
[LinkedIn](https://www.linkedin.com/in/dananghilalkurniawan/)

---
