# project-4
## Accessibility and Restaurant Success
## Authors: Drew Johnson, Ellen Grant, Natalie Raver-Goldsby

#### Overview
<br>#TODO An overview of the project and its purpose</br>
Our team, Ellen, Natalie, and Drew sought out to explore the spending behavior of consumers from a dataset from Kaggle. We specifically wanted to investigate whether there was a relationship between holidays and spending. 

#### Data Sources
<br>#TODO what data sources did we use? What did the raw data look like when we started and then when we brought it into analysis.</br>
The primary dataset used for this project is the Kaggle Online Shopping Dataset, which contains records of customer transactions, including demographic information, product details, and transaction-specific data (e.g., price, quantity, and promotions).

Raw Data Overview

•	Customer ID, Transaction ID: Identifiers for transactions and customers.

•	Gender, Location: Demographic details of customers.

•	Transaction Date: Date and time of purchase.

•	Product Category, Description: Product-related information.

•	Quantity, Price, Delivery Charges: Transactional data.

•	Coupon Status, Discount Percentage: Promotion-related data.

Key Changes from Raw to Processed Data
•	Consolidation: The raw dataset had multiple rows per transaction for the same customer, which were consolidated into one row per transaction in the processed dataset.

•	New Features: Added Customer Tenure (how long the customer has been shopping) and Total Sales (Quantity * Average Price).

•	Holiday Indicator: The Near_Holiday column was added to indicate whether the transaction occurred around a holiday (e.g., New Year's Day).

•	State Information: State column added to track customer location.

•	Missing Values: Handled through mean imputation or row removal for critical data.


  
#### Code Structure and Use
<br>#TODO Instructions on how to use and interact with the project</br>

Project Structure:

•	analysis_and_resources: Contains all the project-related resources and outputs.

    o	cleaned.csv: The cleaned and preprocessed version of the original dataset, ready for analysis.

    o	shopping.csv: Raw dataset containing transaction records of customers.

    o	project_4_proposal.doc: The project proposal document outlining the objectives, methodology, and expected outcomes of the analysis.

•	notebooks: Jupyter notebooks used for different stages of the project.

    o	data_cleaning_preprocessing.ipynb: Notebook for cleaning and preprocessing the raw data (handling missing values, transforming date formats, etc.).

    o	initial_analysis.ipynb: Notebook for performing exploratory data analysis (EDA) to gain insights into consumer purchasing behavior and trends.

    o	random_forest_colab.ipynb: Notebook for training a Random Forest machine learning model to predict consumer behavior based on historical data.

    o	sales_predictions_colab.ipynb: Notebook for generating sales predictions and identifying future spending trends using machine learning models.

•	resources: Contains additional tools and resources for model optimization and evaluation.

    o	model_optimization.xlsx: Spreadsheet with the results of hyperparameter optimization for different models, including Random Forest and other algorithms.



  
#### Ethical Considerations

1.	Data Minimization
   
In alignment with the principle of data minimization, we ensured that only the essential data necessary for our analysis was included in the dataset. For example, we focused on transactional data, such as product purchases, quantities, and prices, while intentionally avoiding the inclusion of irrelevant or excessive personal information. During the dataset selection process, we made certain that sensitive data (such as payment methods, customer names, addresses) was excluded, thus safeguarding customer privacy and minimizing potential risks.

2.	Bias and Fairness

We placed an emphasis on fairness and inclusivity throughout our analysis. We considered the diversity of demographic regions within the dataset to mitigate potential geographical or cultural biases in our findings. When performing segmentation, we made conscious efforts to avoid assumptions or generalizations that could result in biased or discriminatory conclusions about specific customer groups.

3.	Limitations in Reporting
   
When compiling our analysis, we took deliberate steps to ensure the protection of customer privacy. We made certain that no identifiable information was included in any reports, notebooks, Excel files, or visualizations. By focusing on aggregated trends and summaries, we ensured that our findings adhered to privacy standards while still providing valuable insights. Additionally, when formulating our predictive model, we prioritized privacy compliance, ensuring that the analysis remained useful for decision-making without compromising confidentiality.


#### Results and Future Considerations 
#TODO Summarize results and say what we might do differently in the future. 


| Methods of Analysis  | Success Measure 1 | Success Measure 2 |
| ------------- | ------------- | ------------- |
| Linear Regression  | TBD  | TBD  |
| Random Forest  | TBD  | TBD  |
| Neural Network  | TBD  | TBD  |

#### References
<br>#TODO References for the data source(s)</br>
<ul>
  <li></li>
  <li></li>
</ul>
#TODO References for any code used that is not your own
<ul>
  <li>ChatGPT</li> 
  <li>AskBCS</li> 
  <li>Gulseevi Rees</li> 
</ul>
<br>___</br>
#### Notes

