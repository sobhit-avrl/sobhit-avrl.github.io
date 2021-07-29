---
layout: default
title: DB Patch System
---

Updated 07/26

This is a combination of a Python and Excel file. The purpose of this system is to quickly add entries to the CADB. Rather than write multiple lines of SQL using the manage_db interface on the CA, you could just put those key-values you want stored on the CADB into the data.csv file and double click the DB-Patch file to have it upload all the data in that CSV file into the CADB. It operates as follows:
+ The Python file is located inside the "patch" folder in the companion app and is in editable Python script form. It is double-clicked to run. When run, it asks the user whether the user would like to set a username on that db. The user should ordinarily enter their consumer username. This username can later be used to decide which rows of data from the excel file gets fed into this CADB.

    _The data in the CSV file has 2 essential columns, key and value and 2 secondary columns: target user and tree\_name._ 

    _However, you can add a username for each line of data in column 3. Doing this will ensure that the row will be entered into_ _only the CADBs which have a username entry that matches the one in that row. This is useful to allow you to have a single data._
    _csv file with key-value pairs that will be selectively fed into multiple CADBs, thereby reducing the work that the coordinator needs to do. Without this functionality, the coordinator would need to build a data.csv file for every single CADB upload._
    _A classic example of this would be usernames and passwords of the TMS' for multiple consumer users; wherein you don't want one_ _user's TMS login information to be fed into another user's TMS._

+ It then asks the user whether there is a path to a new CSV file or whether it should read the associated CSV file. Paths to new CSV files need to be typed into the command prompt and it checks whether that file exists before trying to read it

+ On user selection, it fetches the date from that file and prints that date to the screen asking the user to confirm whether this is the current version of the file. This prevents the user from uploading the wrong file into their DB

+ The CSV file, row 6 onwards, should contain only data to be fed into the ARPA Companion App DB, from 3 columns: key, value, username*
    *The username column is optional

+ While writing to the DB, the Python file then checks the DB to see if a username key exists for each row.

    - If it does, then the Python file checks if the DB has that same username. if the DB doesn't, then that line of data is not written to the DB
    - If it doesn't, then that line of data is always written to the DB

The tree_name field should contain the name of the tree currently being used. If no tree is intended to be used, you should write in **general** into that field.
