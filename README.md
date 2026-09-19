# NFL Analytics with pandas

End-to-end NFL data analysis with pandas and Jupyter notebooks, using QuantCup
datasets to explore team performance, game outcomes, and season trends.

## Project status

The local Python environment and notebook dependencies are configured with uv.
Five starter notebooks contain questions, brief prompts, and empty code cells.
Analysis and findings are not yet implemented; see the [notebook roadmap](notebooks/README.md).

Start with [01 - Data loading and quality](notebooks/01_data_loading_and_quality.ipynb).

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
local and excluded from Git. Re-run the kernel installation command after
recreating the environment or moving the checkout.

| Dependency | Purpose |
| --- | --- |
| pandas | Data loading, cleaning, joins, aggregation, and rolling metrics |
| pyarrow | Parquet reads and writes |
| jupyterlab, ipykernel | Notebook interface and Python execution |
| matplotlib, seaborn | Charts |
| boto3 | Downloads from S3-compatible QuantCup object storage |
| python-dotenv | Optional loading of local credentials from an ignored `.env` file |

## Planned analysis

Explore what separates winning NFL teams and how consistently those strengths
hold up across seasons. The workflow will cover data loading, quality checks,
cleaning, validated joins, aggregation, rolling metrics, and visual storytelling.

## Data

The intended inputs are CSV or Parquet exports from QuantCup's object storage.
Local datasets belong in `data/`, which is excluded from Git. Credentials and
local environment files must stay outside version control.

The environment setup does not download data or configure storage credentials.
CSV files can be loaded with `pandas.read_csv`; Parquet files with
`pandas.read_parquet`. Storage access is needed only for the download step, not
for subsequent analysis of local files.

Public sample data and reproducible loading instructions will be added only after
the permitted distribution scope of the selected datasets is established.
