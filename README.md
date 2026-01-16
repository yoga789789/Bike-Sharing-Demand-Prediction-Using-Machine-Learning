# English Version

# Bike Sharing Demand Prediction Using Machine Learning

## 📌 Project Overview
This project aims to build a machine learning model to predict bike-sharing demand based on historical usage data, time-based patterns, seasonal factors, and weather conditions.  
The objective is not only to achieve accurate predictions, but also to provide insights that can support operational planning and business decision-making in bike-sharing systems.

The project uses regression-based machine learning models, with **XGBoost** selected as the final model due to its superior performance and stability.

---

## 🎯 Business Problem
Bike-sharing operators face challenges in:
- Managing bike availability during peak hours
- Redistributing bikes efficiently across time and seasons
- Anticipating demand fluctuations caused by weather and calendar effects

An inaccurate demand estimation may lead to:
- Bike shortages during high-demand periods
- Excess idle bikes during low-demand periods
- Inefficient operational costs

This project addresses these issues by predicting hourly bike demand using machine learning.

---

## 📊 Dataset
The dataset contains historical bike-sharing data with features including:
- Time-related variables (hour, day, month, year)
- Seasonal indicators
- Weather conditions
- Environmental factors (temperature, humidity)
- Calendar effects (weekday vs weekend, holidays)

Target variable:
- **cnt**: total number of bike rentals

---

## 🔧 Data Preparation
The data preparation process includes:
- Handling missing and duplicated data
- Ensuring correct data types
- Feature selection and transformation
- Encoding categorical variables using One-Hot Encoding
- Scaling numerical features where appropriate
- Preventing data leakage using pipelines

All preprocessing steps are integrated into a machine learning pipeline.

---

## 🤖 Modeling Approach
Several regression models were evaluated using cross-validation:
- Linear Regression
- K-Nearest Neighbors
- Decision Tree
- Random Forest
- XGBoost

To handle skewness in the target variable, a **log transformation** was applied using `TransformedTargetRegressor`.

### Final Model
- **XGBoost Regressor**
- Selected based on lowest error and strongest generalization performance

---

## 📈 Evaluation Metrics
Model performance was evaluated using:
- **RMSE (Root Mean Squared Error)**
- **MAE (Mean Absolute Error)**
- **MAPE (Mean Absolute Percentage Error)**
- **R² Score**

These metrics were chosen to balance interpretability, robustness to outliers, and relevance to business impact.

---

## ⚙️ Hyperparameter Tuning
Hyperparameter tuning was conducted using `RandomizedSearchCV` with a controlled search space to avoid overfitting.

Key tuned parameters include:
- Max depth
- Learning rate
- Number of estimators
- Subsampling ratio
- Column sampling ratio
- Minimum child weight

The tuned model demonstrated improved performance compared to the baseline model.

---

## 🔍 Model Interpretation
Feature importance analysis shows that bike demand is primarily influenced by:
- **Hour of the day** (strongest predictor)
- **Day type (weekend vs weekday)**
- **Seasonal patterns**
- **Yearly trend (growth in usage over time)**

These insights align with real-world bike-sharing usage behavior.

---

## 💼 Business Impact
With a Mean Absolute Percentage Error (MAPE) of approximately **25%**, the model provides sufficiently reliable predictions for:
- Hourly bike redistribution planning
- Resource allocation during peak demand
- Operational decision support

Even modest improvements in demand prediction accuracy can lead to:
- Reduced operational inefficiencies
- Better bike availability
- Potential revenue optimization

---

## ⚠️ Limitations
- The model performs best under normal conditions and may be less accurate during extreme events (e.g., severe weather, public events).
- The dataset is limited to a specific time period, which may not fully capture long-term behavioral changes.
- Spatial information (station location, trip origin-destination) is not included.

---

## 🚀 Future Improvements
- Incorporate spatial features such as station locations
- Add external data (events, holidays, real-time weather forecasts)
- Explore time-series or deep learning approaches (e.g., LSTM)
- Continuously retrain the model with new data

---

## 📌 Conclusion
This project demonstrates how machine learning can be applied to predict bike-sharing demand and translate predictive performance into actionable business insights.  
The final XGBoost model balances accuracy, stability, and interpretability, making it suitable for operational decision support in bike-sharing systems.

---

## 🛠️ Tools & Libraries
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib / Seaborn
- Tableau (for visualization)

---

# Versi Bahasa Indonesia

# Prediksi Permintaan Bike-Sharing Menggunakan Machine Learning

## 📌 Gambaran Proyek
Proyek ini bertujuan untuk membangun model machine learning yang mampu memprediksi permintaan peminjaman sepeda berdasarkan data historis penggunaan, faktor waktu, musim, dan kondisi cuaca.  
Selain berfokus pada akurasi prediksi, proyek ini juga menekankan interpretasi model serta pemanfaatan hasil prediksi untuk mendukung pengambilan keputusan operasional pada sistem bike-sharing.

Model terbaik yang digunakan dalam proyek ini adalah **XGBoost Regressor**, yang dipilih berdasarkan hasil evaluasi performa dan stabilitas model.

---

