# Truncate-transaction-log-of-database

Databases are usually in <b>Full Recovery</b> mode. This means that every transaction is retained in the transaction logs allowing a point in time recovery.<br/>
The implication of this is that unless the transaction log is truncated, no space gets freed up on deleting rows from any tables. Delete operations only shift data from the table to the logs.<br/>
Following are the steps to reduce the size of transaction log in SQL Server Management Studio:
1. Right click the database, select <b>Tasks</b> → <b>Shrink</b> → <b>Files</b> as shown in the following figure:

<p align="center">Fig 1: Options to reduce transaction log file size</p>
 
2. On the <b>Shrink File - testing_log</b> window, change the <b>File type</b> field option to <b>Log</b>. You can also choose either <b>Release unused space</b>, <b>Reorganize pages before releasing unused space</b>, or <b>Empty file by migrating the data to other files in the same filegroup</b> options:


3. Click <b>OK</b>, this will reduce the file size of the transaction log.

