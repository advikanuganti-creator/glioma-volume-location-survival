# Tumor volume, centroid location, and overall survival in diffuse glioma (UCSF-PDGM)

Code and analytical dataset for: "Association of Tumor Volume and Centroid-Based Location
Measures With Overall Survival in Diffuse Glioma: A Retrospective Secondary Analysis of the
UCSF-PDGM Cohort".

## Files
- Tumor_Analysis_Revised.ipynb: full analysis (cohort construction, tumor volume and centroids,
  Kaplan-Meier and log-rank tests, Levene tests, power analysis, Lasso, figures).
- analytical_dataset.csv: one row per patient (n = 494). qc_outlier = 1 marks the 7 quality-control
  outliers; the primary cohort (n = 487) is the rows with qc_outlier = 0.
- Result tables (km_summary_*, logrank_levene_power_*, grade_pairwise_*, lasso_coefficients_*,
  sensitivity_comparison.csv, table1_characteristics.csv): output tables referenced in the paper.
- figure1_combined_results.png and figure2_flow_and_characteristics.pdf: Figures 1 and 2.

## Data source
The source data are the UCSF-PDGM dataset (version 5), available from The Cancer Imaging Archive
(doi:10.7937/TCIA.BDGF-8V37) and the DSI Studio Fiber Data Hub. Segmentation and clinical files
are not redistributed here. Please follow the TCIA data usage policy.

## Software
Python 3.13.13; numpy 2.4.6; pandas 2.3.3; nibabel 5.4.2; scipy 1.17.1; scikit-learn 1.9.0;
lifelines 0.30.3; matplotlib 3.10.9; seaborn 0.13.2.

## Reproducing the analysis
Set BASE in the first code cell to a folder containing the clinical metadata file, qc.tsv, and the
segmentation files, then run the notebook from top to bottom. Random seed: 42 (repeated 5-fold
cross-validation, 10 repeats).
