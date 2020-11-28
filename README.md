# E-Commerce Transaction Fraud Detection
## Table of Content
  * [Overview](#overview)
  * [Data](#data)
  * [Technical Aspect](#technical-aspect)
  * [Installation](#installation)
  * [Bug / Feature Request](#bug---feature-request)
  * [Credits](#credits)
  * [Connect / Follow](#connect---follow)
## Overview
[Ecommerce frauds](https://review42.com/ecommerce-fraud-statistics/) increased by 45% in 2017 alone leading to losses of $57.8 billion across 8 big industries. The dataset used in this repository is provided by Vesta Corporation to detect fraudalent online transactions. There are 2 classification models:
1. [IEEE](https://github.com/sayeed245/Fraud-Detection/blob/main/IEEE.ipynb): To find the best features for interpretibility to predict fraudalent E-Commerce transactions
2. [IEEE LightGBM CV](https://github.com/sayeed245/Fraud-Detection/blob/main/IEEE%20LightGBM%20CV.ipynb): To predict fraudalent E-Commerce transactions
## Data
The data comes from Vesta's real-world e-commerce transactions and contains a wide range of features from device type to product features.
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
## Technical Aspect
1. [IEEE](https://github.com/sayeed245/Fraud-Detection/blob/main/IEEE.ipynb):
     - Missing values were imputed and LightGBM was used to select 11.5% (50/433) features
     - VIF was applied to further select(29/50) features
     - Generated 55 new features from the selected 29 feautres
     - Negated the class imbalance by applying SMOTE
     - Achieved an AUC score of 0.69 using Logistic Regression with 7%(29/433) of the features for interpretebility
2. [IEEE LightGBM CV](https://github.com/sayeed245/Fraud-Detection/blob/main/IEEE%20LightGBM%20CV.ipynb): 
     - Imputed missing values and applied LightGBM with KFold cross validation
     - Achieved a mean AUC score of 0.929 and out of fold AUC of 0.927
     - Generated 137 new features from 433 features
     - Achieved an 0.55% increase in mean AUC score with 0.934 and 0.61% increase in out of fold AUC score with 0.932 after adding generated features
## Installation
The Code is written in Python 3.7. If you don't have Python installed you can find it [here](https://www.python.org/downloads/). If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after [cloning](https://www.howtogeek.com/451360/how-to-clone-a-github-repository/) the repository:
```bash
pip install -r requirements.txt
```
## Bug / Feature Request
If you find a bug (the website couldn't handle the query and / or gave undesired results), kindly open an issue [here](https://github.com/sayeed245/Fraud-Detection/issues/new) by including your search query and the expected result.
## Credits
[Vesta Corporation](https://trustvesta.com/) for providing datasets to host [IEEE-CIS Fraud Detection](https://www.kaggle.com/c/ieee-fraud-detection/overview) competition in Kaggle.
## Connect / Follow
#### LinkedIn: [https://www.linkedin.com/in/sayeed-mohammad-83b691108/](https://www.linkedin.com/in/sayeed-mohammad-83b691108/)
#### Twitter: [https://twitter.com/6SAYEED](https://twitter.com/6SAYEED)
#### Tableau Public: [https://public.tableau.com/profile/sayeed.mohammad#!/](https://public.tableau.com/profile/sayeed.mohammad#!/)
