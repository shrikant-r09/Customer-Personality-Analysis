# CHEARS Data Analyst Internship: Customer Data Analysis Project

Compiled from the CHEARS portal screenshots and the "Tasks and detailed guide" file.

---

## 1. Overview

A one-month internship giving hands-on experience in data analysis using real-world customer data. Interns work with a customer marketing dataset to clean, explore, analyze, and visualize data to find meaningful patterns and business insights. Interns may choose any analytical tool, programming language, or IDE. The internship emphasizes practical learning, analytical thinking, data interpretation, and communicating findings effectively.

| Item | Detail |
|------|--------|
| Duration | 1 Month |
| Project type | Individual Data Analysis Project |
| Dataset | Customer Personality and Marketing Analysis |
| Presentation | Maximum 15 slides |
| Final video | Mandatory |
| Maximum video duration | 5 minutes |
| Maximum presentation length | 15 slides |

---

## 2. Project Description

**Objective:** Explore the dataset, answer relevant business questions, and provide data-driven recommendations that help a business improve customer engagement, marketing performance, and sales strategies.

### Key Areas of Analysis
1. Customer demographic analysis
2. Customer income and household analysis
3. Product-wise purchasing behavior
4. Marketing campaign performance
5. Discount-based purchasing patterns
6. Online, catalogue, and in-store shopping behavior
7. Customer engagement and purchase recency
8. Customer segmentation and business recommendations

---

## 3. Tools and Technologies

Interns may use any suitable analytical tool or programming environment:

- Microsoft Excel
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- SQL
- Power BI
- Tableau
- Jupyter Notebook
- Google Colab
- Other suitable data analysis tools or IDEs

Interns are not required to use every tool; choose what best suits your approach.

**Chosen tool for this project:** Python in Google Colab (Pandas, NumPy, Matplotlib, Seaborn).

---

## 4. Attributes and Descriptions

### 4.1 Customer Information
| Attribute | Description |
|-----------|-------------|
| Year_Birth | Customer's birth year |
| Education | Customer's education level |
| Marital_Status | Customer's marital status |
| Income | Customer's yearly household income |
| Kidhome | Number of children in the household |
| Teenhome | Number of teenagers in the household |
| Dt_Customer | Date the customer enrolled with the company |
| Recency | Number of days since the customer's last purchase |
| Complain | 1 if the customer complained in the last two years; otherwise 0 |

*(The top of this table, likely the ID column, was cut off in the screenshot.)*

### 4.2 Customer Spending
| Attribute | Description |
|-----------|-------------|
| MntWines | Amount spent on wine in the last two years |
| MntFruits | Amount spent on fruits in the last two years |
| MntMeatProducts | Amount spent on meat products in the last two years |
| MntFishProducts | Amount spent on fish products in the last two years |
| MntSweetProducts | Amount spent on sweet products in the last two years |
| MntGoldProds | Amount spent on gold products in the last two years |

### 4.3 Marketing Campaign
| Attribute | Description |
|-----------|-------------|
| NumDealsPurchases | Number of purchases made using discounts |
| AcceptedCmp1 | 1 if the customer accepted Campaign 1; otherwise 0 |
| AcceptedCmp2 | 1 if the customer accepted Campaign 2; otherwise 0 |
| AcceptedCmp3 | 1 if the customer accepted Campaign 3; otherwise 0 |
| AcceptedCmp4 | 1 if the customer accepted Campaign 4; otherwise 0 |
| AcceptedCmp5 | 1 if the customer accepted Campaign 5; otherwise 0 |
| Response | 1 if the customer accepted the most recent campaign; otherwise 0 |

### 4.4 Shopping Channels
| Attribute | Description |
|-----------|-------------|
| NumWebPurchases | Number of purchases made through the company's website |
| NumCatalogPurchases | Number of purchases made through a catalogue |
| NumStorePurchases | Number of purchases made directly in stores |
| NumWebVisitsMonth | Number of visits to the company's website during the last month |

