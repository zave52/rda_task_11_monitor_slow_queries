# Use slow query log 

The MySQL slow query log can be very helpful when dealing with the database optimisation, and today you will practice analysing it! 

In this task you will work with a `ShopDB` database, which has 2 tables: 
- `Products1` - uses InnoDB database engine. 
- `Products2` - uses MyISAM database engine. 

## Prerequisites

1. Install and configure a MySQL database server on a Virtual Machine.
2. Fork this repository.

## Requirements

In this task, you will need to analyse the MySQL slow query log and copare the read operation performance for 2 database engines - InnoDB and MyIsam:  

1. Connect to your database server virtual machine via SSH, and enable slow query log by updating the mysql configuration file. After the config file update, make sure to restart the mysqsl service using systemctl. 
2. Run the script `task.sql`, which creates the database and populates test data on your database server. 
3. Close database connection from the MySQL Workbench.
4. Connect to your server using **mysql client on your virtual machine** and run 2 sample queries:

    - "Query 1": 
        ```
            select * from Products1 where Name = "AwersomeProduct42";
        ```
    - "Query 2": 
        ```
            select * from Products2 where Name = "AwersomeProduct42";
        ```
Run each query multiple times (at least 10 times). 

If you will run queries from MySQL Workbench, there will be a lot of additional queries in the log, and will be hard to analyse it, so make sure to use terminal client (you already have one installed on the virtual machine, where database server is running). 
5. Analyse the slow query log and identify the query, which works slower (in average) than the other one. 
6. Edit the `task.sql` file - remove the code for creation of table and data, which is used by the "slow" query. Submit your solution for a review.
