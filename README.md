# Forecasting-Business-Performance
Forecasting fashion retail sales using SARIMAX and LSTM models on time series data.

Here's a clean and professional `README.md` based on your **Business Forecasting** slide deck:

---

# Business Forecasting - Solid Sphere

## 📌 Project Overview

This project focuses on **forecasting business performance in the fashion retail industry**, where data-driven decisions are critical for inventory management, budget optimization, and market competitiveness. Our goal is to build predictive models using time series data to support strategic planning and improve supply chain efficiency.

---

## 👥 Team Members

* Nguyễn Hoàng Nghĩa (Leader)
* Nguyễn Minh Hương
* Vũ Minh Quân
* Phạm Việt Anh

---

## 🎯 Objectives

* Analyze historical business data.
* Build a predictive model to forecast future sales performance.
* Help optimize strategic decisions in resource management and supply chain.

---

## 📊 Dataset

* **Main Dataset (SalesFact)**

  * Train set: 2010–2020 (\~900K rows)
  * Test set: 2021–2022 (\~75K rows)
  * Clean dataset: No null values, minimal duplicates
  * Features include sales, units sold, cost metrics, etc.

* **Geography Dataset**

  * Region and city information joined via `Zip` code
  * Feature engineering includes region encoding, city parsing

* **Product Dataset**

  * Clean product info, categories, and segments
  * Categorical encoding applied (e.g., One-hot)

---

## 🧹 Data Preprocessing & Feature Engineering

* Created domain knowledge features:

  * Holidays, seasons (spring, summer, fall, winter)
  * Business days, quarters, week/day of year
* Generated lag features (1, 7, 30 days) and rolling statistics
* Polynomial features (up to degree 3) from variables highly correlated with the target

---

## 🔍 Exploratory Data Analysis

* Sales tend to peak at the beginning and end of months (fashion seasonality)
* Most numerical features are right-skewed
* Outliers observed using boxplots and time-series plots

---

## 🤖 Modeling

### 1. Feature Selection

* Applied **Recursive Feature Elimination with Cross-Validation (RFECV)** using **XGBoost Regressor**
* Selected the top 17 features based on R² score

### 2. Model 1: SARIMAX (Seasonal ARIMA with Exogenous Variables)

* Used **ADF test** to ensure stationarity (applied first differencing)
* Leveraged **Auto-ARIMA** to find optimal parameters
* Achieved strong performance with metrics like R², RMSE, and MAPE
* Visualized predictions vs actuals

### 3. Model 2: LSTM (Long Short-Term Memory)

* Applied **MinMaxScaler** for normalization
* Created time sequences with 50 look-back steps
* Built and trained using **Keras Sequential Model**
* Tracked training loss and evaluated on test set with standard regression metrics

---

## ✅ Results & Conclusion

* Both SARIMAX and LSTM models successfully predicted business performance.
* **SARIMAX outperformed LSTM**, providing better alignment with actual sales data.
* The models offer valuable insights into time-series characteristics and can support **data-driven business decisions** in the fashion industry.


