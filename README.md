# Statistical Analysis of Clinical Study Data

This repository showcases the methodology for a comprehensive statistical analysis project. The goal was to identify significant differences between three independent study groups (a control group and two patient cohorts) using descriptive and inferential statistics.

**Note:** The raw data and analysis scripts for this project are confidential and are not included in this repository. The focus here is on the analytical workflow and statistical reasoning.

---

## 🛠️ Tools and Libraries Used

* **Python 3.x**
* [cite_start]**Pandas:** For data loading, preparation, and cleaning[cite: 4].
* [cite_start]**SciPy (scipy.stats):** For conducting inferential statistical tests, including Levene's test and the Kruskal-Wallis H Test[cite: 13, 15].
* [cite_start]**scikit-posthocs:** For non-parametric post-hoc analysis (Dunn's test)[cite: 20].
* [cite_start]**Matplotlib & Seaborn:** For data visualization, including box plots, swarm plots, bar charts, and heatmaps[cite: 26].
* **NumPy**

---

## 🔬 Analysis Methodology

The analysis was performed in a systematic, multi-step process:

### 1. Data Preparation and Cleaning
* [cite_start]Loaded the raw data from the source file using Pandas[cite: 5].
* [cite_start]Performed cleaning operations, including trimming excess whitespace and standardizing data entries[cite: 6].
* [cite_start]Managed missing values and identified potential outliers using the Interquartile Range (IQR) method[cite: 7].

### 2. Descriptive Statistics
* [cite_start]Calculated key descriptive statistics (Mean, Median, SD, IQR, Range) for all quantitative variables using Pandas functions (e.g., `describe()`)[cite: 9, 10].
* [cite_start]Compiled these statistics for the total sample and for each of the three study groups individually[cite: 10].

### 3. Inferential Statistics (Group Comparison)
* [cite_start]Checked data for assumptions (like homogeneity of variance) using **Levene's test** from SciPy[cite: 13].
* [cite_start]As key variables did not meet the assumptions for parametric tests (like ANOVA), the **Kruskal-Wallis H Test** was employed as the primary non-parametric alternative to compare the three groups[cite: 15].

### 4. Post-Hoc Analysis
* [cite_start]Following a significant Kruskal-Wallis result, post-hoc tests were performed to identify which specific pairs of groups were different[cite: 19].
* [cite_start]The primary non-parametric follow-up was **Dunn's post-hoc test**, implemented using the `scikit-posthocs` library[cite: 20].
* [cite_start]Results were corrected for multiple comparisons to reduce the risk of Type I errors (false positives)[cite: 22].

### 5. Correlation Analysis
* [cite_start]Assessed the strength and direction of relationships between quantitative variables[cite: 30].
* [cite_start]**Spearman's rank correlation** was selected as the primary method due to its robustness for non-normally distributed data and sensitivity to outliers[cite: 31].
* [cite_start]Generated Pearson and Spearman correlation heatmaps for baseline comparison and final analysis[cite: 33, 34].
* [cite_start]Used scatter plots (both before and after outlier removal) to visually assess the robustness of key relationships (e.g., between Ln PVT1 and TGF B)[cite: 35, 36].

### 6. Data Visualization
* [cite_start]Utilized Matplotlib and Seaborn to generate a variety of plots[cite: 26].
* [cite_start]**Box plots and swarm plots** were extensively used to compare distributions, identify outliers, and visually represent the post-hoc test results[cite: 28].
* [cite_start]**Bar charts** were used for categorical variables and mean comparisons[cite: 27].
* [cite_start]**Heatmaps** were used to visualize the correlation matrices[cite: 27].
