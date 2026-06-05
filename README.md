# 🎬 Amazon Prime Video — Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-EDA-green?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![AlmaBetter](https://img.shields.io/badge/AlmaBetter-Capstone%20Project-red)

> **A comprehensive Exploratory Data Analysis on Amazon Prime Video's U.S. content library — uncovering trends in content type, genres, ratings, regional production, and key talent.**

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Business Objective](#-business-objective)
- [Dataset Description](#-dataset-description)
- [Project Architecture](#-project-architecture)
- [Libraries Used](#-libraries-used)
- [Key Visualizations](#-key-visualizations)
- [Insights & Findings](#-insights--findings)
- [Business Recommendations](#-business-recommendations)
- [How to Run](#-how-to-run)
- [Project Structure](#-project-structure)
- [Author](#-author)

---

## 📖 Project Overview

Amazon Prime Video is one of the world's leading streaming platforms, competing with Netflix, Disney+, and others. This project performs a full **Exploratory Data Analysis (EDA)** on its U.S. catalog using two datasets containing **9,871 titles** and **124,235 cast/crew records**.

The analysis answers critical business questions around content diversity, growth trends, quality signals, regional production, and key contributors — translating raw data into actionable strategy.

---

## 🎯 Business Objective

To analyze all shows and movies available on Amazon Prime Video and extract insights around:

- **Content Diversity** — What genres and content types dominate the platform?
- **Trends Over Time** — How has the content library evolved across release years?
- **Quality Signals** — What do IMDb and TMDb ratings reveal about content quality?
- **Talent Analysis** — Who are the most featured actors and directors?
- **Regional Patterns** — Which countries contribute the most content?

These insights support **content strategists**, **marketing teams**, and **investors** in making data-driven decisions.

---

## 📂 Dataset Description

This dataset was sourced from [JustWatch](https://www.justwatch.com/) and contains U.S. Amazon Prime Video data.

### `titles.csv` — 9,871 rows × 15 columns

| Column | Type | Description |
|---|---|---|
| `id` | str | Unique title ID on JustWatch |
| `title` | str | Name of the movie or show |
| `type` | str | MOVIE or SHOW |
| `description` | str | Short plot summary |
| `release_year` | int | Year of original release |
| `age_certification` | str | Age rating (R, PG-13, TV-MA, etc.) |
| `runtime` | int | Duration in minutes |
| `genres` | str | List of genres (string format) |
| `production_countries` | str | List of country codes (string format) |
| `seasons` | float | Number of seasons (shows only) |
| `imdb_id` | str | IMDb title identifier |
| `imdb_score` | float | IMDb rating (0-10) |
| `imdb_votes` | float | Number of IMDb votes |
| `tmdb_popularity` | float | TMDb popularity score |
| `tmdb_score` | float | TMDb rating (0-10) |

### `credits.csv` — 124,235 rows × 5 columns

| Column | Type | Description |
|---|---|---|
| `person_id` | int | Unique person ID on JustWatch |
| `id` | str | Title ID (links to titles.csv) |
| `name` | str | Actor or director name |
| `character` | str | Character name (actors only) |
| `role` | str | ACTOR or DIRECTOR |

---

## 🏗️ Project Architecture

```
Problem Understanding
        ↓
Data Loading & First Look
        ↓
Data Cleaning & Wrangling
        ↓
Exploratory Data Analysis (15 Charts)
        ↓
Business Insights & Recommendations
```

---

## 📚 Libraries Used

```python
import numpy as np               # Numerical operations
import pandas as pd              # Data manipulation & aggregation
import matplotlib.pyplot as plt  # Base visualizations
import seaborn as sns            # Statistical visualizations
import ast                       # Parsing string-formatted lists
```

---

## 📊 Key Visualizations

| # | Chart Type | What It Shows |
|---|---|---|
| 1 | Pie + Bar Chart | Movies vs TV Shows distribution |
| 2 | Horizontal Bar | Top 15 genres on the platform |
| 3 | Line Chart | Number of titles released per year |
| 4 | Histogram + KDE | IMDb score distribution by content type |
| 5 | Scatter + Regression | IMDb score vs TMDb score correlation |
| 6 | Box Plot | Runtime distribution by content type |
| 7 | Bar Chart | Top 10 content producing countries |
| 8 | Horizontal Bar | Top 15 most featured actors |
| 9 | Horizontal Bar | Top 15 most active directors |
| 10 | Grouped Bar | Genre split by Movies vs Shows |
| 11 | Bar Chart | Age certification distribution |
| 12 | Violin Plot | IMDb score distribution by top genres |
| 13 | Dual-axis Line+Bar | Average IMDb score vs titles per year |
| 14 | Heatmap | Correlation matrix of numerical features |
| 15 | Pair Plot | Multivariate overview of all numerical features |

---

## 💡 Insights & Findings

- **Movies dominate** (~80%) over TV Shows — Amazon is a movie-heavy platform
- **Drama and Comedy** are the top two genres by a large margin
- **Content growth peaked in 2018–2020**, then slowed post-COVID
- **TV Shows score slightly higher** on IMDb than Movies on average
- **IMDb and TMDb scores** are moderately correlated (r ≈ 0.65–0.75)
- **USA leads production** followed by India — regional investment is paying off
- **Adult content dominates** (R/TV-MA) — family-friendly content is underrepresented
- **Documentary** has the highest and most consistent IMDb scores
- **Older titles score higher** due to survivor bias
- **TMDb popularity** follows a power-law distribution

---

## 🏆 Business Recommendations

1. **Invest in TV Show Originals** — Shows drive higher retention than one-time movie watches
2. **Quality over Quantity** — Bulk acquisitions lowered average scores; prioritize quality originals
3. **Expand Regional Content** — Replicate India's success in Brazil, Southeast Asia, and Africa
4. **Add Family-Friendly Content** — Compete with Disney+ for the family subscriber segment
5. **Exclusive Talent Deals** — Lock in top directors and actors before competitors do
6. **Build a Combined Rating Score** — Blend IMDb + TMDb for better recommendations
7. **Runtime-Based UI Optimization** — Tag short content as Quick Watch to improve engagement

---

## ▶️ How to Run

### Option 1: Google Colab (Recommended)

1. Go to [colab.research.google.com](https://colab.research.google.com/)
2. Click `File → Upload Notebook` and upload `Amazon_Prime_EDA_AlmaBetter.ipynb`
3. Upload `titles.csv` and `credits.csv` via the folder icon on the left sidebar
4. Click `Runtime → Run All`

### Option 2: Local Jupyter Notebook

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/amazon-prime-eda.git
cd amazon-prime-eda

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch Jupyter
jupyter notebook Amazon_Prime_EDA_AlmaBetter.ipynb
```

---

## 📁 Project Structure

```
amazon-prime-eda/
│
├── Amazon_Prime_EDA_AlmaBetter.ipynb   ← Main notebook (all code + analysis)
├── titles.csv                          ← Dataset 1: Title metadata
├── credits.csv                         ← Dataset 2: Cast & crew records
└── README.md                           ← This file
```

---

## 👤 Author

**ALOK KHARE**

- 🎓 AlmaBetter Data Science & Machine Learning Program
- 💼 LinkedIn:
- 🐙 GitHub: https://github.com/al00kk/amazon-prime-video-eda

---

## 📃 License

This project is open source and available under the [MIT License](LICENSE).


*If you found this project helpful, please give it a ⭐ star on GitHub!*
