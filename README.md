# 🌍 Global Shocks & Inflation Dynamics Engine

An end-to-end machine learning and econometric pipeline evaluating the impact of global supply-side shocks on U.S. consumer price inflation (CPI) and industrial output.

---

## 📌 Project Overview
📊 **[View Project Presentation Deck (PDF)](./Global_Shocks_Inflation_Engine.pdf)**
Macroeconomic shocks do not transmit to consumer prices instantaneously. This project investigates the non-linear and lagged transmission mechanisms of global economic disruptions on U.S. inflation dynamics using historical monthly data from 2000 onward.

### 🔑 Key Features & Methodology
- **Data Pipeline:** Programmatically fetches real-time macroeconomic and shock data via official APIs and repositories (**FRED**, **New York Fed GSCPI**, and **Geopolitical Risk Index**).
- **Stationarity & Feature Engineering:** Converts raw price levels into Month-over-Month (MoM) growth rates to prevent spurious correlations, alongside engineered lag structures ($t-1, t-3, t-6, t-12$) and rolling window statistics (`rolling().mean()`, `rolling().std()`).
- **Machine Learning Architecture:** Trains a **Random Forest Regressor** using a chronological train-test split (`shuffle=False`) to prevent future data leakage.
- **Scenario Stress Testing:** Simulates conditional forward-looking stress scenarios (Adverse Supply Shocks vs. Disinflationary Relief) to evaluate inflation persistence and downward price rigidity.

---

## 📊 Core Findings & Scenario Simulation
1. **Delayed Transmission ($t-3$ to $t-6$):** Energy and supply chain shocks peak with a structural lag of 3 to 6 months.
2. **Stagflationary Pressure:** Adverse supply shocks drive monthly inflation to a peak of ~0.53% with persistent stickiness.
3. **Policy Implication:** Central banks must adopt proactive, scenario-driven frameworks anchored to real-time global energy and logistics indicators rather than relying solely on backward-looking trends.

---

## 💻 Tech Stack & Libraries
* **Language:** Python
* **Core Libraries:** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `shap`
* **Environment:** Google Colab / Jupyter Notebook
