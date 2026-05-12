# dmi-analysis

Weather data analysis using real observations from the 'Danish Meteorological Institute' (DMI).

**Author:** Maria-Helena

---

## About

This project extrude and analyse data from DMI's Open Data API. The goal is to explore temperature trends and extremes for Danish weather stations, with the potential to expand into precipitation analysis and simple forecast verification.

The project is built as a Jupyter Notebook and is intended as a portfolio piece demonstrating applied meteorological data analysis in Python.

---

## Data Source

Data is retrieved from [DMI Open Data](https://opendataapi.dmi.dk) — a free, publicly available API provided by Danmarks Meteorologiske Institut.

**Station used:** Copenhagen (station ID `06180`)  
**Parameter:** Dry bulb temperature (`temp_dry`)

---

## What the Notebook Does

- Fetches 10-minute temperature observations from DMI's API
- Parses the JSON response into a pandas DataFrame
- Resamples to daily mean, max, and min temperatures
- Visualises the results with a time series plot including a min/max shaded range

---

## Requirements

```
requests
pandas
matplotlib
```

Install with:

```bash
pip install requests pandas matplotlib
```

---

## How to Run

1. Clone the repository
2. Install the requirements
3. Open `dmi_analysis.ipynb` in VS Code or Jupyter
4. Run all cells


---

## License

MIT
