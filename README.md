# Beyond the Numbers: PSX Non-Financial Sector Performance Analysis (2005–2023)

## What is this project?

This is a research project analyzing the financial performance of **non-financial sectors listed on the Pakistan Stock Exchange (PSX)** over a 19-year period (2005–2023). It identifies the top-performing sector and the leading company within that sector, using a full data analytics workflow.

## Why did we do this?

The State Bank of Pakistan publishes detailed financial data for hundreds of listed companies across many years, but the raw data is scattered, inconsistently formatted, and hard to interpret on its own. This project turns that raw data into a clean, structured dataset and uses it to answer real questions: which sectors and companies actually perform best, and why.

## About the Data

- **Source:** State Bank of Pakistan (SBP) — "Financial Statements Analysis of All Listed Non-Financial Companies"
- **Nature:** Secondary data, compiled from companies' audited annual financial statements
- **Time period:** 2005–2023 (19 years)
- **Coverage:** 15 major non-financial sectors (e.g., Textile, Cement, Food, Fuel & Energy)
- **Format:** Originally spread across 3 separate worksheets (2005–08, 2009–13, 2014–23), each using a different reporting format, with financial line items (Assets, Liabilities, Revenue, etc.) stored as rows rather than columns

## What We Did (Step by Step)

### Step 1: Cleaned the Data (Excel)
- Standardized inconsistent financial indicator names across the three worksheets (e.g., multiple variations of "Non-Current Assets" merged into one label)
- Removed indicators that weren't common across all three worksheets
- Reshaped the data from long format (indicators as rows) into wide format (indicators as columns)
- Merged all three worksheets into a single consolidated dataset
- Standardized column names (spaces → underscores) for compatibility with SQL, R, and Tableau
- Cleaned organization names by removing numeric prefixes (e.g., "703-All Sector" → "All Sector")
- Replaced missing values with 0 and converted fields to proper numeric types

### Step 2: Extracted the Data (SQL / BigQuery)
- Loaded the cleaned dataset into Google BigQuery
- Wrote a SQL query to keep only organizations with **complete financial records for all 19 years** (2005–2023), ensuring a consistent, comparable dataset
- Sorted the final output by organization and year, ready for analysis

### Step 3: Ran Statistical Analysis (R)
- Performed **correlation analysis** in R across key financial ratios (profitability, liquidity, leverage, efficiency) for 14 sectors
- Generated a correlation heatmap to visualize relationships between ratios

### Step 4: Built Dashboards (Tableau)
- Built three interactive dashboards:
  1. **Overview Dashboard** — performance of all sectors combined
  2. **Sector Analysis** — deep dive into the top-performing sector
  3. **Company Analysis** — deep dive into the leading company within that sector

## Key Findings

**Correlation Analysis:**
- Net Profit Margin, Gross Profit Margin, and Operating Margin are strongly positively correlated (they measure similar things)
- Higher leverage (liabilities-to-assets) is linked to **lower** profitability
- Current Ratio and Quick Ratio are highly correlated (both measure liquidity)
- Inventory Turnover and Receivables Turnover are largely independent of profitability and leverage

**Overall Portfolio (all sectors, 2005–2023):**
- Total sales: **PKR 390,103.22M** vs. total assets of PKR 418,213.31M
- Average ROE: **11.46%**
- Sales and profitability rose sharply from 2020 onward (likely post-COVID recovery + currency effects)

**Top Sector — Coke & Refined Petroleum Products:**
- Total sales: **PKR 79,802.26M**
- Average ROE: **20.73%** — well above the portfolio average
- Sharp growth between 2021–2023, with rising dividends from 2021 onward

**Top Company — Pakistan State Oil (PSO):**
- Total sales: **PKR 19,927.25M** (~25% of the entire sector's revenue)
- ROE: **28.22%** — the highest of all levels analyzed (company > sector > portfolio)
- Entered an aggressive growth/reinvestment phase after 2021, with a temporary profitability dip around 2009 (global financial crisis) followed by steady recovery

## Tools Used
- **Excel** — data cleaning and reshaping
- **SQL (Google BigQuery)** — data extraction
- **R** — correlation/statistical analysis
- **Tableau** — interactive dashboards

## Relevance to Sustainable Development Goals (SDGs)
- **SDG 8 (Decent Work and Economic Growth):** evaluates financial health and productivity across major sectors of Pakistan's economy
- **SDG 9 (Industry, Innovation and Infrastructure):** covers core industrial sectors like Textile, Cement, and Fuel & Energy
- **SDG 17 (Partnerships for the Goals):** transforms scattered, inconsistent government data into a clean, reliable, analysis-ready dataset

## Key Takeaway

Profitability at every level — company, sector, and overall portfolio — is highest for firms with lower leverage. The Coke & Refined Petroleum sector, led by Pakistan State Oil (PSO), was the standout performer of the entire 19-year period, consistently outperforming the broader market on both sales and returns.


