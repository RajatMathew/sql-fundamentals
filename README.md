# SQL fundamentals

## Creating a table
  
``
create table customer (
cust_id int primary key,
age int,
location varchar(20),
gender varchar(20)
);
``
  

## Creating a table with foreign key  
  
`` 
create table orders (
order_id int primary key,
date date,
amount decimal(5,2),
cust_id int,
foreign key (cust_id) references customer(cust_id)
on delete cascade
);
``
  
Foreign key is what relates a table to another one. Foreign key contains the primary key of another table.  
  
The cust_id column in the orders table is a foreign key and related the orders table to the customer table. We specify this condition while creating the table.  
  
In the last line, we specify another condition with “on delete cascade” phrase. It tells MySQL what to do when a row in the customer table is deleted. Each row in the orders table belongs to a customer. Each row in the customer table contains a unique customer id and represents a customer. If a row in the customer table is removed, it means we do not have that customer any more. As a result, the orders that belonged to that customer do not have an associated customer id anymore. “On delete cascade” indicates that orders that do not have an associated customer id will also be deleted.  


