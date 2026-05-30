# Decision-Analytics

Graduate coursework in advanced analytics for managerial decision-making: predictive simulation and stochastic modeling (Monte Carlo, Markov chains) alongside prescriptive optimization (LP/ILP, network flow, dynamic programming, sensitivity analysis, metaheuristics).

---

## 1. Title and Summary

**Decision Analytics**  
Northwestern University M.S. in Data Science (Data Engineering specialization): advanced analytics from uncertainty modeling and state propagation through business optimization formulation and solution with PuLP/CBC/GLPK in Jupyter notebooks and standalone Python scripts.

---

## 2. Concepts and Methods

- **Predictive simulation (Monte Carlo):** uniform sampling, pi estimation via unit disk, batch replication, 95% confidence intervals (`Analytics.ipynb`)
- **Stochastic modeling (Markov chains):** build country adjacency graph for South America; derive row-stochastic transition matrix from equal neighbor probabilities; propagate initial state (spy last seen in Chile) via matrix powers; visualize with NetworkX and pandas Styler heatmaps (`How to Track a Spy with Markov Chains and Stochastic Matrices .ipynb`)
- **Linear programming (LP):** `LpProblem`, continuous decision variables, constraint formulation (`<=`, `>=`, `==`), maximize/minimize objectives; product-mix examples (tables/chairs, multi-product extensions in `Operations Analytics.ipynb`)
- **Make-or-buy / sourcing LP:** split make vs. buy decisions under capacity constraints (`Electro-Poly Analytics.ipynb`; wiring and harnessing hours, order fulfillment for three slip-ring models)
- **Staffing / resource allocation LP:** fractional FTE staffing with supervisory and ratio constraints (`Healthcare Clinic Analytics.ipynb`; minimize MD/NP/PA payroll cost subject to coverage rules)
- **Transportation / network flow LP:** bipartite supply-demand allocation with per-route profit coefficients (`Network Models.ipynb`; wine distribution across regions A1–A4 and B1–B4)
- **Integer linear programming (ILP):** binary knapsack selections with `cat='Integer'` (`Space Optimization .ipynb`, `Analytics.ipynb`)
- **Dynamic programming:** recursive 0/1 knapsack (`Analytics.ipynb`)
- **LP sensitivity analysis:** export `.lp` models; solve with GLPK `--ranges` for shadow prices and allowable ranges (`Sensitivity_Analysis.py`; theme-park shift scheduling and hot-dog blend problems)
- **Metaheuristic (simulated annealing sketch):** Metropolis acceptance criterion with cooling schedule over knapsack objective

---

## 3. Stack

| Layer | Tools |
|-------|-------|
| Language | Python 3 |
| Environment | Jupyter Notebook |
| Optimization | PuLP, CBC MILP solver, GLPK (sensitivity ranges) |
| Simulation / numerics | NumPy, `random`, `scipy.stats.norm` |
| Data / viz | pandas, matplotlib, seaborn |
| Graph / Markov | NetworkX (adjacency graph, layout, edge labels) |
| Scripts | `Sensitivity_Analysis.py` (standalone LP + GLPK sensitivity) |

---

## 4. Structure

```
Decision-Analytics/
├── Operations Analytics.ipynb
├── Electro-Poly Analytics.ipynb
├── Healthcare Clinic Analytics.ipynb
├── Network Models.ipynb
├── Space Optimization .ipynb
├── Analytics.ipynb
├── How to Track a Spy with Markov Chains and Stochastic Matrices .ipynb
├── Sensitivity_Analysis.py
└── README.md
```

- **Organization:** one notebook per business case or method cluster; sensitivity analysis extracted to a runnable `.py` script
- **Reusable modules:** none; LP and simulation helpers defined inline per assignment
- **Engineering practice:** explicit problem framing before modeling; Monte Carlo replication with confidence intervals; graph-based stochastic transition matrices; explicit LP formulation before solve; solver status inspection; GLPK range files for post-optimal sensitivity analysis

---

**Course context:** Northwestern University, M.S. in Data Science, Data Engineering specialization  
**Repository:** https://github.com/EAName/Decision-Analytics
