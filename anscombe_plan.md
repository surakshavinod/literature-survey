# Analyzing the Anscombe dataset

## Goal
Analyze the dataset and visualize it, and see what we want to do next with it.

## Implementation
1. Look at the anscombe_quartet.tsv data and generate descriptive statistics.
2. Create a Jupyter notebook in which you will generate the plots.
3. Propose the types of plots that you would like to generate.
4. Save this proposal to the end of this file and let me look at it.

I will need to approve this plan and tell you to go ahead before we actually do anything. Append the plan to the end of this file.

## Proposal

### Descriptive Statistics
Compute and display a single styled summary table with per-dataset values for:
- n, mean(x), mean(y), std(x), std(y)
- Pearson r, R²
- OLS regression slope (b1) and intercept (b0)
- min/max/median of x and y

Highlight cells where values are near-identical across datasets to emphasize the
"same statistics" side of the quartet's thesis.

### Plots

1. **2×2 Scatter Grid with Regression Lines** (primary figure)
   One subplot per dataset, all sharing axis limits x∈[3,20], y∈[2,14]. Each
   subplot has the fitted OLS line overlaid and is annotated with the regression
   equation and r value. Suptitle: "Anscombe's Quartet: Same Statistics, Different Data".

2. **2×2 Residual Plots**
   Residuals (y − ŷ) vs. fitted values for each dataset. Reveals the parabolic
   pattern in II, single large residual in III, and leverage structure in IV.

3. **Grouped Bar Chart of Summary Statistics**
   All key statistics (mean x/y, std x/y, r, slope, intercept) for all four
   datasets side by side. Placed *before* the scatter grid to set up the reveal.

4. **Strip Plots of y by Dataset**
   Marginal distribution of y per dataset with mean and median marked. Shows the
   arch of II, outlier spike of III, and vertical cluster of IV.

5. **Correlation Heatmap (Wide Format)**
   8-column wide-form pivot (x_I, y_I, …, x_IV, y_IV) rendered as a Pearson
   correlation matrix. Confirms x_I = x_II = x_III and isolates x_IV.

### Notebook Structure
8 sections: Introduction → Setup/Data Loading → Descriptive Statistics →
Scatter Grid → Regression Diagnostics → The Statistical Illusion (bar chart) →
Marginal Distributions → Conclusions. Bar chart (Plot 3) precedes scatter grid
(Plot 1) for the before/after narrative.

### Libraries
pandas, numpy, matplotlib, scipy.stats (no seaborn required)

### Styling
Single color map defined once: I=blue, II=orange, III=green, IV=red. All figures
saved as PNG at 150 dpi.
