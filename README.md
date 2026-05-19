# 🛍️ Myntra MarketWatch — Unveiling E-commerce Trends

> **An end-to-end Exploratory Data Analysis (EDA) of real Myntra fashion data** — uncovering pricing patterns, brand dominance, colour preferences, customer ratings, and actionable business insights using Python.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation & Setup](#-installation--setup)
- [Methodology](#-methodology)
- [Feature Engineering](#-feature-engineering)
- [Visualizations & Key Findings](#-visualizations--key-findings)
- [Business Insights & Recommendations](#-business-insights--recommendations)
- [Results Summary](#-results-summary)
- [Future Scope](#-future-scope)
- [Author](#-author)

---

## 🧠 Project Overview

**Myntra MarketWatch** is a comprehensive Exploratory Data Analysis project built on a real Myntra fashion e-commerce dataset. The goal is to extract meaningful patterns and business intelligence from product listings — spanning pricing, brand performance, colour trends, customer ratings, and product composition.

This project demonstrates:
- End-to-end data wrangling and cleaning in Pandas
- Feature engineering to derive new business-relevant attributes
- Multi-dimensional visual storytelling with Matplotlib & Seaborn
- Data-driven business recommendations suitable for product/marketing teams

---

## 📦 Dataset

| Property | Details |
|---|---|
| **File** | `Fashion Dataset v2.csv` |
| **Source** | Real Myntra product listings |
| **Domain** | Women's Ethnic Fashion (Kurtas, Sarees, Dupatta Sets, etc.) |
| **Key Columns** | `name`, `brand`, `price`, `colour`, `avg_rating`, `ratingCount`, `products`, `p_id` |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3.x** | Core language |
| **Pandas** | Data loading, cleaning, transformation |
| **NumPy** | Numerical operations, trend fitting |
| **Matplotlib** | Base charting engine |
| **Seaborn** | Statistical visualizations, heatmaps, boxplots |
| **Jupyter Notebook** | Interactive analysis environment |

---

## 📁 Project Structure

```
myntra-marketwatch/
│
├── code.ipynb                        # Main analysis notebook
├── Fashion Dataset v2.csv            # Raw dataset
│
├── charts/
│   ├── chart1_price_distribution.png
│   ├── chart2_top_brands.png
│   ├── chart3_colour_trends.png
│   ├── chart4_product_type.png
│   ├── chart5_ratings.png
│   ├── chart6_price_vs_rating.png
│   ├── chart7_brand_ratings.png
│   ├── chart8_dupatta_analysis.png
│   ├── chart9_segment_vs_rating.png
│   └── chart10_heatmap.png
│
└── README.md
```

---

## ⚙️ Installation & Setup

**1. Clone the repository**
```bash
git clone https://github.com/yourusername/myntra-marketwatch.git
cd myntra-marketwatch
```

**2. Create a virtual environment (recommended)**
```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

**3. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

**4. Launch the notebook**
```bash
jupyter notebook code.ipynb
```

> Ensure `Fashion Dataset v2.csv` is in the same directory as the notebook before running.

---

## 🔬 Methodology

The analysis follows a structured EDA pipeline:

```
Raw Data → Understand → Clean → Engineer Features → Visualize → Insights
```

### Step 1 — Understand the Data
- Inspect shape, column types, missing values, and duplicate rows

### Step 2 — Clean the Data
- Remove duplicate entries
- Drop rows with missing `price` values
- Impute `ratingCount` and `avg_rating` with `0` for unrated products
- Coerce numeric columns to proper `float` types
- Strip whitespace from `colour` and `brand` columns

### Step 3 — Feature Engineering
Four new derived columns are added (see below)

### Step 4 — Visualize & Analyse
Ten charts covering price, brand, colour, product type, ratings, and correlations

---

## 🧪 Feature Engineering

| New Column | Logic | Purpose |
|---|---|---|
| `Price_Segment` | Bucketed price into Budget / Mid-Range / Premium / Luxury | Market segmentation |
| `Rating_Category` | Labelled ratings as No Rating / Low / Average / Good / Excellent | Customer satisfaction analysis |
| `Has_Dupatta` | Boolean — whether the product listing contains a Dupatta | Set completeness analysis |
| `Product_Type` | First item extracted from the `products` comma-separated field | Product category breakdown |

---

## 📊 Visualizations & Key Findings

### Chart 1 — Price Distribution
- Histogram + KDE with Mean/Median markers
- Pie chart of price segment distribution
- **Finding:** Distribution is right-skewed; most products fall in the ₹1K–₹2.5K Mid-Range band

### Chart 2 — Top 15 Brands by Listings
- Horizontal bar chart with annotated counts
- **Finding:** A single dominant brand leads listings, reflecting heavy presence in ethnic women's wear

### Chart 3 — Top 15 Colour Trends
- Bar chart with approximate real colour mapping
- **Finding:** Dark and bold colours (Black, Blue, Pink) dominate the catalogue

### Chart 4 — Product Type Distribution
- Pie chart of top 10 product types
- **Finding:** Kurtas are the backbone of Myntra's women's ethnic catalogue

### Chart 5 — Customer Rating Distribution
- Histogram of ratings + bar chart of rating categories
- **Finding:** Platform average is ~4.x/5; majority of products fall in the "Good (4.0–4.5)" bucket

### Chart 6 — Price vs Rating Scatter Plot
- Colour-encoded by review count, with polynomial trend line
- **Finding:** Near-zero correlation — higher price does NOT guarantee higher ratings

### Chart 7 — Top Brands by Avg Rating
- Filtered to brands with ≥ 20 products for statistical reliability
- **Finding:** Quality-focused smaller brands can outperform volume leaders in customer satisfaction

### Chart 8 — Dupatta Set Analysis
- Side-by-side bar comparison of avg price and avg rating
- **Finding:** Sets with Dupattas command higher prices but sustain equal or better ratings

### Chart 9 — Price Segment vs Rating (Boxplot)
- Distribution of ratings across all four price segments
- **Finding:** Rating distributions are similar across segments — Budget products achieve 4+ ratings just as often as Luxury ones

### Chart 10 — Correlation Heatmap
- Pearson correlations between Price, Avg Rating, and Rating Count
- **Finding:** All three metrics are weakly correlated with each other, confirming that price is not a proxy for quality or popularity

---

## 🎯 Business Insights & Recommendations

| Area | Insight | Recommendation |
|---|---|---|
| **Pricing** | Mid-Range (₹1K–₹2.5K) dominates by volume | Focus GMV and marketing budget here |
| **Quality Perception** | Price ≈ Rating correlation is near-zero | Promote affordable products as "value picks" |
| **Colour Strategy** | Dark/bold colours lead in listings | Prioritise Black, Blue, Pink inventory |
| **Product Mix** | Kurtas are the dominant product type | Expand Kurta variety and exclusive launches |
| **Dupatta Sets** | Higher price, same/better satisfaction | Bundle promotions to increase AOV |
| **Brand Strategy** | Volume ≠ Rating leaders | Separate brand strategies for reach vs. loyalty |
| **Customer Trust** | Most products rated 4.0–4.5 | Leverage ratings in ad creatives |

---

## 📈 Results Summary

```
🛍️  Total Products Analysed  : [from dataset]
🏪  Unique Brands            : [from dataset]
🎨  Unique Colours           : [from dataset]
💰  Average Price            : ~₹[from dataset]
⭐  Platform Avg Rating      : ~4.x / 5
🧣  Products with Dupatta    : [from dataset]
🔗  Price–Rating Correlation : ~0.0xx (near-zero)
```

> Exact values populate at runtime based on the loaded dataset.

---

## 🚀 Future Scope

- **Sentiment Analysis** on product names/descriptions using NLP
- **Brand Clustering** using K-Means based on price, rating, and volume
- **Time-Series Analysis** if listing dates are available
- **Recommendation Engine** — "similar products by price + colour + rating"
- **Dashboard** — Streamlit or Plotly Dash interactive version
- **Discount Analysis** — MRP vs. selling price to compute effective discount bands

---

## 👤 Author

**[Yadav Sumit]**
- GitHub: [@aiworld212](https://github.com/aiworld212)
- LinkedIn: [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)

---
