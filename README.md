<img width="1486" height="881" alt="viz6_positive_rate_category" src="https://github.com/user-attachments/assets/a3e43920-960c-44f5-9cc2-9af92bc04aaa" />
<img width="1634" height="881" alt="viz5_rating_vs_discount" src="https://github.com/user-attachments/assets/c8c5a796-3d01-49f8-bb04-0d80c4945990" />
<img width="2086" height="923" alt="viz4_keyword_analysis" src="https://github.com/user-attachments/assets/6fffbd91-98fb-400b-b28e-08a358dda067" />
<img width="1636" height="1031" alt="viz3_sentiment_by_category" src="https://github.com/user-attachments/assets/d7e12080-19e9-482d-9682-f5c6a3a76518" />
<img width="1784" height="881" alt="viz2_rating_distribution" src="https://github.com/user-attachments/assets/8af7bac6-2a59-4e8e-876d-da9c6f6ac231" />
<img width="934" height="1032" alt="viz1_sentiment_donut" src="https://github.com/user-attachments/assets/e76fd783-7d00-4350-a8a7-9183dea9ff98" />
# 🛒 Amazon Product Reviews — Sentiment Analysis

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c?style=for-the-badge)
![Seaborn](https://img.shields.io/badge/Seaborn-Heatmaps-4c72b0?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![NLP](https://img.shields.io/badge/NLP-Keyword%20Analysis-00d4ff?style=for-the-badge)

**Sentiment classification of 1,464 Amazon India product reviews using ratings, keyword analysis & visual storytelling.**

[📊 Dashboard](#-interactive-dashboard) · [📓 Notebook](#-jupyter-notebook) · [📈 Visuals](#-visualizations) · [🔍 Findings](#-key-findings)

</div>

---

## 📌 Project Overview

This project performs **end-to-end sentiment analysis** on Amazon India product reviews across 3 major categories (Electronics, Computers & Home) to answer:

- What percentage of products receive positive vs negative sentiment?
- What keywords dominate positive and negative reviews?
- Do higher discounts correlate with better or worse ratings?
- Which product categories have the highest customer satisfaction?

---

## 📁 Repository Structure

```
amazon-sentiment-analysis/
│
├── 📓 Amazon_Sentiment_Analysis.ipynb     ← Jupyter Notebook (full analysis)
├── 📊 Sentiment_Dashboard.html            ← Interactive Power BI-style Dashboard
├── 📄 amazon.csv                          ← Dataset (1,464 products)
├── 🐍 ai_impact_analysis.py               ← Python analysis script
├── 📋 requirements_ai.txt                 ← Dependencies
│
└── visuals/
    ├── viz1_sentiment_donut.png
    ├── viz2_rating_distribution.png
    ├── viz3_sentiment_by_category.png
    ├── viz4_keyword_analysis.png
    ├── viz5_rating_vs_discount.png
    └── viz6_positive_rate_category.png
```

---

## 📊 Dataset

| Column | Description |
|---|---|
| `product_name` | Full product title |
| `category` | Hierarchical category path |
| `rating` | Numeric star rating (0–5) |
| `discounted_price` | Sale price (₹ INR) |
| `discount_percentage` | % off from original |
| `review_title` | Short review headline |
| `review_content` | Full customer review text |

**1,464 rows · 16 columns · 3 main categories · Amazon India**

---

## 🔧 Sentiment Methodology

```python
def label_sentiment(rating):
    if rating >= 4.0:   return 'Positive'   # ✅ 75.8%
    elif rating >= 3.0: return 'Neutral'    # 😐 23.8%
    else:               return 'Negative'   # ❌  0.4%
```

Keyword analysis uses a custom **stop-word filtered word frequency count** on combined `review_title + review_content`.

---

## 📈 Visualizations

### 1. Sentiment Distribution (Donut Chart)
> 75.8% Positive · 23.8% Neutral · 0.4% Negative — Amazon India shoppers are largely satisfied.

![Sentiment Donut](visuals/viz1_sentiment_donut.png)

---

### 2. Rating Distribution by Sentiment
> Most product ratings cluster between 4.0–4.3, confirming a left-skewed distribution favoring positive experiences.

![Rating Distribution](visuals/viz2_rating_distribution.png)

---

### 3. Sentiment Breakdown by Category
> Electronics leads in volume. All categories maintain strong positive ratios above 74%.

![Sentiment by Category](visuals/viz3_sentiment_by_category.png)

---

### 4. Keyword Analysis — Positive vs Negative
> Positive reviews emphasize *charging, quality, fast, durable, value*. Negative reviews flag *stopped, return, broken, issue*.

![Keywords](visuals/viz4_keyword_analysis.png)

---

### 5. Rating vs Discount % Scatter
> No strong correlation between discount size and product rating — quality drives satisfaction, not price cuts.

![Scatter](visuals/viz5_rating_vs_discount.png)

---

### 6. % Positive Reviews by Category
> All major categories exceed 74% positive sentiment. Office Products leads slightly.

![Positive Rate](visuals/viz6_positive_rate_category.png)

---

## 🔍 Key Findings

| # | Finding |
|---|---------|
| ✅ | **75.8%** of Amazon India products receive Positive sentiment |
| 😐 | **23.8% Neutral** — improvement opportunity in mid-range products |
| 💬 | Top positive words: *charging, quality, fast, durable, value, nice* |
| 🔴 | Top negative words: *stopped, issue, return, broken, defective* |
| 💰 | **Higher discounts ≠ higher ratings** — quality matters more than price |
| 🛍️ | Electronics (526 products) dominates, followed by Computers (453) |
| ⭐ | Average rating: **4.10 / 5.0** across all products |

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/theabdulwasay/amazon-sentiment-analysis.git
cd amazon-sentiment-analysis

# Install dependencies
pip install -r requirements_ai.txt

# Launch Jupyter Notebook
jupyter notebook Amazon_Sentiment_Analysis.ipynb
```

---

## 📦 Requirements

```
pandas>=1.5.0
matplotlib>=3.6.0
seaborn>=0.12.0
numpy>=1.23.0
jupyter>=1.0.0
```

---

## 🌐 Interactive Dashboard

Open **`Sentiment_Dashboard.html`** in any browser — no server required.
Features: Live donut chart, stacked category bars, keyword bars, KPI cards.

---

## 👤 Author

<div align="center">

**Abdul Wasay**

[![GitHub](https://img.shields.io/badge/GitHub-theabdulwasay-181717?style=for-the-badge&logo=github)](https://github.com/theabdulwasay)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Abdul%20Wasay-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/theabdulwasay)
[![Email](https://img.shields.io/badge/Email-abdulwasaymalik757@gmail.com-D14836?style=for-the-badge&logo=gmail)](mailto:abdulwasaymalik757@gmail.com)

</div>

---

## 📄 License

MIT License — see [LICENSE_AI.txt](LICENSE_AI.txt)

---

<div align="center">
⭐ Star this repo if you found it useful!
</div>
