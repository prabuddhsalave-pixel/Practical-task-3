# Banking DB - Complete SQL Practical (Task 1–60)

## Part A - Database & Table Creation

**Task 1: Create the database**
```sql
CREATE DATABASE banking_db;
```

**Task 2: Use/select the database**
```sql
USE banking_db;
```

**Task 3: Create the accounts table**
```sql
CREATE TABLE accounts (
    account_id     INT PRIMARY KEY,
    account_number VARCHAR(20),
    customer_name  VARCHAR(100),
    account_type   VARCHAR(30),
    branch         VARCHAR(50),
    city           VARCHAR(50),
    balance        DECIMAL(12,2),
    credit_score   INT,
    status         VARCHAR(20),
    opened_date    DATE
);
```

**Task 4: Display the structure of the accounts table**
```sql
DESCRIBE accounts;
```

**Task 5: Display all tables available inside banking_db**
```sql
SHOW TABLES;
```

---

## Part B - INSERT Operations

**Task 6:**
```sql
INSERT INTO accounts VALUES (1001, 'ACC10001', 'Aarav Sharma', 'Savings', 'FC Road', 'Pune', 85000, 780, 'Active', '2025-01-15');
```

**Task 7:**
```sql
INSERT INTO accounts VALUES (1002, 'ACC10002', 'Priya Patil', 'Current', 'Andheri', 'Mumbai', 145000, 810, 'Active', '2024-11-20');
```

**Task 8:**
```sql
INSERT INTO accounts VALUES (1003, 'ACC10003', 'Rohan Joshi', 'Savings', 'Baner', 'Pune', 42000, 735, 'Active', '2026-02-10');
```

**Task 9:**
```sql
INSERT INTO accounts VALUES (1004, 'ACC10004', 'Sneha Kulkarni', 'Salary', 'Nashik Road', 'Nashik', 67000, 760, 'Active', '2025-08-05');
```

**Task 10:**
```sql
INSERT INTO accounts VALUES (1005, 'ACC10005', 'Vikram Deshmukh', 'Savings', 'Camp', 'Pune', 18500, 690, 'Dormant', '2023-06-18');
```

**Task 11:**
```sql
INSERT INTO accounts VALUES (1006, 'ACC10006', 'Neha More', 'Current', 'Thane', 'Mumbai', 225000, 825, 'Active', '2024-03-12');
```

---

## Part C - DQL / SELECT Queries

**Task 12: Display all records**
```sql
SELECT * FROM accounts;
```

**Task 13: customer_name and account_number**
```sql
SELECT customer_name, account_number FROM accounts;
```

**Task 14: customer_name, account_type, balance and status**
```sql
SELECT customer_name, account_type, balance, status FROM accounts;
```

**Task 15: All Savings account holders**
```sql
SELECT * FROM accounts WHERE account_type = 'Savings';
```

**Task 16: All customers from Pune**
```sql
SELECT * FROM accounts WHERE city = 'Pune';
```

**Task 17: Balance greater than 50000**
```sql
SELECT * FROM accounts WHERE balance > 50000;
```

**Task 18: Balance less than or equal to 50000**
```sql
SELECT * FROM accounts WHERE balance <= 50000;
```

**Task 19: Balance between 50000 and 200000**
```sql
SELECT * FROM accounts WHERE balance BETWEEN 50000 AND 200000;
```

**Task 20: credit_score >= 750**
```sql
SELECT * FROM accounts WHERE credit_score >= 750;
```

**Task 21: Only Active accounts**
```sql
SELECT * FROM accounts WHERE status = 'Active';
```

**Task 22: Status is Dormant or Closed**
```sql
SELECT * FROM accounts WHERE status = 'Dormant' OR status = 'Closed';
```

**Task 23: Pune AND status = Active**
```sql
SELECT * FROM accounts WHERE city = 'Pune' AND status = 'Active';
```

**Task 24: Mumbai OR Nashik**
```sql
SELECT * FROM accounts WHERE city = 'Mumbai' OR city = 'Nashik';
```

**Task 25: account_type Savings OR Salary**
```sql
SELECT * FROM accounts WHERE account_type = 'Savings' OR account_type = 'Salary';
```

**Task 26: Balance NOT BETWEEN 25000 AND 100000**
```sql
SELECT * FROM accounts WHERE balance NOT BETWEEN 25000 AND 100000;
```

**Task 27: customer_name starts with 'A'**
```sql
SELECT * FROM accounts WHERE customer_name LIKE 'A%';
```

**Task 28: customer_name ends with 'a'**
```sql
SELECT * FROM accounts WHERE customer_name LIKE '%a';
```

**Task 29: branch contains the word 'Road'**
```sql
SELECT * FROM accounts WHERE branch LIKE '%Road%';
```

**Task 30: Top 3 accounts having the highest balance using LIMIT**
```sql
SELECT * FROM accounts ORDER BY balance DESC LIMIT 3;
```

**Task 31: First 5 accounts using LIMIT 5**
```sql
SELECT * FROM accounts LIMIT 5;
```

**Task 32: 3 accounts starting from the 4th record using LIMIT 3, 3**
```sql
SELECT * FROM accounts LIMIT 3, 3;
```

