# Phase Space Reconstruction of Atmospheric Temperature Data

Applying dynamical systems theory to real meteorological observations from the Danish Meteorological Institute (DMI) — reconstructing the attractor of the Copenhagen atmosphere from a single observed variable.

**Author:** Maria Helena

---

## Background

In [lorenz-analysis](../project_2_Lorentz/), we demonstrated that a simple three-equation model of atmospheric convection produces chaotic behaviour — deterministic yet unpredictable, with trajectories that diverge exponentially from nearly identical starting points.

But that was a simulation. The question this project asks is:

> *Can we find similar structure in real atmospheric data?*

The answer comes from **Takens' embedding theorem (1981)**, which states that the attractor of a dynamical system can be reconstructed from a single observed time series by plotting the signal against time-delayed copies of itself. No knowledge of the underlying equations is required — just the data.

---

## Data Source

Data is retrieved from [DMI Open Data](https://opendataapi.dmi.dk) — a free, publicly available API provided by Danmarks Meteorologiske Institut.

**Station:** Copenhagen (station ID `06180`)  
**Parameter:** Dry bulb temperature (`temp_dry`)  
**Period:** June–August 2024 (Copenhagen summer)  
**Resolution:** 10-minute observations, resampled to hourly averages

---

## What This Notebook Does

### 1. Data Fetching & Preprocessing
Hourly temperature observations are fetched from the DMI API and resampled into a clean time series using pandas.

### 2. Autocorrelation Analysis
The autocorrelation function is computed to determine the optimal time delay τ for phase space reconstruction. The first zero crossing of the autocorrelation gives the lag at which `T(t)` and `T(t + τ)` are maximally independent — essential for unfolding the attractor without redundancy.

For Copenhagen summer 2024, the autocorrelation reveals:
- A **first zero crossing at τ = 6 hours** — our embedding lag
- A strong **24-hour periodicity** — the daily heating and cooling cycle clearly visible in the data

### 3. Phase Space Reconstruction (2D & 3D)
Using Takens' embedding theorem, the attractor is reconstructed by plotting:
- **2D:** `T(t)` vs `T(t + 6h)`
- **3D:** `T(t)` vs `T(t + 6h)` vs `T(t + 12h)`

The resulting structure is neither a clean loop (which would indicate a purely periodic system) nor uniform random scatter (which would indicate pure noise) — it is a structured, bounded, non-repeating trajectory: the hallmark of a **chaotic attractor**.

---

## Key Finding

The reconstructed attractor of Copenhagen summer temperature has clear geometric structure, consistent with a low-dimensional chaotic system. This is direct empirical evidence that atmospheric variability is not random — it is deterministic chaos, governed by the same mathematical principles demonstrated in the Lorenz system.

This is why ensemble forecasting exists: not because our models are imperfect, but because the atmosphere itself amplifies small uncertainties exponentially.

---

## Requirements

```
numpy
pandas
scipy
matplotlib
requests
```

Install with:

```bash
pip install numpy pandas scipy matplotlib requests
```

---

## How to Run

1. Clone the repository
2. Create and activate a virtual environment
3. Install the requirements
4. Open `lorenz_dmi.ipynb` in VS Code or Jupyter
5. Run all cells

---

## Relationship to Other Projects

This project is the third in a series:

| Project | Description |
|---|---|
| [dmi-analysis](../project_1_dmi/) | Observational temperature trends and extremes using DMI data |
| [lorenz-analysis](../project_2_Lorentz/) | Simulation of the Lorenz system and sensitive dependence on initial conditions |
| **lorenz-dmi** | Phase space reconstruction of real DMI temperature data using Takens' theorem |

---

## References

- Takens, F. (1981). *Detecting strange attractors in turbulence*. Lecture Notes in Mathematics, 898, 366–381.
- Lorenz, E. N. (1963). *Deterministic Nonperiodic Flow*. Journal of Atmospheric Sciences, 20(2), 130–141.
- Kantz, H. & Schreiber, T. (2004). *Nonlinear Time Series Analysis*. Cambridge University Press.
- DMI Open Data API: https://opendataapi.dmi.dk

---

## License

MIT
