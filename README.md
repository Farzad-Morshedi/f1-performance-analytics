# 🏎️ F1 Performance Analytics — Predictability vs. Grit

Applying the full data analysis lifecycle to quantify how qualifying performance, circuit characteristics, and mechanical reliability shape race outcomes.

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-yellow)
![SQL](https://img.shields.io/badge/SQL-Ergast%20DB-red)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange)
![Status](https://img.shields.io/badge/Status-In%20Progress-green)

---

## 📌 Overview

This repository contains a two-part analytical study of Formula 1 race dynamics using the **Ergast Motor Racing Database**.  
The goal is to measure how much of F1 performance is **predictable** (car pace, qualifying position) versus how much comes from **driver grit** (racecraft, overtaking, consistency).

---

## 🚥 Project Status

* [x] **Project B — The Midfield King Metric:** Complete (Stages 1–5 executed, pure pace gaps isolated, grid mobility quantified).
* [ ] **Project A — The Grid-to-Podium Predictor:** Pending (Linear regression modeling, track-specific segmentation for Monaco vs. Monza).
* [ ] **Interactive Dashboard:** Pending (Plotly/Dash implementation for web deployment).

---

## 🧩 Project Structure

```text
f1-performance-analytics/
├── data/                  # Raw Kaggle CSVs and clean exported summary datasets
├── notebooks/             # Jupyter notebooks covering each lifecycle stage
├── src/                   # Python modules for data wrangling, metrics, and visualization
├── visuals/               # Exported figures, dashboards, and performance matrices
└── README.md              # Project documentation and summary report
```

---

## 🎯 Project A — The Grid-to-Podium Predictor

**Objective**  
Quantify how strongly qualifying rank predicts final race position across different circuit types.

**Method**  
Linear Regression with circuit-specific segmentation (e.g., Monaco vs. Monza).

**Why it matters**  
Some tracks reward pure pace; others reward racecraft. Measuring this helps isolate **driver vs. car** contributions.

**Key Question**  
How does the **R² correlation** between qualifying and finishing position differ between a street circuit (Monaco) and a high-speed circuit (Monza)?

---

## 🎯 Project B — The Midfield King Metric

**Objective**  
Identify drivers and constructors who consistently outperform their machinery by isolating pure race pace and quantifying grid position mobility across the Hybrid Era (2014–2026).

**Method**  
Feature engineering, DNF filtering, and aggregated performance scoring.

**Why it matters**  
Finishing position alone hides reliability noise. Removing DNFs reveals **true overtaking efficiency**.

**Key Question**  
Which drivers gain the most positions **after removing mechanical DNFs**, and how consistent is that performance across seasons?

**Key Findings**
* **Top-Tier Determinism vs. Midfield Volatility:** Top-tier teams display a strong grid-to-finish correlation ($r_s = 0.589$), whereas midfield race outcomes are 22% more volatile ($r_s = 0.460$), driven by strategy variance, DRS trains, and traffic.
* **The 0.8s/lap Performance Cliff:** Pure race pace analytics reveal an isolated top tier—Mercedes ($+0.57\text{s/lap}$), Red Bull ($+0.83\text{s/lap}$), and Ferrari ($+1.01\text{s/lap}$)—separated by a massive $0.8$-second gap from the fastest midfield entry (Aston Martin at $+1.84\text{s/lap}$).
* **DNF-Adjusted "Midfield King" Driver Rankings:**
  * **Backmarker Positional Floor:** Felipe Nasr ($+2.63$ positions gained/race, $\sigma=3.80$) and Stoffel Vandoorne ($+2.47$, $\sigma=3.89$) lead the metric. Drivers qualifying near the back face zero downside risk while benefiting from attrition ahead.
  * **Driver Volatility Spectrum:** Pastor Maldonado demonstrates extreme outcome variance ($\sigma=5.01$, $+1.23$ avg gain), whereas Nicholas Latifi ($\sigma=3.67$) shows tighter, lower-risk positional consistency.
* **Noise Variance Reduction:** Filtering pit stops and safety car disruptions reduced dataset lap time variance by $\approx 6.1\%$, establishing an unpolluted baseline for car development and stint consistency.

**Generated Data Artifacts**
* f1_driver_pace_summary.csv — 4,438 clean driver-race stints with median pace gaps and consistency metrics.
* f1_constructor_pace_summary.csv — Aggregated constructor hierarchy and within-stint standard deviation.
* f1_grid_mobility_summary.csv — Cohort-level Spearman rank correlations and mean position deltas.
* f1_midfield_kings_summary.csv — DNF-adjusted driver position gains and multi-season standard deviations.

---

## 🛠️ Tools & Technologies

- Python (pandas, numpy, matplotlib, seaborn, scikit-learn)
- SQL (Ergast API queries)
- Jupyter Notebooks
- Custom pipelines for data cleaning, feature engineering, and modeling

---

## 📊 Project Deliverables & Visuals

- [x] F1 Hybrid Era Performance Matrix (Pure Pace Gap vs. Stint Variance Scatter Plot)

- [x] Grid Determinism vs. Midfield Mobility Dashboard (Spearman Correlation & Position Delta)

- [x] Top 10 Drivers by Net Position Gain (Mechanical DNFs Removed Bar Chart with Variance Error Bars)

- [x] Cleaned Summary CSV Data Exports (f1_driver_pace_summary.csv, f1_constructor_pace_summary.csv, f1_grid_mobility_summary.csv)

- [ ] Circuit-specific regression models (Project A: Monaco vs. Monza)

- [ ] Interactive Dash/Plotly Web Application
---

## 🚧 Upcoming Work

- Integrate multi-season datasets  
- Add driver and team metadata  
- Build interactive dashboards (Plotly)  
- Publish final written report and key insights  

---

## 📚 Data Source

**Ergast Developer API**  
https://ergast.com/mrd/

---
