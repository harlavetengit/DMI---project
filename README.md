# DMI Weather Analysis Portfolio

A collection of meteorological data analysis projects using real observations from the Danish Meteorological Institute (DMI) — combining observational analysis, chaos theory, and dynamical systems applied to atmospheric data.

**Author:** Maria Helena

---

## Projects

### 1. [Temperature Trends & Extremes](./project_1(ETL_and_plot)/)
Fetching and analysing real temperature observations from Copenhagen (station 06180) using the DMI Open Data API. Covers data extraction, resampling, and visualisation of daily mean, max, and min temperatures.

**Tools:** Python, requests, pandas, matplotlib

---

### 2. [Chaos Theory & The Lorenz System](./project_2(Lorentz)/)
A simulation of the Lorenz attractor — the mathematical system that gave birth to chaos theory while Lorenz was running a weather model in 1963. Demonstrates sensitive dependence on initial conditions and its direct implications for the limits of weather forecasting.

**Tools:** Python, numpy, scipy, matplotlib

---

### 3. [Phase Space Reconstruction of Atmospheric Data](./project_3(Lorentz_dmi)/)
Applying Takens' embedding theorem to real DMI temperature observations from Copenhagen summer 2024 — reconstructing the attractor of the atmosphere from a single observed variable. Bridges the theoretical foundations of project 2 with the real data of project 1.

**Tools:** Python, numpy, pandas, scipy, matplotlib, requests

---

## The Story

These three projects are intentionally connected. Weather forecasting is not just a data problem — it is a problem of nonlinear dynamics. The atmosphere is a chaotic system, and understanding *why* forecasts have a fundamental horizon requires both hands-on data analysis and a grounding in dynamical systems theory.

Project 1 shows what the data looks like. Project 2 shows why it behaves the way it does. Project 3 shows the two ideas meeting in the real world.

---

## Data Source

All observational data is retrieved from the [DMI Open Data API](https://opendataapi.dmi.dk) — free and publicly available, no API key required.

---

## License

MIT
