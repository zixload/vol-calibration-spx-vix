# Calibration of SABR and Heston Models on SPX and VIX Options

## Overview

Comparison of SABR and Heston stochastic volatility models calibrated on real SPX and VIX out-of-the-money call options. Each model is tested under a standard (SPX-only) and a joint (SPX + VIX) calibration. The analysis is based on a fixed market snapshot dated 2026-04-09, stored in `data/` for full reproducibility.

## Results summary

| Model | RMSE SPX (pp) | RMSE VIX (pp) |
|---|:---:|:---:|
| SABR Standard | 0.429 | 117.051 |
| SABR Joint | 0.890 | 14.690 |
| Heston Standard | 1.067 | 57.746 |
| Heston Joint | 1.029 | 15.577 |

Standard SABR gives the best SPX fit. Joint Heston offers the best overall compromise between SPX and VIX accuracy, and is 14x faster than joint SABR thanks to an analytical VIX pricing relation.

## Setup

```bash
git clone https://github.com/<your-username>/vol-calibration-spx-vix.git
cd vol-calibration-spx-vix
pip install -r requirements.txt
jupyter notebook notebook.ipynb
```

## Structure

```
├── notebook.ipynb
├── data/
│   └── market_snapshot_2026-04-09.csv
├── report/
│   └── report.pdf
└── requirements.txt
```

## References

- Hagan et al. (2002). Managing smile risk. The Best of Wilmott.
- Heston (1993). A closed-form solution for options with stochastic volatility. RFS.
- Andersen (2007). Efficient Simulation of the Heston Stochastic Volatility Model. SSRN 946405.


