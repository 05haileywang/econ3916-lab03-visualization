# econ3916-lab03-visualization

**Project Title:** Honest vs. Misleading Visualizations

**Objective:** This project examines how choices in chart construction—axis scaling, time-window selection, and data transformation—can distort or clarify the same underlying economic data, using Anscombe's Quartet, FRED wage series, and World Bank GDP data as case studies.

**Methodology:**
- Recreated Anscombe's Quartet (four 11-observation datasets, n=44 total) to demonstrate that identical summary statistics (mean, variance, correlation ≈ 0.816) can correspond to visually distinct underlying distributions
- Quantified chart distortion using Tufte's Lie Factor metric, computing a Lie Factor of **49.0** for a truncated-axis revenue chart, then redesigned the chart with a zero-based axis and honest annotation
- Constructed four alternative visualizations of real average hourly earnings (FRED AHETPI, deflated to 2020 dollars using CPIAUCSL) to illustrate how axis truncation, time-window selection, and scale choice (linear vs. log) each produce a different narrative from one dataset
- Executed a systematic four-step exploratory data analysis (Structure → Distributions → Relationships → Anomalies) on World Bank GDP data spanning **262 countries** and **64 years** (1960–2023)
- Built an interactive Lie Factor toggler (ipywidgets + matplotlib) allowing real-time comparison of nominal vs. real earnings under adjustable axis floors, time windows, and scale types

**Key Findings:**
- Statistical summaries alone are insufficient for data validation; visual inspection revealed structurally different relationships despite matching regression parameters across all four Anscombe datasets
- A modest 4.1% revenue increase was visually exaggerated to appear as a 200% increase through y-axis truncation alone—a Lie Factor of 49.0
- Real (inflation-adjusted) hourly earnings rose only ~20% over 60 years, in contrast to a more-than-twelvefold nominal increase, underscoring the necessity of deflating wage series before drawing conclusions
- World Bank GDP data exhibited strong right-skew requiring log-transformation for meaningful distributional analysis, with missingness concentrated at the panel's temporal edges (early 1960s and most recent year) rather than randomly distributed—consistent with data-not-missing-at-random (MNAR)
