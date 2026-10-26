# Inventory & Supply Chain Analysis using Excel

## Project Overview

This project focuses on analyzing inventory and supply chain data using Microsoft Excel. The goal is to understand inventory value, stock movement, reorder status, warehouse performance, and monthly inventory trends through data validation, KPI calculations, PivotTables, and an interactive dashboard.

The project demonstrates how Excel can be used to transform raw inventory records into meaningful business insights that support inventory monitoring and operational decision-making.

## Business Objectives

- Analyze inventory value across different warehouses.
- Identify product categories contributing the highest inventory value.
- Monitor stock received, stock issued, and closing stock quantities.
- Analyze inventory records flagged for reorder.
- Compare recorded inventory values across different months.
- Validate inventory data for consistency and reliability.
- Present key metrics and findings through a dashboard.

## Dataset Information

- **Dataset:** BeeProton Stock Register
- **Source:** [BeeProton Inventory Dataset](https://beeprotonai.info/resources/datasets/inventory/)
- **Records:** 1,000 rows
- **Columns:** 15
- **Period:** February–March 2026
- **Format:** CSV / Excel
- **Tools:** Microsoft Excel

The dataset contains inventory records across five warehouses, six product categories, and 120 SKUs.

### Key Columns

| Column | Description |
|---|---|
| month | Month associated with the inventory record |
| warehouse | Warehouse identifier |
| sku | Stock Keeping Unit identifier |
| item_name | Product name |
| category | Product category |
| unit | Unit of measurement |
| opening_stock | Stock available at the beginning of the period |
| received_qty | Quantity of stock received |
| issued_qty | Quantity of stock issued |
| closing_stock | Stock remaining at the end of the period |
| reorder_level | Stock threshold used for reorder monitoring |
| needs_reorder | Source reorder status flag |
| unit_cost | Cost per unit |
| stock_value | Recorded inventory value |
| supplier | Supplier name |

## Tools and Techniques Used

- Microsoft Excel
- Excel formulas
- Data validation and consistency checks
- PivotTables
- KPI calculations
- Bar charts and pie charts
- Dashboard design and data visualization
- Business analysis and interpretation

## Project Workflow

1. Imported the inventory dataset into Excel.
2. Preserved the original data and created a separate working sheet for validation.
3. Performed stock movement and inventory value checks.
4. Checked reorder flags against an assumed reorder threshold rule.
5. Checked the uniqueness of month, warehouse, and SKU combinations.
6. Calculated key inventory KPIs.
7. Created PivotTables to summarize inventory data by warehouse, category, reorder status, and month.
8. Designed a dashboard to present key metrics and comparisons.

## Data Validation

### 1. Stock Movement Validation

Verified whether closing stock matched the stock movement calculation:

Closing Stock = Opening Stock + Received Quantity - Issued Quantity

**Result:** All 1,000 records passed the stock movement check.

### 2. Reorder Flag Validation

Compared the closing stock, reorder level, and source reorder flag using the assumed rule that stock at or below the reorder level should be flagged for reorder.

One record did not match this assumption:

- Warehouse: WH-Delhi
- SKU: SKU-1070
- Item: Measuring Tape 5m (Bulk)
- Closing Stock: 225
- Reorder Level: 225
- Source Reorder Flag: FALSE

The original source flag was retained. This exception may reflect a different rule in the source system for stock exactly equal to the reorder threshold.

### 3. Inventory Value Validation

Compared recorded stock value against closing stock multiplied by unit cost.

A tolerance-based check was used to account for differences in the recorded values.

**Result:** All records passed under the selected tolerance.

Passing this check means the values were within the chosen tolerance; it does not establish the exact valuation methodology used by the source system.

### 4. Duplicate and Record-Key Checks

Checked for exact duplicate rows and verified the uniqueness of the combination of month, warehouse, and SKU.

**Result:** No exact duplicate rows were found, and all 1,000 month-warehouse-SKU combinations were unique.

## Key Performance Indicators (KPIs)

| KPI | Value |
|---|---:|
| Total Inventory Value | ₹16,21,86,704.90 |
| Total Closing Stock Units | 247,837 |
| Total Units Issued | 118,139 |
| Total Units Received | 134,661 |
| Total Inventory Records | 1,000 |

**Important:** The dataset contains records from two months. These totals represent sums across the dataset and should not be interpreted as a single-date inventory balance.

## Key Analysis and Findings

### 1. Inventory Value by Warehouse

| Warehouse | Recorded Inventory Value |
|---|---:|
| WH-Kolkata | ₹3,37,11,648.75 |
| WH-Mumbai | ₹3,32,82,114.69 |
| WH-Chennai | ₹3,23,12,068.48 |
| WH-Pune | ₹3,19,25,297.89 |
| WH-Delhi | ₹3,09,55,575.07 |

**Finding:** WH-Kolkata recorded the highest summed inventory value, while WH-Delhi recorded the lowest.

The difference between the two was approximately ₹27.56 lakh.

These figures represent summed recorded values across the available records, not necessarily the current physical inventory balance of each warehouse.

### 2. Inventory Value by Category

| Category | Recorded Inventory Value |
|---|---:|
| Electrical | ₹6,69,42,028.08 |
| Hardware | ₹2,89,49,775.46 |
| Cleaning | ₹1,91,67,362.45 |
| Stationery | ₹1,68,52,386.15 |
| Packaging | ₹1,60,00,110.68 |
| Grocery | ₹1,42,75,042.06 |

**Finding:** Electrical was the largest category by recorded inventory value, contributing approximately 41.3% of the total.

A high inventory value does not automatically indicate overstocking. Further analysis of demand, stock turnover, reorder requirements, and lead times would be needed.

### 3. Reorder Status Analysis

| Reorder Status | Number of Records |
|---|---:|
| TRUE | 267 |
| FALSE | 733 |
| Total | 1,000 |

**Finding:** Approximately 26.7% of inventory records were flagged as requiring reorder.

This represents the proportion of records flagged TRUE, not necessarily the proportion of unique products requiring reorder.

The source reorder flag exception identified during validation should be considered when interpreting this result.

### 4. Monthly Inventory Value Analysis

| Month | Recorded Inventory Value |
|---|---:|
| February 2026 | ₹7,48,61,784.87 |
| March 2026 | ₹8,73,24,920.01 |

**Finding:** March had approximately 16.65% higher summed recorded inventory value than February.

This comparison describes the values recorded for each month. It does not, by itself, prove that physical inventory increased by the same percentage.

## Dashboard Overview

The Excel dashboard presents key inventory metrics and visual comparisons in a consolidated view.

### Dashboard Components

- Total Inventory Value
- Total Closing Stock Units
- Total Units Issued
- Total Units Received
- Total Inventory Records
- Inventory Value by Warehouse chart
- Inventory Value by Category chart
- Reorder Status chart
- Inventory Value by Month chart

The dashboard helps users review inventory performance and compare warehouse, category, reorder, and monthly records efficiently.

## Business Value

This project demonstrates how inventory data can be organized and analyzed to support business monitoring.

The analysis can help stakeholders:

- Compare recorded inventory value across warehouses.
- Identify categories with a large share of recorded inventory value.
- Monitor records flagged for reorder.
- Review stock movement and data consistency.
- Compare monthly inventory records.
- Use KPI cards and charts to communicate findings clearly.

## Limitations

- The dataset is synthetic and may not represent actual business operations.
- The records cover two months, so summed values do not equal a single-date inventory balance.
- The reorder validation uses an assumed threshold rule, and one source record differs at the equality threshold.
- Inventory value validation uses a selected tolerance and does not establish the source system's exact valuation methodology.
- The analysis is descriptive and does not establish the causes of inventory differences or prove that any category is overstocked.

## Skills Demonstrated

- Microsoft Excel
- Data cleaning and validation
- Inventory analysis
- Stock movement calculations
- KPI development
- PivotTables
- Data visualization
- Dashboard development
- Business insight generation
- Analytical documentation

## Repository Structure

```text
BeeProton-Stock-Register/
├── README.md
├── inventory_data.xlsx
└── screenshots/
    └── Dashboard.png
