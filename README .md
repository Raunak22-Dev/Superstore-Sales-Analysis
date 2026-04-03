# 🛒 Superstore Sales — Business Analytics & EDA

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-4c9be8)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter)
![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-20BEFF?logo=kaggle)

> *Finding what drives profit — and what quietly destroys it — in a US retail superstore.*

---

## 📌 Project Overview

This project performs a complete **Business Analytics & EDA** on the [Sample Superstore dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final), covering 9,994 orders placed across the United States between **2014–2017**.

Each row is a line item — a product sold within an order. The analysis identifies which regions, categories, products, and discount levels are making money and which are not.

🔗 **[View on Kaggle](https://www.kaggle.com/code/raunakgangwal/superstore-sales-analysis)** 

---

## 🔍 Key Questions Answered

- Which **Region** generates the most Sales and Profit?
- Which **Category** is most profitable — and which is a liability?
- Does **discounting** actually help sales or does it destroy margins?
- Which **products** make the most profit — and which lose the most money?
- Which **State** is bleeding the most losses?
- What is the **monthly sales trend** — when does the store peak?
- How long does it take to **ship orders** by mode?

---

## 💡 Key Findings

| Finding | Detail |
|---|---|
| 🏆 Highest Sales Region | West |
| 💰 Most Profitable Category | Technology |
| 📉 Least Profitable Category | Furniture (near breakeven or loss) |
| 🎯 Biggest Discount Sub-Category | Binders |
| ⚠️ Discount–Profit Correlation | −0.22 (higher discount = lower profit) |
| 📦 Most Used Ship Mode | Standard Class (~60% of orders) |
| 🗓️ Peak Sales Month | November (Black Friday / holiday season) |
| 🔴 Highest Loss State | Texas (−$24,853) |
| 📊 Loss-Making Orders | ~30% of all orders result in a loss |

---

## 📁 Project Structure

```
superstore-sales-eda/
│
├── data/
│   └── Sample - Superstore.csv
│
├── superstore_portfolio.ipynb 
└── README.md
```

---

## 📊 Visualizations Included

| Chart | Key Insight |
|---|---|
| Bar chart — Sales by Region | West dominates, South lags |
| Bar chart — Profit by Category (with labels) | Technology earns 3× more than Office Supplies |
| Line chart — Monthly Sales Trend | November is the clear peak every year |
| Scatter + regression — Discount vs Profit | Discount above 40% = almost guaranteed loss |
| Horizontal bar — Top 10 Profitable Sub-Categories | Copiers alone outperform most categories |
| Bar chart — Orders by Ship Mode | Standard Class handles 60% of volume |
| Heatmap — Avg Profit by Region × Category | Furniture loses money in Central and East regions |

---

## 🗂️ Analysis Sections

### 1. Data Loading & Exploration
- 9,994 rows × 21 columns, zero nulls, zero duplicates
- 793 unique customers, 1,862 products, 531 cities
- Encoding: `windows-1252` (required for this CSV)

### 2. Data Cleaning
- `Order Date` and `Ship Date` converted from string to datetime
- `Processing Days` column created (`Ship Date − Order Date`)
- 519 same-day shipment rows removed (zero processing time)
- Whitespace stripped from all string columns to prevent silent groupby mismatches

### 3. Feature Engineering
- `Order Year`, `Order Month`, `Order Quarter` extracted from `Order Date`
- `Profit Margin (%)` = `(Profit / Sales) × 100`
- `Loss` boolean column — flags every loss-making order
- `Sales Category` — 4 bins using `pd.cut()`: Low / Medium / High / Very High

### 4. Business Insights
- Sales and Profit broken down by Region, Category, Sub-Category
- Top 5 most profitable and top 5 most loss-making products identified
- Discount vs Profit correlation computed and visualized
- Monthly and yearly trend analysis
- Worst-performing state by total profit identified

### 5. Visualizations
- 7 charts with business narrative interpretation after each

---

## 🚀 How to Run

**Option 1 — Kaggle (recommended, no setup needed)**
> Dataset is pre-attached. Just open and Run All.  
> 🔗 [View Notebook on Kaggle](https://www.kaggle.com/code/raunakgangwal/superstore-sales-analysis)

**Option 2 — Run Locally**

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/superstore-sales-eda.git
cd superstore-sales-eda

# 2. Install dependencies
pip install pandas matplotlib seaborn jupyter

# 3. Download dataset from Kaggle
pip install kaggle
kaggle datasets download -d vivek468/superstore-dataset-final
unzip superstore-dataset-final.zip -d data/

# 4. Launch notebook
jupyter notebook superstore_portfolio.ipynb
```

> ⚠️ **Important:** Load the CSV with `encoding='windows-1252'` — standard UTF-8 will throw a `UnicodeDecodeError`.

```python
df = pd.read_csv('data/Sample - Superstore.csv', encoding='windows-1252')
```

---

## 🧠 Skills Demonstrated

| Skill | Used In |
|---|---|
| `pd.to_datetime()` | Converting Order Date and Ship Date from strings |
| `pd.Timedelta()` | Date arithmetic for Processing Days |
| `pd.cut()` | Binning Sales into Low / Medium / High / Very High |
| `groupby()` + `agg()` | Regional, category, product-level profit analysis |
| `pivot_table()` + heatmap | Region × Category profit matrix |
| `corr()` | Quantifying Discount → Profit relationship |
| `ax.text()` on barplot | Adding data labels directly on chart bars |
| Whitespace stripping | Preventing silent groupby mismatches |

---

## 📚 Dataset

- **Name:** Sample — Superstore
- **Source:** [Kaggle — vivek468/superstore-dataset-final](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- **Period:** 2014 – 2017
- **Size:** 9,994 orders × 21 columns
- **License:** CC0 Public Domain

---

## 👤 Author

**Raunak**  
Final Year Engineering Student — SNJB's College of Engineering, Nashik  

[![Kaggle](https://img.shields.io/badge/Kaggle-Profile-20BEFF?logo=kaggle)](https://www.kaggle.com/raunakgangwal)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?logo=linkedin)](https://www.linkedin.com/in/raunakgangwal/)

---

