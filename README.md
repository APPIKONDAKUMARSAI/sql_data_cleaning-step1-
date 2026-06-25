# sql_data_cleaning-step1-

# SQL Data Cleaning: Finding and Replacing NULL Values

## Project Overview

This project demonstrates how SQL can be used to identify, investigate, and replace missing values in a dataset.

The objective was to locate records with missing customer IDs and update them using SQL statements.

---

## Problem Statement

Missing values can reduce data quality and affect reporting and analytics. This project focuses on identifying NULL customer IDs and replacing them with valid values.

---

## Step 1: Identify NULL Values

```sql
SELECT *
FROM accessories_sales
WHERE customer_id IS NULL;
```

---

## Step 2: Review Affected Records

Three records were found with missing customer IDs.

---

## Step 3: Update Individual Records

```sql
UPDATE accessories_sales
SET customer_id = 'CUST101'
WHERE customer_name = 'Joseph Morales';
```

---

## Step 4: Update Multiple Records Using CASE

```sql
UPDATE accessories_sales
SET customer_id =
CASE
    WHEN customer_name = 'Joseph Morales' THEN 'CUST101'
    WHEN customer_name = 'Customer2' THEN 'CUST102'
    WHEN customer_name = 'Customer3' THEN 'CUST103'
END
WHERE customer_id IS NULL;
```

---

## Step 5: Validate Results

```sql
SELECT *
FROM accessories_sales
WHERE customer_id IS NULL;
```

---

## Key Learnings

* Identified missing values using WHERE conditions.
* Updated records using SQL UPDATE statements.
* Applied CASE expressions for bulk updates.
* Performed validation queries after cleaning.
* Improved data quality for downstream analysis.

---

## Skills Used

* SQL
* Data Cleaning
* Data Validation
* CASE Statements
* UPDATE Queries
* Data Quality Management

---

## Business Impact

Accurate and clean data improves reporting quality, reduces analytical errors, and supports reliable business decisions.