## 🎯 Permasalahan Bisnis
Operator bike-sharing menghadapi berbagai tantangan, antara lain:
- Ketidakseimbangan ketersediaan sepeda pada jam sibuk
- Kesulitan mengantisipasi lonjakan dan penurunan permintaan
- Inefisiensi biaya operasional akibat distribusi sepeda yang tidak optimal

Kesalahan dalam memprediksi permintaan dapat menyebabkan:
- Kekurangan sepeda saat permintaan tinggi
- Sepeda menganggur pada periode permintaan rendah
- Penurunan kualitas layanan dan kepuasan pengguna

Proyek ini berupaya menjawab permasalahan tersebut melalui pendekatan machine learning.

---

## 📊 Dataset
Dataset yang digunakan merupakan data historis sistem bike-sharing yang mencakup:
- Variabel waktu (jam, hari, bulan, tahun)
- Faktor musiman
- Kondisi cuaca
- Faktor lingkungan (suhu dan kelembapan)
- Informasi kalender (hari kerja, akhir pekan, dan hari libur)

Target prediksi:
- **cnt**: jumlah total peminjaman sepeda

---

## 🔧 Data Cleaning & Feature Engineering
Tahapan persiapan data meliputi:
- Penanganan data hilang dan duplikat
- Penyesuaian tipe data
- Pemilihan fitur yang relevan
- Encoding variabel kategorikal menggunakan One-Hot Encoding
- Scaling variabel numerik
- Pencegahan data leakage dengan penggunaan pipeline

Seluruh proses preprocessing diintegrasikan dalam pipeline machine learning.

---

## 🤖 Pendekatan Pemodelan
Beberapa model regresi dievaluasi menggunakan cross-validation, antara lain:
- Linear Regression
- K-Nearest Neighbors
- Decision Tree
- Random Forest
- XGBoost

Untuk mengatasi distribusi target yang tidak simetris, dilakukan transformasi logaritmik pada variabel target menggunakan `TransformedTargetRegressor`.

### Model Final
- **XGBoost Regressor**
- Dipilih karena memberikan error terendah dan kemampuan generalisasi terbaik

---

## 📈 Evaluation Metrics
Evaluasi performa model dilakukan menggunakan metrik berikut:
- **RMSE (Root Mean Squared Error)**
- **MAE (Mean Absolute Error)**
- **MAPE (Mean Absolute Percentage Error)**
- **R² (Coefficient of Determination)**

Pemilihan metrik ini mempertimbangkan keseimbangan antara interpretabilitas, sensitivitas terhadap error ekstrem, serta relevansi terhadap dampak bisnis.

---

## ⚙️ Hyperparameter Tuning
Hyperparameter tuning dilakukan menggunakan `RandomizedSearchCV` dengan ruang pencarian parameter yang terkontrol untuk menghindari overfitting.

Parameter yang dioptimalkan meliputi:
- Kedalaman pohon (max depth)
- Learning rate
- Jumlah pohon (n_estimators)
- Subsample
- Colsample by tree
- Minimum child weight

Hasil tuning menunjukkan peningkatan performa model dibandingkan model baseline.

---

## 🔍 Interpretasi Model
Analisis feature importance menunjukkan bahwa permintaan sepeda terutama dipengaruhi oleh:
- **Jam dalam sehari** (faktor paling dominan)
- **Hari dalam minggu (akhir pekan vs hari kerja)**
- **Musim**
- **Tren tahunan (pertumbuhan penggunaan dari waktu ke waktu)**

Temuan ini selaras dengan pola penggunaan sepeda di dunia nyata.

---

## 💼 Dampak Bisnis
Dengan nilai MAPE sekitar **25%**, model mampu memberikan estimasi permintaan yang cukup andal untuk:
- Perencanaan distribusi dan redistribusi sepeda
- Optimalisasi operasional pada jam sibuk
- Pengambilan keputusan berbasis data

Peningkatan akurasi prediksi berpotensi menurunkan biaya operasional dan meningkatkan kualitas layanan.

---

## ⚠️ Limitasi Model
- Model kurang optimal dalam menangani kondisi ekstrem, seperti cuaca buruk atau event khusus.
- Dataset terbatas pada periode tertentu sehingga belum sepenuhnya merepresentasikan perubahan perilaku jangka panjang.
- Informasi spasial (lokasi stasiun, rute perjalanan) belum dimanfaatkan.

---

## 🚀 Pengembangan Selanjutnya
- Menambahkan fitur spasial (lokasi stasiun, origin–destination)
- Mengintegrasikan data eksternal seperti event dan prakiraan cuaca
- Menerapkan pendekatan time-series atau deep learning (misalnya LSTM)
- Melakukan retraining model secara berkala dengan data terbaru

---

## 📌 Kesimpulan
Proyek ini menunjukkan bahwa machine learning dapat digunakan secara efektif untuk memprediksi permintaan bike-sharing dan menghasilkan insight yang relevan bagi operasional bisnis.  
Model XGBoost yang dikembangkan mampu memberikan keseimbangan antara akurasi, stabilitas, dan interpretabilitas, sehingga layak digunakan sebagai alat pendukung pengambilan keputusan.

---

## 🛠️ Tools & Library
- Python
- Pandas & NumPy
- Scikit-learn
- XGBoost
- Matplotlib & Seaborn
- Tableau (visualisasi)

---


## 👤 Author
Yoga Brahma  
Capstone Project – Machine Learning
