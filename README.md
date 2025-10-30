# Seed Market Decision Science  
*Data-driven insights for agricultural yield optimization using USDA open data.*

---

## 🌾 Project Overview  
This project applies **decision science and predictive modeling** to analyze U.S. Department of Agriculture (USDA) crop yield data.  
Using open-access datasets from the **National Agricultural Statistics Service (NASS)**, it explores how environmental, regional,  
and temporal factors influence **corn and soybean yields** — two major crops in U.S. seed markets.

By combining **statistical analysis**, **machine learning**, and **data visualization**, the project demonstrates how  
agricultural decision-makers (e.g., seed suppliers, policy analysts, and agronomists) can use real data to inform  
**strategic planning, yield forecasting, and resource allocation**.

---

## 🎯 Research Question  
**How can open USDA yield data be leveraged to model, visualize, and predict patterns in agricultural productivity  
across major U.S. growing regions?**

---

## 🔬 Scientific Method Framework  

| Step | Description |
|------|--------------|
| **Ask a Question** | What environmental or regional patterns most influence crop yield trends in the U.S.? |
| **Conduct Background Research** | Use USDA NASS open data to understand historical yield behavior for Corn and Soybeans. |
| **Form a Hypothesis** | Higher yields correlate with favorable growing regions (Midwest states) and recent technology adoption. |
| **Test the Hypothesis** | Perform exploratory data analysis and regression modeling on multi-year USDA datasets. |
| **Analyze the Data** | Identify which features (year, crop type, region) most contribute to yield variance. |
| **Draw a Conclusion** | Summarize findings and propose follow-up research for predictive modeling and resource planning. |

---

## 🧠 Methods  

### **1. Data Retrieval**  
- Uses the USDA **Quick Stats API** for live data access.  
- Retrieves crop yield data for Corn and Soybeans between 2015–2023.  
- Falls back to synthetic data generation if the API or key is unavailable.

### **2. Data Cleaning & Aggregation**  
- Normalizes numeric yield values and removes null entries.  
- Aggregates by **year × state × crop** to compute `mean_yield_per_acre`.  
- Saves cleaned dataset to `/data/processed/usda_yields_cleaned.csv`.

### **3. Analysis & Modeling**  
- Performs descriptive statistics and exploratory data visualization.  
- Fits linear regression models to identify significant yield predictors.  
- Evaluates model performance with MAE, RMSE, and R² metrics.

### **4. Visualization**  
- Uses **Matplotlib** and **Seaborn** to create yield trend and distribution plots.  
- Saves figures to `/figures/` for inclusion in reports and presentations.

---

## 🧩 Repository Structure  

```text
seed-market-decision-science/
├── data/
│   ├── raw/                 # Original USDA or synthetic datasets
│   └── processed/           # Cleaned and aggregated CSVs
├── figures/                 # Visualizations and regression plots
├── notebooks/               # Jupyter notebooks with full analysis
├── requirements.txt         # Python dependencies
├── .gitignore               # Ignored system/data files
└── README.md                # Project documentation
