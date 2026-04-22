# Made in Rwanda: Niche-First Recommender System

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1GKgE703JzriXkpYKHxuXbjrZ1WD9UqXb?usp=sharing)

## 📌 Project Overview
This repository contains a specialized recommendation engine designed to prioritize local Rwandan artisans in retail search results. By leveraging **TF-IDF similarity** and **Inverse Position Weighting**, the system identifies "high-intent" local products that are often buried by global baseline algorithms.


* **Goal:** Increase visibility for Rwandan products in a global marketplace.
* **Approach:** A data-driven engine that identifies and "boosts" local products.
* **Problem:** Traditional algorithms bury high-quality local goods under global brands.


---

## 📊 The "Intent Gap" Discovery
During Exploratory Data Analysis, I identified a critical failure in the baseline ranking system:
* **Visibility Gap:** Rwandan products were buried **+0.146 positions** deeper than global brands.
* **The Rank 4 Anomaly:** While Rank 1 had a CTR of 30.1%, **Rank 4 achieved 33.3%**.
* **The Insight:** Users are intentionally bypassing the top three (global) results to find local goods. This **+0.35% Intent Gap** at Rank 4 proves that current algorithms do not align with user desires for authenticity.

## 🏆 Final Impact Evaluation
By implementing a **1.2x Local Multiplier** combined with position-bias correction:
* **Local Top-Spot Capture:** **100.0%** (Rwandan products now win the #1 spot in every category).
* **Avg Local Items in Top 5:** **4.38 / 5.0** (Balanced visibility that maintains variety).
* **Search Efficiency:** The system now correctly "nudges" local artisans to the front of the digital shelf.

---


## 🚀 Quick Start (Reproduction)
To reproduce the results on a free Google Colab CPU, follow these two steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/sittana-afifi/AIMS-KTT-Hackathon---Challenge-S2.T1.3.git
   cd AIMS-KTT-Hackathon---Challenge-S2.T1.3

---


2. **Generate Data:**
   ```bash
   python data_generator.py
  
 catalog.csv, queries.csv and click_log.csv will be created.

---


3. **Run Evaluation:**
   ```bash
   python recommender.py


to see the NDCG@5 metrics.

---


4. **One-Click Option:**
   
   Click the [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1GKgE703JzriXkpYKHxuXbjrZ1WD9UqXb?usp=sharing) This launches a hosted environment that automatically runs the data generation and evaluation pipeline.

---

## 📁 Repository Structure
* **data_generator.py:** The "reproducible recipe" that builds the project datasets.
* **recommender.py:** Core engine using TF-IDF and Local-Boost logic.
* **eval.ipynb:** Notebook visualizing the CTR anomalies and final metrics.
* **process_log.md:** Detailed log of the 4-hour build and technical decisions.
* **dispatcher.md:** Strategy for SMS-based distribution for rural artisans.
* **SIGNED.md:** Fellowship Honor Code signed by the developer.

---

## 🛠️ Technical Implementation
* **Similarity Matching:** TF-IDF Vectorization for multilingual queries (English, French, Kinyarwanda).
* **Bias Correction:** Inverse Position Weighting (treating Rank 4-10 clicks as higher value than Rank 1).
* **Nudge Factor:** A `1.2` multiplier applied to products with an `origin_district` in Rwanda.
* **Efficiency:** Optimized to run in under 30 seconds on standard CPU hardware.
* **Reproducibility:** Fully automated data pipeline ensures identical results across environments.
  
---

## ⚖️ License
* **Type:** MIT License.
* **Usage:** Free for open-source development and educational purposes.

