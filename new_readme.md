# apachehop_sql_server_autocommit_off 
Estudo de como desativar o autocommit do Apache Hop conectado no Sql Server

# select com filtro de uncommitted no sql server
para realizar um select filtrando linha ainda não commitadas execute com o script abaixo

> [!IMPORTANT]
> Exemplo para SQL Server Management Studio(SSMS)

> [!TIP]
>ALTER DATABASE MyDatabase  
>SET ALLOW_SNAPSHOT_ISOLATION ON  
>  
>ALTER DATABASE MyDatabase  
>SET READ_COMMITTED_SNAPSHOT ON 
>
>SET TRANSACTION ISOLATION LEVEL READ COMMITTED
>
>SELECT COUNT(*) FROM MyDatabase;

# configurações de sistema
Maquina: Windev2304Eval\
Java 11\
Apache Hop 2.9\
SQL Server 2019\