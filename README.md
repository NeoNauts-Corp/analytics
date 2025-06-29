# User Behavior & Churn Analysis incl. a ML Model predicting user inactivity for a neo bank

## Context

This project was developed during the Le Wagon Bootcamp and centers on analyzing user behavior within a globally recognized neo-bank that aims to eliminate hidden fees in cross-currency transactions. The bank is particularly interested in understanding the factors driving user retention and engagement.

Our primary objective was to extract actionable insights, propose strategies to reduce churn, and identify opportunities to boost user involvement.

As a team, our role in this project was to:

- Explore user behavior and introduce a definition of churn
- Uncover patterns that lead to churn
- Act on this patters and give recommendations for targeted intervention to mitigate churn

The final deliverables consist of:

- A Logistic Regression Model (Logit Model) implemented in Python for churn prediction
- An interactive data report built with Google Looker Studio

## High-level Work Packages

1. Initial familiarization with the dataset
2. Ideation & set up of project in Notion
3. Selection of tech stack (SQL, dbt, BigQuery, Google Looker Studio, Python, Github)
4. EDA & Data Cleaning (SQL)
5. Data Enrichment & Feature Engineering (SQL & Python)
6. Creation of a user engagement scoring system and user segments based on it
7. Identifying retention levers and introducing recommendations to retain users
9. Documentation in Github & dbt

## Tech Stack
- **Data Warehouse:** BigQuery
- **Data Platform (Cleaning, Transformation, IDE):** dbt Cloud
- **Version Control:** Github
- **Business Intelligence & Visualization:** Google Looker Studio
- **Scripting/Modelling:** Google Colab (Python)

## Links
- Google Looker Studio: https://lookerstudio.google.com/reporting/ccb9c711-c443-4407-a669-6ab1fa7c7b71

## Data Sources

### 1. devices

A table of devices associated with a user

- brand: string corresponding to the phone brand
- user_id: string uniquely identifying the user

### 2. users

A table of user data

- user_id: string uniquely identifying the user
- birth_year: integer corresponding to the user’s birth year
- country: two letter string corresponding to the user’s country of residence
- city: two string corresponding to the user’s city of residence
- created_date: datetime corresponding to the user’s created date
- user_settings_crypto_unlocked: integer indicating if the user has unlocked the crypto
- plan: string indicating on which plan the user is on
- attributes_notifications_marketing_push: float indicating if the user has accepted to receive
- attributes_notifications_marketing_email: float indicating if the user has accepted to receive
- num_contacts: integer corresponding to the number of contacts the user has on neo bank
- num_referrals: integer corresponding to the number of users referred by the selected user
- num_successful_referrals: integer corresponding to the number of users successfully

### 3. notifications

A table of notifications that a user has received

- reason: string indicating the purpose of the notification
- channel: string indicating how the user has been notified
- status: string indicating the status of the notification
- user_id: string uniquely identifying the user
- created_date: datetime indicating when the notification has been sent

### 4. transactions

A table with transactions that a user made

- transaction_id: string uniquely identifying the transaction
- transactions_type: string indicating the type of the transaction
- transactions_currency: string indicating the currency of the transaction
- amount_usd: float corresponding to the transaction amount in USD
- transactions_state: string indicating the state of a transaction
  - COMPLETED - the transaction was completed and the user’s balance was changed)
  - DECLINED/FAILED - the transaction was declined for some reason, usually pertains to insufficient balance
  - REVERTED - the associated transaction was completed first but was then rolled back later in time potentially due      to customer reaching out to neo bank
- ea_cardholderpresence: string indicating if the card holder was present when the transaction
- ea_merchant_mcc: float corresponding to the Merchant Category Code (MCC) 
- ea_merchant_city: string corresponding to the merchant’s city
- ea_merchant_country: string corresponding to the merchant’s country
- direction: string indicating the direction of the transaction
- user_id: string uniquely identifying the user
- created_date: datetime corresponding to the transaction’s created date
