# MySql
# MySql class - 02
mysql> SHOW DATABASES;
+-------------------------------------+
| Database                            |
+-------------------------------------+
| AUTH_DB_DEV                         |
| Blogging                            |
| BOOKING_DB_DEV                      |
| classicmodels                       |
| database_sequelize_demo_development |
| delivery_service_db                 |
| ecom_api_db_dev                     |
| ecommerce                           |
| Ecommerce_API                       |
| employee_hiring_system              |
| Entertainment                       |
| filmsdatabase                       |
| fitness_db                          |
| Flights                             |
| Flights_Search_DB_DEV               |
| information_schema                  |
| Movie                               |
| Movies_Database                     |
| mysql                               |
| performance_schema                  |
| REMINDER_DB_DEV                     |
| sys                                 |
+-------------------------------------+
22 rows in set (0.03 sec)

mysql> CREATE DATABASE MOVIES_DB_PW;
Query OK, 1 row affected (0.00 sec)

mysql> SHOW DATABASES;
+-------------------------------------+
| Database                            |
+-------------------------------------+
| AUTH_DB_DEV                         |
| Blogging                            |
| BOOKING_DB_DEV                      |
| classicmodels                       |
| database_sequelize_demo_development |
| delivery_service_db                 |
| ecom_api_db_dev                     |
| ecommerce                           |
| Ecommerce_API                       |
| employee_hiring_system              |
| Entertainment                       |
| filmsdatabase                       |
| fitness_db                          |
| Flights                             |
| Flights_Search_DB_DEV               |
| information_schema                  |
| Movie                               |
| Movies_Database                     |
| MOVIES_DB_PW                        |
| mysql                               |
| performance_schema                  |
| REMINDER_DB_DEV                     |
| sys                                 |
+-------------------------------------+
23 rows in set (0.00 sec)

mysql> USE AUTH_DB_DEV                         |
| Blogging                            |
| BOOKING_DB_DEV                      |
| classicmodels                       |
| database_sequelize_demo_development |
| delivery_service_db                 |
| ecom_api_db_dev                     |
| ecommerce                           |
| Ecommerce_API                       |
| employee_hiring_system              |
| Entertainment                       |
| filmsdatabase                       |
| fitness_db                          |
| Flights                             |
| Flights_Search_DB_DEV               |
| information_schema                  |
| Movie                               |
| Movies_Database                     |
| MOVIES_DB_PW                        |
| mysql                               |
| performance_schema                  |
| REMINDER_DB_DEV                     |
| sys                                 |
+------------------------------------Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> | Blogging                            |
    -> | BOOKING_DB_DEV                      |
    -> | classicmodels                       |
    -> | database_sequelize_demo_development |
    -> | delivery_service_db                 |
    -> | ecom_api_db_dev                     |
    -> | ecommerce                           |
    -> | Ecommerce_API                       |
    -> | employee_hiring_system              |
    -> | Entertainment                       |
    -> | filmsdatabase                       |
    -> | fitness_db                          |
    -> | Flights                             |
    -> | Flights_Search_DB_DEV               |
    -> | information_schema                  |
    -> | Movie                               |
    -> | Movies_Database                     |
    -> | MOVIES_DB_PW                        |
    -> | mysql                               |
    -> | performance_schema                  |
    -> | REMINDER_DB_DEV                     |
    -> | sys                                 |
    -> +------------------------------------

^C
mysql> \! CLEAR
mysql> USE MOVIES_DB_PW;
Database changed
mysql> CREATE TABLE Actors (Firstname VARCHAR(20), Lastname VARCHAR(20), Gender VARCHAR(10), Networth INTEGER);
Query OK, 0 rows affected (0.02 sec)

mysql> SHOW TABLES;
+------------------------+
| Tables_in_movies_db_pw |
+------------------------+
| Actors                 |
+------------------------+
1 row in set (0.00 sec)

