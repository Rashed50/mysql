# Mysql Ins and Outs

## Import Mysql database using command line :
```
 open terminal and go to the file location of which database do you want to import using terminal.
for example , your database name "studentdb.sql" that stored in  D drive . so you have to go D drive using "cd" command. then write the below command
"mysql -u root -p newdb_name < studentdb.sql"

if you get mysql command not found error, then you need to set mysql enviroment path by this command below:
set path=%PATH%;E:\xampp\mysql\bin
```

## How to solved utf8mb4_0900_ai_ci error

After a little investigation, I found that the MySQL server running on the destination is an older version 
than the source. So we got that the destination server doesn’t contain the required database collation.
This is the eror for xampp server version error. If the source and destination xampp verser version
are mismatch then you can get this error. suppose you source server is 8.0 and destination server 8.2
then you will get this error.

### Solution
```
Then we do a little tweak in the backup file to resolve this. Edit the database backup file in text editor
and replace “utf8mb4_0900_ai_ci” with “utf8mb4_general_ci” and “CHARSET=utf8mb4” with “CHARSET=utf8“.
```

