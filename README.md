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
