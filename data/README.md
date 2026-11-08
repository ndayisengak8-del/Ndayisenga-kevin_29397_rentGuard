RentGuard Rwanda – Data README

 1. Introduction

This folder contains the data used for the RentGuard Rwanda project.

The project is designed to help landlords manage rental properties, tenants, rent payments, and unpaid rent using Oracle Database and PL/SQL.

The data will be used to test the database and check whether the system works correctly.

 2. Data Source

The main dataset selected for this project is the **House Rent Prediction Dataset** from Kaggle.

**Dataset name:** House Rent Prediction Dataset

**Author:** Sourav Banerjee

**Source:** Kaggle

**Dataset link:** https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset

The dataset contains information about rental properties, such as:

- City or location
- House size
- Number of bedrooms
- Furnishing status
- Rental price

 3. How the Data Will Be Used

The dataset will help me understand rental property information and work with rental prices.

However, it does not contain all the information required for RentGuard Rwanda. For example, it does not provide actual Kigali landlords, tenants, rental agreements, invoices, or payment histories.

For this reason, I may create sample records for testing the following database tables:

- LANDLORD
- PROPERTY
- UNIT
- TENANT
- LEASE
- RENT_INVOICE
- PAYMENT
- LATE_FEE_RULE
- ARREARS_ALERT
- AUDIT_LOG

Any records created for testing will be clearly identified as fictional sample data. They will not be presented as real rental transactions from Kigali.

 4. Data Preparation

Before loading data into Oracle Database, I will:

1. Download the dataset from Kaggle.
2. Check the columns and available records.
3. Identify the information relevant to rental properties.
4. Check for missing or incorrect values.
5. Prepare the data for loading into Oracle tables.
6. Create additional sample records where necessary for testing.

 5. Data Privacy

The project will avoid using personal information belonging to real tenants or landlords without permission.

Sample records will be used for testing when actual rental information is not available.

 6. Dataset Limitations

The selected dataset has some limitations:

- It contains rental listings from India, not Rwanda.
- It does not include actual tenant payment histories.
- It does not contain rental agreements or unpaid rent records.
- Additional sample data will be needed to test the complete system.

These limitations will be considered when developing and evaluating the project.

 7. Dataset Licence

The dataset is obtained from Kaggle. Its licence and permitted use will be checked before including the data in the project.

 8. Conclusion

The dataset will provide useful rental property information for the RentGuard Rwanda project. Additional clearly labelled sample records will help test rent invoices, payments, balances, late fees, and overdue payment alerts in Oracle Database.
