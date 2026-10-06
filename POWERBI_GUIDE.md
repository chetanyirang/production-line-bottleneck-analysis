# Power BI dashboard setup

## Load the automotive data

1. Install `requirements.txt`, then run `analysis.py` from this folder.
2. In Power BI Desktop, import `outputs/powerbi_dashboard_data.csv`.
3. Rename the imported table to `Automotive`; use `PowerBI_Measures.dax` to add the measures.
4. Set `shift_date` to the Date data type. Format the OEE and percentage measures as percentages and time measures in seconds.
5. Add a date slicer and a `line_id` slicer so the visuals can be filtered by time and line.

## Suggested report page

- **KPI cards:** OEE, average takt, average actual cycle time, average bottleneck cycle time, average throughput, and unplanned downtime.
- **Takt vs. bottleneck:** line chart or clustered bar chart by `line_id` with average takt and average bottleneck cycle time.
- **OEE by line:** clustered bar chart by `line_id`, using the OEE measure.
- **Bottleneck severity:** bar chart by `line_id` using the positive bottleneck gap; sort descending. Add `Positive Gap Pareto Share %` as a line on a combo chart if desired.
- **Downtime Pareto:** import `outputs/automotive_clean.csv` and unpivot the six `downtime_category_*` columns in Power Query, or use the `Downtime Pareto` sheet in `outputs/automotive_analysis.xlsx`. The Pareto is based on those provided category fields; their sum does not reconcile exactly to the unplanned downtime total.
- **Throughput by line:** bar chart by `line_id` using average throughput.
- **Production trend:** line chart by `shift_date` using actual or good units; use average OEE as a separate visual.

The dashboard is based on synthetic source records with shift and production-order context; some line/shift keys repeat across production orders. An interactive `.pbix` file must be authored and saved in Power BI Desktop; this project supplies the importable data, measures, and visual blueprint rather than claiming a PBIX was generated.

## Interpretation cautions

- A positive bottleneck gap means the recorded bottleneck cycle time exceeds takt.
- Some automotive rows share a `shift_id` and `line_id` because their production orders differ. Keep `production_order_id` when identifying records; don't label row counts as unique shifts.
- Use averages for comparing record-level rates; summing rates is not meaningful.
- Do not combine the simulated improvement scenario with actual production results. The 5%, 10%, and 15% cycle-time reductions in the workbook are hypothetical capacity calculations.
- The supplied line-level records and aggregate loss categories do not establish causal root causes. Verify suspected causes on the production floor.
