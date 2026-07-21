# 🚀 SpaceX Falcon 9 — First-Stage Landing Prediction

> Predicting whether the Falcon 9 first stage will land successfully — and, by extension, the true cost of a launch.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Overview

SpaceX advertises Falcon 9 launches at **\$62 million**, while other providers charge upward of **\$165 million**. Most of that saving comes from one thing: SpaceX **reuses the first stage** instead of discarding it.

That makes a single question worth a lot of money: **will the first stage land?** If we can predict the landing, we can estimate the real cost of a launch — exactly the kind of insight a competitor would need to bid intelligently against SpaceX.

This project takes the role of a data scientist at a rival company and works end-to-end: collecting the data, exploring it, mapping it, building an interactive dashboard, and training a machine-learning model to predict landing success from public information alone.

*Completed as the capstone of the [IBM Data Science Professional Certificate](https://www.coursera.org/professional-certificates/ibm-data-science).*

---

## 🎯 Objectives

- Collect Falcon 9 launch data from the **SpaceX REST API** and by **web-scraping Wikipedia**.
- Wrangle the data and engineer a **binary landing-outcome label**.
- Explore the drivers of landing success with **SQL** and **visual analytics**.
- Map launch sites and analyse their geography with **Folium**.
- Build an **interactive dashboard** with Plotly Dash.
- Train and compare **four classification models** to predict landing success.

---

## 🗂️ Repository Structure

```
SpaceX-Falcon9-Landing-Prediction/
│
├── notebooks/
│   ├── jupyter-labs-spacex-data-collection-api.ipynb   # 1 · Data collection (API)
│   ├── jupyter-labs-webscraping.ipynb                  # 2 · Data collection (web scraping)
│   ├── jupyter-labs-spacex-Data wrangling.ipynb        # 3 · Data wrangling
│   ├── jupyter-labs-EDA-sql.ipynb                       # 4 · EDA with SQL
│   ├── jupyter-labs-spacex-EDA-Visualization.ipynb     # 5 · EDA with visualization
│   ├── lab_jupyter_launch_site_location.ipynb          # 6 · Interactive maps (Folium)
│   ├── SpaceX_Machine Learning Prediction_Part_5.ipynb # 7 · Predictive modelling
│   └── spacex-dash-app.py                               #     Plotly Dash dashboard
│
├── data/                                                # Datasets used across notebooks
│
└── README.md
```

---

## 🔬 Workflow

| Stage | What happens | Tools |
|-------|--------------|-------|
| **1. Data Collection — API** | Request past-launch data from the SpaceX REST API and normalise the JSON. | `requests`, `pandas` |
| **2. Data Collection — Scraping** | Scrape the Falcon 9 launch table from Wikipedia. | `BeautifulSoup` |
| **3. Data Wrangling** | Filter to Falcon 9, handle missing values, build the binary `Class` label. | `pandas`, `numpy` |
| **4. EDA — SQL** | Query launch sites, payloads, booster versions, and outcomes. | `SQL`, `SQLite` |
| **5. EDA — Visualization** | Explore success by orbit, site, payload, and flight number. | `matplotlib`, `seaborn` |
| **6. Interactive Maps** | Plot launch sites and their proximity to coastlines, railways, and highways. | `folium` |
| **7. Prediction** | Train, tune, and compare four classifiers. | `scikit-learn` |

---

## 📊 Key Findings

- **Landing success has improved dramatically over time** — from **0% (2010–2013)** to roughly **90% (2019–2020)** — as SpaceX gained experience.
- **Orbit matters:** low-energy orbits (SSO, ES-L1, GEO) land almost every time, while heavy **GTO** missions succeed only ~52% of the time.
- **Launch site matters:** KSC LC-39A shows the highest success rate (~77%).
- **Payload matters:** heavier payloads are associated with a lower chance of a successful landing.

---

## 🤖 Predictive Modelling

Four classifiers were trained with hyperparameter tuning via `GridSearchCV`:

| Model | Test Accuracy |
|-------|:---:|
| **Decision Tree** | **~89%** |
| Logistic Regression | ~83% |
| Support Vector Machine (SVM) | ~83% |
| K-Nearest Neighbours (KNN) | ~83% |

The **Decision Tree** performed best. *Note: with only ~18 test samples, a single prediction shifts accuracy by ~5.6%, so cross-validation scores were used to confirm model ranking.*

---

## 🛠️ Tech Stack

**Language:** Python
**Data:** pandas, NumPy, SQL (SQLite)
**Visualization:** Matplotlib, Seaborn, Plotly, Folium
**Dashboard:** Plotly Dash
**Machine Learning:** scikit-learn
**Collection:** SpaceX REST API, BeautifulSoup (web scraping)

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/MohamedZaatour/SpaceX-Falcon9-Landing-Prediction.git
cd SpaceX-Falcon9-Landing-Prediction

# Install the main dependencies
pip install pandas numpy scikit-learn matplotlib seaborn folium plotly dash beautifulsoup4 requests

# Open the notebooks
jupyter notebook

# To run the interactive dashboard
python "notebooks/spacex-dash-app.py"
```

---

## 👤 Author

**Mohamed Zaatour**
Computer Science student — Big Data & Data Analysis, ISAMM

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/mohamed-zaatour-b309a7336/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?logo=github)](https://github.com/MohamedZaatour)

---

## 🙏 Acknowledgements

- **IBM** & **Coursera** for the Applied Data Science Capstone.
- **SpaceX** for making launch data publicly available.
- Rocket diagrams referenced in the course by Forest Katsch.
