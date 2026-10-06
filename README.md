# Syntecxhub Internship — Website Traffic Analysis

**Internship:** Syntecxhub Data Analytics Internship  
**Project:** Website Traffic Analysis
# Syntecxhub Website Traffic Analysis

## 🌐 Live Dashboard

[View Live Website](https://syntecxhub-website-traffic-analysis.vercel.app)

## 💻 GitHub Repository

This repository contains the complete source code, dataset, Jupyter Notebook, dashboard, and visualizations for the Website Traffic Analysis project.

## Objective

Analyze the supplied website traffic export to understand traffic trends, channel contribution, user engagement, peak traffic hours, and the relationship between session volume and engagement. The analysis uses only fields present in the supplied CSV.

## Dataset

The source file is [`csv/website_traffic.csv`](csv/website_traffic.csv). It contains a descriptive first row, a header row, and hourly channel-level observations from **April 6 through May 3, 2024**. The notebook identifies the actual header row rather than assuming the CSV starts with its header. It preserves additional columns and validates the required analysis fields.

Counts are aggregated from channel-hour records. In particular, **Total Users is the sum of the Users field across those records and is not a deduplicated count of unique people**. Channel and hourly engagement rates are calculated as total engaged sessions divided by total sessions, not as an unweighted mean of row-level rates.

## Tools

- Python
- pandas and NumPy
- Matplotlib and Seaborn
- Jupyter Notebook / VS Code

## Folder structure

```text
.
├── csv/
│   └── website_traffic.csv
├── dashboard/
│   ├── README.md
│   └── (generated dashboard.html and dashboard-ready CSV files)
├── visualizations/
│   └── (generated PNG charts)
├── requirements.txt
├── README.md
└── Website_Traffic_Analysis.ipynb
```

The notebook creates `visualizations/` and the generated dashboard outputs when it runs. It does not modify the original CSV.

## Install requirements

From the project directory, create a local environment if needed and install:

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

If `.venv` already exists, skip the creation step. If you use another environment, run `python -m pip install -r requirements.txt` with that environment's Python. Select the installed environment as the notebook kernel in VS Code.

## Run the notebook

1. Open `Website_Traffic_Analysis.ipynb` in VS Code.
2. Select the project `.venv` kernel (or another environment with `requirements.txt` installed).
3. Choose **Run All**.

The CSV is located automatically from the project notebook and its sibling `csv/` folder when run with the project directory (or one of its subfolders) as the notebook working directory. No machine-specific absolute paths are used.

## View the dashboard

After running all notebook cells, open `dashboard/dashboard.html` in a browser. This is a self-contained, offline dashboard with KPI cards, date/channel filters for recalculating KPIs and the channel summary, and the generated charts. The chart images show the full supplied date range; the accompanying CSVs in `dashboard/` can be filtered further in Excel, Power BI, or another reporting tool. The dashboard uses browser JavaScript and requires no extra Python packages.

## Analysis questions

The notebook answers:

1. How do users and sessions change over time?
2. Which channel brought the most users?
3. Which channel has the highest average engagement time?
4. How does engagement rate vary by channel?
5. How do engaged and non-engaged sessions compare by channel?
6. At what hours does each channel drive the most sessions?
7. How are hourly session volume and engagement rate related?

Each question has calculated results, a visualization, and a concise business interpretation in the notebook.

## Key findings from the supplied data

These figures are computed from 3,182 channel-hour records; rerun the notebook to refresh the charts and dashboard:

- **Organic Social** led traffic with 47,572 summed users and 60,627 sessions.
- **Referral** had the highest weighted engagement rate among the higher-volume sources: 66.6%, with 30,990 sessions and 20,653 engaged sessions.
- **Organic Video** showed the highest average engagement time (about 180 seconds) and engagement rate (77.3%), but represented only 141 sessions; treat this as a small-volume signal, not a stable benchmark.
- **Unassigned** had the weakest engagement rate (0.7%) across 559 sessions, indicating an attribution and/or audience-quality issue to investigate.
- The overall engagement rate was 55.3%. The strongest overall session hour was April 17, 2024 at 18:00, with 513 sessions.
- Hourly sessions and engagement rate had a positive Pearson correlation of about **0.27** (672 hourly timestamps), a weak association that does not establish causation.

## Business recommendations

1. Protect and test the Organic Social acquisition funnel, which contributes the largest traffic volume; use controlled creative and landing-page tests to improve engagement without assuming that volume alone means quality.
2. Study Referral partner sources and landing pages because Referral combines substantial volume with a high engagement rate; replicate the strongest partner placements where appropriate.
3. Run a small, measured Organic Video growth test. Its engagement metrics are promising, but its current sample is too small to justify broad budget shifts.
4. Audit Unassigned traffic and campaign tagging first, then examine audience and landing-page fit to address its very low engagement.
5. Review the late-night Direct peak and other channel-specific peak hours when planning publishing and campaign schedules; validate with additional weeks before changing staffing or spend.

## Dataset limitations

The export provides channel-hour traffic and engagement measures, but no bounce rate, conversions, goal completions, page-level performance, campaign cost, device, or landing-page fields. Those metrics cannot be calculated from this file. Add corresponding analytics and campaign-cost exports to evaluate conversion, ROI, page performance, or device-specific behavior. The Users field is summed across records and is not de-duplicated across hours or channels.

## Author

Author: **KUDUKA APPASI VAISHNAVI**
