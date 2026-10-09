# E-Commerce Sales & Customer Behavior Analysis

An exploratory data analysis (EDA) project that investigates transactional data from an online retail business to identify sales trends, customer purchasing patterns, product performance, and cancellation behavior.

The project uses Python and data analysis libraries to transform raw transactional data into meaningful insights through statistical analysis, data cleaning, and visualization.

## Project Overview

Understanding customer behavior and sales performance is essential for making informed business decisions.

This project analyzes the UCI Online Retail dataset to explore:

- Overall sales performance and revenue distribution
- Monthly sales and order trends
- Best-performing products by revenue and quantity sold
- Geographic distribution of sales
- Customer purchasing behavior
- Cancelled invoices and potential product returns
- Quantity, unit price, and revenue distributions
- Relationships between numerical sales variables

The objective is to identify patterns in the data and communicate findings through visualizations and summary statistics.

## Objectives

- Perform data cleaning and preprocessing.
- Calculate key performance indicators (KPIs).
- Analyze monthly revenue and order trends.
- Identify top-performing products and countries.
- Examine customer-level purchasing behavior.
- Investigate cancellations and negative-quantity transactions.
- Detect outliers and examine variable distributions.
- Visualize relationships between sales variables.
- Generate reusable CSV reports for further analysis.

## Dataset

**Dataset:** Online Retail  
**Source:** UCI Machine Learning Repository  
**Period:** December 2010 – December 2011

**Dataset Link:** https://archive.ics.uci.edu/dataset/352/online+retail

The dataset contains transactional records from a UK-based online retail business.

### Key Features

| Column | Description |
|---|---|
| InvoiceNo | Invoice identifier |
| StockCode | Product identifier |
| Description | Product description |
| Quantity | Number of units purchased |
| InvoiceDate | Date and time of the transaction |
| UnitPrice | Price per unit |
| CustomerID | Customer identifier |
| Country | Customer's country |

The dataset was retrieved using the UCI Machine Learning Repository API and processed using Pandas.

## Technologies Used

- **Python:** Core programming language
- **Pandas:** Data manipulation and analysis
- **NumPy:** Numerical operations
- **Matplotlib:** Data visualization
- **Seaborn:** Statistical visualizations
- **ucimlrepo:** Dataset retrieval
- **Google Colab:** Cloud-based notebook environment

## Project Workflow

### 1. Data Collection

Retrieved the Online Retail dataset from the UCI Machine Learning Repository.

### 2. Data Cleaning

- Standardized text fields.
- Converted invoice dates to datetime format.
- Converted quantity and unit price to numeric values.
- Identified and removed duplicate records.
- Removed rows missing essential transaction information.
- Examined missing customer identifiers.

### 3. Feature Engineering

Created additional analytical features:

- `IsCancelled`: Identifies invoices with cancellation prefixes.
- `Revenue`: Calculates line-level revenue using quantity multiplied by unit price.
- `YearMonth`: Extracts the year and month.
- `Week`: Extracts the transaction week.
- `Hour`: Extracts the transaction hour.
- `DayOfWeek`: Identifies the weekday of each transaction.

### 4. Exploratory Data Analysis

Performed descriptive statistical analysis and investigated sales distributions, product performance, customer behavior, cancellations, and relationships between numerical variables.

### 5. Data Visualization

Created charts to identify trends, compare categories, and communicate findings.

### 6. Report Generation

Exported analytical summaries into CSV files for further analysis and reporting.

## Key Performance Indicators

The following results were obtained from the executed notebook.

| Metric | Result |
|---|---:|
| Sales transaction lines analyzed | 524,878 |
| Unique invoices/orders | 19,960 |
| Identified customers | 4,338 |
| Gross sales revenue | £10,642,110.80 |
| Total units sold | 5,572,420 |
| Average order value | £533.17 |

These metrics reflect the filtering and calculation methods implemented in the notebook.

## Key Findings

### 1. Geographic Sales Distribution

The United Kingdom was the dominant market in the analyzed dataset.

| Country | Gross Revenue | Revenue Share |
|---|---:|---:|
| United Kingdom | £9,001,744.09 | 84.59% |
| Netherlands | £285,446.34 | 2.68% |
| EIRE | £283,140.52 | 2.66% |
| Germany | £228,678.40 | 2.15% |
| France | £209,625.37 | 1.97% |

**Insight:** Approximately 84.59% of recorded gross revenue came from the United Kingdom, indicating substantial geographic concentration.

**Business implication:** The business could explore opportunities to expand its international customer base while maintaining its established UK market.

### 2. Top Products by Revenue

The highest-revenue product descriptions included:

