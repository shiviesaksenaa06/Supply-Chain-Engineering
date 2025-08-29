# Supply-Chain-Engineering
Optimized AppliChem’s global supply chain strategy using Mixed-Integer Linear Programming (MILP) in Python with Gurobi. Modeled 6-year production plans across 6 plants, accounting for costs, tariffs, exchange rates, and CO₂ emissions. Delivered insights on plant selection, cost reduction, and sustainable long-term operations.

# 🌍 Supply Chain Optimization Case Study: AppliChem Global Strategy  

📘 **Course:** IE 7200 – Supply Chain Engineering  
👨‍🏫 **Professor:** Paul Pei  
👩‍💻 **Team Members:** Sakshi Agarwal · Shivie Saksenaa · Neha Patil  

---

## 🚀 Project Overview  
Applichem, a global chemical manufacturer, faces **rising costs** and **environmental pressures** in its plant network.  
We built a **Mixed-Integer Linear Programming (MILP)** model in **Python (Gurobi solver)** to optimize global production of *“Release-ease”* over a **6-year horizon (1982–1987)**.  

Key features of our model:  
- ✅ Considers **inflation, exchange rates, tariffs, transport costs**  
- ✅ Accounts for **startup/shutdown penalties**  
- ✅ Integrates **CO₂ emission constraints**  
- ✅ Provides **strategic plant selection & production allocation**  

---

## 📊 Data Inputs  
We engineered data from case study files, including:  
- Local production costs (per lb, 1982 baseline)  
- Country-specific **inflation & FX adjustments**  
- Tariff schedules by plant/year  
- Transportation cost per lb  
- Plant capacity limits (M lbs)  
- Global demand forecasts (1982–1987)  
- Plant-specific CO₂ emission factors  

**Assumptions:**  
- Costs converted to USD  
- Startup penalties discourage short-term opportunism  
- CO₂ costs applied as sustainability incentives  

---

## 🧮 Optimization Model  

### Model 1 – Cost + Emissions + Operations Penalty
\[
\text{Minimize: } \sum (C_{pt} \cdot x_{pt} + \lambda \cdot CO2_p \cdot x_{pt} + \alpha \cdot y_{pt})
\]

### Model 2 – Adds Startup Cost Penalty
\[
+ \sum \beta \cdot startup_p
\]

**Constraints:**  
- Meet annual global demand  
- Respect plant capacity  
- At least 2 plants active per year  
- At least 1 plant active in the Americas each year  
- Startup triggered if plant becomes active  

---

## 🛠️ Implementation Stack  
- **Python 3.10**  
- **Gurobi 12.0.1** (MILP solver)  
- **Jupyter Notebook** (experiments & reporting)  
- **Plotly + Pandas** (visualizations)  
- **Custom dashboard** for scenario exploration  

---

## 📈 Results  

**Baseline (No Startup Cost):**  
- Total Cost: **$780.88M**  
- Plants: Frankfurt, Gary, Mexico active; Canada used only in 1987  
- Excluded: Venezuela & Sunchem (too costly & high emissions)  

**With Startup Cost:**  
- Total Cost: **$792.88M**  
- Same plants as baseline  
- Greater **stability & realistic long-term strategy**  

---

## 💡 Managerial Insights  
- **Frankfurt** = Core hub (low cost, low emissions)  
- **Gary (USA)** = Strong supplementary site (low transport, tariff-free)  
- **Mexico** = Growing competitiveness (FX + tariff benefits)  
- **Canada** = Backup for peak demand  
- **Venezuela & Sunchem** = Inefficient → excluded  

**Conclusion:** Adding startup costs slightly increases total cost but leads to **sustainable, stable operations**.  

---

## 🔮 Future Work  
- Add **global CO₂ emission caps**  
- Model **plant expansion or new facilities**  
- Extend to **warehousing & multi-echelon transport**  

**Extra data needed:**  
- Freight rates & lead times  
- Plant downtime schedules  
- Tax & incentive policies  

---

## 📌 Key Takeaways  
Our optimization framework demonstrates how **MILP + real-world economics** can:  
- Balance **cost, environment, and policy**  
- Provide **data-driven, actionable insights**  
- Support **long-term strategic planning** in global supply chains  

---
