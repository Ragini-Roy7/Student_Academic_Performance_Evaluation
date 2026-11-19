# Student Academic Performance Evaluation

A Jupyter Notebook project that explores student academic data through exploratory data analysis (EDA), statistical analysis, and regression models, to understand which factors relate to academic performance.

## Overview

The notebook walks through a typical data-analysis workflow on student academic data: loading and inspecting the dataset, identifying missing values, separating numerical and categorical features, encoding categorical features, running Pearson correlation analysis, and visualizing the results. It then trains Linear Regression and Decision Tree Regression models to predict student performance and compares predictions against actual values.

This is a learning project. Correlations and feature importances shown here describe patterns in the data and do not establish cause and effect.

## Objectives

- Explore and understand the dataset's structure and features.
- Identify missing values and relationships between features.
- Analyze factors associated with academic performance.
- Evaluate performance using regression models.

## Dataset

The data contains student-level records with 20 columns and a few thousand rows (the missing-values plot's row index runs past 6,370).

| Type | Columns |
|------|---------|
| Numerical | `Hours_Studied`, `Attendance`, `Sleep_Hours`, `Previous_Scores`, `Tutoring_Sessions`, `Physical_Activity`, `Exam_Score` |
| Categorical | `Parental_Involvement`, `Access_to_Resources`, `Extracurricular_Activities`, `Motivation_Level`, `Internet_Access`, `Family_Income`, `Teacher_Quality`, `School_Type`, `Peer_Influence`, `Learning_Disabilities`, `Parental_Education_Level`, `Distance_from_Home`, `Gender` |

`Exam_Score` is the performance measure the analysis centers on. Categorical columns are one-hot encoded before the correlation analysis (for example `Parental_Involvement_Low` and `Parental_Involvement_Medium`).

<!-- TODO: confirm exact row count from df.shape, and add the dataset's original source/link only if you can verify it. -->

## Repository Structure

```text
Student_Academic_Performance_Evaluation/
│
├── assets/
│   └── screenshots/                       # Output plots used in this README
├── .gitignore
├── README.md                              # Project documentation
└── student-academic-performance (1).ipynb # Main analysis and modeling notebook
```

The dataset file is not included in the repository.

## Technology Stack

| Tool | Role |
|------|------|
| Python | Core language |
| NumPy | Numerical computation |
| Pandas | Data loading and manipulation |
| Matplotlib | Plotting |
| Seaborn | Statistical visualizations (heatmaps) |
| scikit-learn | Preprocessing, train-test split, regression models, evaluation |
| Jupyter Notebook | Interactive development environment |

## Analysis Performed

- Dataset loading and inspection
- Missing-value identification and visualization
- Numerical and categorical feature identification
- Categorical feature encoding
- Statistical summaries
- Pearson correlation analysis and correlation heatmap
- Feature selection
- Train-test split
- Linear Regression and Decision Tree Regression
- Prediction, model evaluation, and feature importance analysis
- Actual-versus-predicted visualization

## Screenshots

### Missing values

![Missing values heatmap](assets/screenshots/Screenshot%202026-04-12%20163450.png)

Each yellow line marks a missing entry. Most columns are complete; the gaps are sparse and appear in `Teacher_Quality`, `Parental_Education_Level`, and `Distance_from_Home`.

### Correlation matrix

![Correlation matrix of the student performance dataset](assets/screenshots/Screenshot%202026-04-12%20163523.png)

Pearson correlation heatmap over the numerical and one-hot encoded columns. Among the numerical features, `Exam_Score` shows its clearest positive correlations with `Hours_Studied` and `Attendance`, with weaker ones for `Previous_Scores` and `Tutoring_Sessions`. The strong negative blocks along the diagonal are between dummy columns of the same original feature (for example `Parental_Involvement_Low` and `Parental_Involvement_Medium`), which is an expected result of encoding. These are correlations, not evidence of cause and effect.

### Further output

**Analysis heatmap**

![Analysis heatmap](assets/screenshots/Screenshot%202026-04-12%20163546.png)

<!--
TODO: add a short caption for each screenshot, and a model results table
(Linear Regression vs Decision Tree Regression) using the exact metrics
printed in the notebook. Do not add numbers that are not in the notebook output.
-->

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/Ragini-Roy7/Student_Academic_Performance_Evaluation.git
   cd Student_Academic_Performance_Evaluation
   ```

2. Install the dependencies:

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
   ```

3. Download the dataset and place it where you like. The notebook was written on Kaggle, so the data-loading cell uses a Kaggle file path. Update the path in that cell (the one that reads the CSV) to point to your local copy.

4. Open and run the notebook:

   ```bash
   jupyter notebook "student-academic-performance (1).ipynb"
   ```

## Limitations and Future Work

**Current limitations**

- The dataset is not included, and the notebook uses a Kaggle-specific path, so it needs a small edit to run locally.
- There is no `requirements.txt`, so library versions are not pinned.
- The project is a notebook only; there is no packaged script or deployed application.

**Possible improvements (not yet implemented)**

- Add a `requirements.txt` and a configurable dataset path.
- Add cross-validation and additional regression models for comparison.
- Wrap preprocessing and modeling in a scikit-learn pipeline.

## Author

Ragini Roy — [GitHub](https://github.com/Ragini-Roy7)




