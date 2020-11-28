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
In this competition, you’ll benchmark machine learning models on a challenging large-scale dataset. You also have the opportunity to create new features to improve your results.  
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

## Run
> STEP 1
#### Linux and macOS User
Open `.bashrc` or `.zshrc` file and add the following credentials:
```bash
export AWS_ACCESS_KEY="your_aws_access_key"
export AWS_SECRET_KEY="your_aws_secret_key"
export ICP_BUCKET='your_aws_bucket_name'
export ICP_BUCKET_REGION='bucket_region'
export ICP_UPLOAD_DIR='bucket_path_to_save_images'
export ICP_PRED_DIR='bucket_path_to_save_predictions'
export ICP_FLASK_SECRET_KEY='anything_random_but_unique'
export SENTRY_INIT='URL_given_by_sentry'
```
Note: __SENTRY_INIT__ is optional, only if you want to catch exceptions in the app, else comment/remove the dependencies and code associated with sentry in `app/main.py`

#### Windows User
Since, I don't have a system with Windows OS, here I collected some helpful resource on adding User Environment Variables in Windows.

__Attention__: Please perform the steps given in these tutorials at your own risk. Please don't mess up with the System Variables. It can potentially damage your PC. __You should know what you're doing__. 
- https://www.tenforums.com/tutorials/121855-edit-user-system-environment-variables-windows.html
- https://www.onmsft.com/how-to/how-to-set-an-environment-variable-in-windows-10

> STEP 2

To run the app in a local machine, shoot this command in the project directory:
```bash
gunicorn wsgi:app
```
## Bug / Feature Request
If you find a bug (the website couldn't handle the query and / or gave undesired results), kindly open an issue [here](https://github.com/sayeed245/Fraud-Detection/issues/new) by including your search query and the expected result.

## Technologies Used

## Credits

## Connect


# Credit Card Fraud Detection

Three models trained to label anonymized credit card transactions as fraudulent or genuine. Dataset from [Kaggle](https://www.kaggle.com/dalpozz/creditcardfraud). Project through [ML@B](https://ml.berkeley.edu).

Project by [Makena Schwinn](https://github.com/makenaschwinn), [Sunny Zhang](https://github.com/sunnyzhang13), and [Georgy Marrero](https://github.com/georgymh).

**[Click here to read about our approach and results.](https://github.com/georgymh/ml-fraud-detection/blob/master/paper.pdf)** 

**Important Note: The results presented in the paper are currently inconsistent with our latest experimentations. Please view the notebooks to view our empirical results and read the paper to understand our approach.**
