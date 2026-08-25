# Player360 — Gaming Analytics & Monetization Command Center

Concise synthetic data generator and notebook for gaming analytics experiments.

## Overview

This project produces synthetic gaming datasets that simulate a simple star-schema: player dimension plus session and economy facts. The outputs (CSV) are suitable for practicing ETL, analytics, SQL, and dashboarding workflows.

Key datasets generated:

- `dim_users` — player profiles and demographics
- `fact_sessions` — gameplay sessions and metrics
- `fact_economy` — in-game transactions and monetization events

## Repository structure

.
- `data/` — generated CSV outputs
- `notebook/` — Jupyter notebook(s) used to generate data
- `README.MD` — this document

Current important paths:

- Notebook: `notebook/data_generator.ipynb`
- Data folder: `data/`

## Getting started

Prerequisites

- Python 3.10+ (or compatible 3.x)
- Recommended: create a virtual environment

Quick setup (PowerShell example):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt  # if present, or: pip install pandas numpy jupyter
```

If you don't have a `requirements.txt`, install the minimal packages:

```powershell
pip install pandas numpy jupyter
```

## Running the notebook

1. Open `notebook/data_generator.ipynb` in VS Code or Jupyter Lab/Notebook.
2. Run the cells sequentially. The notebook generates CSV files in `data/`.

Tip: use the VS Code Jupyter experience or run `jupyter lab` from the project root.

## Data files

After a successful run the `data/` folder should contain:

- `dim_users.csv` — player information
- `fact_sessions.csv` — session events and metrics
- `fact_economy.csv` — economy/transaction events

The generated datasets are deterministic when the notebook's random seed is fixed (see cell that sets the seed in the notebook).

## Notes & best practices

- Keep the notebook cells small and idempotent so re-running is predictable.
- Use a dedicated virtual environment to avoid package conflicts.
- Consider adding a `requirements.txt` or `pyproject.toml` for reproducibility.
- For production-like experimentation, load the CSVs into a local SQL database (SQLite, Postgres) to run realistic queries and create indexes.

## Future work

- Add data quality checks and validation rules.
- Provide an optional CLI or Python script to generate data headlessly (non-interactive).
- Export a schema file (DDL) for quick database ingestion.

## ContributingR

Contributions are welcome. Please:

1. Fork the repo
2. Create a feature branch
3. Open a pull request with a clear description of changes
