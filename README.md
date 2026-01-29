# Hybrid AACO–SQP for Nonlinear Programming

**Adaptive Ant Colony Optimization + Sequential Quadratic Programming**  
A course project for Linear and Nonlinear Programming (Math 303) – Zewail City of Science and Technology

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Reproducibility](https://img.shields.io/badge/30_runs-seeded-blue)](https://github.com/yourusername/yourrepo)

## 📖 Overview

This repository contains the implementation and experimental evaluation of an **Adaptive Ant Colony Optimization (AACO)** algorithm for continuous-domain global search, combined in a **hybrid pipeline** with **Sequential Quadratic Programming (SQP)** for fast, high-precision local refinement.

The work addresses key limitations of continuous ACO (parameter sensitivity, discretization effects, precision plateaus) by introducing adaptive parameter scheduling and a two-phase hybrid strategy.

We compare the hybrid approach against:
- Pure AACO
- SciPy SLSQP and L-BFGS-B (random initialization)
- AACO + Projected Gradient Descent

**Key result**: The hybrid AACO–SQP achieves **~10,000× better accuracy** on Rosenbrock and **~26× better** on Rastrigin compared to standard SciPy solvers (30 independent runs).

**Authors**: Ahmed Moatasem, Ali Mohab, Assem Aldurini, Mohamed Darwish, Mohamed Tarek  
**Supervisor**: Dr. Ahmed Abdelsamea  
**Date**: December 2025

## ✨ Features

- Scratch implementation of **Adaptive ACO** with linear parameter adaptation (α, β, ρ)
- Hybrid pipeline: AACO global exploration → SciPy SLSQP local refinement
- Reproducible experiments: 30 seeded runs, convergence curves, boxplots
- Benchmark functions: 5D Rosenbrock & Rastrigin
- Exports: CSV tables, PDF/PNG plots for the course paper & presentation

## 🚀 Results Summary (from paper)

| Method                  | Rosenbrock (mean ± std) | Rastrigin (mean ± std) | Approx. Time (s) |
|-------------------------|---------------------------|--------------------------|------------------|
| Hybrid AACO + SQP       | 2.73 × 10⁻⁷ ± 1.00×10⁻⁷  | 1.23 ± 0.43             | ~1.4            |
| Hybrid AACO + PGD       | 2.00 ± 0.17              | 1.23 ± 0.43             | —               |
| Scratch AACO            | 3.97 ± 0.12              | 7.11 ± 0.06             | —               |
| SciPy SLSQP (random)    | 1.18 ± 1.83              | 32.83 ± 13.58           | ~0.01           |
| SciPy L-BFGS-B (random) | 0.92 ± 1.69              | 36.18 ± 11.52           | ~0.01           |

→ Hybrid wins in **accuracy** and **robustness** (lowest variance).

## 📂 Repository Structure
.
├── Final-Code (1).ipynb       ← Main notebook: experiments, plots, CSV export
├── math__final__project (7).pdf   ← Full project report (IEEE-style)
├── Ahmed Moatasem ... .pptx   ← Presentation slides
├── outputs/                   ← Generated plots (convergence, boxplots), CSVs
└── README.md


## 🛠️ Requirements

- Python 3.10+
- Core packages: `numpy`, `scipy`, `pandas`, `matplotlib`
- Optional (for full reproducibility): JupyterLab / VS Code

Install via pip:

```bash
pip install numpy scipy pandas matplotlib
