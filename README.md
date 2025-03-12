# apachehop_sql_server_autocommit_off 
Estudo de como desativar o autocommit do Apache Hop conectado no Sql Server

## autocommit off mysql
exemplo de autocommit off no mysql
https://dev.mysql.com/doc/refman/8.4/en/innodb-autocommit-commit-rollback.html

## autocommit off sql server 
codigo do exemplo do mysql corvertido para o sql server 

> [!TIP]
>CREATE TABLE customer (a INT, b CHAR(20));
>CREATE INDEX idx_a ON customer(a);
>
>SET IMPLICIT_TRANSACTIONS OFF;
>
>BEGIN TRANSACTION;
>INSERT INTO customer VALUES (10, 'Heikki');
>COMMIT;
>
>SET IMPLICIT_TRANSACTIONS ON;
>
>INSERT INTO customer VALUES (15, 'John');
>INSERT INTO customer VALUES (20, 'Paul');
>DELETE FROM customer WHERE b = 'Heikki';
>
>ROLLBACK;
>
>SELECT * FROM customer;
>
>SET IMPLICIT_TRANSACTIONS OFF;

### Resultado
>[!IMPORTANT]
> a | b
>10 | Heikki