# 🛒 Superstore Performance Analysis

Predicting whether a retail store will be a High, Medium, or Low performer using machine learning — and uncovering the key factors that drive store performance.

---

## 📌 Business Question

> *Can we predict whether a superstore will perform at a High, Medium, or Low level based on its store characteristics?*

Retail companies manage hundreds of stores across different locations. Without understanding what drives performance, they risk misallocating resources — investing in stores that don't need support while neglecting those that do. This project uses data to answer that question.

---

## 📊 Dataset

- **Source:** [Kaggle — Superstore Sales & Performance Analysis](https://www.kaggle.com/)
- **Size:** 895 store records
- **Features used:**

| Feature | Description |
|---|---|
| `Store_Area` | Size of the store in square feet |
| `Items_Available` | Number of different product lines stocked |
| `Daily_Customer_Count` | Average number of customers per day |
| `Store_Sales` | Total sales revenue (Rs) |
| `Performance` | Target variable — High / Medium / Low |

---

## 🔧 Tools & Libraries

- **Python** — pandas, matplotlib, seaborn, scikit-learn
- **Jupyter Notebook**
- **Machine Learning** — Decision Tree Classifier

---

## 🔍 What I Did

### 1. Data Cleaning
- Fixed column name formatting issues
- Converted Store Sales from text to numeric
- Removed one row with an invalid sales value
- Dropped the Store ID column (not useful for prediction)
- Confirmed no missing values or duplicates

### 2. Exploratory Data Analysis (EDA)
Visualised how each feature varies across performance categories before modelling:
- Store performance distribution (High: 604, Medium: 274, Low: 17)
- Average sales by performance category
- Store Area vs Sales scatter plot coloured by performance
- Average daily customer count by performance

### 3. Decision Tree Classification
- Split data 80% train / 20% test
- Set max depth of 4 to keep the model interpretable
- Evaluated using accuracy score and confusion matrix
- Extracted feature importance scores

---

## 📈 Key Results

- **Model Accuracy: 66.5%** on 179 unseen stores
- The model performs best for **High-performing stores**
- Struggled with Low-performing stores due to class imbalance (only 17 examples)

### Feature Importance
| Feature | Importance Score |
|---|---|
| Store Area | 0.376 |
| Daily Customer Count | 0.360 |
| Items Available | 0.264 |

Store size and customer traffic are the strongest predictors of performance.

---

## 💡 Most Interesting Finding

**Low-performing stores actually had the highest average daily customer count (955) — more than both Medium (760) and High (794) stores.**

This suggests a **conversion problem**: these stores attract customers but fail to turn visits into sales. The issue isn't foot traffic — it's what happens once customers are inside.

---

## 📁 Repository Structure
superstore-performance-analysis/
│
├── code.ipynb                        # Full analysis notebook
├── Superstore_Sales_Performance.csv  # Dataset
├── figures/
│   ├── fig1_performance_dist.png
│   ├── fig2_sales_by_perf.png
│   ├── fig3_area_vs_sales.png
│   ├── fig4_customers_by_perf.png
│   ├── fig5_confusion_matrix.png
│   ├── fig6_feature_importance.png
│   └── fig7_tree_diagram.png
└── README.md

## ▶️ How to Run

1. Clone the repository
git clone https://github.com/boomiga18/superstore-performance-analysis.git

2. Install dependencies
pip install pandas matplotlib seaborn scikit-learn jupyter

3. Open the notebook
jupyter notebook code.ipynb

---

## 🚀 Future Improvements

- Address class imbalance using SMOTE or oversampling techniques
- Try Random Forest or XGBoost for better accuracy
- Add a sales per customer metric to capture conversion rate directly
- Build an interactive dashboard using Power BI or Tableau