### 4.5 Notes on the Provided Files
- `customer_analysis_dummy.csv`: 2,508 rows and 29 columns. Besides the attributes above it contains `ID`, `Z_CostContact`, and `Z_Revenue`.
- The Excel file (`972212_...xlsx`) is the official dataset to load. Confirm column names against it before coding.

---

## 5. Internship Schedule

*Suggested schedule, but you can go at your own pace to complete it within 4 weeks.*

### Week 1: Dataset Understanding and Data Cleaning
**Topics and activities**
- Introduction to the project and dataset
- Understanding data types and attributes
- Loading the Excel file into the selected tool
- Checking missing values and duplicates
- Cleaning and preparing the data

**Weekly milestone:** Submit or save a clean dataset and document the preprocessing steps.

### Week 2: Exploratory and Product Analysis
**Topics and activities**
- Descriptive statistics
- Customer demographic analysis
- Product spending analysis
- Income and household analysis
- Creating charts and visualizations

**Weekly milestone:** Complete initial EDA and prepare key observations.

### Week 3: Campaign, Channel, and Customer Analysis
**Topics and activities**
- Marketing campaign performance
- Shopping channel comparisons
- Customer segmentation
- Identification of trends and patterns
- Formulation of business recommendations

**Weekly milestone:** Complete the main analysis and finalize the key findings.

### Week 4: Final Project and Submission
**Topics and activities**
- Review and validate analytical results
- Finalize charts and insights
- Prepare a PowerPoint presentation
- Record a video explaining the analysis and outcomes
- Review the deliverables before submission

**Weekly milestone:** Submit the presentation, video, and analysis/code file through the internship portal once the submission link becomes available.

---

## 6. Tasks and Instructions

Official task text from the portal, followed by practical guidance from the detailed guide.

| # | Task | Week | Expected outcome |
|---|------|------|------------------|
| 1 | Data Collection and Understanding | 1 | A clear understanding of the dataset and its business context |
| 2 | Data Cleaning and Preprocessing | 1 | A clean, reliable dataset ready for analysis |
| 3 | Exploratory Data Analysis (EDA) | 2 | Visualizations and observations that reveal important customer patterns |
| 4 | Product and Spending Analysis | 2 | Insights into product preferences and customer spending patterns |
| 5 | Marketing Campaign Analysis | 3 | An assessment of campaign performance and potential opportunities to improve marketing effectiveness |
| 6 | Shopping Channel Analysis | 3 | Insights into customer channel preferences and potential areas for improvement |
| 7 | Customer Segmentation and Insights | 3 | Meaningful customer groups and explanations of how a business could use them |
| 8 | Business Recommendations | 3 | A concise set of evidence-based business recommendations |

*The task-to-week mapping is inferred from the weekly topics; confirm with your program if needed.*

### Task 1: Data Collection and Understanding
**Official requirements**
- Download and load the provided Excel dataset.
- Identify the number of rows and columns.
- Understand the meaning of each attribute.
- Identify the data types of the columns.
- Inspect the dataset to understand its overall structure.

**Expected outcome:** A clear understanding of the dataset and its business context.

**Guidance:** `pd.read_excel`, `df.shape`, `df.info()`, `df.head()`, `df.describe()`. Output: row/column count, data dictionary table (Attribute, Meaning, Data Type, Category), short business-context paragraph.

### Task 2: Data Cleaning and Preprocessing
**Official requirements**
- Check for missing or null values.
- Identify duplicate records.
- Check for invalid or inconsistent values.
- Inspect income and spending columns for unusual values.
- Convert date and numerical columns to appropriate data types.
- Handle data quality issues using suitable methods.
- Document any assumptions made during preprocessing.

**Expected outcome:** A clean, reliable dataset ready for analysis.

**Guidance**

