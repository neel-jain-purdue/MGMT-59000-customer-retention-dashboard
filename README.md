# Customer Growth & Retention Intelligence Dashboard

An interactive Streamlit dashboard for analyzing `NR_dataset.xlsx`. It helps commercial and marketing teams:

1. **Identify growth opportunities** — emerging high-potential customers, categories, and region/channel combinations within the existing customer base.
2. **Detect early warning signs of decline** — low satisfaction, revenue-at-risk, and inactive/recency-flagged customers.
3. **Get data-driven recommendations** — auto-generated, filter-aware action items to guide commercial and marketing strategy.

## Files

| File | Purpose |
|---|---|
| `app.py` | Main Streamlit application |
| `NR_dataset.xlsx` | Source dataset (must sit alongside `app.py`) |
| `requirements.txt` | Python dependencies |

Fields used: `label`, `purchaseamount`, `customerregion`, `productcategory`, `retailchannel`, `customerid`, `transactiondate` (plus `customersatisfaction` as a supporting churn-risk signal).

## Run locally

```bash
pip install -r requirements.txt
streamlit run app.py
```

The app will open at `http://localhost:8501`.

## Notes

- The dashboard is fully filter-driven (sidebar: date range, region, channel, category, segment label) — every KPI, chart, and recommendation on every tab recalculates from the current selection.
- Charts are built with Plotly for interactivity (hover, zoom, legend toggling).
- If you refresh `NR_dataset.xlsx` with new data, keep the same column names (`label`, `CustomerID`, `TransactionDate`, `ProductCategory`, `PurchaseAmount`, `CustomerRegion`, `RetailChannel`, and optionally `CustomerSatisfaction`) and the dashboard will work without code changes.
