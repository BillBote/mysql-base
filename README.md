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



