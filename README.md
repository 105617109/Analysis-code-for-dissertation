📘 From Coverage to Fairness: WBE equity analysis for Great Britain

A sewershed → borough workflow, with residual-based Fairness Score (FS)

This repository contains the data artefacts and notebook used in my dissertation to assess representativeness and spatial equity of wastewater-based epidemiology (WBE) in Great Britain. We link LSOA→sewershed overlays to borough/LAD statistics to move from simple coverage to a residual-based Fairness Score (FS) and policy-facing maps.

🔍 Research question

How can we quantify “fairness” of WBE coverage—beyond a binary covered/not covered—under like-for-like supply–demand conditions, and identify under-served pockets?

⸻

🧭 How to run
	1.	Open JupyterLab and run the notebook 分析.ipynb (the analysis pipeline).
	•	The notebook expects the CSV/Shapefile files in the repository root (as in this repo).
	•	CRS is EPSG:27700 (British National Grid) for spatial operations.
	2.	Intermediate and final tables (e.g. coverage by borough, FS) are written back as CSV; figures/maps are saved under outputs/ (create if missing).

If you prefer English filenames, you may duplicate 分析.ipynb as analysis.ipynb—the code paths remain identical.


🗂 Files in this repository (what they are for)

Core spatial + lookup
	•	catchments_consolidated.cpg / .dbf / .prj ( + .shp, .shx ) – Sewershed/catchment geometry (harmonised).
	•	lsoa_catchment_lookup.csv – LSOA ↔ catchment crosswalk (tile-level or many-to-one).
	•	LSOA-to-borough-lookup.csv – LSOA ↔ borough/LAD crosswalk.
	•	waterbase_catchment_lookup.csv / waterbase_consolidated.csv – Auxiliary lookup and consolidated waterbase info (site/catchment metadata).

Borough/LAD aggregated tables
	•	borough_area_from_lsoa.csv – Borough area derived from LSOA union (for checks).
	•	borough_area_pop_combined.csv – Borough population & area combined table.
	•	borough_model_input.csv – Final modelling matrix (GeoCov, log density, EDI, GDPpc).
	•	borough_coverage_rate.csv – Coverage share by borough (observed).
	•	borough_sitecount_vs_gdp.csv – Site counts vs GDP diagnostic.

Equity & breakdowns
	•	coverage_by_ethnic_group.csv / ethics_group_split.csv – Coverage by ethnicity categories / splits.
	•	coverage_by_employment_decile.csv – Coverage by employment/IMD-like deciles.
	•	uk-borough_GDP.csv – GDP per capita by borough/LAD (or closest proxy).

LSOA-level results
	•	lsoa_coverage.csv – LSOA served/covered status or coverage-derived metrics.

Chinese-named data (used in the notebook)
	•	常住人口.csv – Resident population by unit (used in overlays/weights).
	•	经济活跃人数_拆分后.csv – Economically active population (processed split).

Shapefile note: place all shapefile components (.shp, .shx, .dbf, .prj, .cpg) together. Only some extensions appear in the file list; ensure the full set exists locally.

⸻

📈 Outputs produced by the notebook
	•	Borough/LAD coverage and FS (Fairness Score) tables (CSV).
	•	Choropleth maps of FS (PNG/PDF) with quantile breaks.
	•	Sensitivity summaries (if enabled in the notebook).

⸻

🔒 Data and licensing

This repository includes derived tables needed to reproduce figures and maps. Some source datasets may be under third-party licences and are therefore not included. Where external data are required, code cells are annotated with !!! to indicate where/how to acquire them. Please respect original licences.

⸻

🤝 Acknowledgements

Supervision by Dr Duncan Hay (weekly meetings and methodological guidance) greatly improved the quality and focus of this work.

⸻

📣 How to cite

Please cite the dissertation if you use these ideas or outputs. A Harvard-style bibliography is provided in the thesis.
