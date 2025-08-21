📘 Exploring equity in wastewater-based epidemiology (WBE)

A spatial pipeline from sewersheds to fairness-oriented planning

This repository contains the analysis code for my dissertation on representativeness and spatial equity in wastewater-based epidemiology (WBE) across Great Britain. It links operator-harmonised sewershed polygons, LSOA census populations, and borough/LAD attributes to move from simple “coverage” to a residual-based Fairness Score (FS) and policy-facing maps.

Research question

How can we quantify and improve the fairness of WBE coverage—beyond whether an area is covered—to identify under-served pockets under like-for-like supply–demand conditions?


🔁 Run order (do not skip steps)

Tip: Keep the repository structure as provided; notebooks assume relative paths under data/ and outputs/.

	1.	01_sewershed_population_overlay.ipynb – LSOA–sewershed spatial overlay; estimate served population per catchment.
	2.	02_aggregate_to_LAD.ipynb – Roll up catchments and site metadata to borough/LAD; attach admin statistics.
	3.	03_build_indicators.ipynb – Construct population coverage, geometric coverage, density (log), and EDI (Gini–Simpson, population-weighted).
	4.	04_regression_coverage.ipynb – Fit coverage model (HC3-robust); export fitted values and residuals.
	5.	05_fairness_score_mapping.ipynb – Winsorise residuals, scale to FS ∈ [−100, 100], render maps.
	6.	06_sensitivity_checks.ipynb – Alternative scaling/winsorisation and covariate sets; rank-stability outputs.
	7.	07_figures_tables.ipynb – Final figures/tables for the dissertation (maps, regression table, summary panels).

Notebooks write intermediate CSV/GeoPackage files to outputs/intermediate/ and final artefacts to outputs/final/.
