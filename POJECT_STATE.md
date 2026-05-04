# F1_performance_analytics: Project State

## 1. Project Lifecycle Status
*   **Current Phase:** Stage 3: **Process**
*   **Completed Phases:** 
    *   Stage 1: **Ask** (Defined "Midfield King" analysis goals and performance metrics).
    *   Stage 2: **Prepare** (Kaggle CSV files downloaded and local directory structure verified).
*   **Active Focus:** Data cleaning, lineage mapping for constructors, and outlier detection logic for lap times.

## 2. Technical Infrastructure & Constraints
*   **Data Source:** Local Kaggle CSV files.
*   **Stack:** Python (Pandas/NumPy) and SQL.
*   **Coding Standard:** 
    *   **No Method Chaining:** Break all transformations into logical, step-by-step variables for easier auditing.
    *   **Documentation:** Mandatory docstrings for all functions; descriptive comments for every code block explaining the "why."
    *   **Naming Convention:** Strict `snake_case` for all dataframes, columns, and SQL tables.

## 3. Data Schema Tracker
| File / Table | Key Columns (PK/FK) | Cleaning Status | Notes |
| :--- | :--- | :--- | :--- |
| `results.csv` | `raceId`, `driverId`, `constructorId` | Pending | Core outcomes and finishing positions. |
| `drivers.csv` | `driverId` | Pending | Driver metadata (names, codes, nationality). |
| `races.csv` | `raceId`, `year` | Pending | Required for season filtering and era analysis. |
| `status.csv` | `statusId` | Pending | Used to filter DNFs (Mechanical vs. Accident). |
| `lap_times.csv` | `raceId`, `driverId`, `lap` | Pending | Granular pace data; requires IQR outlier detection. |
| `pit_stops.csv` | `raceId`, `driverId`, `stop` | Pending | Analyzing stop durations and strategy impact. |
| `constructors.csv`| `constructorId` | Pending | Requires mapping for rebranding (e.g., Renault → Alpine). |

## 4. Current Task List (Process Phase)
- [ ] **Data Loading:** Build modular Python scripts to load CSVs into memory.
- [ ] **Standardization:** Rename all Kaggle headers to consistent `snake_case`.
- [ ] **Constructor Lineage:** Create a mapping dictionary to handle team name changes over the Hybrid Era.
- [ ] **Pace Cleaning:** Implement IQR (Interquartile Range) logic to remove lap time outliers (VSCs, Red Flags).
- [ ] **Type Validation:** Ensure numeric columns (milliseconds, points, years) are correctly typed.
