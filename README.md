# 🏨 GTC ML Project 1 – Hotel Booking Data Cleaning & Preprocessing

This repository contains my solution to **GTC ML Project 1**.  
The goal is to transform the raw **hotel_bookings.csv** dataset into a clean, machine-learning-ready dataset for **hotel booking cancellation prediction**.

---

## 📂 Repository Contents
- `hotel_booking_cleaning.ipynb` → Jupyter/Colab notebook with full pipeline  
- `hotel_bookings.csv` → raw dataset (uploaded if size < 100 MB, otherwise link in README)  
- `README.md` → this documentation  

---

## 🚀 Project Phases

### Phase 1: Exploratory Data Analysis (EDA)
- Loaded dataset and explored structure (`.info()`, `.describe()`).
- Checked missing values (counts + heatmap).
- Detected outliers in **ADR** and **Lead Time** with boxplots & IQR method.

### Phase 2: Data Cleaning
- Imputed missing values:
  - `agent` & `company` → 0  
  - `children` → median  
  - `country` → mode  
- Removed duplicates.  
- Capped extreme ADR values (`adr > 1000` → 1000).  
- Converted `reservation_status_date` to datetime.  

### Phase 3: Feature Engineering & Preprocessing
- Created new features:
  - `total_guests = adults + children + babies`  
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`  
  - `is_family` (binary flag if children or babies present)  
- Dropped leakage columns: `reservation_status`, `reservation_status_date`.  
- Encoded categorical features (one-hot, frequency encoding for `country`).  
- Final train-test split: 80/20.  

---

## 📊 Results
- ✅ Cleaned dataset with no missing values.  
- ✅ Outliers handled.  
- ✅ Feature set engineered for ML models.  
- ✅ Dataset split and ready for modeling.  

---

## 🛠️ Libraries Used
- Python (Pandas, NumPy)  
- Visualization: Matplotlib, Seaborn, Missingno  
- Preprocessing: scikit-learn  

---

## 📌 How to Run
1. Clone the repo:  
   ```bash
   git clone https://github.com/Farisemad001/GTC-FirstProject.git
   cd GTC-First_Project
