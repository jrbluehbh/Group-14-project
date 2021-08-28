# Group 14 Credit Line Increase Model Card
### Basic information:

* **  Group member names and emails**：
      Bohao,     'bohaohe16@gwu.edu'
      Shreyas,   'Sdeo1@gwu.edu'
      Honey,     'honeypramod@gwu.edu'
      James,     'jamesworrall@gwu.edu'
      
* **    Date**: 25/08/2021
* ** Model version**: 1.0
    ○ License: MIT
    ○ Model implementation code: https://colab.research.google.com/github/jrbluehbh/Group-14-project/blob/main/DNSC_6301_Group_Project.ipynb#scrollTo=Dph0yEdlCZNc
    
    ○ Intended Use: 
        ■ Intended uses :By building up forecasting model to forecast whether customer will delinquent or not 
        ■ Intended users :Business intelligence department of banks
        ■ Out-of-scope uses :None
        
### Training data (Training data has eliminated all ):

    ○ Source of training data: GWU Blackboard, email `jphall@gwu.edu` for more information
    ○ How training data was divided into training and validation data : 
      set seed and devide 50% for training data and another 50% for validation data
    ○ Number of rows in training and validation data ：
      Training data: 15000 rows 
      Validation data: 7500 rows 
    ○ Data dictionary:
    
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

        
### Test data :

    ○ Source of test data: GWU Blackboard, email `jphall@gwu.edu` for more information
    ○ Number of rows in test data : 7500 rows
    
### Model details : 

    ○ Columns used as inputs in the final model:
      ['LIMIT_BAL', 'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6', 'BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5', 'BILL_AMT6', 'PAY_AMT1', 'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5', 'PAY_AMT6']
    ○ Column(s) used as target(s) in the final model :'DELINQ_NEXT'
    ○ Type of model : DECISION TREE
    ○ Software used to implement the model  : google.colab-python
    ○ Version of the modeling software :python 3.0
    
### ??Quantitative analysis:

    ○ Metrics used to evaluate your final model :AUC PLOT
    <font color="red"> 
    ```diff
    ○ State the final values of the metrics for all data: training, validation, and test data 

![image](https://user-images.githubusercontent.com/89275341/130871845-cf31bfb1-5b26-47d1-999b-b1cb9a504b53.png)

### ??Ethical considerations:

    ○ Describe potential negative impacts of using your model: 
        ■ Math or software problems: None
        ■ Real-world risks: Some hacker might hack into raw data, change user's 'DELINQ_NEXT' and thus 
    ○ Describe potential uncertainties relating to the impacts of using your model: 
        ■ Math or software problems: None
        ■ Real-world risks: Not detected yet
