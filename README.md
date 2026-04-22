# Made in Rwanda: Niche-First Recommender System

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1GKgE703JzriXkpYKHxuXbjrZ1WD9UqXb?usp=sharing)

## 📌 Project Overview
This repository contains a specialized recommendation engine designed to prioritize local Rwandan artisans in retail search results. By leveraging **TF-IDF similarity** and **Inverse Position Weighting**, the system identifies "high-intent" local products that are often buried by global baseline algorithms.


* **Goal:** Increase visibility for Rwandan products in a global marketplace.
* **Approach:** A data-driven engine that identifies and "boosts" local products.
* **Problem:** Traditional algorithms bury high-quality local goods under global brands.

## 📊 The "Rank 4" Discovery (EDA Insight)
During Exploratory Data Analysis of the `click_log.csv`, a significant anomaly was found:
* **Rank 1 CTR:** 30.1%
* **Rank 4 CTR:** **33.3%**
* **The Insight:** Users are bypassing the first three results to find specific items at Rank 4. This "intentional clicking" proves that products at lower ranks are actually more relevant.



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
* **Nudge Factor:** A `0.2` multiplier applied to products with an `origin_district` in Rwanda.
* **Efficiency:** Optimized to run in under 30 seconds on standard CPU hardware.

---

## ⚖️ License
* **Type:** MIT License.
* **Usage:** Free for open-source development and educational purposes.
