# Credit Risk Analysis

## Overview of the Analysis
LendingClub wants to take a deep look at their client base and assess their customers' level of credit risk. After analyzing the data set, with over 60k entries, machine learning was employed to take a closer look at the customers' loan stats for the year 2019. 

## Results
### Naive Random Oversampling
![Screen Shot 2021-12-26 at 8 50 33 PM](https://user-images.githubusercontent.com/89168119/147426343-59df06e6-491f-40da-9401-67f1633e99de.png)
- Oversampling achieved an accuracy percentage of **65%**, which is not bad on its own.
- However, the model's precision **1%** (high risk) and 100% (low risk) 
- And **63%** and **67%** for sensitiviy. The last two bullets combined make it a bad model as the model completely copies the low-risk data points and cannot accurately predict any high-risk data points. Which causes the model to assess every case as low risk. 

### SMOTE Oversampling
![Screen Shot 2021-12-26 at 8 57 07 PM](https://user-images.githubusercontent.com/89168119/147426664-dda3a477-f368-4791-b92e-8097ba6afbb5.png)
- SMOTE Oversampling achieved an accuracy percentage of **65%**, which is not bad. 
- However, like in the previous model, the precision is **1%** (high risk) and **100%** (lowr isk)
- And, **63%** (high risk) and **67%** (low risk) sensitivity. Again, combing the last two points--this is not a good model for predicting the credit risk of customers as the model will predict the customers' behaviors to be low risk. 

### Undersampling
![Screen Shot 2021-12-26 at 9 02 02 PM](https://user-images.githubusercontent.com/89168119/147426933-a14b9caa-e5ec-4cca-92e3-8834bcc9937c.png)
- Undersampling achieved an accuracy percentage of **51%** which is great. 
- However, this model too follows the same trend the previous two models had--it will erroneously predict that that the customers are low risk with a low risk precision percentage of **100%** and a **1%** precision with high risk cases. 
- Adding fuel to fire, moreover, this model has very poor sensitivity with **59%** for high_risk cases and **43%** for low risk clients. 

### Combination-Sampling
![Screen Shot 2021-12-26 at 9 07 49 PM](https://user-images.githubusercontent.com/89168119/147427202-e189593e-1975-4582-a7ea-0e90e9e49301.png)
- Combination sampling achieved an accuracy percentage of **62%** which is fine. 
- But, once again, this model's precision with high risk customers was **1%** and low risk customer precision was **100%**
- This model's sensitivity was nominally better than the previous ones' at **69%** for low risk and **55%** for high risk. 

### Balanced Random Forest Classifier
![Screen Shot 2021-12-26 at 9 11 36 PM](https://user-images.githubusercontent.com/89168119/147427380-495de405-59a0-4eff-84bb-b6053fbbb169.png)
- The balance random forest classifier achieved an accuracy score of nearly **79%**, which is far too high for a machine learning model. 
- The model's precision for high risk customers was **4%** and **100%** for low risk--which would make the machine still mark cases as low-risk
- The model had a **67%** sensitivity for high risk cases and **91%** sensitivity for low risk customers. 

### Adaboost Classifier
![Screen Shot 2021-12-26 at 9 19 11 PM](https://user-images.githubusercontent.com/89168119/147427762-68be37d4-5da4-4b15-acbd-f75216f945ca.png)
- The adaboost classifier obtained an accuracy percentage of **93%**-- which is much too high for a machine learning model. 
- The model's precision is **7%** for high risk customers--which is the best out of all 6 models, but still too low. And **100%** for low risk customers. 
- This model also had the best sensitivity out of any model at **91%** for high risk customers and **94%** for low risk customers. 

## Summary 
In sum, all of the models show too many characterstics of a bad machine learning model. I would not choose any of them.  On the whole, the ensemble models seemed to fair the best. But, the accuracy is  too high and the precision for the customer types is too varied. This might be due to the nature of the data, and maybe bagging the data would improve the metrics. The main point of contention with these models is that they would put LendingClub in a bad position where the models erroneously mark every case as low risk. This would cause them to hand out loans to unworthy debtors and end up losing money. 
