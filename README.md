# Hospital Readmissions Dashboard

**Live demo:** https://ruqsmohammed03-rgb.github.io/Hospital-quality-dashboard/

An interactive, zero-install dashboard that compares U.S. hospitals on 30-day readmissions using the CMS **Hospital Readmissions Reduction Program (HRRP)** data from the [CMS Provider Data Catalog](https://data.cms.gov/provider-data/dataset/9n3s-kdb3).

<!-- After adding a screenshot to docs/, uncomment the next line:
![Dashboard screenshot](docs/screenshot.png)
-->

## Why it matters
Medicare reduces payments to hospitals with more readmissions than expected. This tool makes that comparison easy to explore by condition, state, and hospital size.

## Features
- **Condition filter:** heart attack (AMI), CABG, COPD, heart failure, hip/knee replacement, pneumonia.
- **Distribution chart** of Excess Readmission Ratios (ERR) with a marker at 1.0.
- **State comparison:** median ERR by state.
- **Best and worst 10 hospitals** for any filter combination.
- **Side-by-side comparison** of up to 5 hospitals across all conditions.
- **CSV export** of the current view.

## How to read ERR
ERR = predicted readmission rate ÷ expected rate for similar hospitals. Above 1.0 means more readmissions than expected; below 1.0 means fewer.

## Run it
1. Open the live demo, or open `index.html` locally.
2. Load data in one of three ways:
   - Place the CMS CSV at `data/hospital_readmissions.csv` (loads automatically; see `data/README.md`).
   - Click **Load live from data.cms.gov** (may be blocked by some browsers).
   - Download the CSV from CMS and use **Choose File**.
3. **Synthetic demo data** is for previewing the layout only and is not real.

## Method
- Source columns: facility name and ID, state, measure, discharges, ERR.
- Column names are matched flexibly because CMS has renamed headers between releases.
- Rows marked "Not Available" or "Too Few to Report" are excluded.
- State medians require at least 5 hospitals.

## Limitations
- ERR is risk-adjusted but is only one measure of quality.
- Small hospitals have noisy ratios; use the minimum-discharges filter.
- The data covers Medicare patients. From FY 2027, CMS adds Medicare Advantage data and a 2-year performance period, so compare years carefully.

## Roadmap
- Trend across fiscal years
- Link to HCAHPS patient-experience scores
- State map

## License and attribution
MIT License. Data from CMS; this project is not affiliated with or endorsed by CMS.
