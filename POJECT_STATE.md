# F1_performance_analytics: Project State

## 1. Project Lifecycle Status

* **Current Phase:** Stage 6: Act / Portfolio Polish
* **Completed Phases:**
  * **Stage 1: Ask:** Defined "Midfield King" racecraft metrics and "Grid-to-Podium" determinism objectives.
  * **Stage 2: Prepare:** Kaggle/Ergast CSV datasets ingested and verified.
  * **Stage 3: Process:** Data cleaning, snake_case standardization, constructor rebranding lineage mapping, and lap time IQR outlier removal completed.
  * **Stage 4: Analyze:** OLS linear regression models, global circuit determinism indexing ($R^2$), and DNF-adjusted Spearman rank correlations ($r_s$) computed.
  * **Stage 5: Share:** Visuals exported, interactive Plotly/Dash HTML dashboards generated, and summary CSV deliverables written.
* **Active Focus:** Finalizing raw repo documentation (`README.md` and `project_state.md`) for GitHub presentation.

---

## 2. Technical Infrastructure & Constraints

* **Data Source:** Local downloaded Ergast CSV datasets.
* **Stack:** Python (`pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `plotly`) and SQL.
* **Coding Standard:**
  * **No Method Chaining:** Transformations are executed step-by-step using discrete variables for clean debugging.
  * **Documentation:** Explicit docstrings for every custom function and explanatory comments for complex analytical logic.
  * **Naming Convention:** Strict `snake_case` enforced across all dataframes, column headers, and SQL tables.

---

## 3. Data Schema Tracker

| File / Table | Key Columns (PK/FK) | Cleaning Status | Notes |
| :--- | :--- | :--- | :--- |
| `results.csv` | `race_id`, `driver_id`, `constructor_id` | Completed | Core outcomes, grid positions, and finishing spots standardized. |
| `drivers.csv` | `driver_id` | Completed | Metadata and nationalities mapped to snake_case. |
| `races.csv` | `race_id`, `year`, `circuit_id` | Completed | Filtered strictly for Hybrid Era season boundaries (2014–2026). |
| `status.csv` | `status_id` | Completed | Categorized to separate mechanical reliability failures from crash/collision DNFs. |
| `lap_times.csv` | `race_id`, `driver_id`, `lap`, `milliseconds` | Completed | IQR outlier filtering applied to remove VSC, Safety Car, and pit lap distortions. |
| `pit_stops.csv` | `race_id`, `driver_id`, `stop`, `milliseconds` | Completed | Outlier pit durations isolated for stint pace correction. |
| `constructors.csv` | `constructor_id`, `constructor_ref` | Completed | Full rebranding lineage mapped across the Hybrid Era (e.g., Renault $\rightarrow$ Alpine, Sauber $\rightarrow$ Alfa Romeo $\rightarrow$ Stake). |

---

## 4. Completed Stage Deliverables

* **Data Cleaning & Standardization:** Ingestion scripts, snake_case headers, and constructor lineage mappings active in `src/`.
* **Pace & Outlier Cleaning:** IQR thresholding executed on lap times, reducing dataset noise variance by $\approx 6.1$.
* **Project A (Grid-to-Podium Predictor):** Exhaustive global circuit indexing complete; OLS regression models generated across all venues (Monaco $R^2 \approx 0.49$ vs. Monza $R^2 \approx 0.40$).
* **Project B (Midfield King Metric):** Mechanical DNF filtering completed; top-tier vs. midfield volatility quantified ($r_s = 0.589$ vs. $0.460$); net position gains calculated.
* **Exported Data Artifacts:** `f1_driver_pace_summary.csv`, `f1_constructor_pace_summary.csv`, `f1_grid_mobility_summary.csv`, `f1_midfield_kings_summary.csv`, and `f1_global_circuit_determinism_rankings.csv`.
* **Visualizations & Interactive Deliverables:** Performance scatter plots, driver mobility bar charts, and standalone interactive Plotly HTML dashboards (`f1_grid_determinism_professional.html`).
