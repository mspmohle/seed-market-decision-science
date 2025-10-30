# Seed Market Decision Science  
Data-driven insights for agricultural yield optimization using USDA open data.

---

## Project Overview  
This project applies decision science and predictive modeling to analyze U.S. Department of Agriculture (USDA) crop yield data.  
Using open-access datasets from the National Agricultural Statistics Service (NASS), it explores how environmental, regional,  
and temporal factors influence corn and soybean yields — two major crops in U.S. seed markets.

By combining statistical analysis, machine learning, and data visualization, the project demonstrates how  
agricultural decision-makers (e.g., seed suppliers, policy analysts, and agronomists) can use real data to inform  
strategic planning, yield forecasting, and resource allocation.

---

## Research Question  
How can open USDA yield data be leveraged to model, visualize, and predict patterns in agricultural productivity  
across major U.S. growing regions?

---

## Scientific Method Framework  

| Step | Description |
|------|--------------|
| Ask a Question | What environmental or regional patterns most influence crop yield trends in the U.S.? |
| Conduct Background Research | Use USDA NASS open data to understand historical yield behavior for corn and soybeans. |
| Form a Hypothesis | Higher yields correlate with favorable growing regions (Midwest states) and recent technology adoption. |
| Test the Hypothesis | Perform exploratory data analysis and regression modeling on multi-year USDA datasets. |
| Analyze the Data | Identify which features (year, crop type, region) most contribute to yield variance. |
| Draw a Conclusion | Summarize findings and propose follow-up research for predictive modeling and resource planning. |

---

## Methods  

### 1. Data Retrieval  
- Uses the USDA Quick Stats API for live data access.  
- Retrieves crop yield data for corn and soybeans between 2015–2023.  
- Falls back to synthetic data generation if the API or key is unavailable.

### 2. Data Cleaning and Aggregation  
- Normalizes numeric yield values and removes null entries.  
- Aggregates by year × state × crop to compute `mean_yield_per_acre`.  
- Saves cleaned dataset to `data/processed/usda_yields_cleaned.csv`.

### 3. Analysis and Modeling  
- Performs descriptive statistics and exploratory data visualization.  
- Fits linear regression models to identify significant yield predictors.  
- Evaluates model performance with MAE, RMSE, and R² metrics.

### 4. Visualization  
- Uses Matplotlib and Seaborn to create yield trend and distribution plots.  
- Saves figures to `/figures/` for inclusion in reports and presentations.

---

## Repository Structure  

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

How to Run

Clone the repository:
git clone https://github.com/mspmohle/seed-market-decision-science.git
cd seed-market-decision-science
Set up your environment:
conda create -n seed python=3.11
conda activate seed
pip install -r requirements.txt
Run the notebook:
jupyter lab
If you have a USDA NASS API key, assign it in a dedicated cell:
USDA_API_KEY = "YOUR_KEY_HERE"
Example Insight
Average yield (2015–2023): ~175 bushels/acre (corn), ~52 bushels/acre (soybeans)
Top-performing states: Iowa, Illinois, and Indiana
Linear regression: R² ≈ 0.72 (year and state are strong predictors)
Future Work: Integrate weather data (precipitation, temperature) for improved yield forecasting.

License
This project is released under the MIT License.
You are free to reuse, modify, and build upon this work with attribution.

Author

Shaun Mohle
BS Data Analytis, MS AI & Machine Learning Computer Science(in progress)
