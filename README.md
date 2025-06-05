![download (5)](https://github.com/user-attachments/assets/93caec63-fed6-43c4-8a7a-0829985c1051)# 🔥 K-Means Clustering untuk Titik Panas di Provinsi Lampung

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

## 📁 Struktur Folder
project-root/
│
├── titik_panas_indonesia_1_tahun.csv
├── GDAM/ # Shapefile wilayah Indonesia
├── kmeans_lampung.py # Kode utama analisis
├── hasil_klaster_lampung.csv # Output data dengan label klaster
├── README.md


## 📌 Tujuan Proyek
- Mengidentifikasi sebaran dan intensitas titik panas di Lampung
- Mendukung pengambilan keputusan dalam pengawasan kebakaran hutan/lahan
- Menunjukkan bagaimana machine learning dapat diterapkan untuk analisis geospasial

## 👤 Author
**Danang Hilal Kurniawan**  
Data Science | Geospatial | Machine Learning  
[LinkedIn](https://www.linkedin.com/in/dananghilalkurniawan/)

---
