# ClaimsSim – Auto‑Insurance Pricing & Reserving Simulator

## Overview

ClaimsSim is a Python and SQL project that builds a stochastic simulator to estimate auto‑insurance premiums and claim reserves. It models claim frequency and severity using statistical distributions and Monte Carlo simulation【674788362766475†L264-L305】. A no‑claims discount (NCD) system is represented as a Markov chain【809559526411396†L156-L189】, and premiums are calculated using the pure premium, expense and profit principle【92135697905065†L444-L487】. The project includes data pipelines, analysis notebooks, dashboards and an actuarial report.

## Business Problem

A fictional auto insurer wants to price policies and set reserves under uncertainty. Historical claims data show variability in the number of claims and claim sizes. The insurer also offers a discount to claim‑free drivers, but needs to understand how the NCD system affects profitability. Traditional spreadsheets cannot simulate thousands of scenarios or model discount transitions. This repository builds a flexible simulator that integrates loss distributions, Monte Carlo simulation and a three‑state NCD Markov model【809559526411396†L156-L189】. The output helps actuaries and underwriters set premiums and reserve levels.

## Features

- **Frequency & severity models:** Fit Poisson/Negative‑Binomial and Log‑normal/Gamma distributions to claim frequency and severity【674788362766475†L264-L305】.
- **Monte‑Carlo simulation:** Generate aggregate loss distributions and estimate required reserves under stochastic scenarios【674788362766475†L264-L305】.
- **No‑claims discount Markov chain:** Model transitions between 0%, 25% and 50% discounts using a simple Markov chain【809559526411396†L156-L189】.
- **Premium calculation:** Calculate premiums using pure loss cost, expense load and profit margin【92135697905065†L444-L487】.
- **Sensitivity analysis:** Explore how changes in claim frequency, severity or transition probabilities impact premiums and reserves.
- **Dashboards & reports:** Interactive dashboard visualising loss distributions, discount state proportions and reserve projections. Executive summary PDF documents assumptions and insights.

## Repository Structure

```text
/claimssim
    /data         # historical claims data and simulated outputs
    /src          # Python modules for distributions, simulation, Markov models and pricing
    /notebooks    # Jupyter notebooks for EDA, model fitting, simulation and reserving
    /dashboards   # Power BI or Tableau dashboards (.pbix / .twb)
    /docs         # actuarial report and methodology diagrams (PDF)
    README.md
    requirements.txt
```

## Getting Started

1. **Clone the repository:**

   ```bash
   git clone https://github.com/TawandaMazh/claimssim.git
   cd claimssim
   ```

2. **Set up a virtual environment and install dependencies:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```

3. **Load the data:**

   - Place raw claims data in the `data/` directory.
   - Run the provided SQL script (to be added) to load data into a SQLite or PostgreSQL database.
   - Use the EDA notebook in `notebooks/` to explore and clean the data.

4. **Run simulations:**

   - Execute the simulation notebook or run the Python scripts in `src/` to estimate loss distributions, premiums and reserves.
   - The simulation will output summary statistics and store results in `data/`.

5. **Review dashboards and reports:**

   - Open the dashboard file in the `dashboards/` folder to interactively explore frequency/severity distributions and NCD state transitions.
   - Read the PDF report in `docs/` for actuarial assumptions and key insights.

## Deliverables

- Cleaned claims dataset and SQL ETL scripts.
- Python modules implementing frequency and severity models, Monte Carlo simulation and the NCD Markov chain.
- Jupyter notebook demonstrating model fitting, simulation and premium calculation.
- Excel workbook illustrating premium calculation and reserving triangles.
- Power BI/Tableau dashboard.
- Executive summary PDF.
- Comprehensive documentation via this README.

## Extensions

To extend this project further, you could:

- Introduce additional discount levels or rating factors using generalized linear models.
- Implement credibility theory or hierarchical models for frequency/severity.
- Build a web application allowing underwriters to adjust assumptions and instantly view updated premium and reserve estimates.