**Task 33: Active Savings accounts from Pune with balance > 50000**
```sql
SELECT * FROM accounts WHERE city = 'Pune' AND account_type = 'Savings' AND status = 'Active' AND balance > 50000;
```

**Task 34: Pune, Mumbai or Nashik with credit_score >= 750**
```sql
SELECT * FROM accounts WHERE city IN ('Pune', 'Mumbai', 'Nashik') AND credit_score >= 750;
```

**Task 35: balance > 100000 AND credit_score >= 800**
```sql
SELECT * FROM accounts WHERE balance > 100000 AND credit_score >= 800;
```

**Task 36: balance between 50000 and 150000 OR credit_score > 800**
```sql
SELECT * FROM accounts WHERE (balance BETWEEN 50000 AND 150000) OR credit_score > 800;
```

**Task 37: status Active AND account_type NOT Current**
```sql
SELECT * FROM accounts WHERE status = 'Active' AND account_type != 'Current';
```

**Task 38: customer_name contains 'ar'**
```sql
SELECT * FROM accounts WHERE customer_name LIKE '%ar%';
```

---

## Part D - UPDATE Operations

**Task 39: Aarav Sharma's balance 85000 → 95000**
```sql
UPDATE accounts SET balance = 95000 WHERE customer_name = 'Aarav Sharma';
```

**Task 40: Vikram Deshmukh's status Dormant → Active**
```sql
UPDATE accounts SET status = 'Active' WHERE customer_name = 'Vikram Deshmukh';
```

**Task 41: Rohan Joshi's credit_score 735 → 755**
```sql
UPDATE accounts SET credit_score = 755 WHERE customer_name = 'Rohan Joshi';
```

**Task 42: Sneha Kulkarni's branch Nashik Road → College Road**
```sql
UPDATE accounts SET branch = 'College Road' WHERE customer_name = 'Sneha Kulkarni';
```

**Task 43: Priya Patil's account_type Current → Premium Current**
```sql
UPDATE accounts SET account_type = 'Premium Current' WHERE customer_name = 'Priya Patil';
```

**Task 44: Increase balance of account_id 1006 by 25000**
```sql
UPDATE accounts SET balance = balance + 25000 WHERE account_id = 1006;
```

**Task 45: Increase balance of all Savings accounts by 5000**
```sql
UPDATE accounts SET balance = balance + 5000 WHERE account_type = 'Savings';
```

**Task 46: Update Pune branch locations to city = 'Pune City'**
```sql
UPDATE accounts SET city = 'Pune City' WHERE city = 'Pune';
```

**Task 47: Increase credit_score by 10 for Active accounts with credit_score below 750**
```sql
UPDATE accounts SET credit_score = credit_score + 10 WHERE status = 'Active' AND credit_score < 750;
```

**Task 48: Status to Dormant for balance below 20000**
```sql
UPDATE accounts SET status = 'Dormant' WHERE balance < 20000;
```

---

## Part E - DELETE Operations

**Task 49: Delete account_id = 1005**
```sql
DELETE FROM accounts WHERE account_id = 1005;
```

**Task 50: Delete account_number = 'ACC10004'**
```sql
DELETE FROM accounts WHERE account_number = 'ACC10004';
```

**Task 51: Delete all accounts with status = 'Closed'**
```sql
DELETE FROM accounts WHERE status = 'Closed';
```

**Task 52: Delete accounts where balance < 10000 OR credit_score < 600**
```sql
DELETE FROM accounts WHERE balance < 10000 OR credit_score < 600;
```

**Task 53: Delete accounts from a selected city where status is Dormant**
```sql
DELETE FROM accounts WHERE city = 'Pune' AND status = 'Dormant';
```
*(Replace 'Pune' with whichever city you want to target.)*

---

## Part F - ALTER TABLE / DDL Practice

**Task 54: Add email column**
```sql
ALTER TABLE accounts ADD COLUMN email VARCHAR(100);
```

**Task 55: Add mobile column**
```sql
ALTER TABLE accounts ADD COLUMN mobile VARCHAR(15);
```

**Task 56: Change size of branch to VARCHAR(100)**
```sql
ALTER TABLE accounts MODIFY COLUMN branch VARCHAR(100);
```

**Task 57: Rename customer_name to name**
```sql
ALTER TABLE accounts RENAME COLUMN customer_name TO name;
```

**Task 58: Delete mobile column**
```sql
ALTER TABLE accounts DROP COLUMN mobile;
```

---

## Part G - Table-Level DDL Practice

**Task 59: Add account_category column, update at least two records, then rename table to bank_accounts**
```sql
ALTER TABLE accounts ADD COLUMN account_category VARCHAR(30);

UPDATE accounts SET account_category = 'Premium' WHERE account_id = 1002;
UPDATE accounts SET account_category = 'Standard' WHERE account_id = 1001;

RENAME TABLE accounts TO bank_accounts;
```

**Task 60: Display structure of bank_accounts, then TRUNCATE, then DROP the table**
```sql
DESCRIBE bank_accounts;

TRUNCATE TABLE bank_accounts;

DROP TABLE bank_accounts;
```
