# 🗺️ Project Roadmap — F1 Performance Analytics (Kaggle Dataset)

A structured, end‑to‑end plan for analyzing Formula 1 performance using the Kaggle F1 dataset.

---

## Phase 1 — Data Acquisition
- Download the Kaggle Formula 1 dataset (CSV files)
- Store all raw files in the `data/` directory
- Verify file integrity (row counts, missing files, encoding issues)
- Document each CSV and its purpose

**Output:** Raw CSV files + dataset reference notes

---

## Phase 2 — Data Audit & Cleaning
- Inspect each table (drivers, constructors, races, results, qualifying, circuits)
- Standardize column names and data types
- Identify missing values (DNFs, DNS, DSQ, nulls)
- Merge tables into a unified race‑driver dataset
- Remove non‑race sessions if needed (sprint, practice)

**Output:** Cleaned master dataset ready for feature engineering

---

## Phase 3 — Feature Engineering
- Compute position change (finish − qualifying)
- Create DNF categories (mechanical vs. non‑mechanical)
- Encode circuit types (street, permanent, hybrid)
- Add season‑normalized metrics (z‑scores or percentiles)
- Create driver‑level aggregates (career stats, season stats)

**Output:** Feature‑rich dataset for modeling and ranking

---

## Phase 4 — Project A: Grid‑to‑Podium Predictor
- Filter dataset by circuit type
- Fit linear regression models (qualifying → finishing)
- Evaluate R², MAE, RMSE
- Compare predictability across circuits
- Visualize regression lines and residuals

**Output:** Circuit‑specific predictability analysis

---

## Phase 5 — Project B: Midfield King Metric
- Remove mechanical DNFs
- Compute adjusted position gains
- Aggregate by driver and season
- Rank drivers by overtaking efficiency
- Build consistency heatmaps

**Output:** Midfield King scoring table + visualizations

---

## Phase 6 — Visualization & Reporting
- Build comparison dashboards (Monaco vs. Monza)
- Create driver performance heatmaps
- Generate season‑over‑season trend charts
- Export all visuals to `visuals/`

**Output:** Final visual analytics package

---

## Phase 7 — Final Deliverables
- Publish full written analysis
- Upload notebooks to `notebooks/`
- Update README with results
- Prepare portfolio‑ready summary