| Check | Possible handling |
|-------|-------------------|
| Missing values | Fill numeric gaps with median, or drop if very few rows |
| Duplicates | Drop exact duplicates |
| Inconsistent categories | Standardize labels; group odd values (e.g. "Absurd", "YOLO") into "Other" |
| Outliers in income/spending | Investigate first (boxplots, IQR); document the rule |
| Date columns | `pd.to_datetime` on `Dt_Customer` |
| Numbers stored as text | `pd.to_numeric(errors='coerce')` |
| Invalid values | Implausible birth years, negative spending: correct or remove with a stated reason |

Derived columns: `Age`, `TotalSpending`, `TotalChildren`, `TotalPurchases`, `TotalCampaignsAccepted`. Output: before/after summary, assumptions log, saved clean file (`clean_data.csv`).

### Task 3: Exploratory Data Analysis (EDA)
Explore the dataset using descriptive statistics, charts, and visualizations.

**Suggested analysis**
- Customer distribution by education and marital status.
- Customer income distribution.
- Household composition based on children and teenagers.
- Customer purchase recency.
- Spending distribution across product categories.
- Relationship between income and customer spending.
- Shopping channel preferences.
- Website visits compared with web purchases.

**Expected outcome:** Visualizations and observations that reveal important customer patterns.

**Guidance:** Also include a correlation heatmap. Output: 8 or more charts, each with a written observation, plus a descriptive statistics table.

### Task 4: Product and Spending Analysis
Analyze how customers spend across different product categories.

**Suggested activities**
- Calculate total spending for each product category.
- Identify the most and least popular product categories by spending.
- Compare product spending across income groups.
- Explore how household composition relates to purchasing behavior.
- Identify high-spending and low-spending customer groups.

**Expected outcome:** Insights into product preferences and customer spending patterns.

**Guidance:** Rank categories and show each one's share of total spending. Build income groups with `pd.qcut` or `pd.cut` and state the rule. Define high/low spenders (e.g. top and bottom 25% of `TotalSpending`) and profile them. Output: category ranking table and chart, spending by income group, spending by household composition, high vs low spender profile, written insights.

### Task 5: Marketing Campaign Analysis
Evaluate customer responses to marketing promotions.

**Suggested activities**
- Calculate the acceptance rate of each of the five campaigns.
- Analyze acceptance of the most recent campaign using the Response column.
- Compare campaign acceptance across demographic or income groups.
- Examine the relationship between discount purchases and customer spending.
- Explore whether purchasing behavior differs between customers who accept and reject campaigns.
- Identify customer groups that may respond well to future campaigns.

**Expected outcome:** An assessment of campaign performance and potential opportunities to improve marketing effectiveness.

**Guidance:** Acceptance rate = column mean x 100. Caution: correlation does not prove causation, so phrase findings as associations. Output: acceptance rate chart, group comparison charts, accepter vs non-accepter table, list of high-potential groups.

### Task 6: Shopping Channel Analysis
Study how customers purchase products across different channels.

**Suggested activities**
- Compare website, catalogue, and in-store purchase counts.
- Identify the most frequently used shopping channel.
- Analyze the relationship between website visits and web purchases.
- Compare shopping channel preferences across customer groups.
- Identify opportunities to improve online engagement and sales.

**Expected outcome:** Insights into customer channel preferences and potential areas for improvement.

**Guidance:** Use a scatter plot, correlation, and a conversion ratio (web purchases per visit; handle zero visits). Look for segments with high visits but low purchases. Output: channel comparison chart, visits vs purchases analysis, preference by group, engagement opportunities backed by numbers.

### Task 7: Customer Segmentation and Insights
Group customers according to relevant characteristics or purchasing behavior.

**Possible segmentation approaches**
- Income-based segmentation.
- Spending-based segmentation.
- Product preference segmentation.
- Campaign response segmentation.
- Shopping channel segmentation.
- Recency-based engagement segmentation.

