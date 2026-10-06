# Dashboard outputs

Run every cell in `../Website_Traffic_Analysis.ipynb` to generate:

- `dashboard.html` — self-contained, offline dashboard with date/channel filters, recalculated KPI cards and channel summary, and embedded charts. The images summarize the full date range.
- `traffic_channel_hour.csv` — cleaned detail rows suitable for filtering by date and channel.
- `channel_summary.csv` — channel totals and weighted engagement measures.
- `hourly_channel_traffic.csv` — sessions by hour and channel.
- `sessions_engagement_trend.csv` — sessions and weighted engagement rate by timestamp.
- `kpi_summary.csv` — project-level KPI values.
- `visualizations/` — copies of the PNG charts used by the dashboard.

Open `dashboard.html` in a browser to use the local date/channel filters, or import the CSVs into Excel/Power BI for further interactive filtering. No dashboard-only package is required.
