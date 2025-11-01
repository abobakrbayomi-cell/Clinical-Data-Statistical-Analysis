# Statistical Analysis of Clinical Study Data

This repository showcases the methodology for a comprehensive statistical analysis project. The goal was to identify significant differences between three independent study groups (a control group and two patient cohorts) using descriptive and inferential statistics.

**Note:** The raw data and analysis scripts for this project are confidential and are not included in this repository. The focus here is on the analytical workflow and statistical reasoning.

---

## 🛠️ Tools and Libraries Used

* **Python 3.x**
* **Pandas:** For data loading, preparation, and cleaning.
* **SciPy (scipy.stats):** For conducting inferential statistical tests, including Levene's test and the Kruskal-Wallis H Test.
* **scikit-posthocs:** For non-parametric post-hoc analysis (Dunn's test).
* **Matplotlib & Seaborn:** For data visualization, including box plots, swarm plots, bar charts, and heatmaps.
* **NumPy**

---

## 🔬 Analysis Methodology

The analysis was performed in a systematic, multi-step process:

### 1. Data Preparation and Cleaning
* Loaded the raw data from the source file using Pandas.
* Performed cleaning operations, including trimming excess whitespace and standardizing data entries.
* Managed missing values and identified potential outliers using the Interquartile Range (IQR) method.

### 2. Descriptive Statistics
* Calculated key descriptive statistics (Mean, Median, SD, IQR, Range) for all quantitative variables using Pandas functions (e.g., `describe()`).
* Compiled these statistics for the total sample and for each of the three study groups individually.

### 3. Inferential Statistics (Group Comparison)
* Checked data for assumptions (like homogeneity of variance) using **Levene's test** from SciPy.
* As key variables did not meet the assumptions for parametric tests (like ANOVA), the **Kruskal-Wallis H Test** was employed as the primary non-parametric alternative to compare the three groups.

### 4. Post-Hoc Analysis
* Following a significant Kruskal-Wallis result, post-hoc tests were performed to identify which specific pairs of groups were different.
* The primary non-parametric follow-up was **Dunn's post-hoc test**, implemented using the `scikit-posthocs` library.
* Results were corrected for multiple comparisons to reduce the risk of Type I errors (false positives).

### 5. Correlation Analysis
* Assessed the strength and direction of relationships between quantitative variables.
* **Spearman's rank correlation** was selected as the primary method due to its robustness for non-normally distributed data and sensitivity to outliers.
* Generated Pearson and Spearman correlation heatmaps for baseline comparison and final analysis.
* Used scatter plots (both before and after outlier removal) to visually assess the robustness of key relationships (e.g., between Ln PVT1 and TGF B).

### 6. Data Visualization
* Utilized Matplotlib and Seaborn to generate a variety of plots.
* **Box plots and swarm plots** were extensively used to compare distributions, identify outliers, and visually represent the post-hoc test results.
* **Bar charts** were used for categorical variables and mean comparisons.
* **Heatmaps** were used to visualize the correlation matrices.