mysql> INSERT INTO Actors (Firstname, Lastname, Gender, Networth) VALUES ("Johnny", "Depp", "Male", 200);
Query OK, 1 row affected (0.01 sec)

mysql> INSERT INTO Actors (Firstname, Lastname, Gender, Networth) VALUES ("Chris", "Hemsworth", "Male", 400);
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO Actors (Firstname, Lastname, Gender, Networth) VALUES ("Scarlett", "Johnson", "Female", 500), ("Chris", "Evans", "Male", 700), ("Paul", "Rudd", "Male", 150), ("Brie", "Larson", "Female", 650);
Query OK, 4 rows affected (0.00 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM Actors;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
+-----------+-----------+--------+----------+
6 rows in set (0.00 sec)

mysql> \! clear
mysql> SELECT * FROM Actors;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
+-----------+-----------+--------+----------+
6 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE Networth >= 500;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Scarlett  | Johnson  | Female |      500 |
| Chris     | Evans    | Male   |      700 |
| Brie      | Larson   | Female |      650 |
+-----------+----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE Networth >= 500 OR Networth < 200;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Scarlett  | Johnson  | Female |      500 |
| Chris     | Evans    | Male   |      700 |
| Paul      | Rudd     | Male   |      150 |
| Brie      | Larson   | Female |      650 |
+-----------+----------+--------+----------+
4 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE Gender = "Female";
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Scarlett  | Johnson  | Female |      500 |
| Brie      | Larson   | Female |      650 |
+-----------+----------+--------+----------+
2 rows in set (0.01 sec)

mysql> SELECT Firtname, Networth FROM ACTORS WHERE Gender = "Female";
ERROR 1054 (42S22): Unknown column 'Firtname' in 'field list'
mysql> SELECT Firstname, Networth FROM ACTORS WHERE Gender = "Female";
+-----------+----------+
| Firstname | Networth |
+-----------+----------+
| Scarlett  |      500 |
| Brie      |      650 |
+-----------+----------+
2 rows in set (0.00 sec)

mysql> select * from actors
    -> ;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
+-----------+-----------+--------+----------+
6 rows in set (0.00 sec)

mysql> INSERT INTO Actors (Firstname, Lastname, Gender, Networth) VALUES ("Chadwick", "Boseman", "Male", 400);
Query OK, 1 row affected (0.01 sec)

mysql> select * from actors;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME = "Chris";
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
2 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "Ch%";
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "%is";
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
2 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%";
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "%a%";
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Scarlett  | Johnson  | Female |      500 |
| Paul      | Rudd     | Male   |      150 |
| Chadwick  | Boseman  | Male   |      400 |
+-----------+----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%";
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS ORDER BY Networth ASC;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Paul      | Rudd      | Male   |      150 |
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Chadwick  | Boseman   | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Brie      | Larson    | Female |      650 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS ORDER BY Networth DESC;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Evans     | Male   |      700 |
| Brie      | Larson    | Female |      650 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Hemsworth | Male   |      400 |
| Chadwick  | Boseman   | Male   |      400 |
| Johnny    | Depp      | Male   |      200 |
| Paul      | Rudd      | Male   |      150 |
+-----------+-----------+--------+----------+
7 rows in set (0.01 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%";
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%" ORDER BY Networth DESC;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Evans     | Male   |      700 |
| Chris     | Hemsworth | Male   |      400 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS ORDER BY Networth DESC  WHERE FIRSTNAME like "CH%";
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'WHERE FIRSTNAME like "CH%"' at line 1
mysql> SELECT * FROM ACTORS ORDER BY Networth;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Paul      | Rudd      | Male   |      150 |
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Chadwick  | Boseman   | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Brie      | Larson    | Female |      650 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%" ORDER BY Firstname;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chadwick  | Boseman   | Male   |      400 |
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%" ORDER BY Firstname;Chris     | Hemsworth | Male   |      400 |
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chadwick  | Boseman   | Male   |      400 |
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

    -> | Chris     | Evans     | Male   |      700 |

^C
mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%" ORDER BY Firstname, Networth DESC;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chadwick  | Boseman   | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
| Chris     | Hemsworth | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%" ORDER BY Firstname;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chadwick  | Boseman   | Male   |      400 |
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%" ORDER BY Firstname, Networth DESC;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chadwick  | Boseman   | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
| Chris     | Hemsworth | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.01 sec)

mysql> select * from actors;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
7 rows in set (0.00 sec)

mysql> select * from actors limit 3;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 2;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
+-----------+-----------+--------+----------+
2 rows in set (0.00 sec)

mysql> select * from actors offset 0 limit 3;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '0 limit 3' at line 1
mysql> select * from actors limit 3 offset 0;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 2;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Scarlett  | Johnson  | Female |      500 |
| Chris     | Evans    | Male   |      700 |
| Paul      | Rudd     | Male   |      150 |
+-----------+----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 0;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 3;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Chris     | Evans    | Male   |      700 |
| Paul      | Rudd     | Male   |      150 |
| Brie      | Larson   | Female |      650 |
+-----------+----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 6;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Chadwick  | Boseman  | Male   |      400 |
+-----------+----------+--------+----------+
1 row in set (0.00 sec)

mysql> select * from actors;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
7 rows in set (0.01 sec)

mysql> select * from actors limit 3 offset 2;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Scarlett  | Johnson  | Female |      500 |
| Chris     | Evans    | Male   |      700 |
| Paul      | Rudd     | Male   |      150 |
+-----------+----------+--------+----------+
3 rows in set (0.02 sec)

mysql> select * from actors limit 3 offset 3;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Chris     | Evans    | Male   |      700 |
| Paul      | Rudd     | Male   |      150 |
| Brie      | Larson   | Female |      650 |
+-----------+----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 5;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Brie      | Larson   | Female |      650 |
| Chadwick  | Boseman  | Male   |      400 |
+-----------+----------+--------+----------+
2 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 15;
Empty set (0.00 sec)

mysql> select * from actors limit 3 offset 0;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 3;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Chris     | Evans    | Male   |      700 |
| Paul      | Rudd     | Male   |      150 |
| Brie      | Larson   | Female |      650 |
+-----------+----------+--------+----------+
3 rows in set (0.00 sec)

mysql> select * from actors limit 3 offset 6;
+-----------+----------+--------+----------+
| Firstname | Lastname | Gender | Networth |
+-----------+----------+--------+----------+
| Chadwick  | Boseman  | Male   |      400 |
+-----------+----------+--------+----------+
1 row in set (0.00 sec)

mysql> select * from actors offset 3;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '3' at line 1
mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%";
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM ACTORS WHERE FIRSTNAME like "CH%" limit 2;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Chris     | Hemsworth | Male   |      400 |
| Chris     | Evans     | Male   |      700 |
+-----------+-----------+--------+----------+
2 rows in set (0.01 sec)

mysql> select * from actors;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
| Chadwick  | Boseman   | Male   |      400 |
+-----------+-----------+--------+----------+
7 rows in set (0.00 sec)

mysql> UPDATE Actors SET Networth = 500 WHERE Firstname = "Chadwick";
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from actors;
+-----------+-----------+--------+----------+
| Firstname | Lastname  | Gender | Networth |
+-----------+-----------+--------+----------+
| Johnny    | Depp      | Male   |      200 |
| Chris     | Hemsworth | Male   |      400 |
| Scarlett  | Johnson   | Female |      500 |
| Chris     | Evans     | Male   |      700 |
| Paul      | Rudd      | Male   |      150 |
| Brie      | Larson    | Female |      650 |
| Chadwick  | Boseman   | Male   |      500 |
+-----------+-----------+--------+----------+
7 rows in set (0.00 sec)

mysql>
