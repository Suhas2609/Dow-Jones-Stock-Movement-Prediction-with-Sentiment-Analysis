# Dow Jones Stock Movement Prediction with News Sentiment

## 🔍 Problem Statement

Predict whether the Dow Jones index will go **Up**, **Down**, or remain **Stable** using a combination of **historical stock price data** and **news sentiment**.

---

## 📦 Data Sources

1. **`Combined_News_DJIA.csv`**

   * Contains 25 news headlines per day.
   * Target: Whether DJIA increased (1) or decreased (0) that day.

2. **`formatted_stock_data.csv`**

   * Contains daily OHLC (Open, High, Low, Close) stock data.
   * Target labels converted into `Up`, `Down`, `Stable` based on price movements.

---

## ⚙️ Workflow Overview

### 1. Data Cleaning & Preparation

* Convert date columns to datetime format.
* Merge Top1 to Top25 headlines into one unified text field.
* Lowercase and clean special characters from headlines.
* Merge news data and stock data on the common `Date` column.

### 2. Feature Engineering

* TF-IDF vectorization for textual data.
* Combine with numerical stock data (technical indicators if needed).

### 3. Label Creation

* Based on difference between `Close` and `Open`:

  * Positive change: `Up`
  * Negative change: `Down`
  * Small/no change: `Stable`

### 4. Model Training

* Used **Random Forest Classifier** as baseline.
* Input: Combined sentiment and stock features.
* Output: Multi-class classification (Up, Down, Stable).

### 5. Evaluation

* Metrics: Accuracy, Confusion Matrix, Classification Report.
* Visualizations for class distribution and feature impact.

---

## 📊 Key Results

* The model captured market movement patterns reasonably well.
* Sentiment data added value, especially on volatile days.
* Accuracy improved with combined textual + numerical input vs either alone.

---

## 🧠 Learnings

* Merging text and numeric data can significantly improve predictive modeling.
* Proper text preprocessing (like merging, cleaning) is critical.
* Temporal alignment of datasets is non-trivial but essential.

---

## 🚀 Future Enhancements

* Replace TF-IDF with **FinBERT** or **Transformer-based sentiment extraction**.
* Explore sequence models like **LSTM** or **Temporal Fusion Transformers**.
* Use real-time news API for dynamic predictions.

---

## 📁 Folder Structure (Suggested)

```
DowJonesPrediction/
├── stock.ipynb
├── README.md
```

---

## 📈 Tools & Libraries

* `pandas`, `numpy`, `matplotlib`, `seaborn`
* `sklearn` (RandomForestClassifier, metrics)
* `nltk` or `re` for basic text preprocessing

---

## 📅 Timeline Summary

* Data Ingestion ✅
* Preprocessing & Cleaning ✅
* Feature Engineering ✅
* Model Training & Evaluation ✅
* Analysis & Reporting ✅
