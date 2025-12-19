# 📘 Judul Proyek
Perbandingan Logistic Regression, Random Forest, dan MPL untuk Prediksi Keberadaan 7 Spesies Amfibi Berdasarkan Fitur Lingkungan

## 👤 Informasi
- **Nama:** Fadillah Dwi Anggraini 
- **Repo:** (https://github.com/Fadillahdaa/DataScientUAS.git)
- **Video:** (https://drive.google.com/drive/folders/1JRL8NxJUzQbC_0ocWCBIB8qer999WU9d?usp=sharing) 

---

# 1. 🎯 Ringkasan Proyek
- Menyelesaikan permasalahan sesuai domain  
- Melakukan data preparation  
- Membangun 3 model: **Baseline**, **Advanced**, **Deep Learning**  
- Melakukan evaluasi dan menentukan model terbaik  

---

# 2. 📄 Problem & Goals
**Problem Statements:**  
- Model perlu mampu memprediksi keberadaan 7 spesies amfibi secara multi-label.
-  Dataset yang terbatas (189 sampel) berpotensi menyebabkan model overfitting dan sulit menangkap pola umum
- Terjadi ketidakseimbangan kelas antar spesies, di mana beberapa spesies jauh lebih sering muncul dibanding spesies lain.
- Diperlukan pipeline preprocessing yang tepat untuk data fitur lingkungan campuran (numerik dan kategorikal/ordinal) agar model dapat memanfaatkan informasi habitat secara optimal dan menghasilkan prediksi yang stabil pada berbagai kondisi lingkungan.

**Goals:**  
- Membangun pipeline data science lengkap dari EDA hingga deployment.
- Mencapai akurasi >65% untuk prediksi keberadaan spesies.
- Mengidentifikasi fitur-fitur yang mempengaruhi keberadaan amfibi.
- Membandingkan model yang berbeda.

---
## 📁 Struktur Folder
```
project/
│
├── data/                   # Dataset (tidak di-commit, download manual)
│
├── notebooks/              # Jupyter notebooks
│   └── ML_Project.ipynb
│
├── src/                    # Source code
│   
├── models/                 # Saved models
│   ├── model_baseline.pkl
│   ├── model_rf.pkl
│   └── model_cnn.h5
│
├── images/                 # Visualizations
│   └── r
│
├── requirements.txt        # Dependencies
├── .gitignore
└── README.md
```
---

# 3. 📊 Dataset
- **Sumber:** UCI Machine Learning Repository +1 https://archive.ics.uci.edu/dataset/528/amphibians 
- **Jumlah Data:** 189 
- **Tipe:** tabular

### Fitur Utama
 ["ID", "Integer", "ID unik", "1, 2, 3"],
    ["Motorway", "Categorical (String)", "Jenis/ruas jalan tempat lokasi pengamatan berada.", "A1, S52"],
    ["SR", "Numerik (Integer)", "Luas permukaan waduk/kolam", "200, 600"],
    ["NR", "Numerik (Integer)", "Jumlah waduk atau kolam air di sekitar lokasi", "1, 2, 6"],
    ["TR", "Kategorikal (kode Integer)", "Tipe/jenis waduk atau badan air", "1, 5, 12"],
    ["VR", "Kategorikal (kode Integer)", "Kondisi/keberadaan vegetasi pada waduk/sekitar lokasi", "0, 1, 4"],
    ["SUR1", "Kategorikal (kode Integer)", "Tutupan lahan/lingkungan sekitar lokasi", "2, 6, 10"],
    ["SUR2", "Kategorikal (kode Integer)", "Tutupan lahan/lingkungan sekitar lokasi", "1, 2, 6"],
    ["SUR3", "Kategorikal (kode Integer)", "Tutupan lahan/lingkungan sekitar lokasi", "1, 2, 6"],
    ["UR", "Kategorikal (kode Integer)", "Jenis pemanfaatan waduk/area oleh manusia", "0, 1, 2"],
    ["FR", "Kategorikal (kode Integer)", "Intensitas/aktivitas memancing di lokasi", "0, 1, 2, 3"],
    ["OR", "Ordinal", "Tingkat/kelas keterbukaan/akses area tepi waduk", "25, 50, 75, 99"],
    ["RR", "Ordinal", "Kelas jarak minimum lokasi ke jalan", "0, 1, 2"],
    ["BR", "Ordinal", "Kelas jarak minimum lokasi ke bangunan", "0, 1, 5"],
    ["MR", "Kategorikal", "Kondisi pemeliharaan/kebersihan/maintenance lokasi", "0, 1, 2"],
    ["CR", "Kategorikal", "Karakter tepi waduk", "1, 2"],
    ["Label (7 spesies)", "Kategorikal (Binary 0/1)", "Label target (ada/tidak ada) untuk 7 spesies amfibi", "0, 1"],

---

# 4. 🔧 Data Preparation
- Cleaning (missing/duplicate/outliers)  
- Transformasi (encoding/scaling)  
- Splitting (train/val/test)  

---

# 5. 🤖 Modeling
- **Model 1 – Baseline:** Logistic Regression  
- **Model 2 – Advanced ML:** Random Forest  
- **Model 3 – Deep Learning:** Deep Learning Model

---

# 6. 🧪 Evaluation
**Metrik:** Accuracy / F1 / MAE / MSE (pilih sesuai tugas)

### Hasil Singkat
 ["LogReg (Baseline)", 0.5339, 0.4577, 0.3872, 0.0279, None],
    ["Random Forest (Advanced)", 0.7014, 0.5110, 0.2368, 9.0999, None],
    ["Deep Learning (MLP Keras)", 0.6667, 0.3941, 0.2594, 5.0654, 0.8245],

---

# 7. 🏁 Kesimpulan
- Model terbaik: Random Forest  
- Alasan: Random Forest memberikan performa paling baik dibanding model lainnya, ditunjukkan oleh Micro-F1 tertinggi (0.7014) dan Hamming Loss terendah (0.2368). Hasil ini menunjukkan Random Forest lebih mampu menangkap pola hubungan fitur lingkungan yang cenderung non-linear. Dibanding MLP, Random Forest juga lebih stabil pada dataset kecil dan label yang tidak seimbang.
- Insight penting: Dataset bersifat multi-label, sehingga satu lokasi dapat memiliki lebih dari satu spesies amfibi sekaligus.
Dataset memiliki ketidakseimbangan label, di mana beberapa spesies sangat dominan (misalnya Brown frogs) sedangkan spesies tertentu jarang muncul (misalnya Great crested newt).


Fitur SR (luas permukaan) memiliki rentang nilai yang sangat besar sehingga perlu penanganan seperti transformasi log agar lebih stabil saat pemodelan

# 8. 🔮 Future Work
- [v] Tambah data  
- [v] Tuning model  
- [v] Coba arsitektur DL lain  
- [v] Deployment  

---

# 9. 🔁 Reproducibility
Gunakan environment:
