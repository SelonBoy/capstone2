# Hotel Booking Cancellation Prediction

## Project Overview

Project ini bertujuan untuk memprediksi kemungkinan customer melakukan **booking cancellation** menggunakan machine learning. Model ini diharapkan dapat membantu hotel mengurangi potensi kerugian akibat pembatalan reservasi dengan memberikan insight berbasis data.

Dataset yang digunakan adalah **Hotel Booking Demand Dataset** yang berisi informasi terkait karakteristik customer, detail reservasi, serta histori booking.

---

## Business Problem

### Background

Dalam industri perhotelan, booking cancellation menjadi salah satu faktor utama yang mempengaruhi revenue stability. Tingginya cancellation rate dapat menyebabkan:

* Loss revenue dari kamar kosong
* Kesalahan revenue forecasting
* Inefficient room allocation
* Inefficient staff planning

Tanpa sistem prediksi, hotel hanya dapat bereaksi setelah cancellation terjadi.

### Problem Statement

Bagaimana memprediksi apakah customer akan melakukan booking cancellation berdasarkan data reservasi?

### Goals

Project ini bertujuan untuk:

* Membangun model machine learning untuk prediksi cancellation
* Mengidentifikasi faktor yang mempengaruhi cancellation
* Memberikan business insight berbasis data
* Membantu hotel mengurangi cancellation rate

---

## Dataset Information

Dataset berisi data reservasi hotel dimana:

* Setiap baris = 1 booking
* Setiap kolom = atribut reservasi

Beberapa feature penting:

| Feature                     | Description              |
| --------------------------- | ------------------------ |
| country                     | Negara asal customer     |
| market_segment              | Channel reservasi        |
| previous_cancellations      | Riwayat cancellation     |
| booking_changes             | Jumlah perubahan booking |
| deposit_type                | Jenis deposit            |
| customer_type               | Tipe customer            |
| reserved_room_type          | Tipe kamar               |
| required_car_parking_spaces | Kebutuhan parkir         |
| total_of_special_requests   | Special request          |
| is_canceled                 | Target variable          |

Target:

0 → Not canceled
1 → Canceled

---

## Data Preprocessing

Langkah preprocessing:

* Remove duplicate data
* Handling missing values
* Feature selection
* Encoding categorical features
* Train test split
* Handling class imbalance

Missing value pada feature country diisi dengan kategori:

Unknown

---

## Machine Learning Approach

Problem ini merupakan:

**Supervised Classification Problem**

Model yang diuji:

* Logistic Regression
* Decision Tree
* Random Forest

Improvement yang dilakukan:

* Class weight balancing
* Hyperparameter tuning

---

## Evaluation Metric

Metric yang digunakan:

* Accuracy
* Precision
* Recall
* F1 Score

Metric utama:

**F1 Score**

Karena memberikan keseimbangan antara precision dan recall.

---

## Model Performance

### Baseline Model

| Model               | Accuracy | Recall | F1 Score |
| ------------------- | -------- | ------ | -------- |
| Logistic Regression | 0.79     | 0.25   | 0.36     |
| Decision Tree       | 0.68     | 0.26   | 0.28     |
| Random Forest       | 0.70     | 0.29   | 0.31     |

---

### Improved Model

| Model               | Accuracy | Recall | F1 Score |
| ------------------- | -------- | ------ | -------- |
| Logistic Regression | 0.68     | 0.80   | 0.54     |
| Decision Tree       | 0.59     | 0.86   | 0.50     |
| Random Forest       | 0.70     | 0.79   | 0.55     |

---

## Final Model

Model terbaik:

**Random Forest Classifier**

Alasan:

* Performance paling seimbang
* Recall tinggi untuk deteksi cancellation
* F1 Score terbaik
* Tidak overfit seperti Decision Tree

Model ini memberikan trade-off terbaik antara business needs dan model performance.

---

## Business Insight

Insight yang ditemukan:

Customer dengan previous cancellations tinggi memiliki kemungkinan cancel lebih besar.

Customer dengan deposit cenderung tidak cancel.

Customer dengan banyak special request memiliki kemungkinan cancel lebih kecil.

Segment booking tertentu memiliki cancellation rate lebih tinggi.

---

## Tech Stack

Project ini menggunakan:

Python

Libraries:

* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn

Environment:

Google Colab / Jupyter Notebook

---

## Project Structure

```
project-folder
│
├── Capstone2.ipynb
├── data_hotel.csv
├── README.md
```

---

## How to Run

1 Install dependencies:

```
pip install pandas numpy scikit-learn matplotlib seaborn
```

2 Open notebook:

```
jupyter notebook Capstone2.ipynb
```

atau buka di Google Colab.

3 Run semua cell.

---

## Future Improvement

Beberapa improvement yang bisa dilakukan:

* Feature engineering tambahan
* Model boosting (XGBoost / LightGBM)
* Model deployment
* API prediction service
* Dashboard visualization

---

## Author

Project ini dibuat sebagai bagian dari machine learning capstone project.

---

## Conclusion

Machine learning dapat membantu hotel memprediksi booking cancellation dan memberikan insight untuk mengurangi potensi revenue loss melalui pendekatan data driven decision.

---
