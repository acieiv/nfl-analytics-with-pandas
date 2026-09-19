# Notebook roadmap

This repository is a portfolio-oriented pandas curriculum using NFL data as the
subject matter. The football questions keep the work interesting; the technical
goal is to demonstrate practical Python and pandas understanding from foundational
data inspection through advanced transformations and a capstone analysis.

These are starter notebooks with prompts and empty code cells, not completed
solutions. Complete them in sequence when practical.

## Foundation

### 01_data_loading_and_quality.ipynb

**Question:** What data do we have, and which records are suitable for analysis?

**pandas focus:** `read_csv`, `read_parquet`, dtypes, `info`, missing values,
duplicates, `value_counts`, filtering, datetime parsing, assertions.

**Deliverable:** a compact data-quality report and documented inclusion rules.

### 02_building_the_analysis_dataset.ipynb

**Question:** How can game results and team performance be combined correctly?

**pandas focus:** `merge`, `concat`, `melt`, mapping, nullable types,
vectorized calculations, declared join cardinality, coverage checks.

**Deliverable:** a validated team-game analytical dataset.

### 03_what_separates_winning_teams.ipynb

**Question:** How do selected performance measures differ across wins, losses,
and ties?

**pandas focus:** `groupby().agg`, `transform`, `pivot_table`, ranking,
binning, distribution summaries.

**Deliverable:** evidence-backed descriptive findings and charts.

### 04_team_form_and_consistency.ipynb

**Question:** Does recent team performance persist into subsequent games?

**pandas focus:** chronological sorting, grouped `shift`, `rolling`, window
statistics, leakage-aware comparisons.

**Deliverable:** team trend analysis based only on information available before
the game being evaluated.

### 05_findings_and_recommendations.ipynb

**Question:** What should a reader take away from the first analysis sequence?

**pandas focus:** reproducible loading, recomputed summaries, concise tables,
final analytical synthesis.

**Deliverable:** a portfolio-ready summary of supported findings, limitations,
and follow-up questions.

## Intermediate pandas

### 06_reshaping_nfl_data.ipynb

**Question:** How can the same NFL data be represented in long and wide forms for
different analytical tasks?

**pandas focus:** `melt`, `pivot`, `pivot_table`, `stack`, `unstack`,
index naming, shape validation.

**Deliverable:** equivalent long- and wide-form datasets plus an explanation of
when each layout is useful.

### 07_advanced_filtering_and_indexing.ipynb

**Question:** How can precise slices of games, teams, seasons, and situations be
selected cleanly?

**pandas focus:** `.loc`, `.iloc`, Boolean masks, `.query()`, `.isin()`,
`.between()`, index operations, optional MultiIndex work.

**Deliverable:** a set of readable, validated analytical slices without chained
indexing.

### 08_groupby_deep_dive.ipynb

**Question:** How can team and season behavior be summarized at multiple levels
without losing row-level context?

**pandas focus:** multi-column `groupby`, named aggregation, `transform`,
`filter`, `size`, `nunique`, grouped ranking.

**Deliverable:** team/season summary tables and row-level columns derived from
group context.

### 09_time_series_analysis.ipynb

**Question:** How does team performance change over the course of a season?

**pandas focus:** datetime conversion, `DatetimeIndex`, `resample`, `rolling`,
`expanding`, `ewm`, chronological boundaries.

**Deliverable:** time-aware team trends with clearly defined windows.

### 10_joining_nfl_datasets.ipynb

**Question:** How can multiple NFL datasets be joined without silently creating
duplicate or unmatched records?

**pandas focus:** `merge`, `join`, `concat`, `validate=`, `indicator=True`,
anti-join patterns, key reconciliation, coverage checks.

**Deliverable:** a documented multi-table join with explicit cardinality and
unmatched-record reporting.

### 11_cleaning_messy_nfl_data.ipynb

**Question:** How can inconsistent identifiers, text fields, missing values, and
types be standardized safely?

**pandas focus:** `.str` methods, `replace`, `fillna`, `astype`, nullable
types, categoricals, duplicate handling, explicit cleaning maps.

**Deliverable:** a before/after cleaning report and reusable cleaning rules.

## Advanced pandas

### 12_feature_engineering_with_pandas.ipynb

**Question:** How can useful analytical variables be created efficiently from
existing game and team columns?

**pandas focus:** `assign`, `np.select`, `where`, `mask`, `cut`, `qcut`,
vectorized arithmetic, grouped features.

**Deliverable:** a documented feature table with validation for every derived
column.

### 13_performance_and_memory.ipynb

**Question:** How can a larger NFL dataset be processed more efficiently without
changing the analytical result?

**pandas focus:** `memory_usage`, efficient numeric dtypes, categoricals,
vectorization, avoiding unnecessary copies, comparing vectorized logic with
row-wise `apply`.

**Deliverable:** measured before/after memory or runtime comparisons and a short
explanation of the tradeoffs.

### 14_advanced_window_operations.ipynb

**Question:** How can prior performance, streaks, ranks, and evolving baselines be
computed within team and season boundaries?

**pandas focus:** grouped `rolling`, `expanding`, `ewm`, `shift`, `rank`,
`cumcount`, cumulative operations.

**Deliverable:** leakage-aware window features and trend visualizations.

### 15_pandas_capstone.ipynb

**Question:** Can one NFL question be answered end to end using the pandas skills
demonstrated throughout the repository?

**pandas focus:** select the appropriate combination of loading, cleaning,
reshaping, joining, grouping, temporal operations, feature engineering,
validation, and visualization.

**Deliverable:** a standalone portfolio analysis that starts from raw inputs,
documents every important transformation, and ends with supported findings and
limitations.

## Conventions for every notebook

1. Open with the analytical question, pandas skills being practiced, input grain,
   and expected output.
2. Keep imports and path setup near the top and use repository-relative paths.
3. Alternate short explanations with focused code cells and interpreted outputs.
4. Use assertions at important joins and transformations.
5. Explain cleaning decisions instead of silently dropping inconvenient rows.
6. Load required files explicitly; do not rely on hidden kernel state.
7. Distinguish retrospective/descriptive variables from information that would
   have been available beforehand.
8. Prefer clear vectorized pandas operations before reaching for row-wise
   `apply`.
9. End with findings, limitations, and a brief pandas-skills recap.
10. Before publishing, restart the kernel and run all cells in order.

Add reusable helpers only when repeated code genuinely justifies them. The point
of the repository is visible pandas practice, not building an application
framework.
