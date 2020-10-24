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
## UC2_Create addressBook table in the Payroll_Service database
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

## UC3_Insert new Contacts to AddressBook

```
       INSERT INTO Address_book(firstName ,lastName , address , city ,state,zip,phoneNumber,email) VALUES
    -> ('Ashwini' ,'jadi' ,'kukatpally','Hyderabad','TS',541545,789456123,'ash@gmail.com'),
    -> ('Sony' ,'j' ,'kazipet','Warangal','Telangana',500545,722561230,'sony@gmail.com'),
    -> ('Arun' ,'jadi','kukatpally','Hyderabad' ,'Telangana',541545,998456123,'arun@gmail.com');
```

### see database table data using data base query

```
SELECT * FROM Address_book;
```

## UC4_Edit Contacts in AddressBook using name

```
 update Address_book set state='Telangana' where firstName ='Ashwini';
```

### see updated database table data using data base query

```
SELECT * FROM Address_book;
```

## UC5_Delete Contacts in AddressBook using name

```
 DELETE FROM Address_book WHERE firstName='Arun';
```
### see updated database table data using data base query

```
SELECT * FROM Address_book;
```

## UC6_Retrieve Person belonging to a City or State from the Address Book

### to view data of person belonging to city hyderabad using data base query

```
SELECT * FROM Address_book WHERE city='Hyderabad';
```

### to view data of person belonging to city Warangal using data base query

```
 SELECT * FROM Address_book WHERE city='Warangal';
```

### to view data of person belonging to state Telangana using data base query

```
SELECT * FROM Address_book WHERE state='Telangana';
```

## UC7_ Size of Addressbook by City and State

```
SELECT city,COUNT(city) FROM Address_book GROUP BY city;
```

```
SELECT state,COUNT(state) FROM Address_book GROUP BY state;
```
## UC8_Retrieve entries sorted alphabetically by Person’s name for a given city

### to sort person names belonging to city hyderabad using data base query

```
 SELECT * FROM Address_book WHERE city='Hyderabad' ORDER BY firstName;
```

### to sort person names belonging to city Warangal using data base query

```
 SELECT * FROM Address_book WHERE city='Warangal' ORDER BY firstName;
```
## UC9_identify each Address Book with name and Type.

### Altering table and updating addressBookName and type

```
ALTER TABLE Address_Book ADD addressBookName VARCHAR(150) AFTER email;
update Address_book set addressBookName='Personal' where firstName ='Ashwini';
update Address_book set addressBookName='Business' where firstName ='Arun';
ALTER TABLE Address_Book ADD Type VARCHAR(150) AFTER addressBookName;
update Address_book set Type='Family' where firstName ='Ashwini';
update Address_book set Type='Friends' where firstName ='Sony';
```
## UC10 Get Number of Persons by type

``` 
SELECT Type,COUNT(Type) FROM Address_book GROUP BY Type;
``` 