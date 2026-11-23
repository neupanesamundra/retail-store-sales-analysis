# Retail Store Sales Analysis

An end-to-end data analysis of retail store transactions using Python. The project covers data cleaning, transformation, exploratory data analysis (EDA), and visualization, with the goal of finding patterns that can guide business decisions.

## Dataset

The dataset (`retail_store_sales.csv`) contains 12,575 transactions from January 2022 to January 2025.

| Column | Description |
|---|---|
| Transaction ID | Unique ID for each transaction |
| Customer ID | Customer identifier (25 customers) |
| Category | Product category (8 categories) |
| Item | Specific product (200 items) |
| Price Per Unit | Price of one unit |
| Quantity | Number of units bought |
| Total Spent | Price Per Unit × Quantity |
| Payment Method | Cash, Credit Card, or Digital Wallet |
| Location | Online or In-store |
| Transaction Date | Date of the purchase |
| Discount Applied | Whether a discount was used |

## Project Workflow

### 1. Data Collection and Exploration
Loaded the data with Pandas and checked its structure, data types, summary statistics, missing values, outliers, and consistency.

### 2. Data Cleaning and Transformation
- Recovered missing **prices** using Total Spent ÷ Quantity.
- Recovered missing **items** using the Category + Price combination, which maps to exactly one item.
- Dropped the 604 rows with missing Quantity and Total Spent, since they can't be recovered.
- Labeled missing **Discount Applied** values as "Unknown" instead of guessing.
- Checked outliers with box plots and the IQR rule. They were genuine large purchases, so they were kept.
- Converted data types, created new features (year, month, quarter, day of week, weekend flag, spend level), encoded categorical variables, and standardized numeric columns.

### 3. Exploratory Data Analysis
Descriptive statistics, distributions, relationships, correlations, time trends, and significance tests (t-test and ANOVA), shown with a wide range of charts (histograms, density plots, scatter plots, heatmaps, pie charts, and more).

## Key Findings

- **Category is the only factor that clearly affects spending.** Butchers earns the most (about 208K) and Milk Products the least (about 180K). The gap is driven by price, not quantity.
- **Location, payment method, and discounts have no significant effect** on spend per transaction. Discounts don't appear to increase spending.
- **Revenue is stable over time.** It dipped about 4% from 2022 to 2023 and recovered about 7% in 2024. January is consistently the strongest month.
- **Customers contribute evenly,** so revenue doesn't depend on a few large accounts.
- **Online vs in-store** differs for some categories (for example, Computers and electric accessories), which is worth a follow-up analysis.

## Limitations

- The data looks synthetic (only 25 customers and very even distributions), so real-world patterns may be stronger.
- January 2025 contains only 18 days, so it was excluded from trend charts.
- About 4.8% of rows were dropped because of missing values.

## Tools and Libraries

Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn

## Repository Structure

```
retail-store-sales-analysis/
├── retail_store_sales.csv
├── [your_notebook_name].ipynb
├── requirements.txt
└── README.md
```

## How to Run

1. Clone the repository:
   ```
   git clone https://github.com/[your-username]/retail-store-sales-analysis.git
   cd retail-store-sales-analysis
   ```
2. Install the dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Open the notebook:
   ```
   jupyter notebook [your_notebook_name].ipynb
   ```

## Author

[Your Name] - [LinkedIn or email]
