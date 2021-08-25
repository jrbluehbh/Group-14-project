# Group-14-project
● Basic information:

    ○ Group member names and emails：
      Bohao     bohaohe16@gwu.edu
      Shreyas   Sdeo@gwu.edu
      promound  honeypramod@gwu.edu
      James     jamesworral@gwu.edu
      
    ○ Date: 25/08/2021
    ??○ Model version:Decision tree
    ○ License: MIT
    ○ Model implementation code: https://colab.research.google.com/github/jrbluehbh/Group-14-project/blob/main/DNSC_6301_Group_Project.ipynb#scrollTo=Dph0yEdlCZNc
    
    ##○ Intended Use: 
    ##    ■ Intended uses :By building up forecasting model to forecast
    ##    ■ Intended users :Business intelligence department of banks
    ##    ■ Out-of-scope uses :Avoid demographical result of forecasting(avoid being racist)
        
● Training data (Training data has eliminated all ):

    ○ Source of training data: 50% From raw data
    ○ How training data was divided into training and validation data : 
      set seed and devide 50% for training data and another 50% for validation data
    ○ Number of rows in training and validation data ：
      Training data: 15000 rows 
      Validation data: 7500 rows 
    ○ Data dictionary; for each column in the training dataset include: 
        ■ Name :['LIMIT_BAL', 'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6',                            'BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5',                              'BILL_AMT6', 'PAY_AMT1',   'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5',                    'PAY_AMT6']
        ■ Modeling role :x
        ■ Measurement level : NOMINAL:PAY_0,2~6, CONTINIOUS: LIMIT_BAL, BILLAMT1~6,PAY_ATM1~6
        ■ Description : 
          LIMIT_BAL: refer to each accounts limit balance
          ??PAY_0,2~6: 
          ??BILLAMT1~6,PAY_ATM1~6: The amount they bill and pay at ATM each time.
        
        ■ Name :'DELINQ_NEXT'
        ■ Modeling role :y
        ■ Measurement level : NOMINAL
        ■ Description : Whether customer delinquent or not(1 refers to delinquent)
        
● Test data (5 pts.):

    ○ Source of test data: 50% from validation_test data
    ○ Number of rows in test data : 7500 rows
    
● Model details (8 pts.): 

    ○ Columns used as inputs in the final model:
      ['LIMIT_BAL', 'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6',                            'BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5',                              'BILL_AMT6', 'PAY_AMT1',   'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5',                    'PAY_AMT6']
    ○ Column(s) used as target(s) in the final model :'DELINQUENT'
    ○ Type of model : DECISION TREE
    ○ Software used to implement the model  : google.colab-python
    ○ Version of the modeling software :python 3.0
    
??● Quantitative analysis (7 pts.):
??
??    ○ Metrics used to evaluate your final model :AUC PLOT
??    ○ State the final values of the metrics for all data: training, validation, and test data 
??    ![image](https://user-images.githubusercontent.com/89275341/130796658-0dae97d9-0c64-410f-beea-6cff2973392f.png)
??
??● Ethical considerations (6 pts.)
??
??    ○ Describe potential negative impacts of using your model: 
??        ■ Math or software problems: The very begining result shows our model have                     demographical bias
??        ■ Real-world risks: who, what, when or how 
??    ○ Describe potential uncertainties relating to the impacts of using your model: 
??        ■ Math or software problems 
??        ■ Real-world risks: who, what, when or how? 
??    ○ Describe any unexpected or results
