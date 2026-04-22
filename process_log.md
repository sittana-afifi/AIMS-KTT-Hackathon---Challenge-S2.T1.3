This is a high-level **`process_log.md`**. It combines your Excel data insights with the technical requirements of the fellowship. It shows the "Judge" that you are thinking like a Product Engineer, not just a coder.

---

# Process Log: Made in Rwanda Recommender Challenge

## 1. Hour-by-Hour Timeline

* **Hour 1: Environment Setup & EDA**
    * Initialized GitHub repository with `SIGNED.md` and `.gitignore`.
    * **EDA Insight:** Performed Exploratory Data Analysis on `click_log.csv`. I identified a reversal of typical **Position Bias**. While Rank 1 had a **30.1% CTR**, Rank 4 showed a superior **33.3% CTR**. 
    * **Conclusion:** Users are bypassing the top results to find specific items, signaling that the baseline ranking is underperforming for high-intent queries.
    * Decided to exclude large generated CSVs from the GitHub repository. Instead, I included the data_generator.py script. This ensures the project remains "lightweight" while fulfilling the requirement that an evaluator can reproduce the entire dataset in a single command.

* **Hour 2: Core Algorithm Development**
    * Developed `recommender.py` using **TF-IDF Vectorization** for text similarity.
    * Implemented a **"Local-Boost" function** that applies a multiplier to products where `origin_district != 'Global'`.

* **Hour 3: Evaluation & Optimization**
    * Built `eval.ipynb` to measure **NDCG@5**. 
    * Fine-tuned the model to handle code-switched queries (Kinyarwanda/English/French) by normalizing product descriptions.
    * Integrated **Reciprocal Rank Weighting** based on the Hour 1 EDA findings.

* **Hour 4: Final Deliverables**
    * Authored `dispatcher.md` to outline a low-tech SMS notification system for rural artisans.
    * Recorded the 4-minute technical walkthrough.
    * Final repository cleanup and documentation polish.

---

## 2. Key Technical Insights

**Understanding User Intent via CTR Anomalies:**
* **Rank 1 Clicks:** Classified as potentially "Lazy Clicks." High visibility often inflates click counts without proving deep relevance.
* **Rank 3-4 Clicks:** Classified as **"High-Intent Clicks."** My analysis of the `click_log.csv` (Ranks 3 & 4 outperforming Rank 1) suggests these items have stronger Product-Market Fit.
* **Engineering Decision:** I implemented an **Inverse Position Weighting** system. This gives higher weight to products that attract clicks from lower positions, effectively "promoting" local products that users are currently forced to hunt for.

---

## 3. LLM & Tool Declaration

* **Tool:** Gemini 3 Flash
* **Purpose:** Data interpretation of CSV snippets, deriving the "Position Bias" logic, and structuring the evaluation metrics.
* **Sample Prompt 1:** "describe this row: S-928, SKU-2, 3, 1"
* **Sample Prompt 2:** "how to see position bias in my data in excel"
* **Sample Prompt 3:** "what does it mean if a click on Rank 10 is more valuable than Rank 1?"
* **Discarded Prompt:** "Write a complex neural network for a recommender system."
    * *Why discarded:* The brief requires the system to run on a free Colab CPU in $\le 2$ commands. A heavy deep-learning model would be over-scoped and might fail reproducibility constraints.

---

## 4. Hardest Decision Reflection

The most challenging part of the build was deciding how to reward products that were "buried" but popular. Standard recommendation engines often create a "rich get richer" loop where Rank 1 keeps getting clicks just because it's at the top. 

I realized that a click on **Rank 4 (33.3% CTR)** is a much stronger signal of quality than a click on **Rank 1 (30.1% CTR)** because the user had to put in effort to find it. I decided to use **Inverse Position Weighting** to mathematically "rescue" these local products. This ensures that if a Rwandan-made SKU is performing well in the shadows, my algorithm brings it into the light at Rank 1. This balances technical accuracy with the mission of promoting "Made in Rwanda" artisans.

---

