# Risk, Liquidity, and the Heterogeneous Value of Medicaid  
## Evidence from the Oregon Health Insurance Experiment

This repository contains the research code and paper for the project:

> **“Risk, Liquidity, and the Heterogeneous Value of Medicaid: Evidence from the Oregon Health Insurance Experiment”**

The project develops and tests a two-channel model of the value of public health insurance and brings it to the Oregon Health Insurance Experiment using modern causal machine learning (instrumental / generalized random forests).

The paper combines a Rothschild–Stiglitz–style **risk-smoothing** channel with a Nyman-style **liquidity/access** channel and then uses instrumental forests to recover **conditional local average treatment effects (C-LATEs)** of Medicaid along continuous **risk** and **liquidity** indices.

---

## 1. Research overview

Medicaid can create welfare gains through (at least) two conceptually distinct mechanisms:

1. **Risk smoothing (Rothschild–Stiglitz channel)**  
   For risk-averse but liquidity-unconstrained households, Medicaid reduces the dispersion of consumption across health states by insuring against high medical spending shocks.

2. **Liquidity / access value (Nyman channel)**  
   For liquidity-constrained households, Medicaid relaxes binding budget constraints, enabling access to necessary care and reducing medical debt and collections.

This project:

- Builds a **unified microeconomic model** in which both channels arise from a single framework.
- Constructs **empirical proxies** for ex-ante health risk and financial liquidity at baseline using the OHIE microdata.
- Uses the randomized Medicaid lottery as an instrument and applies **instrumental forests / generalized random forests** to estimate **C-LATEs** of Medicaid on financial outcomes (e.g., any medical debt/collections at 12 months) across the joint distribution of risk and liquidity.
- Maps the resulting heterogeneity back to the theory to interpret which channel (risk vs. liquidity) is doing the work and for whom.

---

## 2. Repository structure

The repository is organized as follows:

- `Code/`  
  Jupyter notebooks implementing the empirical pipeline, including:
  - Data cleaning, merging, and construction of baseline variables.
  - Construction of risk and liquidity indices.
  - Econometric checks (balance, first stage, attrition).
  - Causal ML estimation (instrumental forests / C-LATEs).
  - Export of tables and figures used in the paper.

- `Output/`  
  Exported tables and figures produced by the notebooks. This is where regression tables, diagnostic plots, and main figures for the paper are saved.

- `Paper/`  
  Compiled PDF of the paper, including theory, empirical strategy, results, and robustness checks.

> Note: The OHIE microdata are **not included** in this repository due to data-use restrictions, but you can access the OHIE data from NBER via the Oregon Health Insurance Experiment page:  
   https://www.nber.org/programs-projects/projects-and-centers/oregon-health-insurance-experiment

---

## 3. Software and environment

The empirical analysis is implemented in **Python** using **Jupyter notebooks**.

A typical environment includes:

- Python ≥ 3.9
- Core scientific stack:
  - `numpy`
  - `pandas`
  - `scipy`
  - `statsmodels`
  - `scikit-learn`
- Causal ML:
  - `econml` (for instrumental / generalized random forests)
- Plotting and reporting:
  - `matplotlib`
  - `seaborn`
- Notebook environment:
  - `jupyter` / `jupyterlab`

A minimal setup using `pip` might look like:

```bash
pip install numpy pandas scipy statsmodels scikit-learn matplotlib seaborn econml jupyter
```
## 4. Clone

To clone this repository:

```bash
git clone https://github.com/Suzanna-Ayash/OHIE_Causal_ML.git
cd OHIE_Causal_ML
```
