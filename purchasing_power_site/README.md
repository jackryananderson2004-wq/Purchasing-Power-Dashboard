# The Death of Purchasing Power

FINN 43303 Project B — research report and interactive dashboard.

## Files
- `index.html`: narrative research report, three findings, four KPIs, methodology and placeholder agreement table.
- `dashboard.html`: interactive dashboard with year and category filters, three charts, four KPIs, and data table.
- `styles.css`: shared dark financial-terminal theme.
- `common.js`: shared CSV loading, calculations, and Chart.js visualizations.
- `report.js`: report-specific calculations and charts.
- `dashboard.js`: interactive filter and chart logic.
- `data.csv`: 260 category-year rows, 2000–2025, annual CPI averages and normalized indices.

## Source and methodology
Source: Federal Reserve Economic Data (FRED), using BLS CPI series from the supplied `fredgraph.xlsx` export. See `Series_ID` in `data.csv` for exact series identifiers. Annual means of monthly observations were used for monthly source series; the supplied housing series was already annual. Normalized CPI = annual CPI / 2000 annual CPI × 100.

For each selected category: change = (end normalized index / start normalized index - 1) × 100. KPI average is the unweighted mean of selected category changes; highest/lowest are the extreme category changes; count is distinct selected categories. The categories overlap and do not represent a weighted CPI basket.

## Preview locally
Run `python -m http.server 8000` in this folder and open `http://localhost:8000`. Do not open the HTML file directly; the browser needs to fetch `data.csv`.

## Publish
Create a **public** GitHub repository, upload all files to its root, and enable **Settings → Pages → Deploy from a branch → main / (root)**. GitHub Pages URL is typically `https://USERNAME.github.io/REPOSITORY/`.

## Before submission
1. Confirm the FRED series definitions, especially the childcare series, and source periods.
2. Build the Tableau Public dashboard from `data.csv` using the same default filters and formulas.
3. Compare the four KPIs and replace the `Pending verification` cells in `index.html` with actual Tableau numbers; add the Tableau Public link.
4. Verify the repository, website, and Tableau links in a logged-out browser.
