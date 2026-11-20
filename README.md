# Marketing-Campaign-Performance-Dashboard-Excel-
An Excel dashboard that analyzes 1,000 marketing campaigns across 5 channels (Jan 2024 – Nov 2025) and answers three business questions about return on ad spend (ROAS), budget discipline, and performance over time.

![Dashboard preview]
<img width="871" height="768" alt="exceldashboard png" src="https://github.com/user-attachments/assets/02349144-5540-47ee-bd0b-ab3750a88db1" />


> **Note:** The dataset is a free sample dataset, not real company data. Treat the findings as a practice case study, not as real-world marketing advice.

## Business questions

1. Which channels give the best return, and is money going to the right ones?
2. Are campaigns staying within budget, and where are the overruns?
3. Is performance improving or slipping over time?

## Dataset

- **Source:** Marketing Campaigns sample data, TrumpExcel (dataset #14 of 15 free sample datasets)
- **Size:** 1,000 campaigns, 5 channels: Email, LinkedIn, Google Ads, Facebook, Instagram
- **Period:** campaign start dates from Jan 2024 to 29 Nov 2025
- **Columns:** Campaign ID, Campaign Name, Channel, Start Date, End Date, Budget Allocated, Amount Spent, Impressions, Clicks, Conversions, Revenue Generated
- **Data quality:** no blank cells, no duplicate campaign IDs, no impossible values (for example, conversions above clicks)
- **Added by me:** ROAS (Revenue Generated ÷ Amount Spent) and Overspent (1 if Amount Spent > Budget Allocated, else 0)

The source does not state a currency. The $ symbol is used to match the dashboard layout.

## Metric definitions

| Metric | Definition |
|---|---|
| ROAS | Revenue Generated ÷ Amount Spent (revenue earned per $1 of ad spend) |
| Budget variance | Amount Spent − Budget Allocated (negative = under budget) |
| Var % | Budget variance ÷ Budget Allocated |
| Overspent campaign | A campaign whose Amount Spent exceeds its Budget Allocated |

## Key findings

### 1. Channel efficiency

| Channel | Revenue | ROAS | Share of spend | Share of revenue |
|---|---|---|---|---|
| Email | $21.02M | 12.99 | 13.9% | 32.4% |
| LinkedIn | $11.86M | 5.67 | 17.9% | 18.3% |
| Google Ads | $14.35M | 5.04 | 24.4% | 22.1% |
| Facebook | $10.47M | 3.66 | 24.5% | 16.1% |
| Instagram | $7.23M | 3.20 | 19.3% | 11.1% |
| **Total** | **$64.94M** | **5.56** | **100%** | **100%** |

- Email earns about 13.0x on only 13.9% of spend and delivers 32.4% of revenue.
- Facebook and Instagram take about 44% of spend but deliver about 27% of revenue.
- ROAS range by campaign (lowest to highest): Email 5.23–19.98, LinkedIn 2.05–9.89, Google Ads 2.01–7.98, Facebook 1.50–5.96, Instagram 1.50–5.00.
- Email's worst campaign (5.23) beats Instagram's best (5.00).

### 2. Budget vs actual

| Channel | Budget | Actual | Variance | Var % | Overspent campaigns |
|---|---|---|---|---|---|
| Email | $1.78M | $1.62M | −$0.16M | −9.1% | 41 |
| Facebook | $3.15M | $2.86M | −$0.29M | −9.1% | 64 |
| Google Ads | $3.20M | $2.85M | −$0.35M | −11.0% | 57 |
| Instagram | $2.54M | $2.26M | −$0.28M | −11.1% | 41 |
| LinkedIn | $2.31M | $2.09M | −$0.22M | −9.4% | 52 |
| **Total** | **$12.98M** | **$11.68M** | **−$1.30M** | **−10.0%** | **255** |

Every channel finished 9–11% under budget, yet 255 of 1,000 campaigns (25.5%) overspent. Being under budget overall can hide individual overruns. Underspending is not automatically good: it can also mean unused budget or missed opportunity.

### 3. Trend over time

Monthly revenue ranges from about $1.6M (Feb–Mar 2024) to about $3.8M (Jun 2024).

The data ends on 29 Nov 2025, so 2025 has 11 months and 2024 has 12. A full-year comparison would be misleading, so the fair comparison is Jan–Nov in both years:

| | Jan–Nov 2024 | Jan–Nov 2025 | Change |
|---|---|---|---|
| Revenue | $30.41M | $31.49M | about +3.6% |
| Spend | $5.30M | $5.93M | about +12% |
| ROAS | 5.74 | 5.31 | down |
| Campaigns | 449 | 514 | up |

Revenue grew, but spend grew faster, so efficiency (ROAS) declined.

## Recommendations

*These are hypotheses based on sample data and should be tested before acting on them.*

- **Test a budget shift toward Email and LinkedIn.** Move a small share of spend (for example 10%) away from Facebook and Instagram for one quarter, and track the incremental ROAS. Returns usually shrink as spend on a channel grows, so Email's 13x may not hold at higher spend.
- **Review the 255 overspent campaigns.** Check whether the overruns share a channel, a month, or a campaign type, and whether they earned a higher ROAS (justified) or a lower one (waste).
- **Investigate why spend is growing faster than revenue.** Compare 2025 campaigns against 2024 ones on ROAS to find where efficiency dropped.
- **Look into the low-revenue months (Feb–Apr 2024)** to check for seasonality before planning budgets.
- **Learn from the best and worst campaigns within each channel.** The ROAS ranges are wide (for example, 5.23 to 19.98 within Email), so campaign-level differences are large.

## Limitations

- **Sample (synthetic-style) data.** Findings describe this dataset only and should not be treated as real-world results.
- **ROAS is not profit.** The data has no costs of goods, margins, or overhead, so a high ROAS does not prove a channel is profitable.
- **Revenue attribution is unknown.** The source does not say how revenue is credited to channels, and ROAS differences between channels may partly reflect attribution rules.
- **Descriptive analysis only.** No statistical tests were run, so differences (for example, the 2024 vs 2025 change) are not tested for significance.
- **Time uses Start Date.** Campaigns that span several months are counted fully in their start month.
- **Campaign Name quarter labels were not used.** 883 of 1,000 campaign names include a quarter label that does not match the campaign's start date, so all time grouping uses Start Date.
- **2025 is incomplete** (data through 29 Nov 2025), so the year-over-year comparison uses Jan–Nov only.
- **ROAS ranges use minimum and maximum,** which are sensitive to outliers. Percentiles (for example, 25th–75th) would be more robust.
- **Impressions, Clicks, and Conversions are not analyzed** in this version (no CTR, conversion rate, or cost per conversion).
- **KPI cards and the budget table use formulas and do not react to filters.** Only the PivotCharts can be refreshed or filtered, so there are no slicers in this version.

## How it was built

1. Loaded the data into an Excel Table and added ROAS and Overspent calculated columns.
2. Built PivotTables and PivotCharts for revenue by channel and for the monthly revenue trend (grouped by year and month).
3. Built a floating bar ("football field") chart of ROAS ranges using MINIFS / MAXIFS for Low and High, with Delta = High − Low plotted on a stacked bar and the Low series set to No fill.
4. Built a budget vs actual table with SUMIFS.
5. Built KPI cards (Total Revenue, Total Spend, ROAS, Overspent Campaigns) with SUM formulas.
6. Assembled everything on one dashboard sheet using the layout style of the CFI dashboard template.

**Quality checks:** channel revenues sum to the total ($64.94M), overspent counts by channel sum to 255, and the key figures were cross-checked with an independent calculation in Python.

**Excel skills used:** Excel Tables, PivotTables, PivotCharts, SUMIFS, MINIFS/MAXIFS, calculated columns, custom number formats, and dashboard layout.

## Possible next steps

- Add Impressions → Clicks → Conversions funnel metrics (CTR, conversion rate, cost per conversion)
- Add slicers (Channel, Year) and make the KPI cards slicer-aware using `GETPIVOTDATA`
- Use percentile ranges (25th–75th) in the ROAS range chart
- Rebuild the dashboard in Power BI
- Add cost and margin data (if available) to measure profit instead of ROAS

## Repository structure

```
├── README.md
├── Marketing_Campaign_Dashboard.xlsx
└── images/
    └── exceldashboard.png
```

## Credits

- **Dataset:** [TrumpExcel, Excel sample data] 
- **Dashboard layout inspiration:** CFI (Corporate Finance Institute), *Excel Data Visualization and Dashboards* template

Please review the original sources' terms before redistributing their files.

## Author

Jitendriya Satyadarshi 

[Marketing_Campaign_Dashboard.xlsx](https://github.com/user-attachments/files/35160271/Marketing_Campaign_Dashboard.xlsx)
