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

| Model             | MSE (or Loss) | MAE  | R-squared | Key Features                     | Notes                                  |
|-------------------|---------------|------|-----------|----------------------------------|----------------------------------------|
| Random Forest     | 364.57        | 0.95 | 0.981     | `Near_Holiday`, `Product_Category`, `State` | High R-squared indicates strong fit; interpretable feature importance |
| Neural Network    | 32.17         | 1.6  | N/A       | `Near_Holiday`, `Product_Category`, `Discount Percentage` | Best configuration used 3 layers with 6/6 nodes, relu/linear activations; optimized with 50 epochs |
| Neural Network (Alternative Config) | 22.2   | 2.08 | N/A       | `Near_Holiday`, `Product_Category`, `Discount Percentage` | Performed well with 4 layers and 50 epochs; possible overfitting at 100 epochs |

### **Summary of Neural Network Configurations:**
- **Best Neural Network (Loss: 32.17, MAE: 1.6)**: Achieved with 3 layers (6 nodes in each of the first two layers), 50 epochs, and `relu/linear` activation functions.
- **Alternative Configurations**: 
  - **4-layer Model with Loss: 22.2, MAE: 2.08** - Lower loss but slightly higher MAE, indicating possible overfitting as complexity increased.
  - **4-layer Model with 100 epochs** - Higher loss (63.91) and MAE (5.16), likely due to overfitting.

This summary provides an overview of the neural network configurations tested, highlighting the most effective setup and potential signs of overfitting with increased complexity.

---

## **References**

- **Data Source**: [Kaggle Online Shopping Dataset](https://www.kaggle.com/)
#TODO References for any code used that is not your own
<ul>
  <li>ChatGPT</li> 
  <li>AskBCS</li> 
  <li>Gulseevi Rees</li> 
</ul>
<br>___</br>

