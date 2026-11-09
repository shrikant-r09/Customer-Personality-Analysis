# Customer Personality Analysis

Customer behaviour, spending and segmentation analysis using **Python, Pandas, Matplotlib, Seaborn and K-Means clustering**. Completed as part of the **CHEARS Data Analyst Internship**.

![Python](https://img.shields.io/badge/Python-3.x-blue) ![Pandas](https://img.shields.io/badge/Pandas-data%20analysis-150458) ![scikit-learn](https://img.shields.io/badge/scikit--learn-K--Means-orange) ![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00)

---

## Overview

This project analyzes a customer dataset to understand **who the customers are, how they spend, how they respond to marketing campaigns, and which channels they use**. It ends with two K-Means customer segments and a set of evidence-based business recommendations.

**Questions answered**

- Who are the customers (age, education, marital status, income, household)?
- Which product categories generate the most spending?
- How does spending vary with income and household composition?
- Which marketing campaigns receive the strongest response?
- Which shopping channels are used most, and does website traffic turn into purchases?
- Can customers be grouped into useful behavioural segments?

## Dataset

| Item | Value |
|------|-------|
| Original data | 2,240 rows × 29 columns |
| Cleaned data | 2,240 rows × 35 columns |
| K-Means sample | 2,237 customers (3 excluded because Age was missing) |
| Column groups | Demographics, household, income, product spending, purchase channels, campaign responses |

The cleaned dataset has 35 columns after feature engineering and removal of two constant columns (`Z_CostContact`, `Z_Revenue`).

## Project workflow

1. **Data understanding**: load the Excel file, inspect structure, types and missing values, build a data dictionary.
2. **Data cleaning and preprocessing**: handle missing values, invalid birth years, inconsistent labels and outliers, then create derived features.
3. **Exploratory data analysis**: distributions, relationships and a correlation heatmap.
4. **Product and spending analysis**: category totals and shares, spending by income group and household.
5. **Marketing campaign analysis**: acceptance rates and accepter vs non-accepter comparisons.
6. **Shopping channel analysis**: channel shares and website visits vs web purchases.
7. **Customer segmentation**: K-Means with elbow and silhouette analysis.
8. **Business recommendations**: findings turned into proposals to test.

## Data cleaning summary

- 0 exact duplicate rows.
- 24 missing `Income` values imputed with education-group medians.
- 3 invalid birth years (1893, 1899, 1900) set to missing, so Age is missing for 3 customers.
- `Absurd`, `YOLO` and `Alone` marital-status labels standardized to `Single`.
- 8 high-income outliers flagged using the IQR rule and **kept**, including Income = 666,666.
- `Dt_Customer` had mixed formats: 1,324 text dates were standardized and 916 ambiguous Excel datetime cells were left unresolved. The standardized date field is incomplete, so no date-based claims are made.
- Derived features: `Age`, `TotalSpending`, `TotalChildren`, `TotalPurchases`, `TotalCampaignsAccepted`.

## Key findings

**Customers**
- Mean age 55.10 (median 54); mean income 52,242.59 (median 51,498.50); mean 5.32 website visits per month.
- Graduation is the most common education group and Married the largest marital group.

**Product spending**
- Wine accounts for 50.17% and meat for 27.56% of category spending, together **77.73%**.
- Mean total spending is 605.80 (median 396), a right-skewed distribution.
- Average spending rises across income quartiles: 81.93 (Low), 239.52 (Lower-Middle), 744.53 (Upper-Middle), 1,357.21 (High).
- Customers with no children average 1,106.03 in spending, versus 472.73 with one child and 245.95 with two.

**Campaigns**

| Campaign | Acceptance rate |
|----------|-----------------|
| Campaign 1 | 6.43% |
| Campaign 2 | 1.34% |
| Campaign 3 | 7.28% |
| Campaign 4 | 7.46% |
| Campaign 5 | 7.28% |
| Most recent (`Response`) | 14.91% |

609 customers accepted at least one campaign; those customers averaged 1,001.33 in spending versus 458.11 for the rest.

**Channels**
- Store 46.18% (12,970 purchases), Web 32.58% (9,150), Catalog 21.23% (5,963).
- Website visits vs web purchases correlation is only **−0.056**, so more visits do not necessarily mean more purchases.

## Customer segmentation (K-Means)

- **Features:** Income, TotalSpending, TotalPurchases, TotalChildren, Age, Recency, NumWebVisitsMonth (scaled with `StandardScaler`).
- **Choosing K:** elbow method and silhouette scores for K = 2 to 10. The highest silhouette score is **0.3202 at K = 2**, which indicates moderate (not sharp) separation.

| Segment | Customers | Avg. income | Avg. spending | Avg. purchases | Avg. children | Web visits / month | Campaigns accepted |
|---------|-----------|-------------|---------------|----------------|---------------|--------------------|--------------------|
| High-Value | 957 (42.78%) | 71,840.78 | 1,185.36 | 19.33 | 0.52 | 3.67 | 0.76 |
| Low-Value | 1,280 (57.22%) | 37,571.43 | 172.39 | 7.47 | 1.27 | 6.55 | 0.21 |

High-Value customers spend about **6.9 times** as much as Low-Value customers. "High-Value" and "Low-Value" are descriptive labels assigned after reviewing cluster profiles, not judgments about people.

## Business recommendations (proposals to test)

1. Test wine-focused promotions and bundles.
2. Test complementary wine-and-meat bundles.
3. Test loyalty rewards and exclusive offers for the high-value segment.
4. Test introductory deals and relevant product recommendations for lower-spending customers.
5. Study the stronger response of the most recent campaign and test similar approaches.
6. Maintain in-store strength while improving online convenience.
7. Improve website navigation, product discovery and checkout, and measure conversion rather than visits alone.
8. Test premium product recommendations for higher-income customers.

These are hypotheses based on observed patterns. Their impact must be measured, for example with A/B tests.

## Limitations

- Findings are descriptive; correlations and clusters do not establish causation.
- The income outlier (666,666) was retained and may influence K-Means (maximum standardized income 24.54).
- 916 ambiguous date values were not standardized, so the date field is not used for conclusions.
- A silhouette score of 0.3202 means the two segments are useful but not sharply separated.
- There is no cost data, so ROI cannot be calculated.

## Repository structure

```
Customer-Personality-Analysis/
├── 01_Original_Dataset/        Original Excel dataset
├── 02_Cleaned_Dataset/         Cleaned CSV dataset (clean_data.csv)
├── 03_Colab_Notebooks/         Main analysis notebook
├── 04_Charts_and_Visuals/      Exported charts (Task 3 to Task 7)
├── 05_Worksheet_and_Reports/   Data dictionary, summaries, cleaning report, cluster profiles, recommendations
├── 06_Presentation/            Final PowerPoint presentation
├── .gitignore
└── README.md
```

Notable files: `Customer_Personality_Analysis_Setup.ipynb` (notebook), `Task2_Cleaning_Report.xlsx`, `Task1_Data_Dictionary.csv`, `Task7_Cluster_Profiles.csv`, `Task7_Silhouette_Scores.csv`, `Task8_Business_Recommendations.csv`.

## How to run

1. Open `03_Colab_Notebooks/Customer_Personality_Analysis_Setup.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Upload the repository folders to Google Drive (for example `My Drive/Customer Personality Analysis`) and mount Drive when prompted.
3. Check that the file paths at the top of the notebook match your Drive location.
4. Use **Runtime → Restart and run all**.

**Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `openpyxl`

```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
```

## Author

**Shrikant Rathod**
CHEARS Data Analyst Internship project
GitHub: [@shrikant-r09](https://github.com/shrikant-r09)
