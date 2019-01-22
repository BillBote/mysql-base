# mysql-base
learn MySQL at the base level

I decided to learn some MySQL by my self and this project is a notebook for myself
## 1. about database
column: column represents a certain type of information, like . One column has one datatype

row: store a record. A record consists of different kind of information

primary key: in one column, to distinguish different rows
## 2. about MySQL
MySQL is the database based on the form client-server. We visit server to visit database. Our orders are given to server and operate on database.

download MySQL Server: download MySQL Community Server from https://dev.mysql.com/downloads/mysql/

download MySQL Workbench: download MySQL Workbench from https://dev.mysql.com/downloads/workbench/

MySQL Server is the server we put order in and is the direct window we could operate on. I am a mac user and I use it through terminal.

MySQL Workbench provides DBAs and developers an integrated tools environment. It looks like an IDE and is more convenient to use than Server itself.

MySQL use language SQL and this is a quite simple and easy-understanding language. The most simple and basic ones is those to select and show the database. But first we must understand the structure of databases in MySQL. Data are stored as tables in databases. Thus the following orders are clear. Note that SQL is not case-sensitive and each order should end with ';' or '\g'.

select a database: USE database(name);

see databases: SHOW databases;

see data in database: SHOW tables;

see specific columns: SHOW COLUMNS FROM table(name);

## 3. Index--SELECT
Order Select choose specific columns from tables, like SELECT columnname FROM tablename. This is quite obvious and simple. Orders below:

select one column: SELECT column-name FROM table-name;

select multiple columns: SELECT column-name1,column-name2,... FROM table-name;

select all columns: SELECT * FROM table-name;

select columns with different row values(all rows with unique values): SELECT DISTINCT column-name FROM table-name;

select columns and output limited amount of results: SELECT column-name FROM table-name LIMIT num;

select columns and output num2 results start from index num1: SELECT column-name FROM table-name LIMIT num1,num2; or SELECT column-name FROM table-name LIMIT num2 OFFSET num1;

fully constrain the column names and table names: SELECT table-name.column-name FROM table-name;

fully constrain the column names and table names: SELECT table-name.coliumn-name FROM database-name.table-name;

## 4. order--ORDER BY
According to last part, select items actually do not follow an order. If we want sort data in a specific way, we need to use clause ORDER BY. I say clause which means ORDER BY is used after SELECT, like the FROM and LIMIT showed before. Of course, clause is very important. 

order by a column: SELECT column-name FROM table-name ORDER BY column-name;

order by multiple columns: SELECT column-name FROM table-name ORDER BY column-name1,column-name2,...;

defult order is ascending order(ASC), to obtain descending order: SELECT column-name FROM table-name ORDER BY column-name DESC; Note that DESC only works on the column just in front it, if you want to obtain multiple descending-order, each column should follow a DESC.

## 5.filter 1--WHERE
In order to obtain results under specific condition, we should set filter condition. Clause WHERE is applied after FROM for this purpose.

In this part, the coditions are likely to those in C++ or other language and is very flexible and easy to use. It is hard to summarize the orders thus I show some examples.

check single value: SELECT column-name FROM table-name WHERE column-name = value;(here take '=' as an example, other operators also satisfy)

not match: SELECT column-name FROM table-name WHERE column-name <> value;(<> means not match)

check intervals: SELECT column-name FROM table-name WHERE column-name BETWEEN value1 and value2;

check NULL: SELECT column-name FROM table-name WHERE column-name IS NULL;

## 6. filter 2--WHERE clause
In this part, we combine simple mathematical operators with some logical operators like AND,OR.

AND: SELECT column-name FROM table-name WHERE condition1 AND condition2;

OR: SELECT column-name FROM table-name WHERE condition1 OR condition2;

AND and OR: divided by ();

IN: SELECT column-name FROM table-name WHERE column-name IN interval;(note that IN is similar to OR but much faster)

NOT: (NOT reject all the operations behind it) SELECT column-name FROM table-name WHERE NOT condition;

## 7. filter 3--wildcard character
In the previous parts of filtering, the value we use for filtering is known. For example, we would like to find out the company name whose amount of employees are is more than 100. In this example, 100 is a known value. But for some other examples, the conditions are not as specific as last example, like find the company names containing 'ology'. Thus the simple filtering condition does not work. In this case we should consider wildcard. If you are familiar with regular expression, you would find they are really close.

In order to tell server we are using wildcard, we need to put operator LIKE at first. LIKE is like a symbol of wildcard.

%: match any character for any times;

\_: match any character once;

Example: 

SELECT column-name FROM tabe-name LIKE '%ology';

SELECT column-name FROM table-name LIKE '\_ology';

## 9. regular expression
Regular expression is very important in matching text. Regular expression is widely used in many areas and like another language, it has a complete rule. Since whole rules for regular expression are not the critical point in this chapter, we leave them to yourselves. Only usage in MySQL is included. Regular expression is quite easy in MySQL. Begin with REGEXP, you could put expressiond behind it.

In previous part, wildcard beginning with LIKE was introduced. Since LIKE could match patterns, why regular expression is introduced? There exists an important difference. LIKE matches the whole column, which means the expression behind LIKE should be a value in a column. However, REGEXP matches values, which means the expression behind REGEXP could appear in the value.

We would ignore the grammar part of regular expression.

## 10. 

