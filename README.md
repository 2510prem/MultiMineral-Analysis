# Multimineral Analysis Using Well Logs

## Overview

This project performs multimineral analysis of carbonate reservoir formations using density (RHOB), neutron porosity (NPHI), and photoelectric factor (PEF) well logs. A constrained nonlinear optimization approach is employed to estimate the volumetric fractions of calcite, dolomite, pyrite, and effective porosity while satisfying the mineral volume closure constraint.

The workflow demonstrates the application of optimization techniques in petrophysical evaluation for reservoir characterization.

---

## Objectives

- Perform shale correction on well log measurements.
- Estimate mineral volume fractions using constrained optimization.
- Predict well log responses from the estimated mineral composition.
- Evaluate inversion quality using RMSE and volume closure.
- Visualize mineral composition and porosity profiles.

---

## Methodology

The workflow consists of the following steps:

1. Import and preprocess well log data.
2. Apply shale correction to RHOB, NPHI, and PEF logs.
3. Define mineral end-member properties.
4. Formulate an optimization problem to minimize the mismatch between observed and predicted log responses.
5. Enforce the mineral volume closure constraint.
6. Estimate:
   - Calcite Volume
   - Dolomite Volume
   - Pyrite Volume
   - Effective Porosity
7. Evaluate inversion quality using:
   - Root Mean Square Error (RMSE)
   - Volume Closure
8. Export results and generate visualizations.

---

## Mathematical Formulation

The optimization minimizes the difference between measured and predicted log responses:

\[
\min \sum (L_{observed}-L_{predicted})^2
\]

subject to

\[
V_{Calcite}+V_{Dolomite}+V_{Pyrite}+\phi=1
\]

where

- \(V_{Calcite}\) = Calcite volume fraction
- \(V_{Dolomite}\) = Dolomite volume fraction
- \(V_{Pyrite}\) = Pyrite volume fraction
- \(\phi\) = Effective porosity

---

## Project Structure

```
MultiMineral-Analysis/
│
├── Multi_Mineral_Analysis.ipynb
├── well_logs.csv
├── outputs/
│   ├── multimineral_analysis_results.csv
│   ├── volume_closure.png
│   ├── rmse.png
│   ├── mineral_composition.png
│   ├── porosity.png
│   └── log_matching.png
│
├── README.md
└── requirements.txt
```

---

## Technologies Used

- Python
- NumPy
- Pandas
- SciPy
- Matplotlib
- Jupyter Notebook

---

## Input Data

The analysis requires a CSV file containing the following well logs:

| Column | Description |
|---------|-------------|
| Depth | Measured depth |
| RHOB | Bulk Density |
| NPHI | Neutron Porosity |
| PEF | Photoelectric Factor |
| Vsh | Shale Volume |

---

## Output

The project generates:

- Estimated Calcite Volume
- Estimated Dolomite Volume
- Estimated Pyrite Volume
- Effective Porosity
- Bulk Porosity
- Volume Closure
- RMSE
- Predicted Well Log Responses

---

## Visualizations

The notebook automatically generates:

- Mineral Volume Closure
- Optimization Error (RMSE)
- Estimated Mineral Composition
- Porosity Profile
- Measured vs Predicted Well Logs

All plots are exported to the `outputs` directory.

---

## Installation

Clone the repository

```bash
git clone https://github.com/<your-username>/MultiMineral-Analysis.git
```

Install the required libraries

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook

```bash
jupyter notebook
```

Run all notebook cells.

---

## Future Improvements

- Incorporation of additional minerals such as quartz and clay.
- Integration of resistivity and sonic logs.
- Uncertainty analysis using Monte Carlo simulation.
- Interactive visualization using Plotly.
- Extension to machine learning-assisted multimineral prediction.

---

## Author

**Prem Kumar Singh**

B.Tech Petroleum Engineering  
Indian Institute of Technology (ISM) Dhanbad
