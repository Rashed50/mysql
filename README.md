# Large size (More then 200 MB)  Mysql database resotre using terminal in XMAPP Server

## Import Mysql database using command line :
```
 open terminal and go to the file location of which database do you want to import using terminal.
for example , your database name "studentdb.sql" that stored in  D drive . so you have to
go D drive using "cd" command. then write the below command
"mysql -u root -p newdb_name < studentdb.sql"

if you get mysql command not found error, then you need to set mysql
enviroment path by this command below:
set path=%PATH%;E:\xampp\mysql\bin
```

## import using xamp server terminal,
For this first you have to open terminal from xampp
To do , First just open your pc xampp server , after open you will see the XAMPP control panel
and then click MySql Start button and run the sql engine
then click the "Shell" button that exist in XAMPP control panel.

First you have to transfer you mysql database backup .sql file 
to the location of XAMPP->mysql->bin

Now you teminal window opened with current location of XAMPP installed location.
then you cd command to go bin folder inside your XAMPP server. 
type bleow command in your opend terminal and press ENTER to move mysql folder
```
 cd mysql 
```
Then again 

```
 cd bin 
```

Now type the below command for import your mysql database file

```
mysql -u root -p newdb_name_in_xampp_server < studentdb.sql
```

then xampp server will ask for you server password
if you don't set password then jut press ENTER
if no error found then database will import but don't see progress
so wait few minutes then reload your xampp server in localhost in brower
you will see your data base



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

#   
```
 
 

