# Project Name: E-Commerce Sales Forecasting & Revenue Analysis

## Project Overview

The problem I plan to address is whether historical e-commerce data can be used to predict future sales revenue. I plan to use an e-commerce transaction dataset to analyze historical sales trends and develop a machine learning model to forecast future sales revenue. Additionally, I will perform a secondary analysis to examine which products contribute most to revenue. This analysis could be useful to business executives, financial analysts, and business and data analysts. Executives could use the sales forecast to support strategic decisions about budgeting resources. Financial analysts could use sales forecasts and historical revenue trends to support financial planning, and business and data analysts could use the results to identify product and seasonal trends and recommend strategies for effective decision-making.

## Data Source

* **Source:** Sourced from [Kaggle](https://www.kaggle.com/datasets/carrie1/ecommerce-data), originally from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail).
* **Description:** The dataset contains actual transaction records from a UK-based online retailer. It contains 541,909 transaction records and 8 variables: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`. Additionally, the dataset contains transactions from December 2010 through December 2011.
* **Storage & Data Access:** The dataset is not stored on GitHub due to file size. To run this project locally:
  1. Download the data from [Kaggle](https://www.kaggle.com/datasets/carrie1/ecommerce-data).
  2. Put the downloaded file in `data/raw/` and name it `E-commerce_data.csv`.

## Environment Setup

Clone the repository and install required dependencies:

```bash
# Clone the repository
git clone https://github.com/walji123/senior-capstone-project.git
cd senior-capstone-project

# Install required Python packages
pip install -r requirements.txt
```

## Running the Notebooks

Open the project in VS Code and navigate to the `notebooks/` directory.

Open the project notebooks and run the cells in order.

## Project Progress (Unit 4 - Assignment 3)
- **Notebook**: `notebooks/02_data_cleaning_and_eda.ipynb`
- **Data Cleaning**: Handled missing values, standardized country codes, and resolved cancellation outliers (£77k & £168k) using quantity matching.
- **Exploratory Data Analysis**: Analyzed product revenue distributions, top revenue drivers, seasonal trends, and weekly revenue lag relationships.

## Project Progress I (Unit 5 - Assignment 4)
- **Notebook**: notebooks/03_baseline_model.ipynb
- **Data Cleaning**: Automated the cleaning process, standardized country codes, and removed fees and canceled orders.
- **Weekly Analysis**: Grouped transactions by week and confirmed that the £0 period in early January was a holiday closure, not missing data. Created two versions of the data: one keeping £0 and one using interpolation.
- **Modeling**: Used an 80/20 chronological train/test split. Compared a 1-week baseline with simple linear regression using MAE, RMSE, and R².
- **Key Finding**: The baseline performed better, with an MAE of £62,939.95 compared with £91,790.05 and £93,910.00 for the linear models. The baseline followed changes in sales more closely, while the linear models stayed mostly flat and missed the large Q4 holiday increase above £350,000.

## Project Progress II (Unit 6 - Assignment 5)
- **Notebook**: notebooks/04_model_evaluation_and_comparison.ipynb
- **Feature Engineering**: Added prior week revenue, revenue from two weeks prior, prior week orders, and 4-week rolling revenue.
- **Evaluation**: Used an 80/20 chronological train/test split with 39 training weeks and 10 testing weeks. Compared the 1-week baseline with Multiple Linear Regression and Ridge Regression using MAE, RMSE, and R^2.
- **Modeling**: Tested both versions of the data, including the £0 closure week and the interpolated version.
- **Key Finding**: The baseline performed best, with an MAE of £59,202.27 compared with £61,802.95 for Linear Regression and £61,802.99 for Ridge Regression. The regression models had negative R^2 values and missed the large mid-November sales increase above £350,000.