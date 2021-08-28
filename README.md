# Credit Line Increase Model Card

### Basic Information
* __Person or organization developing model__: Shuning Ma, `shuningma@gwu.edu`
* __Model date__: August, 2021
* __Model version__: 1.0
* __License__: MIT
* __Model implementation code__: [DNSC_6301_Project.ipynb](DNSC_6301_Project.ipynb)

### Intended Use
* __Primary intended uses__: This model is an *example* probability of default classifier, with an *example* use case for determining eligibility for a credit line increase.
* __Primary intended users__: Students in GWU DNSC 6301 bootcamp.
* __Out-of-scope use cases__: Any use beyond an educational example is out-of-scope.

### Training Data
* **Data dictionary**:

| Name | Modeling Role | Measurement Level| Description|
| ---- | ------------- | ---------------- | ---------- |
|**ID**| ID | int | unique row indentifier |
| **LIMIT_BAL** | input | float | amount of previously awarded credit |
| **SEX** | demographic information | int | 1 = male; 2 = female
| **RACE** | demographic information | int | 1 = hispanic; 2 = black; 3 = white; 4 = asian |
| **EDUCATION** | demographic information | int | 1 = graduate school; 2 = university; 3 = high school; 4 = others |
| **MARRIAGE** | demographic information | int | 1 = married; 2 = single; 3 = others |
| **AGE** | demographic information | int | age in years |
| **PAY_0, PAY_2 - PAY_6** | inputs | int | history of past payment; PAY_0 = the repayment status in September, 2005; PAY_2 = the repayment status in August, 2005; ...; PAY_6 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; ...; 8 = payment delay for eight months; 9 = payment delay for nine months and above |
| **BILL_AMT1 - BILL_AMT6** | inputs | float | amount of bill statement; BILL_AMNT1 = amount of bill statement in September, 2005; BILL_AMT2 = amount of bill statement in August, 2005; ...; BILL_AMT6 = amount of bill statement in April, 2005 |
| **PAY_AMT1 - PAY_AMT6** | inputs | float | amount of previous payment; PAY_AMT1 = amount paid in September, 2005; PAY_AMT2 = amount paid in August, 2005; ...; PAY_AMT6 = amount paid in April, 2005 |
| **DELINQ_NEXT**| target | int | whether a customer's next payment is delinquent (late), 1 = late; 0 = on-time |

* **Source of training data**: GWU Blackboard, email `shuningma@gwu.edu` for more information
* **How training data was divided into training and validation data**: 50% training, 25% validation, 25% test
* **Number of rows in training and validation data**:
  * Training rows: 15,000
  * Validation rows: 7,500

### Test Data
* **Source of test data**: GWU Blackboard, email `shuningma@gwu.edu` for more information
* **Number of rows in test data**: 7,500
* **State any differences in columns between training and test data**: None

### Model details
* **Columns used as inputs in the final model**: 'LIMIT_BAL', 'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6', 'BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5', 'BILL_AMT6', 'PAY_AMT1', 'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5', 'PAY_AMT6'
* **Column(s) used as target(s) in the final model**: 'DELINQ_NEXT'
* **Type of model**: Decision Tree model
* **Software used to implement the model**:  Colaboratory & Jupiter Notebook
* **Version of the modeling software**: Ubuntu 18.04.5 LTS & Python 3.7.11
* **Hyperparameters or other settings of your model**: None

### Quantitative analysis
* **Metrics used to evaluate your final model**: Confusion metrix & AUC & AIR
* **State the final values of the metrics for all data: training, validation, and test data**:
  * **Training AUC**: 0.78
  * **Validation AUC**: 0.75
  * **Test AUC**: 0.75
  * **Asian-to-White AIR**: 1.01
  * **Black-to-White AIR**: 0.83
  * **Female-to-Male AIR**: 1.04
  * **Hispanic-to-White AIR**: 0.83
* **Provide any plots related to your data or final model -- be sure to label the plots!**:
![image](https://user-images.githubusercontent.com/31402450/130837562-70373579-fa81-4fdd-8748-99f474801996.png)

### Ethical considerations
* **Describe potential negative impacts of using your model**
  * **Math or software problems**: Maybe computationally expensive for some computers to grow the decision tree
  * **Real-world risks: who, what, when or how**: hackers
* **Describe potential uncertainties relating to the impacts of using your model**
  * **Math or software problems**
  * **Real-world risks: who, what, when or how**
* **Describe any unexpected or results**: None
