# YieldCurve

[![Repo](https://img.shields.io/badge/GitHub-YieldCurve-181717?logo=github)](https://github.com/sinhaarya04/YieldCurve)

## Overview

A Python package for downloading U.S. Treasury yields from FRED, fitting yield curve models (Cubic Spline and Nelson–Siegel–Svensson), and performing comprehensive yield curve analysis.

## Features

- Exploratory analysis in Jupyter notebooks

## Tech Stack

- Python
- Jupyter

## Getting Started

### Prerequisites

- Git
- A recent runtime for the stack above (e.g., Python 3.10+ or Node 18+)

### Installation

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -e .
```

### Run / Usage

```bash
jupyter lab
```

## Project Structure

- `yieldcurve/`
- `pyproject.toml`
- `README.md`

## Roadmap

- [ ] Add clearer usage examples and expected outputs
- [ ] Add tests / CI (if applicable)
- [ ] Document data sources and assumptions (if applicable)

## License

No license file found in this repository.


---

## Notes / Original README

The content below is preserved from the previous README for reference.

# Yield Curve Analysis

A Python package for downloading U.S. Treasury yields from FRED, fitting yield curve models (Cubic Spline and Nelson–Siegel–Svensson), and performing comprehensive yield curve analysis.

## Installation

```bash
pip install yieldcurve-analysis
```

**PyPI:** https://pypi.org/project/yieldcurve-analysis/

## Quick Start

```python
from yieldcurve import get_yield_curve, fit_spline, fit_nss, plot_yield_curves

# Load current yield curve from FRED
curve = get_yield_curve()

# Fit models
spline = fit_spline(curve)
nss = fit_nss(curve)

# Plot
plot_yield_curves(curve, spline_model=spline, nss_model=nss)
```

## Features

- **Data Loading**: Fetch real-time U.S. Treasury yields from FRED (no API key required)
- **Yield Curve Models**: 
  - Cubic Spline interpolation
  - Nelson–Siegel–Svensson (NSS) parametric model
- **Visualization**: Publication-quality plots
- **Metrics**: Slope, curvature, forward rates, duration calculations

## Example Usage

```python
from yieldcurve import get_yield_curve, fit_spline, fit_nss
from yieldcurve.utils.metrics import calculate_slope, calculate_curvature

# Load and fit
curve = get_yield_curve()
spline = fit_spline(curve)
nss = fit_nss(curve)

# Calculate metrics
slope = calculate_slope(curve, short_maturity="2Y", long_maturity="10Y")
curvature = calculate_curvature(curve)

# Evaluate at specific maturity
yield_5y = spline(5.0)  # 5-year yield
```

## Documentation

See `examples/demo.ipynb` for a comprehensive walkthrough.

## Requirements

- Python 3.7+
- numpy, scipy, matplotlib, requests

## License

MIT

## Links

- **PyPI**: https://pypi.org/project/yieldcurve-analysis/
- **GitHub**: https://github.com/sinhaarya04/YieldCurve
