# `Bank Database`
CREATE DATABASE MAIN_BANK_DATABASE;
USE MAIN_BANK_DATABASE;

CREATE TABLE BRANCH(
BRANCH_ID VARCHAR(10) PRIMARY KEY,
BRANCH_NAME VARCHAR(20),
BRANCH_CITY VARCHAR(20),
ASSETS DECIMAL(10,2)
);

CREATE TABLE ACCOUNT(
ACCOUNT_NUMBER INT PRIMARY KEY,
BRANCH_ID VARCHAR(10),--FOREIGN KEY
BALANCE DECIMAL(10,2)
);

CREATE TABLE DEPOSITER(
CUSTOMER_ID INT,--FOREIGN KEY
ACCOUNT_NUMBER INT--FOREIGN KEY
);

CREATE TABLE CUSTOMER(
CUSTOMER_ID INT PRIMARY KEY,
CUSTOMER_NAME VARCHAR(20),
CUSTOMER_STREET VARCHAR(20),
CUSTOMER_CITY VARCHAR(20)
);


CREATE TABLE LOAN(
LOAN_NUMBER INT PRIMARY KEY,
BRANCH_ID VARCHAR(10),--FOREIGN KEY
AMOUNT DECIMAL(10,2)
);

CREATE TABLE BORROWER(
CUSTOMER_ID INT,--FOREIGN KEY
LOAN_NUMBER INT--FOREIGN KEY
);

SELECT * FROM BRANCH;
SELECT * FROM ACCOUNT;
SELECT * FROM DEPOSITER;
SELECT * FROM CUSTOMER;
SELECT * FROM LOAN;
SELECT * FROM BORROWER;

ALTER TABLE DEPOSITER ADD FOREIGN KEY(CUSTOMER_ID) REFERENCES CUSTOMER(CUSTOMER_ID);

ALTER TABLE BORROWER ADD FOREIGN KEY(CUSTOMER_ID) REFERENCES CUSTOMER(CUSTOMER_ID);

ALTER TABLE 







DROP TABLE BRANCH;
DROP TABLE ACCOUNT;
DROP TABLE DEPOSITER;
