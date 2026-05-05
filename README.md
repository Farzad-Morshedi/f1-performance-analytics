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

## 🧩 Project Structure

f1-performance-analytics/
|
+-- data/        # Raw & cleaned datasets (not included in repo)
+-- notebooks/   # Jupyter notebooks for each analysis stage
+-- src/         # Python modules for cleaning, modeling, metrics
+-- visuals/     # Exported charts and diagrams
`-- README.md

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
Identify drivers who consistently outperform their machinery by gaining positions relative to their qualifying pace.

**Method**  
Feature engineering, DNF filtering, and aggregated performance scoring.

**Why it matters**  
Finishing position alone hides reliability noise. Removing DNFs reveals **true overtaking efficiency**.

**Key Question**  
Which drivers gain the most positions **after removing mechanical DNFs**, and how consistent is that performance across seasons?

---

## 🛠️ Tools & Technologies

- Python (pandas, numpy, matplotlib, seaborn, scikit-learn)
- SQL (Ergast API queries)
- Jupyter Notebooks
- Custom pipelines for data cleaning, feature engineering, and modeling

---

## 📊 Planned Outputs

- Circuit-specific regression models  
- R² comparison visualizations (Monaco vs. Monza and other circuits)  
- “Midfield King” scoring table by driver and season  
- Driver consistency heatmaps  
- Reliability-adjusted overtaking metrics  
- Season-over-season trend visualizations  

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
