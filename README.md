# Software Quality Insight

## Project Overview

Software Quality Insight is a data analysis project designed to analyze software quality metrics and identify modules that may require additional testing, code review, and maintenance. The project uses Exploratory Data Analysis (EDA), feature engineering, statistical analysis, and Microsoft Excel visualizations to understand defect patterns and software quality.

**Note:** This assessment uses synthetic/mock data for demonstration purposes. The results do not represent real company production data.

## Objectives

- Analyze software modules, components, and release versions.
- Identify modules with high defect counts.
- Study the relationship between code complexity and defects.
- Analyze code churn and its relationship with defects.
- Compare test coverage across modules.
- Examine component trends across software releases.
- Analyze contributor-related metrics.
- Present insights using Excel formulas, PivotTables, and charts.

## Technologies Used

- **Python:** Data preprocessing and exploratory data analysis.
- **Pandas:** Data cleaning and manipulation.
- **Microsoft Excel:** Statistical analysis, formulas, PivotTables, and charts.
- **CSV:** Dataset storage and data exchange.

## Dataset Description

The dataset contains approximately 500 records with software quality metrics.

Important features include:

- `module` – Software module identifier.
- `component` – Functional component name.
- `language` – Programming language.
- `size` – Module size.
- `release` – Software release version.
- `complexity` – Code complexity metric.
- `coupling` – Module coupling metric.
- `churn` – Code change activity.
- `test_coverage` – Test coverage percentage.
- `defect_count` – Number of defects.
- `severity` – Defect severity category.
- `commit_count` – Number of commits.
- `contributors` – Contributor-related metric.
- `changed_lines` – Number of changed lines.

## Data Preprocessing and EDA

The preprocessing workflow includes:

1. Checking missing values and duplicate records.
2. Standardizing module identifiers.
3. Handling missing values in source metrics.
4. Identifying unmatched records during dataset merging.
5. Detecting unusually high complexity and changed-line values.
6. Creating additional features such as defects per commit and high-defect classification.
7. Exploring relationships between software metrics and defect counts.

Unmatched records are reviewed separately because missing values caused by unmatched joins should not automatically be replaced with zero.

## Excel Data Analysis

### 1. Total Defects by Module

Excel `SUMIF` formulas were used to calculate total defects for each module. In the prepared dataset, MOD022 had the highest total, with 59 defects.

### 2. Complexity Relationship

A scatter chart was used to examine the relationship between code complexity and defect count. The exploratory correlation was approximately 0.163 when an extreme complexity value was included and approximately 0.342 when that value was excluded.

This indicates that the observed relationship is sensitive to extreme values and should be interpreted carefully.

### 3. Code-Churn Analysis

Code churn was analyzed to identify modules with greater code change activity. The exploratory correlation between churn and defect count was approximately 0.464, suggesting a positive association in the prepared dataset.

### 4. Coverage Comparison

Test coverage was examined to identify modules that may require additional testing. Modules with lower test coverage can be prioritized for test-case improvement.

The available dataset contains a test coverage field; a separate branch coverage field was not confirmed.

### 5. Component Trend

A PivotTable and line chart can be used to compare defect totals across components and release versions. This helps identify components that may require further investigation based on their observed defect trends.

### 6. Contributor Analysis

Contributor-related metrics can be analyzed to understand development activity. Individual contributor comparisons are appropriate only if the dataset contains actual contributor identities and reliable associated defect information.

### 7. Defect Severity Distribution

Defects can be grouped by severity using an Excel PivotTable and chart. This helps teams understand the distribution of defect counts across severity categories and prioritize further investigation.

## Key Findings

- MOD022 recorded the highest module-level defect count at 59.
- Code churn showed a positive correlation with defect count of approximately 0.464.
- Test coverage showed a negative correlation with defect count of approximately -0.208.
- Complexity analysis was affected by an extreme value.
- Correlation identifies association and does not establish causation.

These findings are exploratory results from synthetic data and may change if the dataset or preprocessing changes.

## Recommendations

- Prioritize code reviews for modules with high defect counts and high code churn.
- Improve test coverage for modules that need additional testing.
- Investigate extreme metric values before drawing conclusions.
- Review component-level defect trends across releases.
- Use defect severity to guide testing and maintenance priorities.
- Avoid attributing defects to individual contributors without reliable supporting data.
- Validate all findings against real project data before using them for operational decisions.

## Limitations

- The dataset is synthetic/mock data.
- Correlation does not prove causation.
- Extreme values can affect statistical relationships.
- Contributor analysis depends on the availability of individual contributor information.
- No trained and evaluated machine-learning model or verified model performance metrics are included in this project summary.

## Conclusion

Software Quality Insight demonstrates how data analysis and Excel visualizations can be used to explore software quality metrics. By examining defects, complexity, code churn, test coverage, and component trends, the project provides a structured approach to identifying areas that may need additional testing and code review.

The findings serve as a demonstration and should be validated using real software project data before being used for production decisions.
