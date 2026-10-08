# 🏎️ F1 Performance Analytics — Predictability vs. Grit

Applying the full data analysis lifecycle to quantify how qualifying performance, circuit characteristics, and mechanical reliability shape race outcomes.

---

## 📌 Overview

This repository contains a comprehensive two-part analytical study of Formula 1 race dynamics using downloaded CSV datasets derived from historical motorsport archives. The goal is to measure how much of F1 performance is predictable (car pace, qualifying position) versus how much comes from driver grit (racecraft, overtaking, consistency).

---

## 🚥 Project Status

* **Project B — The Midfield King Metric:** Complete (Stages 1–5 executed, pure pace gaps isolated, grid mobility quantified).
* **Project A — The Grid-to-Podium Predictor:** Complete (Linear regression modeling, exhaustive global circuit indexing, and automated multi-circuit HTML visualization generation).
* **Interactive Dashboard:** Complete (Plotly standalone web deliverables and modular script exports).

---

## 🧩 Project Structure

```text
f1-performance-analytics/
├── data/                  # Raw downloaded CSVs and clean exported summary datasets
├── notebooks/             # Jupyter notebooks covering each lifecycle stage
├── src/                   # Python modules for data wrangling, metrics, and visualization
├── visuals/               # Exported figures, dashboards, and performance matrices
└── README.md              # Project documentation and summary report
