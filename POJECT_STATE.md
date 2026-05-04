# F1_performance_analytics: Project State

## 1. Project Lifecycle Status
*   **Current Phase:** Stage 3: **Process**
*   **Completed Phases:** 
    *   Stage 1: **Ask** (Defined "Midfield King" analysis goals).
    *   Stage 2: **Prepare** (Kaggle CSV files downloaded, data sources identified, and schema requirements established).
*   **Active Focus:** Data cleaning, schema validation, and column renaming within the local Python environment.

## 2. Technical Infrastructure & Constraints
*   **Data Source:** Local Kaggle CSV files (e.g., `results.csv`, `drivers.csv`, `races.csv`, `status.csv`).
*   **Stack:** Python (Pandas/NumPy) and SQL.
*   **Coding Standard:** 
    *   **No Method Chaining:** Break all transformations into logical, step-by-step variables.
    *   **Documentation:** Mandatory docstrings for functions; descriptive comments for every non-trivial block.
    *   **Naming Convention:** Enforce `snake_case` across all dataframes and SQL tables.

## 3. Data Schema Tracker
| File / Table | Key Columns (PK/FK) | Cleaning Status | Notes |
| :--- | :--- | :--- | :--- |
| `results.csv` | `raceId`, `driverId`, `constructorId` | Pending | Core results data for performance metrics. |
| `drivers.csv` | `driverId` | Pending | Reference for driver names and nationalities. |
| `races.csv` | `raceId`, `year` | Pending | Required for filtering specific seasons/eras. |
| `status.csv` | `statusId` | Pending | Critical for identifying DNFs vs. active finishes. |

## 4. Current Task List (Process Phase)
- [ ] Initialize Python scripts with standard headers and environment checks.
- [ ] Implement robust loading logic for Kaggle CSVs.
- [ ] Standardize column names to `snake_case`.
- [ ] Validate data types (e.g., ensuring `points` are floats and `raceId` is an integer).
- [ ] Handle null/missing values specific to F1 contexts (e.g., qualifying times for back-markers).
