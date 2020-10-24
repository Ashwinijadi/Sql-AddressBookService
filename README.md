# Sql-AddressBookService

## UC1 - Create database for addressbook service

```
create database Address_Book_Service;
```
### see all databases created using data base query

```
 show databases;
```
### go to database created using data base query

```
use Address_Book_Service;
```
## UC2_Create Employee Payroll table in the Payroll_Service database
```
 CREATE TABLE Address_book
    -> (
    -> firstName        VARCHAR(150) NOT NULL,
    -> lastName         VARCHAR(150) NOT NULL,
    -> address          VARCHAR(250) NOT NULL,
    -> city             VARCHAR(150) NOT NULL,
    -> state            VARCHAR(150) NOT NULL,
    -> zip              int(10)      NOT NULL,
    -> phoneNumber      int(15)      NOT NULL,
    -> email            VARCHAR(250) NOT NULL,
    -> PRIMARY KEY      (firstName)
    -> );
```

### see database table created using data base query

```
DESCRIBE Address_book;
```