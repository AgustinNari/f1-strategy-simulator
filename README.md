# F1 Strategy Simulator

An interactive Formula 1 race strategy simulator developed collaboratively.

The application explores tyre degradation, thermal behavior, lap-time estimation, and pit-stop strategy optimization through numerical methods, statistical modeling, and interactive visualizations.

## Features

- Configure circuits, race length, track temperature, and pit-stop time loss.
- Select teams, drivers, and tyre compounds.
- Simulate one-stop and two-stop race strategies.
- Compare two strategies under the same race conditions.
- Estimate lap times, tyre wear, and tyre temperatures.
- Analyze cumulative race time and strategy differences.
- Explore circuit layouts and animated race progress.
- Control simulation playback and speed.
- Access an explanatory panel covering the numerical methods used.

## Tech Stack

- **Python** — Main application and simulation logic.
- **Streamlit** — Interactive user interface.
- **FastF1** — Historical Formula 1 session and telemetry data.
- **NumPy and Pandas** — Numerical and tabular data processing.
- **SciPy** — Scientific computing.
- **scikit-learn** — Regression-based lap-time estimation.
- **Plotly and Matplotlib** — Data visualization.

## Numerical and Statistical Methods

The simulation combines several methods:

- **Runge-Kutta-Fehlberg (RKF45):** Numerical integration of the tyre-temperature model.
- **Polynomial least squares:** Curve fitting and analysis of strategy differences.
- **Simpson's rule:** Numerical integration used in race-time calculations.
- **Newton-Raphson:** Estimation of crossover points between strategies.
- **Regularized regression:** Polynomial feature expansion, scaling, and Ridge regression for lap-time estimates.

These techniques are integrated into a simplified simulation model rather than presented as isolated calculations.

## Data Sources and Modeling

The application uses FastF1 to retrieve historical race-session data when available.

The data-processing pipeline also generates synthetic variables and training samples. If historical session data cannot be loaded, the application can use a synthetic fallback dataset.

Circuit geometry is obtained from position telemetry when possible, with stylized track layouts available as visual fallbacks.

Tyre behavior and race performance are estimated using configurable parameters, numerical calculations, and statistical models.

**Results are simplified simulation estimates, not official Formula 1 predictions or validated real-world race strategies.**

## Getting Started

### Requirements

- Python 3 and pip.
- Internet access for downloading dependencies and retrieving uncached FastF1 data.

### Installation

1. Clone this repository.
2. Open a terminal in the repository root.
3. Install dependencies using `python -m pip install -r requirements.txt`.
4. Start the application using `python -m streamlit run src/app.py`.
5. Open the local URL displayed by Streamlit.

### Optional Data Caching

The repository includes `cache_all_tracks.py`, a utility for preloading historical data and circuit geometry for the configured tracks.

Run `python cache_all_tracks.py` to prepare cached data for local demonstrations.

This step is optional and may require additional download time and internet access.

## Project Structure

- `src/app.py` — Streamlit interface, controls, charts, and explanations of numerical methods.
- `src/strategy.py` — Race-strategy simulation and optimization logic.
- `src/metodos_numericos.py` — Numerical methods and mathematical utilities.
- `src/modelo_ml.py` — Regression-based lap-time prediction model.
- `src/extractor_datos.py` — FastF1 integration and synthetic data generation.
- `src/assets/` — Visual assets.
- `cache_all_tracks.py` — Optional data-caching utility.
- `requirements.txt` — Python dependencies.

## Project Scope

The simulator focuses on numerical modeling, simulation, and race strategy analysis.

This repository is a personal fork of the [original collaborative project](https://github.com/SantiMussi/SimuladorF1).

The project is independent and is not affiliated with or endorsed by Formula 1, the FIA, or any Formula 1 team.
