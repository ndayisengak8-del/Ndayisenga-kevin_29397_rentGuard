 ## RentGuard Rwanda: Rental Billing and Rent Arrears Tracker

**Student Name:** Ndayisenga Kevin  
**Student ID:** 29397  
**Course:** INSY 8311 – Database Development with PL/SQL  
**Instructor:** Eric Maniraguha  
**Institution:** Adventist University of Central Africa (AUCA)  
**Academic Year:** 2026–2027 



## 1. Introduction

RentGuard Rwanda is a database project designed to help landlords manage rental properties and keep track of rent payments. The system will be developed using Oracle Database and PL/SQL.

The main purpose of the project is to make rental payment management easier and more organized. Instead of depending on notebooks or phone messages, landlords will be able to store rental information in one database and check payment records whenever needed.

The system will also help landlords identify tenants who have not paid rent on time and calculate the amount of money that is still outstanding.

## 2. Problem Statement

Many small landlords in Kigali manage their rental properties using notebooks, paper records, or phone messages. Although this method may work when there are only a few tenants, it becomes difficult when the number of properties and tenants increases.

Landlords may forget to record payments, lose important information, or make mistakes when calculating unpaid rent. It can also be difficult to identify tenants who have made partial payments or whose rental agreements have expired.

Another challenge is managing vacant units and avoiding situations where the same unit is rented to more than one tenant during the same period.

These problems show the need for a database system that can organize rental information, record payments, and help landlords monitor unpaid rent.

## 3. Project Objectives

### 3.1 Main Objective

To develop an Oracle database system using PL/SQL that manages rental agreements, records rent payments, calculates outstanding balances, and identifies overdue payments automatically.

### 3.2 Specific Objectives

1. Design a database to store information about landlords, properties, rental units, tenants, leases, invoices, and payments.
2. Organize the database tables and relationships according to Third Normal Form (3NF).
3. Use PL/SQL procedures and functions to calculate rent invoices, late fees, and tenant balances.
4. Use database triggers to prevent overlapping leases and payments that exceed the amount due.
5. Create audit records to keep track of important changes made to invoices and payments.
6. Use cursors to process active leases and generate monthly rent invoices.
7. Use Oracle DBMS_SCHEDULER to check overdue invoices and prepare monthly arrears reports.

## 4. Proposed Solution

RentGuard Rwanda will provide an organized way to manage rental activities through an Oracle database.

The system will store information about landlords, their properties, rental units, tenants, and rental agreements. When a tenant rents a unit, the system will keep the lease information and use it to manage monthly rent invoices.

When a tenant makes a payment, the payment will be recorded in the database. The system will calculate how much has been paid and how much remains unpaid.

For example, if a tenant is required to pay 200,000 RWF and pays 150,000 RWF, the remaining balance will be 50,000 RWF.

The system will also check overdue invoices and calculate late fees according to the rules defined in the database.

## 5. Data Source

The main dataset selected for this project is the **House Rent Prediction Dataset**, available on Kaggle.

**Dataset Name:** House Rent Prediction Dataset  
**Author:** Sourav Banerjee  
**Source:** Kaggle  
**Link:** https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset

The dataset contains rental listing information such as:

- City or location.
- Size of the property.
- Number of bedrooms.
- Furnishing status.
- Monthly rental price.

This information will help provide sample property and rental price data for the project.

However, the dataset contains rental listings from India and does not provide actual Kigali landlord, tenant, lease, or payment records. Therefore, additional fictional sample records will be created where necessary to test the complete database system.

Any fictional records will be clearly identified as test data. They will not be presented as actual rental transactions from Rwanda.

## 6. Planned Database Tables

The project will use the following ten main tables:

### 6.1 LANDLORD

Stores information about landlords who own rental properties.

### 6.2 PROPERTY

Stores information about properties, including their names, locations, and ownership.

### 6.3 UNIT

Stores details about individual rental units within a property, including unit number, size, and rental status.

### 6.4 TENANT

Stores information about tenants who rent the available units.

### 6.5 LEASE

