# SQL

## SQL theory terms

## 4 Categories

DML Data Manipulation Language

    Basic Queries : SELECT, INSERT, UPDATE, DELETE

DDL Data Definition Language

    Create Data Structures ie. Database, Table
        CREATE/DROP     : database and table ie. add or remove completely
        ALTER           : Table ie. add key/column
        TRUNCATE        : remove

DCL Data Control Language

    Permissions         : GRANT/REVOKE

TCL Transaction Control Language

    Group of transactions TOGETHER
        1) COMMIT (all of the transactions in the group as a whole eg. ATM Withdrawal is either ALL COMMIT or nothing)
        2) ROLLBACK to a given point e.g. Start of transaction group
        3) SAVEPOINT : Midway point of saving data progression throughout a series of transactions

## Basic Commands

```sql
use db01    // bring into scope
go
drop database db01   //risk of exeption if no db present
drop database if exists db01
go
create database db01
go
```

## Data Types

    INT
    TINYINT
    CHAR(5)                 FIXED WIDTH IE CUSTOMERID='ALFKI', 8 BIT
    VARCHAR(50)             VARIABLE WIDTH UP TO 50 MAX, 8 BIT
    BIT                     0,1 OR NULL
    NCHAR/NVARCHAR          UNICODE IE 16 BIT
    TIME/DATETIME
    BLOB/BINARY             BINARY LARGE OBJECT E.g Movie.mov
    FLOAT
    DECIMAL

## Getting Help

```sql
# meta data about your table
SP_HELP
```

## Top

```sql
select top 5 * from customers order by CustomerID desc;
```

## Select where ... and...

```sql
select * from Products
where UnitsInStock < 10 and Discontinued = 0
order by UnitsInStock desc;
```

## Operators

    AND OR
    <> or !=
    > < >= <=

## select distinct

```sql
select country from customers order by country;
select distinct country from customers order by country;
```

## Contains ==> 'like' keyword

```sql
--Does it contain abc?
like '%abc%'
--Start
like 'abc%'
--End
like '%abc'
--Does NOT contain
not like '%abc%'
```

## Multiple Exact hits - use 'IN' keyword

```sql
select * from employees where region in('wa','bc')
```

## Between A and B

```sql
select * from products where unitprice between 10 and 20
```

## Cumulative Functions

    Sum, Count, Average, Min, Max

```sql
select count(city) from Customers;
select AVG(UnitPrice) as AVGPrice, MIN(UnitPrice) as MINPrice, MAX(UnitPrice) as MAXPrice from Products
select SUM(Unitsinstock) as TotalStock from Products;
```

## Maths

### Easy to do mathematical operations inside the query

### e.g. Product discount

    £100 with 10% discount ==> £90

    //Get product, price, discount, price after discount

## charindex

    charindex(' ', 'BRZ 4AZ') returns 5, the index of the space

    LTRIM removes leading spaces

    Replace('some text', 'text', 'cheese') returns 'some cheese'

    UPPER

    lower

## case ... when ... else

    case
    when (x>10)
    else 'young'
    end
    as 'how old are you?'

## group by... having

```sql
select 'GROUP BY';
select SupplierID, sum(UnitsOnOrder) as 'Total Units in Order' from products
group by SupplierID
having sum(UnitsOnOrder) = 0
order by 'Total Units in Order' desc;
```

### Order by only works for fields which exist initially but not on commulative fields

    We can find the sum of all units in stock per product category but this field does not exist initially so we can't order by it.

    Cumulative fields ie SUM/MAX/MIN/AVG/COUNT
    Group by... (selecting into branches)
    Having... (same as order by)

### Order Matters

    SELECT DISTINCT FROM WHERE...
    GROUP BY... HAVING...
    ORDER BY...

## As select ... as

    SELECT (calculation) as 'columnname'
    AS IS OPTIONAL
    SELECT (calculation) 'columnname'

## Joins

    Inner join = Left join

        table 1         table 2
        tableID-1       tableID-2

        All from table 1, plus matching from table 2 where there is a match

### Outer Joins

    All from table 2 plus matching records in table 1

### Full Join

    All from table 1 plus all from table 2 and null if no matching record in table 2

### Sub queries

    A Query within a Query : useful for long queries

```sql
-- FIND CUSTOMERS WITH NO ORDERS
select ... from ... where (select ... from ...)
select * from customers where CustomerID not in (select customerID from orders)
```

### Extra Terms

IDENTITY(1,1)           Auto-increment starting at value 1 and jump by 1 each line
IDENTITY                Auto-increment
PRIMARY KEY CLUSTERED   