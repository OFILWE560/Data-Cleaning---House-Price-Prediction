# House Price Prediction - Data Cleaning & EDA

Exploratory data analysis and preprocessing pipeline for a housing price dataset (Boston Housing format), covering data cleaning and exploratory data analysis as two structured tasks.

## Project Overview

This project works through two stages of a typical data science workflow:

1. **Data Cleaning & Preprocessing**: loading raw data, handling missing values, removing duplicates, and standardizing inconsistent formats.
2. **Exploratory Data Analysis (EDA)**: summary statistics, distribution visualizations, and correlation analysis to uncover patterns in the data.

## Dataset

The dataset contains 506 records of housing data with the following features:

| Column    | Description                                                |
|-----------|-------------------------------------------------------------|
| `CRIM`    | Per capita crime rate by town                                |
| `ZN`      | Proportion of residential land zoned for large lots          |
| `INDUS`   | Proportion of non-retail business acres per town              |
| `CHAS`    | Charles River dummy variable (1 = bounds river, 0 = otherwise) |
| `NOX`     | Nitric oxide concentration                                    |
| `RM`      | Average number of rooms per dwelling                          |
| `AGE`     | Proportion of owner-occupied units built before 1940           |
| `DIS`     | Weighted distance to employment centers                       |
| `RAD`     | Index of accessibility to radial highways                     |
| `TAX`     | Property tax rate                                              |
| `PTRATIO` | Pupil-teacher ratio by town                                     |
| `B`       | Derived metric related to proportion of Black residents (1000(Bk - 0.63)²) |
| `LSTAT`   | % lower status of the population                               |
| `MEDV`    | Median value of owner-occupied homes, in $1000s (**target**)   |

## 🛠️ Tools & Libraries

- **Python 3**
- **pandas**: data loading, cleaning, and manipulation
- **numpy**: numerical operations
- **matplotlib**: plotting
- **seaborn**: statistical visualizations

## Project Structure

```
.
├── house_price_prediction.ipynb     # Main notebook (cleaning + EDA)
├── house_Prediction.csv             # Raw input data
├── cleaned_house_data.csv           # Output of the cleaning step
└── README.md
```

## Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Running the notebook

1. Clone this repository
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```
2. Launch Jupyter
   ```bash
   jupyter notebook house_price_prediction.ipynb
   ```
3. Run all cells in order. The cleaning step writes `cleaned_house_data.csv`, which the EDA step reads back in.

## Task 1: Data Cleaning & Preprocessing

- Loads the raw whitespace-delimited CSV and assigns proper column names
- Detects missing values, including common placeholder strings (`?`, `NA`, `null`, blanks, etc.)
- Imputes missing numeric values with the median and categorical values with the mode
- Detects and removes duplicate rows
- Standardizes column names, text formatting, and data types (e.g. enforcing `CHAS` as a 0/1 binary indicator and `RAD` as an integer index)
- Saves the cleaned dataset to `cleaned_house_data.csv`

## Task 2: Exploratory Data Analysis (EDA)

- Summary statistics: mean, median, mode, standard deviation, min/max for every numeric feature
- Distribution visualizations: histograms and boxplots for all features
- Relationship visualizations: boxplot of `MEDV` by `CHAS`, scatter plots of the most correlated features against `MEDV`, and a pairplot of key features
- Correlation analysis: full correlation matrix, heatmap, and ranked correlation of each feature with the target (`MEDV`)

### Key Findings

- `RM` (average rooms per dwelling) shows a strong **positive** correlation with `MEDV`
- `LSTAT` (% lower status population) and `PTRATIO` (pupil-teacher ratio) show strong **negative** correlations with `MEDV`
- The dataset, as provided, contains **no missing values or duplicate rows** — the cleaning pipeline is built to handle them defensively if present in other versions of the data

## License

This project is open source and available under the [MIT License](LICENSE).

## Author

*Ofilwe Gabaitse / https://ofilwe560.github.io/Portfolio/*
