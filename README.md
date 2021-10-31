# SQL fundamentals

### Creating a table
''  
create table customer (  
cust_id int primary key,  
age int,  
location varchar(20),  
gender varchar(20)  
);  
''  
  
### Creating a table with foreign key
''    
create table orders (  
order_id int primary key,  
date date,  
amount decimal(5,2),  
cust_id int,  
foreign key (cust_id) references customer(cust_id)  
on delete cascade  
);
''  
