# apachehop_sql_server_autocommit_off 
Estudo de como desativar o autocommit do Apache Hop conectado no Sql Server

# Problema
Os transforms Table output ou insert / update não respeitam o commit size ao se conectarem ao SQL Server

## arquivos Apache Hop
Os arquivos .hpl são pipelines para o apache hop

### generate_ramdom_values.hpl
este arquivo cria a quantidade de linhas selecionadas no Generate rows incrementa com os dados aleatorios e exporta para o arquivo randoms.csv

### insert_update.hpl
este arquivo faz um truncate na tabela informada no Execute SQL Script e copia os dados genados no arquivo após isso ele faz um insert / update

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
>a  | b  
>10 | Heikki


# configurações de sistema
Maquina: Windev2304Eval
Java 11
Apache Hop 2.9
SQL Server 2019