# 📄 README.md

## Project: Forecast Sales Project

Welcome to the Forecast Sales Project! This repository contains all the code, data, and documentation required for performing time series forecasting of weekly sales for multiple products. The project is designed to be modular, reproducible, and easy to understand for evaluators and collaborators.

## 📂 Project Structure

```plaintext
forecast-sales-project/
├── data/                   # Raw and processed data files
├── notebooks/              # Jupyter Notebooks for EDA and modeling
├── models/                 # Saved models
├── utils/                  # Helper scripts
├── outputs/                # Visualizations and predictions
├── README.md               # Project documentation
└── requirements.txt        # Dependencies
```

## 🚀 Project Overview

This project aims to analyze weekly sales data, uncover trends and seasonality, and build forecasting models to predict future sales for different products. The workflow includes:

- **Exploratory Data Analysis (EDA):** Understanding the sales data, trends, and seasonality.
- **Data Preprocessing:** Cleaning and preparing the dataset for modeling.
- **Modeling & Forecasting:** Using Prophet to forecast sales for each product.
- **Validation:** Evaluating model performance on a holdout validation period.
- **Output Generation:** Saving forecasts and validation results for further analysis.

## 🗂️ Directory Details

- **data/**  
  Contains raw and processed datasets used for analysis and modeling.

- **notebooks/**  
  Jupyter Notebooks for:
  - Exploratory Data Analysis (`01_EDA.ipynb`)
  - Modeling and Forecasting (`02_Modeling_Forecasting.ipynb`)

- **models/**  
  Directory for saving trained forecasting models (if model serialization is implemented).

- **utils/**  
  Helper scripts for data processing, feature engineering, or utility functions.

- **outputs/**  
  Stores generated visualizations, prediction CSVs, and validation accuracy files.

- **README.md**  
  This documentation file.

- **requirements.txt**  
  List of Python dependencies for the project.

## 📊 Workflow Summary

### 1. Exploratory Data Analysis (EDA)
- Loaded weekly sales data with columns for date, channel, brand, category, sub-category, product serial number, and quantity.
- Inspected data for missing values, trends, and seasonality.
- Visualized sales patterns to identify weekly and yearly effects.

### 2. Data Preprocessing
- Parsed and standardized date columns.
- Checked for and handled missing or inconsistent data.
- Renamed columns for consistency (e.g., `SerailNum` to `SerialNum`).

### 3. Modeling & Forecasting
- Used Prophet for time series forecasting, fitting a separate model for each product (`SerialNum`).
- Trained models using all data up to a validation period (June–August 2024).
- Generated forecasts for a future horizon (September–November 2024).

### 4. Validation & Evaluation
- Compared model predictions to actual sales in the validation period.
- Calculated monthly accuracy metrics for each product to assess model performance.
- Saved accuracy results for transparency and reproducibility.

### 5. Output Generation
- Forecasts for each product and period are saved as CSV files in the `outputs/` folder.
- Validation accuracy metrics are also saved for review.

## 🛠️ How to Run

1. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

2. **Run Notebooks**
   - Open the notebooks in the `notebooks/` directory and run cells sequentially for EDA and modeling.

3. **Review Outputs**
   - Forecasts and validation results are saved in the `outputs/` directory for further analysis.

## 📝 Key Files

| File/Folder                | Description                                      |
|----------------------------|--------------------------------------------------|
| `data/`                    | Sales data (raw and processed)                   |
| `notebooks/01_EDA.ipynb`   | Exploratory Data Analysis notebook               |
| `notebooks/02_Modeling_Forecasting.ipynb` | Forecasting and evaluation notebook     |
| `outputs/sept_nov_forecast.csv` | Forecasted sales for Sep–Nov 2024         |
| `outputs/validation_accuracy_Jun_Jul_Aug.csv` | Model accuracy for Jun–Aug 2024  |
| `requirements.txt`         | Python dependencies                              |

## 📦 Dependencies

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels
- prophet
- scikit-learn

Install all dependencies using:
```bash
pip install -r requirements.txt
```

## 📚 Documentation

A comprehensive documentation file is provided below to guide evaluators through the entire workflow, including data structure, modeling approach, and outputs.

# 📖 Project Documentation

## 1. Data Description

The dataset contains weekly sales records with the following columns:
- `weekend_date`: Date of the sales week (varied formats, standardized during preprocessing)
- `channel`: Sales channel identifier
- `brand`: Product brand
- `category`: Product category
- `sub_category`: Product sub-category
- `SerialNum`: Unique product identifier
- `quantity`: Number of units sold

## 2. Exploratory Data Analysis

- Inspected data for completeness and consistency.
- Visualized sales trends by product, channel, and category.
- Identified weekly and yearly seasonality patterns.
- Checked for outliers and missing values.

## 3. Modeling Approach

- Used Prophet, a robust time series forecasting library, to model sales for each product.
- Incorporated both weekly and yearly seasonality.
- Models trained on historical data up to May 2024.
- Forecast horizon: 13 weeks (September–November 2024).

## 4. Validation Strategy

- Held out data from June–August 2024 for validation.
- Compared predicted vs. actual sales for each product.
- Calculated monthly accuracy as:
  $$
  \text{Accuracy} = 1 - \frac{\sum | \text{yhat} - \text{actual} |}{\sum \text{actual}}
  $$
- Results saved in `outputs/validation_accuracy_Jun_Jul_Aug.csv`.

## 5. Outputs

- **Forecasts:**  
  `outputs/sept_nov_forecast.csv` contains forecasted sales for each product for the next 13 weeks.
- **Validation Metrics:**  
  `outputs/validation_accuracy_Jun_Jul_Aug.csv` provides monthly accuracy scores for each product.
- **Visualizations:**  
  Plots and charts (if generated) are saved in the `outputs/` folder.

## 6. Reproducibility

- All code is organized in Jupyter Notebooks for transparency.
- Data preprocessing and modeling steps are clearly documented.
- Outputs are saved with descriptive filenames for easy review.

## 7. Extensibility

- New products or sales data can be added to the `data/` folder and rerun through the pipeline.
- Modeling scripts can be adapted for other time series forecasting tasks.


