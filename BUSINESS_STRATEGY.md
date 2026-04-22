# 📈 Business Strategy: Project Inkunga (The Nyamirambo Pilot)

## 1. The Ground Reality & Problem Statement
While the recommendation engine identifies high-intent matches, the **"Digital Last Mile"** in Rwanda presents unique barriers to local artisans:
* **Connectivity:** Master artisans in markets like Nyamirambo or Kimironko often face intermittent 4G access.
* **Device Gap:** Many rural and semi-urban artisans utilize feature phones rather than smartphones.
* **The "Discovery" Gap:** As identified in our EDA, local products are buried (+0.146 rank gap) despite high user intent (+0.35% CTR spike at Rank 4).

## 2. The Solution: USSD & Telecom Collaboration
To bridge the digital divide, we leverage a **Telecom-Integrated Workflow** (Partnering with providers like MTN or Airtel-Tigo).

### **The Artisan Command Center (*154#)**
Instead of a data-heavy app, artisans interact with the search engine via a zero-rated USSD menu:
1. **Real-Time Leads:** When the Recommender places an artisan's product at Rank 1 for a high-intent query, the artisan receives a "Flash SMS."
2. **Management Menu:** By dialing `*154#`, the artisan can:
    * **Check Intent:** "15 people searched for your leather boots today."
    * **Update Stock:** Toggle items as 'Available' or 'Sold Out' instantly.
    * **Mobile Money:** Receive deposits and payments directly through the USSD interface.

## 3. 3-Month Pilot Implementation
**Scope:** 20 Artisans (Leatherworkers and Weavers) in the Kigali district.

### **Back-of-Envelope Unit Economics**
| Item | Cost (RWF) | Cost (USD) | Frequency |
| :--- | :--- | :--- | :--- |
| **Artisan Onboarding** | 20,000 RWF | ~$15 | One-time (Metadata & Photos) |
| **USSD Session Cost** | 0 RWF | $0.00 | Zero-rated via Telco Partnership |
| **Cost Per Lead (SMS)** | 270 RWF | $0.20 | Per high-intent match notification |
| **Agent Stipend** | 135,000 RWF | $100 | Monthly (Cooperative Manager) |

**Break-Even Analysis:**
* **Revenue Model:** 10% Platform Commission on facilitated sales.
* **Break-even GMV:** The pilot sustains itself when total sales reach **$10,000 USD** over 3 months.
* **Individual Goal:** Each artisan needs to move approximately **$160 USD** of inventory monthly.

## 4. Operational Workflow: "The Human-in-the-Loop"
1. **The Lead:** A customer searches for "Leather boots." The algorithm (1.2x Boost) puts a Nyamirambo artisan at Rank 1.
2. **The Notification:** The artisan receives a USSD/SMS alert: *"High interest in your boots. Press 1 to confirm availability."*
3. **The Facilitation:** If confirmed, a **Local Cooperative Agent (LCA)** assists with the physical logistics and quality check.
4. **The Sale:** Payment is processed via MoMo, and the artisan's "Reliability Score" increases in the database.

## 5. Ethical Fairness & Scalability
To prevent market monopoly, we have implemented a **15% Fairness Cap**:
* No single artisan can occupy more than 15% of the Top-10 slots in a 24-hour period.
* This ensures that as the "Made in Rwanda" initiative grows, wealth is distributed across multiple cooperatives rather than a few "top-rated" sellers.

---
*Prepared for the Fellowship Hackathon - Bridging Data Science and Grassroots Economic Growth.*