| Product | Revenue |
|---|---:|
| DOTCOM POSTAGE | £206,248.77 |
| REGENCY CAKESTAND 3 TIER | £174,156.54 |
| PAPER CRAFT, LITTLE BIRDIE | £168,469.60 |
| WHITE HANGING HEART T-LIGHT HOLDER | £106,236.72 |
| PARTY BUNTING | £99,445.23 |

**Insight:** Product revenue varies considerably, with several descriptions contributing substantially to recorded sales.

**Business implication:** Revenue leaders can be investigated further to understand their margins, repeat-purchase behavior, and contribution to overall business performance.

Note that postage-related entries appear among the leading descriptions. Therefore, the revenue ranking does not represent physical merchandise alone.

### 3. Monthly Sales Trends

The monthly analysis showed substantial variation in revenue and order volume.

- November 2011 recorded the highest monthly revenue in the notebook: £1,503,866.78.
- November also recorded the highest monthly order count shown: 2,769 unique invoices.
- Revenue and order activity fluctuated throughout the analysis period.

**Insight:** November was the strongest recorded month for both revenue and order volume in this analysis.

**Business implication:** The business could investigate seasonal demand, promotional activity, and inventory requirements around the November peak.

### 4. Customer Purchasing Behavior

The customer-level analysis examined revenue, order count, units purchased, and average order value for identified customers.

- Identified customers analyzed: 4,338
- Customer revenue varied considerably.
- Some customers generated substantially more revenue than others.

**Insight:** Customer purchasing activity is unevenly distributed.

**Business implication:** Customer segmentation and retention analysis could help identify valuable customers and opportunities to encourage repeat purchases.

### 5. Cancellation and Return Analysis

The notebook identified cancellation-related transactions and negative-quantity records.

| Metric | Result |
|---|---:|
| Cancelled lines as a percentage of cleaned lines | 1.72% |
| Cancelled invoices as a percentage of unique invoices | 14.81% |
| Lines with negative quantities | 10,587 |
| Revenue sum for negative-quantity lines | -£893,979.73 |

**Insight:** Negative-quantity transactions represent a meaningful component of the dataset and warrant further investigation.

**Business implication:** Analyzing cancellations and potential returns by product, month, and customer could help identify operational issues.

Negative quantities can represent returns or adjustments and should not automatically be interpreted as confirmed refunds or lost revenue.

### 6. Distribution and Outlier Analysis

Histograms and box plots were used to examine quantity, unit price, and line revenue.

The distributions showed substantial right skew, with a relatively small number of unusually large observations.

The notebook also calculated percentile-based summaries to examine the spread of the variables.

**Insight:** A small number of high-value transactions can influence aggregate statistics.

**Business implication:** Median-based summaries, percentile comparisons, and separate investigations of unusual transactions can complement average-based reporting.

### 7. Correlation Analysis

The notebook calculated Pearson correlations between quantity, unit price, revenue, and transaction hour.

| Variable Pair | Correlation |
|---|---:|
| Quantity and Revenue | 0.907 |
| Unit Price and Revenue | 0.137 |
| Unit Price and Quantity | -0.004 |

**Insight:** Quantity and line revenue exhibited a strong positive correlation in the analyzed sales data.

Unit price and quantity had almost no linear correlation.

**Interpretation:** Since line revenue is calculated as quantity multiplied by unit price, the relationship between quantity and revenue is partly mathematical. Correlation alone does not establish causation.

## Visualizations

The notebook includes the following visualizations:

- Missing-value analysis
- Quantity distribution histogram
- Unit-price distribution histogram
- Line-revenue distribution histogram
- Box plots for outlier analysis
- Top products by revenue
- Top products by units sold
- Top countries by revenue
- Top countries by transaction frequency
- Monthly revenue trend
- Monthly order trend
- Monthly average order value
- Geographic revenue-share pie chart
- Customer revenue comparison
- Monthly cancellation-line trend
- Quantity-versus-price scatter plot
- Quantity-versus-revenue scatter plot
- Numerical correlation heatmap
- Log-transformed quantity and unit-price scatter plot

## Exported Reports

The notebook exports summary data to CSV files.

| File | Description |
|---|---|
| `kpi_summary.csv` | Key performance indicators |
| `monthly_sales_summary.csv` | Monthly revenue, units, and orders |
| `country_revenue.csv` | Revenue grouped by country |
| `customer_summary.csv` | Customer-level purchasing summary |

These files are saved in the `/content/outputs/` directory when running the notebook in Google Colab.

## How to Run the Project

### Google Colab

1. Open Google Colab.
2. Upload or open the project notebook.
3. Install the required dependencies:

```python
!pip install -q ucimlrepo pandas numpy matplotlib seaborn
