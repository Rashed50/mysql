# Mysql Ins and Outs

## Import Mysql database using command line :
```
 open terminal and go to the file location of which database do you want to import using terminal.
for example , your database name "studentdb.sql" that stored in  D drive . so you have to go D drive using "cd" command. then write the below command
"mysql -u root -p newdb_name < studentdb.sql"

if you get mysql command not found , then you need to set mysql enviroment path by this command
set path=%PATH%;E:\xampp\mysql\bin
```
