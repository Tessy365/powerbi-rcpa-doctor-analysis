# Pharmaceutical RCPA & Doctor Conversion Dashboard (Power BI)
## Executive Summary
This Power BI analytics project evaluates **Retail Chemist Prescription Audit (RCPA)** data for Laboratory & Allied Ltd (L&A). The dashboard tracks doctor prescription performance across sales divisions (Chronic, Gyn, Pain), evaluates doctor conversion rates against monthly target thresholds, and benchmarks L&A focus products against competitor market share across regional chemist networks.

---

## Project Objectives & Core Metrics

1. **ETL & Data Transformation**: Executing complex Power Query transformations on multi-line text forms, unpivoting nested pharmacy prescription entries, and standardizing null/blank quantity fields.
2. **Doctor Conversion Tracking**: Monitoring doctor prescription behavior to identify medical practitioners meeting or exceeding monthly brand targets.
3. **Brand Competition Audit**: Comparing L&A focus products against competitor equivalents (e.g., *Carboferon* vs. *Ranferon*, *Gynagone* vs. *Trio/Dazel*) by region and chemist.
4. **Sales Rep & Regional Performance**: Aggregating weekly prescription volumes by Medical Representative, Chemist, Doctor, and Sales Division.

---

## Key Business Insights & Findings

* **Prescription Concentration**: A small cohort of top prescribers drives over **40% of total prescription volume**, led by key targets such as *Dr. John Wambugu* (15.7%), *Dr. Joseph Macharia* (12.5%), and *Dr. Joyce Gitonga* (12.5%).
* **Chemist Channel Volume**: *Othaya Chemist* and *Cendco* represent the highest-volume retail fulfillment outlets in the region, serving as critical audit points for tracking prescription conversions.
* **Competitor Pressure Points**: L&A focus products (*Carboferon* and *Gynagone*) face heavy substitution competition from key rival brands including *Ranferon* (Sunpharma), *Hemoforce* (Shalina), and *Trio/Dazel Kit* (Ajanta/Zest).
* **Monthly Growth Trajectory**: Prescription fulfillment showed significant upward momentum moving from September into October across primary chronic and gyn accounts.

---

## Power Query ETL Pipeline

The raw JotForms survey dataset required extensive data cleaning and unpivoting in Power Query:

* **Delimited Text Splitting**: Split raw text strings by line breaks (`#(lf)`) to extract Medical Rep names, Doctors, Regions, and Chemists.
* **Unpivoting Pharmacy Details**: Unpivoted nested columns for Pharmacy 1, Pharmacy 2, and Pharmacy 3 to consolidate Focus Product entries and Competitor details into structured rows.
* **Data Sanitization**: Standardized string headers (`"Focus Product: "`, `"Rx Qty/Week: "`, `"L&A Product: "`) and handled empty string conversions to prevent numeric casting errors.

---


### Key Report Sections:
* **Executive Slicers**: Dynamic filtering by Medical Representative, Chemist, Region, and Doctor.
* **Monthly Volume Trend**: Line chart tracking prescription growth (`Sum of Rx Qty/Week`) over time.
* **Chemist Share**: Horizontal bar chart identifying top-performing regional chemist outlets.
* **Doctor Share Distribution**: Pie chart illustrating prescription volume concentration among top doctors.
* **Detailed Audit Table**: Matrix breakdown detailing monthly prescription counts per Chemist and Doctor.

---

## Repository Structure

```text
├── data/           # Raw Excel workbook (JOTFORMS.xlsx) containing RCPA records
├── pbix/           # Complete Power BI Desktop file (.pbix)
├── screenshots/    # High-resolution dashboard screenshots
└── README.md       # Project documentation
