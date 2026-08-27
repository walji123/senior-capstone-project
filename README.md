# Project Name: E-Commerce Sales Forecasting & Revenue Analysis

## Project Overview
The problem I plan to address is whether historical e-commerce data can be used to predict future sales revenue. I plan to use an e-commerce transaction dataset to analyze historical sales trends and develop a machine learning model to forecast future sales revenue. Additionally, I will perform a secondary analysis to examine which products contribute most to revenue. This analysis could be useful to business executives, financial analysts, and business and data analysts. Executives could use the sales forecast to support strategic decisions about budgeting resources. Financial analysts could use sales forecasts and historical revenue trends to support financial planning, and business and data analysts could use the results to identify product and seasonal trends and recommend strategies for effective decision-making.

## Data Source
* **Source:** The data comes from [Kaggle](https://www.kaggle.com/datasets/ineubytes/online-retail-ecommerce-dataset), but it originated from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail).
* **Description:** The dataset contains actual transaction records from a UK-based online retailer. It contains 541,909 transaction records and 8 variables: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`. Additionally, the dataset contains transactions from December 2010 through December 2011.
* **Storage:** Raw dataset is maintained locally at `data/raw/E-commerce_data.csv` (ignored by Git).

## Environment Setup
Clone the repository and install required dependencies:

```bash
# Clone the repository
git clone [https://github.com/walji123/senior-capstone-project.git](https://github.com/walji123/senior-capstone-project.git)
cd senior-capstone-project

# Install required Python packages
pip install -r requirements.txt