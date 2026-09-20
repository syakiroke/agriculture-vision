# 🌾 Visi Pertanian: Visi Komputer Bertenaga AI untuk Pertanian Modern

<div align="center">

[![Bahasa Indonesia](https://img.shields.io/badge/Language-Bahasa_Indonesia-blue.svg)](#)
[![English](https://img.shields.io/badge/Language-English-red.svg)](README.en.md)

**[ Bahasa Indonesia ]** | **[ [English Version](README.en.md) ]**

---

![License MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue.svg)
![Frameworks](https://img.shields.io/badge/Frameworks-PyTorch%20%7C%20TensorFlow%20%7C%20OpenCV-orange.svg)
![YOLO](https://img.shields.io/badge/YOLO-v8%20%2F%20v11-green.svg)

</div>

Selamat datang di **Agriculture Vision**, sebuah repositori pilihan yang berisi solusi, model, eksperimen penelitian, dan kumpulan data Computer Vision (AI) lengkap yang diterapkan pada pertanian cerdas dan pertanian presisi.

Repositori ini berfungsi sebagai pusat terpusat untuk menerapkan teknik pembelajaran mendalam pada pemantauan tanaman, klasifikasi penyakit, pengelolaan gulma, estimasi hasil panen, dan analisis pertanian dari udara.

---

## 📌 Daftar Isi

* [Gambaran Umum Proyek](#-gambaran-umum-proyek)
* [Domain & Aplikasi Utama](#-domain--aplikasi-utama)
* [Struktur Repositori](#-struktur-repositori)
* [Sub-Proyek Unggulan](#-sub-proyek-unggulan)
* [Susunan Teknologi & Alat](#-susunan-teknologi--alat)
* [Memulai](#-memulai)
  * [Prasyarat](#prasyarat)
  * [Instalasi](#instalasi)
* [Penyebaran Model](#-penyebaran-model)
* [Berkontribusi](#-berkontribusi)
* [Lisensi](#-lisensi)
* [Kontak & Ucapan Terima Kasih](#-kontak--ucapan-terima-kasih)

---

## 🔍 Gambaran Umum Proyek

Pertanian presisi sangat bergantung pada data yang dapat ditindaklanjuti. Dengan memanfaatkan algoritma Computer Vision terkini, **Agriculture Vision** bertujuan untuk mendigitalisasi penilaian lapangan, mengurangi pemborosan input pertanian (pestisida, pupuk), dan memaksimalkan hasil panen melalui inspeksi visual terautomasi secara real-time.

### Tujuan Utama:

1. **Deteksi Dini Penyakit**: Identifikasi cepat patogen tanaman untuk meminimalkan kerusakan tanaman.
2. **Pengelolaan Gulma Presisi**: Segmentasi semantik presisi tinggi untuk memungkinkan penyemprotan herbisida secara lokal.
3. **Prakiraan Hasil Panen Otomatis**: Deteksi dan pelacakan objek untuk menghitung buah, sayuran, dan bunga secara real-time.
4. **Intelijen Pertanian dari Udara**: Pemrosesan gambar satelit/drone multispektral dan RGB untuk pemeriksaan kesehatan lahan skala besar.

---

## 🌿 Domain & Aplikasi Utama

| Domain | Tugas Computer Vision | Arsitektur / Model Umum |
| :--- | :--- | :--- |
| **Patologi Tanaman** | Klasifikasi Gambar Multi-kelas, Deteksi Bounding Box | ResNet, Vision Transformer (ViT), EfficientNet, YOLOv8 |
| **Identifikasi Gulma** | Segmentasi Semantik & Instans | U-Net, DeepLabV3+, Mask R-CNN |
| **Automasi Panen** | Deteksi Objek, Pelacakan Multi-Objek (MOT) | YOLOv8/v11, ByteTRACK, Faster R-CNN |
| **Penginderaan Jauh** | Deteksi Perubahan, Klasifikasi Tutupan Lahan | SegFormer, Swin Transformer, Random Forest (GIS) |

---

## 📂 Struktur Repositori

```text
agriculture-vision/
│
├── 01-plant-disease-detection/    # Model klasifikasi dan lokalisasi penyakit
│   ├── notebooks/                # Jupyter Notebooks pelatihan & EDA
│   ├── models/                   # File bobot tersimpan (.pt, .h5, .onnx)
│   └── src/                      # Kode sumber untuk pelatihan & inferensi
│
├── 02-crop-weed-segmentation/    # Segmentasi tingkat piksel untuk penyemprotan presisi
│   ├── configs/                  # Konfigurasi model
│   └── src/                      # Skrip implementasi U-Net & DeepLab
│
├── 03-fruit-detection-counting/  # Estimasi hasil panen & pelacakan buah real-time
│   ├── tracking/                 # Implementasi pelacakan multi-objek
│   └── inference/                # Skrip pemrosesan aliran kamera real-time
│
├── 04-aerial-crop-monitoring/    # Pemrosesan gambar satelit dan drone
│   ├── raster_processing/        # Alat pemrosesan GIS & kalkulasi NDVI
│   └── notebooks/                # Analisis citra satelit
│
├── data/                         # Sampel himpunan data & skrip saluran data
├── deployment/                   # REST API, Dockerfile, & skrip Aplikasi Web
├── docs/                         # Dokumentasi lanjutan, diagram, & catatan makalah
├── .gitignore                    # Konfigurasi gitignore Python
├── LICENSE                       # Lisensi MIT
├── README.md                     # Dokumentasi utama repositori (Bahasa Indonesia)
├── README.en.md                  # Dokumentasi versi Bahasa Inggris
└── requirements.txt              # Dependensi global Python
```

---

## 🚀 Sub-Proyek Unggulan

### 1. Klasifikasi Penyakit Daun Tanaman 🍃
* **Tujuan**: Mendeteksi hingga 38 kelas penyakit tanaman dari gambar daun menggunakan CNN dan Vision Transformer.
* **Akurasi**: ~98.2% akurasi pengujian pada himpunan data tolok ukur standar.
* **Jalankan Cepat**:
  ```bash
  python 01-plant-disease-detection/src/predict.py --image path/to/leaf.jpg
  ```

### 2. Segmentator Tanaman vs Gulma Real-Time 🌾
* **Tujuan**: Memisahkan tanaman utama dari gulma pengganggu di bawah berbagai kondisi pencahayaan untuk mengarahkan robot penyiang.
* **Metode**: Arsitektur U-Net yang dilatih menggunakan gambar lapangan beresolusi tinggi.

### 3. Penghitung Buah Otomatis & Estimator Bobot 🍎
* **Tujuan**: Mendeteksi dan menghitung buah apel dan tomat yang matang/mentah di pohon dengan pelacakan objek untuk menghindari penghitungan ganda.
* **Metode**: Alur kerja YOLOv8 + ByteTRACK dengan analisis kerapatan bounding box.

---

## 🛠️ Susunan Teknologi & Alat

* **Bahasa Utama**: Python 3.11+
* **Framework Deep Learning**: PyTorch, TensorFlow, Keras
* **Computer Vision**: OpenCV, Ultralytics (YOLO), Albumentations
* **Geospatial & Penginderaan Jauh**: Rasterio, GeoPandas, QGIS, Google Earth Engine API
* **Penyebaran & MLOps**: Streamlit, FastAPI, Docker, ONNX Runtime

---

## 🏁 Memulai

### Prasyarat

Pastikan Anda telah menginstal `git`, `Python 3.11+`, dan `pip` di sistem Anda. Dukungan GPU (CUDA) sangat direkomendasikan untuk pelatihan model.

### Instalasi

1. **Klon Repositori**:
   ```bash
   git clone https://github.com/syakiroke/agriculture-vision.git
   cd agriculture-vision
   ```

2. **Buat dan Aktifkan Lingkungan Virtual**:
   * **Linux/macOS**:
     ```bash
     python -m venv venv
     source venv/bin/activate
     ```
   * **Windows**:
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```

3. **Instal Dependensi**:
   ```bash
   pip install -r requirements.txt
   ```

---

## 🌐 Penyebaran Model

Repositori ini menyertakan templat penyebaran untuk penggunaan langsung di lapangan:

* **Aplikasi Web (Streamlit)**: Jalankan antarmuka web ringan untuk demonstrasi model.
  ```bash
  streamlit run deployment/streamlit_app/app.py
  ```

* **REST API (FastAPI)**: Sediakan titik akhir model untuk integrasi perangkat edge (seperti Raspberry Pi atau Jetson Nano).
  ```bash
  uvicorn deployment.fastapi_app.main:app --reload
  ```

---

## 🤝 Berkontribusi

Kontribusi adalah hal yang membuat komunitas open-source menjadi tempat yang luar biasa untuk belajar, menginspirasi, dan berkreasi. Setiap kontribusi yang Anda berikan **sangat dihargai**!

1. Fork Proyek ini.
2. Buat Feature Branch Anda (`git checkout -b feature/ModelPertanianBaru`).
3. Commit Perubahan Anda (`git commit -m 'Menambahkan model deteksi daun YOLOv11 baru'`).
4. Push ke Branch tersebut (`git push origin feature/ModelPertanianBaru`).
5. Buka Pull Request.

---

## 📜 Lisensi

Didistribusikan di bawah **Lisensi MIT**. Lihat file `LICENSE` untuk informasi lebih lanjut.

---

## 📬 Kontak & Ucapan Terima Kasih

* **Penulis**: Syakir ([@syakiroke](https://github.com/syakiroke))
* **Domain**: Kecerdasan Buatan dalam Pertanian / Computer Vision
* **Ucapan Terima Kasih**: Kumpulan data open-source yang disediakan oleh PlantVillage, Roboflow, dan berbagai peneliti AI Pertanian di seluruh dunia.
