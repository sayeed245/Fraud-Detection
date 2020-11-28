# E-Commerce Transaction Fraud Detection
## Table of Content
  * [Demo](#demo)
  * [Overview](#overview)
  * [Motivation](#motivation)
  * [Technical Aspect](#technical-aspect)
  * [Installation](#installation)
  * [Run](#run)
  * [Deployement on Heroku](#deployement-on-heroku)
  * [Directory Tree](#directory-tree)
  * [To Do](#to-do)
  * [Bug / Feature Request](#bug---feature-request)
  * [Technologies Used](#technologies-used)
  * [Team](#team)
  * [License](#license)
  * [Credits](#credits)
## Overview
This is a classification model to predict fraudalent E-Commerce transactions:
1. [IEEE](https://github.com/sayeed245/Fraud-Detection/blob/main/IEEE.ipynb):The missing values were imputed and LightGBM was used to select 11.5% (50/433) features. VIF was applied to further select(29/50) features. Created 55 new features from these 29 selected feautres. Negated the class imbalance by applying SMOTE and achieved an AUC score of 0.69 using Logistic Regression with 7%(29/433) of the features for interpretebility
2. [IEEE LightGBM CV](https://github.com/sayeed245/Fraud-Detection/blob/main/IEEE%20LightGBM%20CV.ipynb): Imputed missing values and applied LightGBM with KFold cross validation. Achieved a mean AUC score of 0.929 and out of fold AUC of 0.927. Created 137 new features and achieved an 0.55% increase in mean AUC score with 0.934 and 0.61% increase in out of fold AUC score with 0.932
## Motivation
What could be a perfect way to utilize unfortunate lockdown period? Like most of you, I spend my time in cooking, Netflix, coding and reading some latest research papers on weekends. The idea of classifying indian currency struck to me when I was browsing through some research papers. I couldn't find any relevant research paper (and of course dataset!) associated with it. And that led me to collect the images of Indian currency to train a deep learning model using [this](https://github.com/hardikvasa/google-images-download) amazing tool.
## Technical Aspect
This project is divided into two part:
1. Training a deep learning model using Keras. (_Not covered in this repo. I'll update the link here once I make it public._)
2. Building and hosting a Flask web app on Heroku.
    - A user can choose image from a device or capture it using a pre-built camera.
    - Used __Amazon S3 Bucket__ to store the uploaded image and predictions.
    - Used __CSRF Token__ to protect against CSRF attacks.
    - Used __Sentry__ to catch the exception on the back-end.
    - After uploading the image, the predictions are displayed on a __Bar Chart__.
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
## Installation
The Code is written in Python 3.7. If you don't have Python installed you can find it [here](https://www.python.org/downloads/). If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after [cloning](https://www.howtogeek.com/451360/how-to-clone-a-github-repository/) the repository:
```bash
pip install -r requirements.txt
```
## Bug / Feature Request
If you find a bug (the website couldn't handle the query and / or gave undesired results), kindly open an issue [here](https://github.com/sayeed245/Fraud-Detection/issues/new) by including your search query and the expected result.

## Technologies Used

## Credits
## Connect/Follow
#### LinkedIn: [https://www.linkedin.com/in/sayeed-mohammad-83b691108/](https://www.linkedin.com/in/sayeed-mohammad-83b691108/)
#### Twitter: [https://twitter.com/6SAYEED](https://twitter.com/6SAYEED)
#### Tableau Public: [https://public.tableau.com/profile/sayeed.mohammad#!/](https://public.tableau.com/profile/sayeed.mohammad#!/)
