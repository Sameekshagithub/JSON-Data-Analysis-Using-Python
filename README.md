# JSON-Data-Analysis-Using-Python
A end-to-end data analysis project using JSON data with Python.
Covers data loading, cleaning, visualization, and export.

---

## 📁 Project Structure

```
json-data-analysis/
│
├── json_data_analysis.ipynb   # Main Jupyter Notebook
├── sales_data.json            # Sample dataset (30 records)
├── sales_analysis.csv         # Exported cleaned data (generated)
├── sales_analysis.json        # Exported enriched JSON (generated)
├── summary_by_category.csv    # Category summary (generated)
├── monthly_revenue.csv        # Monthly trend (generated)
└── README.md                  # This file
```

---

## 🚀 Getting Started

### 1. Clone / Download
Download or copy `json_data_analysis.ipynb` and `sales_data.json`
into the same folder.

### 2. Install Dependencies
```bash
pip install pandas matplotlib seaborn plotly
```

### 3. Launch Jupyter
```bash
jupyter notebook json_data_analysis.ipynb
```

### 4. Run All Cells
Go to **Kernel → Restart & Run All**

---

## 📦 Requirements

| Library     | Purpose                        |
|-------------|--------------------------------|
| `pandas`    | Data manipulation              |
| `numpy`     | Numerical operations           |
| `matplotlib`| Static charts                  |
| `seaborn`   | Statistical visualizations     |
| `plotly`    | Interactive charts             |

---

## 📋 Notebook Sections

| # | Section                        | Description                                      |
|---|--------------------------------|--------------------------------------------------|
| 1 | Install & Import Libraries     | Setup all dependencies                           |
| 2 | Load JSON Data                 | Parse JSON → Pandas DataFrame                    |
| 3 | Data Exploration               | Shape, dtypes, missing values, `.describe()`     |
| 4 | Cleaning & Feature Engineering | Date parsing, revenue, order size, quarter       |
| 5 | Aggregations & GroupBy         | Category, region, monthly, pivot table           |
| 6 | Visualizations (7 charts)      | Bar, line, donut, heatmap, scatter, Plotly       |
| 7 | Correlation Analysis           | Heatmap of numeric correlations                  |
| 8 | Top Products & Customers       | Top-5 rankings with horizontal bar chart         |
| 9 | KPI Summary Dashboard          | Total revenue, avg order, best month, etc.       |
|10 | Export Results                 | CSV, JSON, and PNG chart files                   |

---

## 🗃️ Dataset — `sales_data.json`

30 e-commerce orders across 2024 with these fields:

| Field        | Type    | Description                          |
|--------------|---------|--------------------------------------|
| `order_id`   | int     | Unique order number                  |
| `date`       | string  | Order date (YYYY-MM-DD)              |
| `customer`   | string  | Customer name                        |
| `category`   | string  | Electronics / Clothing / Books       |
| `product`    | string  | Product name                         |
| `quantity`   | int     | Units ordered                        |
| `unit_price` | int     | Price per unit (₹)                   |
| `region`     | string  | North / South / East / West          |
| `payment`    | string  | Card / UPI / Cash                    |
| `revenue`    | int     | quantity × unit_price                |
| `month`      | string  | Month name                           |
| `quarter`    | int     | Q1 – Q4                              |
| `order_size` | string  | Small / Medium / Large               |

---

## 🔄 Use Your Own JSON

Replace the sample data in **Section 2** with your own file:

```python
import pandas as pd

# Option A — local file
df = pd.read_json('yourfile.json')

# Option B — URL
df = pd.read_json('https://example.com/data.json')

# Option C — nested JSON
import json
with open('yourfile.json') as f:
    data = json.load(f)
df = pd.json_normalize(data)   # flattens nested keys
```

---

## 📈 Charts Generated

- `revenue_by_category.png` — Bar chart
- `monthly_trend.png` — Line chart
- `revenue_share.png` — Donut charts
- `heatmap.png` — Category × Region matrix
- `scatter.png` — Quantity vs Revenue
- `top_products.png` — Horizontal bar
- `correlation.png` — Correlation matrix

---

## 🛠️ Troubleshooting

**Plotly charts not showing?**
```bash
pip install nbformat ipywidgets
jupyter nbextension enable --py widgetsnbextension
```

**ModuleNotFoundError?**
```bash
pip install pandas matplotlib seaborn plotly --upgrade
```

**Date parsing issues?**  
Ensure your date column is in `YYYY-MM-DD` format, or adjust:
```python
df['date'] = pd.to_datetime(df['date'], format='%d/%m/%Y')
```

---

## 📄 License

MIT — free to use, modify, and distribute.

---

> Built with Python 🐍 | pandas · matplotlib · seaborn · plotly
```
