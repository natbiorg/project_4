# **Holiday Spending Analysis and Sales Prediction**
### **Authors**: Drew Johnson, Ellen Grant, Natalie Raver-Goldsby

---

## **Table of Contents**

- [Overview](#overview)
- [Data Sources](#data-sources)
- [Code Structure and Usage](#code-structure-and-usage)
- [Ethical Considerations](#ethical-considerations)
- [Results and Future Considerations](#results-and-future-considerations)
- [References](#references)

---

## **Overview**
Our team—Ellen, Natalie, and Drew—explored consumer spending behavior using a dataset from Kaggle. Our primary goal was to investigate the relationship between holidays and spending patterns to better understand how seasonal trends and promotional strategies impact consumer purchasing.

---

## **Data Sources**

### **Primary Dataset**
The main dataset used in this project is the **Kaggle Online Shopping Dataset**, which includes customer transaction records, demographic details, product information, and transactional specifics like price, quantity, and promotions.

### **Raw Data Overview**
- **Identifiers**: `Customer ID`, `Transaction ID` for unique identification.
- **Demographics**: `Gender`, `Location` of customers.
- **Transaction Details**: `Transaction Date`, `Quantity`, `Price`, `Delivery Charges`.
- **Product Information**: `Product Category`, `Description`.
- **Promotional Data**: `Coupon Status`, `Discount Percentage`.

### **Key Changes from Raw to Processed Data**
- **Consolidation**: Combined multiple entries per transaction into single rows.
- **New Features**:
  - **Customer Tenure**: Duration of each customer's history with the platform.
  - **Total Sales**: Computed as `Quantity * Average Price`.
  - **Holiday Indicator**: A `Near_Holiday` column indicating if the transaction occurred near a holiday.
  - **State Information**: Added a `State` column to capture customer location.
- **Handling Missing Values**: Imputed missing values using mean for numerical data or removed rows where necessary.

---


  
## **Code Structure and Usage**

### **Project Structure**

- **analysis_and_resources**: Contains project resources and processed datasets.
  - `cleaned.csv`: Cleaned and preprocessed dataset ready for analysis.
  - `shopping.csv`: Raw dataset of customer transaction records.
  - `project_4_proposal.doc`: Initial proposal document outlining goals, methodology, and anticipated outcomes.

- **notebooks**: Jupyter notebooks for each phase of the project.
  - `data_cleaning_preprocessing.ipynb`: Data cleaning and preprocessing steps, including handling missing values and formatting dates.
  - `initial_analysis.ipynb`: Exploratory data analysis (EDA) notebook to identify trends and patterns in consumer spending.
  - `random_forest_colab.ipynb`: Implements a Random Forest model to predict spending based on historical data.
  - `sales_predictions_colab.ipynb`: Predictive analysis using a neural network model to identify future spending trends.

- **resources**: Additional tools and resources.
  - `model_optimization.xlsx`: Spreadsheet logging the performance of different models and hyperparameters.

### **Usage Instructions**
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/natbiorg/project_4.git
    ```
2. **Install Dependencies**:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn tensorflow

    ```
3. **Run Notebooks: Open each .ipynb file in Jupyter Notebook, Jupyter Lab, or Google Colab to follow along with the analysis.

---

## **Ethical Considerations**

1. **Data Minimization**  
   We limited our data to only essential transactional information, excluding sensitive customer details such as names and addresses, in compliance with privacy standards.

2. **Bias and Fairness**  
   Efforts were made to ensure inclusivity and to avoid geographical or demographic biases. We focused on aggregated, non-biased trends across all demographic groups.

3. **Privacy**  
   All reports and visualizations focus on aggregated data, protecting individual customer privacy. Identifiable information was not included in any outputs.

---

## **Results and Future Considerations**

### **Results**
Through our analysis, we found:
- **Holiday Influence**: Spending peaks notably around major holidays, especially Thanksgiving and Christmas.
- **Promotional Impact**: Coupons and discounts significantly increase spending, particularly during high-spending holiday periods.
- **Gender Trends**: Small variations in spending behaviors by gender, with specific product preferences.

### **Future Work**
- **Enhanced Feature Engineering**: Further exploration of seasonal and holiday-related features.
- **Advanced Modeling**: Consider additional models like XGBoost and LSTM for time-series analysis.
- **Holiday-Specific Analysis**: Focus on each holiday individually for more granular insights into spending patterns.

### **Performance Summary**

| Model                                 | MSE         | MAE   | R²     | Key Features                                  | Notes                                                                                      |
|---------------------------------------|-------------|-------|--------|------------------------------------------------|--------------------------------------------------------------------------------------------|
| Linear Regression                     | N/A         | N/A   | 0.119  | `Total_Cost` vs. `Total_Sales`                 | Low R² (0.119) indicates a weak linear relationship between Total Cost and Total Sales.     |
| Random Forest                         | 297.05      | 0.92  | 0.98   | `Near_Holiday`, `Product_Category`, `State`    | Performed best with max depth of 100 and 600 trees; captured 98% of the data’s variance.   |
| Random Forest with Outlier Control    | 10,803.24   | 10.24 | 0.45   | `Near_Holiday`, `Product_Category`, `State`    | Ineffective model; removing outliers didn’t improve performance due to inherent data variability. |
| Neural Network                        | 27.36       | 1.98  | N/A    | `Near_Holiday`, `Product_Category`, `Discount Percentage` | Best performance achieved with 4 layers, 8/6/6/2 nodes, and 50 epochs.                             |

### Summary of Key Model Insights

- **Linear Regression**: The R² value of 0.119 shows that Total Cost is not a strong predictor of Total Sales.
- **Random Forest**: Achieved high accuracy with an R² of 0.98, capturing nearly all data variance. The model performed best with 100 max depth and 600 trees.
- **Random Forest with Outlier Control**: Despite attempts to control outliers, this model only achieved an R² of 0.45, indicating outliers didn’t significantly impact model performance.
- **Neural Network**: The neural network performed best with 4 layers, yielding an MSE of 27.36 and an MAE of 1.98, demonstrating that complex architectures with multiple layers can improve predictive accuracy in this dataset.


---

## **References**

- **Data Source**: [Kaggle Online Shopping Dataset](https://www.kaggle.com/)
- **References for any code used that is not your own:**
  - ChatGPT
  - AskBCS
  - Gulseevi Rees

___
