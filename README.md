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

### my xampp server was shutdown unexpectedly and later on when I opened xampp server and trying to start mysql server, it was not working and show below error

Error: MySQL shutdown unexpectedly.

3:18:22 AM  [mysql] This may be due to a blocked port, missing dependencies, 

3:18:22 AM  [mysql] improper privileges, a crash, or a shutdown by another method.

3:18:22 AM  [mysql] Press the Logs button to view error logs and check

3:18:22 AM  [mysql] the Windows Event Viewer for more clues

3:18:22 AM  [mysql] If you need more help, copy and post this

3:18:22 AM  [mysql] entire log window on the forums   

```
This is a common issue with XAMPP, usually caused by a corrupted index file or a "lock" file left behind after the unexpected shutdown. Since your data is important, we will use the safe recovery method that doesn't delete your actual databases.

Follow these steps exactly:

1. The "Backup & Data" Fix (Most Successful)
Go to your XAMPP installation folder (usually C:\xampp\mysql\).

Rename the folder data to data_old.

Create a new empty folder named data.

Go into the backup folder (located at C:\xampp\mysql\backup).

Copy all files from backup and paste them into your new data folder.

Now, go back to data_old and copy these specific items:

All your database folders (except mysql, performance_schema, and phpmyadmin).

The file named ibdata1 (This is the most important file; it contains your table relationships).

Paste these into the new data folder (Replace files when asked).

Try starting MySQL from the XAMPP Control Panel.
```

 
 

