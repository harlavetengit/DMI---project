# Chaos Theory & Weather Forecasting — A Lorenz System Analysis

Exploring the mathematical foundation of forecast uncertainty using the Lorenz attractor and real DMI weather data.

**Author:** Maria Helena

---

## Background

In 1963, mathematician and meteorologist Edward Lorenz published a simplified model of atmospheric convection — a system of just three coupled differential equations. While running weather simulations, he discovered that rounding a starting value from six decimal places to three produced a completely different forecast. This was the discovery of **chaos theory**.

The implications for meteorology are profound: weather forecasting is not limited by the quality of our models, but by a fundamental property of the atmosphere itself. Small errors in initial conditions grow exponentially, setting a hard physical limit on how far ahead we can reliably forecast.

---

## The Lorenz System

The system is defined by three coupled differential equations:

```
dx/dt = σ(y - x)
dy/dt = x(ρ - z) - y  
dz/dt = xy - βz
```

With classic parameters:
- **σ = 10** (Prandtl number — fluid mixing rate)
- **ρ = 28** (Rayleigh number — temperature difference driving convection)
- **β = 8/3** (geometric factor)

---

## What This Notebook Demonstrates

### 1. The Lorenz Attractor
Numerical integration of the Lorenz system using `scipy.integrate.solve_ivp`, visualised as a 3D trajectory. The resulting butterfly-shaped **strange attractor** shows a system that is deterministic yet never repeats the same path — a hallmark of chaos.

### 2. Sensitive Dependence on Initial Conditions
Two simulations are run with starting conditions differing by just **0.0001** in x. The distance between the two trajectories is tracked over time and plotted on a log scale, revealing:

- An initial period of near-identical behaviour
- Exponential divergence (visible as a straight line on the log scale)
- Saturation — the two trajectories are now completely uncorrelated

This divergence point is directly analogous to the **forecast horizon** in operational meteorology.

---

## Requirements

```
numpy
scipy
matplotlib
```

Install with:

```bash
pip install numpy scipy matplotlib
```

---

## How to Run

1. Clone the repository
2. Create and activate a virtual environment
3. Install the requirements
4. Open `lorenz_analysis.ipynb` in VS Code or Jupyter
5. Run all cells

---

## Key Takeaway

The Lorenz system demonstrates that **chaos is not a modelling failure — it is a physical reality**. Understanding this is fundamental to interpreting ensemble forecasts, communicating forecast uncertainty, and knowing when to trust a model.

---

## Next Steps

- Phase space reconstruction of real DMI temperature data using Takens' embedding theorem
- Estimation of the Lyapunov exponent from observed data — a direct measure of how chaotic a real atmospheric signal is

---

## References

- Lorenz, E. N. (1963). *Deterministic Nonperiodic Flow*. Journal of Atmospheric Sciences, 20(2), 130–141.
- DMI Open Data API: https://opendataapi.dmi.dk

---

## License

MIT