Interns may use rule-based segmentation or suitable analytical techniques such as clustering, if appropriate.

**Expected outcome:** Meaningful customer groups and explanations of how a business could use them.

**Guidance**
- Option A (rule-based): e.g. High-value, Bargain seekers, Lapsed customers, Online-focused.
- Option B (K-Means): features such as `Income`, `TotalSpending`, `Recency`, `TotalPurchases`; scale with `StandardScaler`; choose k with elbow method and silhouette score; profile and name clusters.
- Recommended: use both.
- Output: segment definitions, profile table (size, averages), scatter plot colored by segment, and for each segment who they are and how a business could use it.

### Task 8: Business Recommendations
Based on the analysis, prepare practical recommendations.

**Examples include**
- Suggestions for improving campaign acceptance.
- Ideas for targeting high-value customers.
- Opportunities to improve product promotions.
- Recommendations for increasing online purchases.
- Strategies for engaging customers who have not purchased recently.
- Suggestions for improving the customer experience.

Recommendations must be supported by findings from the dataset. Avoid making claims that cannot be justified by the analysis.

**Expected outcome:** A concise set of evidence-based business recommendations.

**Guidance:** Use the format **Finding (with a number) → Recommendation → Expected benefit**. Output: 5 to 8 recommendations tied to findings or charts, plus a limitations note (e.g. no cost data, so ROI cannot be calculated).

---

## 7. Deliverables

### Required Report/Presentation Content (portal list)
1. Project Title, CHEARS, Your name
2. Introduction
3. Problem Statement and Objectives
4. Dataset Overview
5. Tools and Technologies Used
6. Data Cleaning and Preprocessing
7. Exploratory Data Analysis
8. Customer Demographic Insights
9. Product Spending Analysis
10. Marketing Campaign Analysis
11. Shopping Channel Analysis
12. Customer Segmentation
13. Key Findings
14. Business Recommendations
15. Conclusion and Limitations

*(The portal list was still scrolling in the screenshot, so there may be items after #15.)*

### 7.1 Analysis / Code File
- Submit the notebook (File > Download > .ipynb).
- Must be organized, readable, and sufficiently documented: one heading per task, a markdown explanation before each section, code comments, and an observation after each chart.

### 7.2 Presentation Video
- Maximum 5 minutes; you must appear on screen and explain the analysis.
- Cover objective, methodology, important findings, and recommendations.
- Clear audio and readable on-screen content.

| Section | Time |
|---------|------|
| Objective and dataset | ~30 sec |
| Methodology and cleaning | ~45 sec |
| Key findings | ~2 min |
| Recommendations | ~1 min |
| Wrap-up | ~15 sec |

### 7.3 PowerPoint Presentation
- Maximum 15 slides.
- Include project title and objective, methodology and tools, important visualizations and findings, conclusions and business recommendations.

Suggested 12-slide structure: Title, Objective and business context, Dataset overview and tools, Data cleaning summary, Customer demographics, Product spending, Income vs spending, Campaign performance, Shopping channels, Customer segments, Business recommendations, Conclusion.

---

## 8. Colab Tips
- Mount Google Drive so files persist between sessions.
- Save charts with `plt.savefig('name.png', dpi=300, bbox_inches='tight')` for the PowerPoint.
- Use Runtime > Restart and run all before exporting the notebook.

---

## 9. Final Submission Checklist

- [ ] Notebook runs top to bottom without errors
- [ ] Notebook has headings, explanations, comments, and chart observations
- [ ] Cleaning assumptions are documented
- [ ] Clean dataset saved
- [ ] All claims and recommendations are backed by numbers from the data
- [ ] PowerPoint is 15 slides or fewer, with title, objective, methodology, findings, and recommendations
- [ ] Video is 5 minutes or less, you appear on screen, audio is clear, text is readable
- [ ] All three files submitted through the internship portal once the link is available
