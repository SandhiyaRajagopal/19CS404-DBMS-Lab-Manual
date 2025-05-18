# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);

**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/a0f36994-99ca-4330-bb86-0b9f35bb31a3)


```sql
create table products(
product_id INTEGER primary key,
product_name  TEXT  not NULL,
list_price  DECIMAL (10, 2)  not NULL check(list_price>=discount and list_price>=0),
discount  DECIMAL (10, 2)  default 0 not NULL check(discount>=0));
```

**Output:**

![image](https://github.com/user-attachments/assets/a8e47517-938e-4e59-aa01-661c68bc2d56)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/66927636-924d-4304-a47b-d8f790b49051)


```sql
create table Employees(
EmployeeID INTEGER,
FirstName TEXT,
LastName TEXT,
HireDate DATE);
```

**Output:**

![image](https://github.com/user-attachments/assets/59623c11-e266-46d1-9ad5-9ff2667c462c)


**Question 3**
---
![image](https://github.com/user-attachments/assets/19331baa-57e0-4408-9119-111aaf0b9321)


```sql
create table Shipments(
ShipmentID INTEGER primary key,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
foreign key (SupplierID) references Suppliers(SupplierID),
foreign key (OrderID) references Orders(OrderID));
```

**Output:**

![image](https://github.com/user-attachments/assets/5eda27bc-173e-4842-a07d-1a2864edc535)


**Question 4**
---
![image](https://github.com/user-attachments/assets/4c37b7ba-b8b8-4bed-aa85-bd9b6016f382)


```sql
ALTER TABLE Companies
RENAME name to first_name;
ALTER TABLE Companies
ADD COLUMN mobilenumber number;
ALTER TABLE Companies
ADD COLUMN DOB Date;
```

**Output:**
![image](https://github.com/user-attachments/assets/aad866be-a4b8-421a-8cb1-378bd3abc979)

**Question 5**
---
![image](https://github.com/user-attachments/assets/58130e60-5996-4a69-aafa-6c21f4125d54)


```sql
Create table Employees(
EmployeeID primary key,
FirstName NOT NULL,
LastName NOT NULL,
Email unique,
Salary check(Salary>=0),
DepartmentID INTEGER,
foreign key (DepartmentID)references Departments(DepartmentID));
```

**Output:**

![image](https://github.com/user-attachments/assets/804180a8-9826-49d0-9624-55f7a2aacd3e)


**Question 6**
---
![image](https://github.com/user-attachments/assets/3cbc4029-1b33-411d-93a7-fbfda5112fe4)


```sql
ALTER TABLE Student_details
ADD column Country TEXT 
```

**Output:**

![image](https://github.com/user-attachments/assets/03ca895b-ed6f-40aa-892d-2fe9bfd63f53)


**Question 7**
---
![image](https://github.com/user-attachments/assets/2591f934-d473-43e0-915b-a74bdbea7f2c)


```sql
INSERT into Products
select ProductID, ProductName, Price, Stock
FROM Discontinued_products
```

**Output:**

![image](https://github.com/user-attachments/assets/0636b047-01d4-42bb-88aa-1fe220a3a995)


**Question 8**
---
![image](https://github.com/user-attachments/assets/873840a0-9bde-42be-958b-cdc5e7253b27)


```sql
create table orders(
ord_id TEXT NOT NULL check(length(ord_id) = 4),
item_id TEXT NOT NULL,
ord_date DATE,
ord_qty INTEGER,
cost INTEGER,
primary key (item_id,ord_date));
```

**Output:**

![image](https://github.com/user-attachments/assets/2eb76233-4400-487f-924a-2230db872fa3)


**Question 9**
---
![image](https://github.com/user-attachments/assets/0a815f65-bfc1-4006-bca7-0a51b7f41c50)


```sql
INSERT into Products(ProductID,Name,Category,Price,Stock)
values (101,'Laptop','Electronics',1500,50);
```

**Output:**

![image](https://github.com/user-attachments/assets/3a9543a7-c222-4f98-9e4e-a4d7700faab1)


**Question 10**
---
![image](https://github.com/user-attachments/assets/7b1e96a7-073b-43d3-9939-5ebcad86798d)


```sql
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values (2,'John Smith','Developer','IT',75000);
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values (3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

![image](https://github.com/user-attachments/assets/4cb53599-92c8-4d70-9ac8-24a14e9869ea)

```
## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