Stores rental agreements between tenants and landlords, including start dates, end dates, and monthly rent.

### 6.6 RENT_INVOICE

Stores rent invoices generated for tenants and their payment due dates and amounts.

### 6.7 PAYMENT

Stores payments made by tenants, including payment dates and amounts.

### 6.8 LATE_FEE_RULE

Stores the rules used to calculate additional charges when rent is paid late.

### 6.9 ARREARS_ALERT

Stores alerts about invoices that have not been fully paid by their due dates.

### 6.10 AUDIT_LOG

Records important database changes, especially changes involving rent invoices and payments.

## 7. Planned PL/SQL Features

PL/SQL will be used to manage the main operations of the database and enforce the project's business rules.

### 7.1 Procedures

- `create_lease`: Creates a new rental agreement after checking the required information.
- `record_payment`: Records a tenant's rent payment and updates the payment information.

### 7.2 Functions

- `calc_late_fee`: Calculates the late payment charge based on the applicable rule.
- `get_tenant_balance`: Calculates the remaining amount a tenant owes.

### 7.3 Cursor

A cursor will process active rental agreements. It will help generate monthly rent invoices for tenants whose leases are active.

### 7.4 Triggers

Triggers will automatically enforce important rules in the database. They will prevent overlapping leases for the same unit and prevent payments that exceed the outstanding invoice amount.

Audit triggers will also record important changes to invoices and payments.

### 7.5 Package

A package named `rent_pkg` will organize related rental procedures, functions, and other PL/SQL operations in one place.

### 7.6 Exception Handling

Exception handling will manage errors such as:

- Trying to rent a unit that is already occupied.
- Entering an invalid payment amount.
- Recording a payment for an unknown tenant.
- Trying to record a payment that exceeds the amount due.

### 7.7 DBMS_SCHEDULER

Oracle DBMS_SCHEDULER will be used to run scheduled database tasks.

A nightly task will check invoices that have passed their due dates, update their overdue status, calculate applicable late fees, and create alerts in the ARREARS_ALERT table.

A monthly task will prepare a report showing unpaid rent and outstanding balances.

## 8. Project Innovation – Smart Automation

The main innovation of RentGuard Rwanda is **Smart Automation** using Oracle DBMS_SCHEDULER.

Instead of requiring landlords to check every invoice manually, the system will perform some rental management activities automatically.

The innovation will work in the following way:

1. **Automatic overdue checking:** Every night, a scheduled database job will check invoices that have passed their payment due dates.
2. **Automatic status updates:** Invoices that remain unpaid after their due dates will be marked as overdue.
3. **Late fee calculation:** The system will calculate applicable late fees using the rules stored in the LATE_FEE_RULE table.
4. **Automatic alerts:** The system will create records in the ARREARS_ALERT table to identify tenants with unpaid rent.
5. **Monthly reporting:** A scheduled monthly task will prepare a report showing rent collected, unpaid invoices, and outstanding balances.

**Innovation technology:** Oracle DBMS_SCHEDULER and PL/SQL.

This feature will reduce manual work, make it easier to identify unpaid rent, and help landlords follow up on overdue payments. The business rules and calculations will remain inside the Oracle database.

## 9. Expected Results

After completing the project, RentGuard Rwanda is expected to:

1. Provide an organized database for rental property information.
2. Make it easier to record and retrieve tenant payment records.
3. Calculate rent invoices and outstanding balances automatically.
4. Identify tenants with overdue payments.
5. Reduce mistakes caused by manual calculations.
6. Prevent overlapping leases and invalid payments.
7. Keep records of important database changes.
8. Produce useful monthly rent and arrears reports.

## 10. Project Limitations

The selected Kaggle dataset contains rental listings from India rather than Rwanda. It also does not include actual tenant, lease, and payment histories.

For this reason, fictional sample data will be needed to test some parts of the system.

The first version of RentGuard Rwanda will focus mainly on Oracle Database and PL/SQL operations. Features such as online rent payments, SMS notifications, and a web interface may be considered for future development.



## 11. References

The research sources used for this project are recorded in:

`docs/research/research_log.md`