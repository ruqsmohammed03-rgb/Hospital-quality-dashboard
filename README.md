# Hospital Readmissions Dashboard

A single-file, no-build dashboard that compares U.S. hospitals on 30-day readmissions using the CMS **Hospital Readmissions Reduction Program (HRRP)** dataset from the [CMS Provider Data Catalog](https://data.cms.gov/provider-data/dataset/9n3s-kdb3) (dataset ID `9n3s-kdb3`).

## What it shows
- **Excess Readmission Ratio (ERR)** = a hospital's predicted readmission rate ÷ the expected rate for similar hospitals. Above 1.0 means more readmissions than expected; below 1.0 means fewer.
- Filters for condition (AMI, CABG, COPD, heart failure, hip/knee, pneumonia), state, and minimum discharges.
- Summary cards, an ERR distribution histogram, best/worst 10 hospitals, and a side-by-side comparison of up to 5 hospitals across all conditions.

## Run it
1. Open `index.html` in a browser (or enable GitHub Pages: Settings → Pages → deploy from `main`, root).
2. Click **Load live from data.cms.gov**, or download the CSV from the dataset page and use the file picker. **Synthetic demo data** is for previewing only and is not real hospital data.

## Caveats
- ERR is risk-adjusted but is not a full measure of hospital quality. Small hospitals have noisy ratios, so use the minimum-discharges filter.
- Rows CMS marks "Not Available" or "Too Few to Report" are excluded.
- Column names are matched flexibly because CMS has changed headers across releases. If a future release changes them, edit `norm()` in `index.html`.
- CMS announced changes beginning FY 2027 (Medicare Advantage data included, 2-year performance period), so compare across years with care.

## Source
CMS Hospital Readmissions Reduction Program, data.cms.gov. Not affiliated with or endorsed by CMS.
