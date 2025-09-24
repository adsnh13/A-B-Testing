# AB Testing (Marketing Campaigns)

## Project Overview

A/B testing analysis comparing marketing campaigns across two advertising platforms (e.g., Facebook vs. AdWords). The notebook ingests campaign-level data, performs exploratory data analysis, runs statistical hypothesis tests, and produces business-focused recommendations to optimize ad spend and ROI.

## Key Features

* Data ingestion and cleaning (CSV input).
* Exploratory Data Analysis (EDA) with summary statistics and visualizations.
* Metric computation: impressions, clicks, conversions, CTR, CPC, conversion rate, cost per conversion, and ROI.
* A/B hypothesis testing (proportion tests / t-tests / chi-square) to compare platform performance.
* Lightweight regression analysis to identify performance drivers.
* Automated reporting steps and reproducible notebook workflow.

## Dataset

Expected CSV file: `marketing_campaign.csv` with (at minimum) the following columns:

* `campaign_id` — unique campaign identifier
* `platform` — e.g., `facebook`, `adwords`
* `date` — campaign date or timestamp
* `impressions` — number of impressions
* `clicks` — number of clicks
* `conversions` — number of conversions
* `spend` — money spent
* `revenue` — (optional) revenue attributed to conversions

> If column names differ, update the dataset loading cell in the notebook accordingly.

## Requirements

Create a virtual environment and install dependencies.

```bash
python -m venv venv
source venv/bin/activate    # macOS / Linux
venv\Scripts\activate     # Windows
pip install -r requirements.txt
```

Example `requirements.txt` (not exhaustive):

```
pandas
numpy
matplotlib
seaborn
scipy
statsmodels
scikit-learn
jupyterlab
```

## How to Run

1. Place `marketing_campaign.csv` in the same folder as the notebook.
2. Open the notebook:

```bash
jupyter lab
# or
jupyter notebook
```

3. Run cells top-to-bottom. The notebook is organized into the following sections:

   * **1. Problem statement & objectives** — business context and goals
   * **2. Data ingestion & cleaning** — load CSV, type-cast, handle missing values
   * **3. EDA & visualizations** — distributions, time-series, platform comparisons
   * **4. Metric calculations** — CTR, conversion rate, CPC, CPA, ROI
   * **5. A/B hypothesis testing** — statistical tests with p-values and confidence intervals
   * **6. Regression analysis** — optional model to identify drivers
   * **7. Automation & reporting** — example functions to reproduce metrics quickly
   * **8. Conclusions & recommendations** — business actions and next steps

## Example Calculations

* **Conversion Rate** = conversions / clicks
* **CTR (Click-through Rate)** = clicks / impressions
* **CPC (Cost per Click)** = spend / clicks
* **Cost per Conversion (CPA)** = spend / conversions
* **ROI** = (revenue - spend) / spend

## Output / Deliverables

* Notebook with inline charts and test results.
* Summary tables with platform-level aggregated metrics.
* Recommendation section with suggested ad budget reallocation and expected impact.

## Reproducibility Notes

* Seed any random operations (e.g., `random_state=42`) for reproducible results.
* Use aggregated time windows (daily / weekly) for stable A/B comparisons when data is sparse.
* When running proportion tests on conversion rates, ensure minimum sample size per group to satisfy test assumptions.

## Suggested Resume/Portfolio Bullets

* Optimized ad budget allocation by performing A/B testing on two platforms, improving ROI insights.
* Improved campaign strategies through analysis of 10,000+ records, identifying performance drivers.
* Increased evaluation efficiency by automating statistical testing, enabling faster insights.

## Next Steps / Extensions

* Add uplift modeling or Bayesian A/B testing for more robust inference.
* Integrate with ad platform APIs to automate data pulls (e.g., Google Ads / Facebook Marketing API).
* Build a dashboard (Streamlit / Dash) for live monitoring and interactive experimentation.

## License & Contact

License: MIT (or choose an appropriate license).

Author / Contact: (your name) — update README with your email or GitHub profile.
