# Quebec Winter Tire Fulfillment Gap — Root-Cause Analysis

A self-directed case study built to practice end-to-end diagnostic analysis: taking a vague stakeholder complaint, confirming whether it's real, quantifying it, and tracing it to a root cause using SQL and Python.

> This project uses a simulated dataset generated with Python/Faker, built around a realistic distribution/logistics scenario, to practice the analysis process end to end.
> Built with the help of Claude (Anthropic) — used for structuring the investigation narrative, drafting the written report, and as a sounding board for interpreting results. All queries, analysis decisions, and findings were run and verified by me.

## The scenario

A VP of Sales gets anecdotal reports that Quebec garage customers are switching to competitors right before winter tire season, allegedly because orders can't be fulfilled in time. There's no hard data yet — just complaints — and leadership needs numbers before approving any budget to fix it.

## Approach

Rather than jumping straight to "why," the analysis follows a deliberate sequence:

1. **Confirm it's real** — check backorder rates for winter tires specifically, not all orders
2. **Rule out the easy explanation** — check whether Quebec just has more order volume (it doesn't)
3. **Size it over time** — confirm the pattern repeats across both years in the dataset
4. **Quantify the impact** — price out unfulfilled units to get a dollar figure, not just an order count
5. **Find the mechanism** — cross-reference against warehouse inventory snapshots to identify root cause

## Key finding

Quebec's winter tire backorder rate is **~29%**, four to seven times higher than every other region (4–8%), representing an estimated **$124,169 in at-risk revenue** across 738 short-shipped units and 87 orders (Sep–Nov, the pre-season buying window). The root cause: winter tire inventory at the Montreal distribution centre collapses to ~1,200–1,300 units every August through November — exactly when demand peaks — while every other region maintains 6,000–8,500 units through their own equivalent season.

## Repo structure

```
├── data/
│   └── tire_distributor.db        # SQLite database (warehouses, products, orders, order_items, inventory_snapshots)
├── notebooks/
│   └── analysis.ipynb             # Full query-by-query investigation, annotated
├── report/
│   └── Quebec_Winter_Tire_Report.docx   # Final stakeholder-facing report
├── requirements.txt
└── README.md
```

## Tech stack

- **SQLite** — order, product, warehouse, customer, and inventory data
- **Python** (pandas, sqlite3, matplotlib) — querying and analysis in Jupyter
- **Word (docx)** — final report

## Limitations

This analysis quantifies unfulfilled *orders* — it can't see demand that never became an order because a customer went straight to a competitor, which is the exact scenario the original complaint described. It also identifies *where and when* the inventory shortfall occurs, not *why* Montreal's replenishment schedule lags — that would require follow-up with procurement/supply chain data not present in this dataset. Full discussion in the report's Limitations section.

## Run it yourself

```bash
pip install -r requirements.txt
jupyter notebook notebooks/analysis.ipynb
```

The first cell connects to `../data/tire_distributor.db` — no additional setup required.
