# Group 14 Credit Line Increase Model Card
### Basic information:

* **Group members:**
      Bohao,     'bohaohe16@gwu.edu'
      Shreyas,   'Sdeo1@gwu.edu'
      Honey,     'honeypramod@gwu.edu'
      James,     'jamesworrall@gwu.edu'
      
* **Date**: 25/08/2021
* **Model version**: 1.0
* **License**: MIT
* **Model implementation code**: https://colab.research.google.com/github/jrbluehbh/Group-14-project/blob/main/DNSC_6301_Group_Project.ipynb#scrollTo=Dph0yEdlCZNc
    
### Intended Use: 
     
* **Intended uses**: This model is an example probability of default classifier, with an example use case for determining eligibility for a credit line increase. 
* **Intended users**: Students in GWU DNSC 6301 bootcamp.
* **Out-of-scope uses**: Any use outside of an eductional setting is out-of-scope.
        
### Training data (Training data has eliminated all ):

 
* Data dictionary: 
    
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

* **Source of training data**: GWU Blackboard, email 'bohaohe16@gwu.edu', 'Sdeo1@gwu.edu', 'honeypramod@gwu.edu' or 'jamesworrall@gwu.edu' for more information
* **How training data was divided into training and validation data**: 50% training, 25% validation, 25% test
* **Number of rows in training and validation data**:
  * Training rows: 15,000
  * Validation rows: 7,500

        
### Test data :

* **Source of test data**: GWU Blackboard, email 'bohaohe16@gwu.edu', 'Sdeo1@gwu.edu', 'honeypramod@gwu.edu' or 'jamesworrall@gwu.edu' for more information
* **Number of rows in test data**: 7500 rows
* **State any differences in columns between training and test data**: None
    
### Model details : 

* **Columns used as inputs in the final model**:
'LIMIT_BAL', 'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6', 'BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5', 'BILL_AMT6', 'PAY_AMT1', 'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5', 'PAY_AMT6'
* **Column used as target in the final model**:'DELINQ_NEXT'
* **Type of model**: DECISION TREE
* **Software used to implement the model**: Python3, scikit-learn
* **Version of the modeling software**: Python 3.7.11, scikit-learn 0.22.2.post1
    
### Quantitative analysis:

* **Metrics used to evaluate your final model**: Used Training and Validation AUC as well as AIR to determine an ideal depth of 6 for the final model. 
* **Final values of the metrics for all data**: 
  * **Training AUC**: 0.78
  * * **Validation AUC**: 0.75
  * * **Test AUC**: 0.74
  * * **Asian-to-White AIR**: 1.00
  * * **Black-to-White AIR**: 0.85
  * * **Female-to-Male AIR**: 1.02
  * * **Hispanic-to-White AIR**: 0.83

![image](https://user-images.githubusercontent.com/89275341/130871845-cf31bfb1-5b26-47d1-999b-b1cb9a504b53.png)

### Ethical considerations: 
        
* **Model relies too heavily on the PAY_0 variable.**
* **AUC falls within an acceptable range however, could be improved upon and may present unacceptable financial risk.**
* **Explicit bias was mitigated by not using demographic data from in the model however, implicit bias may still exist in the data.** 
* **AIR was improved by using a cutoff of .18 however, Black-to-White AIR and Hispanic-to-White AIR, while legal at above .8, may present unacceptable                         reputational risk.**

