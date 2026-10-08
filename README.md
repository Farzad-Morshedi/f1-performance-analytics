# 🏎️ F1 Performance Analytics — Predictability vs. Grit

Applying the full data analysis lifecycle to quantify how qualifying performance, circuit characteristics, and mechanical reliability shape race outcomes.

📌 Overview

This repository contains a comprehensive two-part analytical study of Formula 1 race dynamics using downloaded CSV datasets derived from historical motorsport archives.
The goal is to measure how much of F1 performance is predictable (car pace, qualifying position) versus how much comes from driver grit (racecraft, overtaking, consistency).

🚥 Project Status

* Project B — The Midfield King Metric: Complete (Stages 1–5 executed, pure pace gaps isolated, grid mobility quantified).
* Project A — The Grid-to-Podium Predictor: Complete (Linear regression modeling, exhaustive global circuit indexing, and automated multi-circuit HTML visualization generation).
* Interactive Dashboard: Complete (Plotly standalone web deliverables and modular script exports).

🧩 Project Structure

f1-performance-analytics/
├── data/                  # Raw downloaded CSVs and clean exported summary datasets
├── notebooks/             # Jupyter notebooks covering each lifecycle stage
├── src/                   # Python modules for data wrangling, metrics, and visualization
├── visuals/               # Exported figures, dashboards, and performance matrices
└── README.md              # Project documentation and summary report

🎯 Project A — The Grid-to-Podium Predictor

Objective
Quantify how strongly qualifying rank predicts final race position across the entire global calendar during the hybrid era (2014–2026).
Method
Ordinary Least Squares (OLS) Linear Regression with automated multi-circuit indexing and strict mechanical DNF filtering.
Why it matters
Some tracks reward pure pace; others reward racecraft. Measuring track-specific determinism helps isolate driver vs. car contributions.
Key Findings
* Hybrid Era Baseline: Across 4,209 clean race entries, starting grid position accounts for roughly 44% of final race outcomes ($R^2 \approx 0.44$).
* Circuit Topology Contrast: High-determinism street venues like Monaco ($R^2 \approx 0.49$) severely restrict overtaking, whereas high-speed fluid circuits and power tracks like Monza ($R^2 \approx 0.40$) enable significant positional recovery from deep starting slots.

🎯 Project B — The Midfield King Metric

Objective
Identify drivers and constructors who consistently outperform their machinery by isolating pure race pace and quantifying grid position mobility across the Hybrid Era (2014–2026).
Method
Feature engineering, DNF filtering, and aggregated performance scoring.
Why it matters
Finishing position alone hides reliability noise. Removing DNFs reveals true overtaking efficiency.
Key Findings
* Top-Tier Determinism vs. Midfield Volatility: Top-tier teams display a strong grid-to-finish correlation ($r_s = 0.589$), whereas midfield race outcomes are 22% more volatile ($r_s = 0.460$), driven by strategy variance, DRS trains, and traffic.
* The 0.8s/lap Performance Cliff: Pure race pace analytics reveal an isolated top tier—Mercedes (+0.57s/lap), Red Bull (+0.83s/lap), and Ferrari (+1.01s/lap)—separated by a massive 0.8-second gap from the fastest midfield entry (Aston Martin at +1.84s/lap).
* DNF-Adjusted "Midfield King" Driver Rankings:
  * Backmarker Positional Floor: Felipe Nasr (+2.63 positions gained/race, $\sigma = 3.80$) and Stoffel Vandoorne (+2.47, $\sigma = 3.89$) lead the metric. Drivers qualifying near the back face zero downside risk while benefiting from attrition ahead.
  * Driver Volatility Spectrum: Pastor Maldonado demonstrates extreme outcome variance ($\sigma = 5.01$, +1.23 avg gain), whereas Nicholas Latifi ($\sigma = 3.67$) shows tighter, lower-risk positional consistency.
* Noise Variance Reduction: Filtering pit stops and safety car disruptions reduced dataset lap time variance by $\approx 6.1$, establishing an unpolluted baseline for car development and stint consistency.

Generated Data Artifacts
* `f1_driver_pace_summary.csv` — 4,438 clean driver-race stints with median pace gaps and consistency metrics.
* `f1_constructor_pace_summary.csv` — Aggregated constructor hierarchy and within-stint standard deviation.
* `f1_grid_mobility_summary.csv` — Cohort-level Spearman rank correlations and mean position deltas.
* `f1_midfield_kings_summary.csv` — DNF-adjusted driver position gains and multi-season standard deviations.
* `f1_global_circuit_determinism_rankings.csv` — Exhaustive regression metrics and $R^2$ scores across all hybrid-era circuits.

🛠️ Tools & Technologies

* Python (`pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `plotly`)
* SQL (Local database queries)
* Jupyter Notebooks
* Custom pipelines for data cleaning, feature engineering, and statistical modeling

📊 Project Deliverables & Visuals

* F1 Hybrid Era Performance Matrix (Pure Pace Gap vs. Stint Variance Scatter Plot)
* Grid Determinism vs. Midfield Mobility Dashboard (Spearman Correlation & Position Delta)
* Top 10 Drivers by Net Position Gain (Mechanical DNFs Removed Bar Chart with Variance Error Bars)
* Cleaned Summary CSV Data Exports
* Exhaustive circuit-specific regression models and automated HTML visualization exports (`f1_grid_determinism_professional.html` and multi-circuit outputs)

📚 Data Source

* Historical local CSV datasets (Ergast archive export)
