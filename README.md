# E-Commerce Transaction Fraud Detection
## Overview
In this competition, you’ll benchmark machine learning models on a challenging large-scale dataset. The data comes from Vesta's real-world e-commerce transactions and contains a wide range of features from device type to product features. You also have the opportunity to create new features to improve your results.

## Data
### Transaction Table
**TransactionDT:** timedelta from a given reference datetime (not an actual timestamp)  
**TransactionAMT:** transaction payment amount in USD  
**ProductCD:** product code, the product for each transaction  
**card1 - card6:** payment card information, such as card type, card category, issue bank, country, etc.  
**addr:** address  
**dist:** distance  
**P_ and (R__) emaildomain:** purchaser and recipient email domain  
**C1-C14:** counting, such as how many addresses are found to be associated with the payment card, etc. The actual meaning is masked.  
**D1-D15:** timedelta, such as days between previous transaction, etc.  
**M1-M9:** match, such as names on card and address, etc.  
**Vxxx:** Vesta engineered rich features, including ranking, counting, and other entity relations.    
**Categorical Features:**
ProductCD,card1 - card6,addr1, addr2,P_emaildomain,R_emaildomain,M1 - M9
### Identity Table
Variables in this table are identity information – network connection information (IP, ISP, Proxy, etc) and digital signature (UA/browser/os/version, etc) associated with transactions.
(The field names are masked and pairwise dictionary will not be provided for privacy protection and contract agreement)  
**Categorical Features:**
DeviceType,DeviceInfo,id_12 - id_38
  

# Credit Card Fraud Detection

Three models trained to label anonymized credit card transactions as fraudulent or genuine. Dataset from [Kaggle](https://www.kaggle.com/dalpozz/creditcardfraud). Project through [ML@B](https://ml.berkeley.edu).

Project by [Makena Schwinn](https://github.com/makenaschwinn), [Sunny Zhang](https://github.com/sunnyzhang13), and [Georgy Marrero](https://github.com/georgymh).

**[Click here to read about our approach and results.](https://github.com/georgymh/ml-fraud-detection/blob/master/paper.pdf)** 

**Important Note: The results presented in the paper are currently inconsistent with our latest experimentations. Please view the notebooks to view our empirical results and read the paper to understand our approach.**
