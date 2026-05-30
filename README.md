# Decision-Analytics

Graduate coursework in prescriptive analytics: linear and integer optimization, transportation-style network models, sensitivity analysis, Monte Carlo simulation, metaheuristics, and Markov chain state propagation for managerial decision support.

---

## 1. Title and Summary

**Decision Analytics**  
Northwestern University M.S. in Data Science (Data Engineering specialization): formulation and solution of business optimization problems with PuLP/CBC/GLPK, stochastic simulation, and Markov chain modeling in Jupyter notebooks and standalone Python scripts.

---

## 2. Concepts and Methods

- **Linear programming (LP):** `LpProblem`, continuous decision variables, constraint formulation (`<=`, `>=`, `==`), maximize/minimize objectives; product-mix examples (tables/chairs, multi-product extensions in `Operations Analytics.ipynb`)
- **Make-or-buy / sourcing LP:** split make vs. buy decisions under capacity constraints (`Electro-Poly Analytics.ipynb`; wiring and harnessing hours, order fulfillment for three slip-ring models)
- **Staffing / resource allocation LP:** fractional FTE staffing with supervisory and ratio constraints (`Healthcare Clinic Analytics.ipynb`; minimize MD/NP/PA payroll cost subject to coverage rules)
- **Transportation / network flow LP:** bipartite supply-demand allocation with per-route profit coefficients (`Network Models.ipynb`; wine distribution across regions A1–A4 and B1–B4)
- **Integer linear programming (ILP):** binary knapsack selections with `cat='Integer'` (`Space Optimization .ipynb`, `Analytics.ipynb`)
- **Dynamic programming:** recursive 0/1 knapsack (`Analytics.ipynb`)
- **LP sensitivity analysis:** export `.lp` models; solve with GLPK `--ranges` for shadow prices and allowable ranges (`Sensitivity_Analysis.py`; theme-park shift scheduling and hot-dog blend problems)
- **Monte Carlo simulation:** uniform sampling, pi estimation via unit disk, batch replication, 95% confidence intervals (`Analytics.ipynb`)
- **Metaheuristic (simulated annealing sketch):** Metropolis acceptance criterion with cooling schedule over knapsack objective [VERIFY: function appears incomplete in notebook; confirm intended coursework deliverable]
- **Markov chains / stochastic matrices:** build country adjacency graph for South America; derive row-stochastic transition matrix from equal neighbor probabilities; propagate initial state (spy last seen in Chile) via matrix powers; visualize with NetworkX and pandas Styler heatmaps (`How to Track a Spy with Markov Chains and Stochastic Matrices .ipynb`)

**Course syllabus topics not represented in committed artifacts:** goal programming, multi-objective optimization, nonlinear programming, queuing models, decision trees, Markov decision processes [VERIFY whether covered in other coursework repos or uncommitted assignments]

**Out of scope for this repo:** deployed analytics applications (see **Analytics-Applications-Engineering**); statistical inference coursework (see **Statistics**); pure ML algorithms (see **Machine-Learning**); production ETL (see **Data-Miners**).

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
- **Engineering practice:** explicit LP formulation before solve, solver status inspection, variable/objective reporting, GLPK range files for post-optimal analysis, Monte Carlo replication with confidence intervals, graph-based construction of stochastic transition matrices

---

**Course context:** Northwestern University, M.S. in Data Science, Data Engineering specialization  
**Repository:** https://github.com/EAName/Decision-Analytics
