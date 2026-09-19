# NFL Analytics with pandas

A portfolio project demonstrating practical Python and pandas skills through real
NFL datasets.

The goal is not to build a production football application or a machine-learning
system. The NFL data provides an interesting, realistic setting for demonstrating
how to load, clean, reshape, join, aggregate, validate, analyze, and communicate
tabular data with Python and pandas.

## Project status

The local Python environment and notebook dependencies are configured with uv.
The repository contains a progressive notebook curriculum with questions, brief
prompts, and empty code cells so the analysis can be completed hands-on.

Start with [01 - Data loading and quality](notebooks/01_data_loading_and_quality.ipynb)
and follow the [notebook roadmap](notebooks/README.md).

## Skills demonstrated

### Python

- Analytical programming and readable notebook workflows
- Functions, comprehensions, and reusable transformations where appropriate
- File and path handling
- Assertions and defensive checks
- Clear separation between inputs, transformations, and outputs

### pandas

- DataFrame and Series fundamentals
- CSV and Parquet IO
- Data types and nullable values
- Indexing, filtering, and querying
- Data cleaning and string operations
- Joins, merges, concatenation, and join-cardinality validation
- Reshaping with melt, pivot, pivot_table, stack, and unstack
- GroupBy aggregation, transform, filter, ranking, and binning
- Datetime handling and chronological analysis
- Rolling, expanding, exponentially weighted, and shifted calculations
- Feature engineering with vectorized operations
- Categorical data and memory-efficient dtypes
- Performance-oriented pandas patterns and alternatives to row-wise apply

### Visualization

- matplotlib
- seaborn
- Clear chart labeling, units, populations, and interpretation

### Data analysis fundamentals

- Dataset grain and key selection
- Missing-data and duplicate handling
- Validation before and after joins
- Leakage-aware temporal analysis
- Reproducible notebook execution
- Distinguishing descriptive findings from predictive claims
- Communicating limitations and supported conclusions

## Curriculum

| # | Notebook | Primary pandas focus |
| --- | --- | --- |
| 01 | Data loading and quality | IO, dtypes, nulls, duplicates, profiling |
| 02 | Building the analysis dataset | merge, concat, vectorization, validation |
| 03 | What separates winning teams? | groupby, agg, transform, pivot_table |
| 04 | Team form and consistency | sort, shift, rolling, temporal analysis |
| 05 | Findings and recommendations | synthesis and reproducibility |
| 06 | Reshaping NFL data | melt, pivot, stack, unstack |
| 07 | Advanced filtering and indexing | loc, iloc, query, masks, MultiIndex |
| 08 | GroupBy deep dive | named aggregation, transform, filter |
| 09 | Time series analysis | datetime, resample, rolling, expanding, ewm |
| 10 | Joining NFL datasets | merge, join, concat, anti-joins, cardinality |
| 11 | Cleaning messy NFL data | strings, nullable types, replace, categoricals |
| 12 | Feature engineering with pandas | assign, cut, qcut, vectorization |
| 13 | Performance and memory | efficient dtypes, categoricals, apply alternatives |
| 14 | Advanced window operations | grouped rolling, expanding, ewm, rank |
| 15 | pandas capstone | end-to-end analysis from raw data to findings |

## Run locally

Install [uv](https://docs.astral.sh/uv/getting-started/installation/), clone this
repository, and run these commands from the repository root:

```powershell
uv sync --locked
uv run --locked python -m ipykernel install --sys-prefix --name nfl-analytics-with-pandas --display-name "Python (NFL Analytics)"
uv run --locked jupyter lab
```

Select **Python (NFL Analytics)** when creating a notebook. In VS Code, open this
repository and select `.venv/Scripts/python.exe` as the notebook's Python
environment. No Conda activation is needed when using the commands above.

Python 3.12 is selected by `.python-version`. Direct dependencies are declared in
`pyproject.toml`; `uv.lock` records resolved versions. The `.venv/` directory is
local and excluded from Git.

## Data

The intended inputs are CSV or Parquet exports from NFL datasets available to the
project. Local datasets belong in `data/`, which is excluded from Git. Credentials
and local environment files must stay outside version control.

The environment setup does not download data or configure storage credentials.
CSV files can be loaded with `pandas.read_csv`; Parquet files with
`pandas.read_parquet`. Public sample data and reproducible loading instructions
can be added only when the selected dataset may be redistributed.

## Portfolio intent

Each notebook should make the pandas concept visible, explain why a technique is
used, and interpret the result in plain language. Football is the subject matter;
the primary purpose of the repository is to demonstrate practical Python and
pandas understanding with data that is more engaging than a generic tutorial
dataset.
