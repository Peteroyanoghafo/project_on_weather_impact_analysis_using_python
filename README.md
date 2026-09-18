# Weather Impact Analysis System
**ClimateSmart Analytics Africa | Junior Data Analyst Portfolio Project**

An end-to-end, menu-driven Python analytical tool designed to evaluate weather observations across key Nigerian locations, model weather-related operational risks, and assess historical impacts on agricultural crop yield and supply chain operations.

> **Data Disclaimer:** This project utilizes a simulated educational dataset for Lagos, Kano, and Ibadan. It does not represent official Nigerian Meteorological Agency (NiMet) data and is intended solely for analytics and demonstration purposes.

---

## Project Overview

Extreme weather events present substantial risks to agricultural productivity and supply chain continuity across Sub-Saharan Africa. This system processes multi-location weather telemetry—including temperature, rainfall, humidity, and wind speed—to extract actionable insights without relying on external third-party libraries.

### Key Objectives
* **Data Summary & Exploration:** Compute high-level operational statistics, trace temporal boundaries, and log dataset parameters across regions.
* **Extreme Event Classification:** Identify acute climate stressors using threshold-based metrics ($>100\text{mm}$ rainfall, $>35^\circ\text{C}$ temperature, or $>25\text{km/h}$ wind speed).
* **Location & Regional Profiling:** Execute multi-attribute comparative analysis between major regional nodes (Lagos, Kano, Ibadan).
* **Custom Weather Risk Scoring:** Calculate composite risk scores combining precipitation intensity, heat stress, and reported operational disruptions.
* **Sensitivity & Impact Analysis:** Track weather-driven disruption frequencies and examine yield variations against climate variables.

---

## Technical Constraints & Architecture

To demonstrate core algorithmic logic, control structures, and functional design, this project was developed under explicit technical constraints:

* **Pure Python Implementation:** Built strictly using Python fundamentals.
* **Zero External Dependencies:** Native data structures (`dicts`, `lists`, `tuples`) were used exclusively—no `Pandas`, `NumPy`, `Matplotlib`, or `CSV` modules.
* **Functional Modularity:** Encapsulated analytical logic within reusable, isolated functions with strict input/output handling.

---

## Analytical Scoring & Classification Models

### 1. Rainfall Thresholds
| Rainfall Range (mm) | Classification | Score Contribution |
| :--- | :--- | :--- |
| `0` | No Rain | 0 |
| `1 – 10` | Light | 0 |
| `11 – 50` | Moderate | 1 |
| `51 – 100` | Heavy | 2 |
| `> 100` | Extreme | 4 |

### 2. Temperature Thresholds
| Temperature Range (°C) | Classification | Score Contribution |
| :--- | :--- | :--- |
| `< 25` | Cool | 0 |
| `25 – 30` | Moderate | 0 |
| `31 – 35` | Hot | 2 |
| `> 35` | Extreme Heat | 4 |

### 3. Risk Level Matrix
Composite Score = $\text{Rainfall Score} + \text{Temperature Score} + \text{Disruption Score (No = 0, Yes = 3)}$

* **0 – 2:** Low Risk
* **3 – 5:** Moderate Risk
* **6 – 8:** High Risk
* **9+:** Critical Risk

---

## Key Analytical Findings

1. **Supply Chain Disruptions:** Operational disruptions correlate strongly with high-rainfall periods ($>50\text{mm}$), indicating that severe precipitation is the primary driver of logistics delay in the sample.
2. **Thermal Stress on Crop Yield:** Northern observations (Kano) demonstrated high heat exposure ($>35^\circ\text{C}$), corresponding with lower average crop yield relative to southwestern nodes (Ibadan, Lagos).
3. **Regional Risk Leaderboard:** Risk profiles vary significantly by region—Lagos experiences higher cumulative precipitation disruption, whereas Kano exhibits elevated thermal stress risk.

---

## System Architecture & Interactive Features

The application features a terminal menu system (`run_menu()`) providing access to 12 analytical modules:

```text
============================================
 WEATHER IMPACT ANALYSIS SYSTEM
============================================
1. Dataset Summary
2. View All Records
3. Highest Temperature
4. Highest Rainfall
5. Analyse Location
6. View Extreme Events
7. Generate Risk Alert
8. Compare Locations
9. Location Leaderboard (Nested Loops)
10. Monthly Analysis
11. Recommendations
12. Exit
