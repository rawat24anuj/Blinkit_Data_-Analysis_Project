# Blinkit_Data_-Analysis_Project

Analyze Blinkit's sales performance, customer satisfaction, and inventory distribution in Python.
This repository mirrors the KPI design and chart ideas from the project presentation (see `reports/`)
and implements them using pandas and Matplotlib.

## 📌 Business Requirements

- **Goal:** Provide a comprehensive analysis of sales, customer ratings, and outlet characteristics to surface
  insights and opportunities for optimization (KPIs + visualizations).
- **KPIs**
  - **Total Sales:** Sum of revenue from all items sold.
  - **Average Sales:** Mean revenue per record.
  - **Number of Items:** Distinct count of item identifiers.
  - **Average Rating:** Mean customer rating.
- **Key Visuals to Reproduce**
  - **Total Sales by Fat Content** (donut/pie) + supporting KPIs
  - **Total Sales by Item Type** (bar) + supporting KPIs
  - **Fat Content by Outlet for Total Sales** (stacked column)
  - **Total Sales by Outlet Establishment Year** (line)
  - **Sales by Outlet Size** (donut/pie)
  - **Sales by Outlet Location** (funnel / bar)

> The included `notebooks/01_eda.ipynb` shows how to compute these KPIs and produce the above visuals.
> The `src/compute_kpis.py` script exports handy aggregates to `outputs/`.

## 🗃️ Dataset

- File: `data/blinkit_data.csv`
- Shape: **8523 rows × 12 columns**
- Columns:
  - Item Fat Content
- Item Identifier
- Item Type
- Outlet Establishment Year
- Outlet Identifier
- Outlet Location Type
- Outlet Size
- Outlet Type
- Item Visibility
- Item Weight
- Sales
- Rating

### Quick Snapshot (computed from this CSV)
- **Total Sales:** 1,201,681.48
- **Average Sales:** 140.99
- **Number of Items:** 1559
- **Average Rating:** 3.97

> Numbers above will differ if you replace the CSV.

## 📁 Project Structure

```
blinkit-analysis/
├─ data/
│  └─ blinkit_data.csv
├─ notebooks/
│  └─ 01_eda.ipynb
├─ outputs/                  # Auto-generated summaries/aggregates
├─ reports/
│  └─ Blinkit Analysis_ppt.pptx
├─ src/
│  └─ compute_kpis.py
├─ .gitignore
├─ LICENSE
├─ README.md
└─ requirements.txt
```

## 🚀 Getting Started

### 1) Create & activate a virtual environment (recommended)

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
```

### 2) Install dependencies

```bash
pip install -r requirements.txt
```

### 3) Explore the notebook

Open the Jupyter notebook and run the cells:

```bash
jupyter notebook notebooks/01_eda.ipynb
```

### 4) Or run the quick KPI script

```bash
python src/compute_kpis.py
```

This will print KPIs to the console and export useful CSV aggregates into `outputs/` that you can visualize in any tool.

## 📊 Suggested Visualizations

The EDA notebook demonstrates how to reproduce:
- Sales by **Item Fat Content** (donut/pie)
- Sales by **Item Type** (bar)
- Sales by **Outlet Size** (donut/pie)
- Sales by **Outlet Location** (bar/funnel)
- Sales by **Outlet Establishment Year** (line)
- **Stacked** sales across **Fat Content × Outlet**

## 🧹 Data Notes & Ideas

- Normalize inconsistent categories (e.g., `Low Fat`, `low fat`, `LF`; `Regular`, `reg`).
- Consider converting establishment **year** to **outlet age** to compare old vs. new outlets.
- Check outliers in `Item Visibility` and `Item Weight` if you extend the analysis.


