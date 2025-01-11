2025-01-07 17:19

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Injection|Injection]] [[2nd Brain/2 - Tags/Attacks|Attacks]] [[Data Base]] 

# SQL injection

SQL Injection is a common and dangerous web security vulnerability that allows an attacker to interfere with the queries a web application makes to its database. By injecting malicious SQL code into user input fields, an attacker can manipulate the underlying SQL queries, potentially accessing or modifying sensitive data, executing administrative operations, or even taking full control of the database.

The problem can occur in any application that manages data through a database

### Injection mechanisms
- User input
- Cookies
- Environment variables & HTTP request header
- Second-order injection - Input is provided so that it is kept in the system (often in the database) and later used

### Attack steps
- Identifying parameters vulnerable to injection
- Database fingerprinting
	- find the type+version of DB
- Discovering DB schema
	- table names, column names, column data types
- Extracting data from the DB
- Adding/modifying data in the DB
- Deleting DB, tables, or users
- Evading detection

### Preventing SQL injection
- **Parameterized SQL commands** - ensure that data is only interpreted as data (and not commands)
- **Whitelisting** - accept only good input (instead of rejecting bad input)
- **Input type checking** - remove malicious input
- **Encoding of input to something that can be trusted**

## Tautologies
Inject code in one (or more) conditional statement so that it always evaluates to true. 
- or 1=1 --

## Union query
Idea is to trick the application into returning arbitrary data by injecting UNION SELECT <…>
- <…> is used to extract data from some other table

## Piggy-backed queries
The idea is to add more (independent) queries.
Example: injection in the pass field
- SELECT accounts FROM users WHERE login='doe' AND pass=''**; DROP TABLE users --** ' AND pin=123
- **;** is the query delimiter, a metacharacter

## Stored procedures
????????????????????

## Illegal/incorrect queries
The objective is to find injectable parameters, DBMS type/version, schema by causing errors.
- **syntax errors**: allow the identification of injectable parameters
- **type errors**: support the deduction of data types of certain columns or extract data
- **logical errors**: often reveal names of tables and columns that caused the error

## Inference
Objective the same as illegal/incorrect queries
- attack attempts to infer if a certain condition on the state of the DBMS is true or false

Two attack techniques
- Blind injection - information is inferred by asking true/false questions
- Timing attacks - information is inferred from timing delays in the response

## Alternate encodings
Useful to complement other attacks but a good trick to evade detection mechanisms (e.g., blacklists) of the web application.
The idea is to encode input in an unusual format

![[SQL injection 1.png]]

- char transforms an integer or hexadecimal encoding in ASCII
- therefore, even if the word "shutdown" is included in a blacklist, the following would be executed: exec(shutdown)

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554471/mod_resource/content/8/T_BD.pdf