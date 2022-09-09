mysql> use join_db;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
**mysql> show tables;
+-------------------+
| Tables_in_join_db |
+-------------------+
| dept              |
| emp               |
+-------------------+
2 rows in set (0.00 sec)**

## INNER JOIN :
```
mysql> select * from emp;                                       mysql> select * from dept;
+--------+----------+------+--------+---------+                 +---------+-----------------+
| emp_id | emp_name | age  | salary | dept_id |					| dept_id | dept_name       |
+--------+----------+------+--------+---------+					+---------+-----------------+
|      1 | akash    |   24 |  20000 |       5 |                 |       1 | Administration  |
|      2 | aniket   |   25 |  21000 |       5 |					|       2 | Human Resources |
|      3 | akshay   |   23 |  19000 |       6 |					|       3 | IT              |
|      4 | amit     |   25 |  21000 |       5 |					|       4 | Purchasing      |
|      5 | john     |   34 |  25000 |       5 |					|       5 | Marketing       |
|      6 | rock     |   40 |  30000 |       4 |					|       6 | Accounting      |
|      7 | riya     |   23 |  18000 |       6 |					|       7 | Manufacturing   |
|      8 | asmita   |   25 |  22000 |       5 |					|       8 | Sales           |
|      9 | michal   |   55 |  45000 |       3 |					+---------+-----------------+
|     10 | jack     |   36 |  31000 |       4 |					8 rows in set (0.00 sec)
|     11 | janani   |   23 |  50000 |       2 |
|     12 | sita     |   30 |  26000 |       5 |
|     13 | ram      |   35 |  47000 |       3 |
|     14 | modi     |   75 |  60100 |       1 |
|     15 | xyz      |   22 |  15000 |       6 |
|     16 | Dhanu    |   24 |  30000 |       9 |
|     17 | sandip   |   25 |  60000 |      10 |
|     18 | santosh  |   26 |  10000 |      11 |
+--------+----------+------+--------+---------+
18 rows in set (0.00 sec)
```
```
mysql> SELECT emp.emp_id as ID,emp.emp_name as Name,emp.salary as Salary,dept.dept_name as Department FROM emp
    -> JOIN dept
    -> ON emp.dept_id=dept.dept_id;
```

```	
+----+--------+--------+-----------------+
| ID | Name   | Salary | Department      |
+----+--------+--------+-----------------+
|  1 | akash  |  20000 | Marketing       |
|  2 | aniket |  21000 | Marketing       |
|  3 | akshay |  19000 | Accounting      |
|  4 | amit   |  21000 | Marketing       |
|  5 | john   |  25000 | Marketing       |
|  6 | rock   |  30000 | Purchasing      |
|  7 | riya   |  18000 | Accounting      |
|  8 | asmita |  22000 | Marketing       |
|  9 | michal |  45000 | IT              |
| 10 | jack   |  31000 | Purchasing      |
| 11 | janani |  50000 | Human Resources |
| 12 | sita   |  26000 | Marketing       |
| 13 | ram    |  47000 | IT              |
| 14 | modi   |  60100 | Administration  |
| 15 | xyz    |  15000 | Accounting      |
+----+--------+--------+-----------------+
15 rows in set (0.00 sec)
```

## LEFT JOIN :
```
mysql> select * from emp;                                       mysql> select * from dept;
+--------+----------+------+--------+---------+                 +---------+-----------------+
| emp_id | emp_name | age  | salary | dept_id |					| dept_id | dept_name       |
+--------+----------+------+--------+---------+					+---------+-----------------+
|      1 | akash    |   24 |  20000 |       5 |                 |       1 | Administration  |
|      2 | aniket   |   25 |  21000 |       5 |					|       2 | Human Resources |
|      3 | akshay   |   23 |  19000 |       6 |					|       3 | IT              |
|      4 | amit     |   25 |  21000 |       5 |					|       4 | Purchasing      |
|      5 | john     |   34 |  25000 |       5 |					|       5 | Marketing       |
|      6 | rock     |   40 |  30000 |       4 |					|       6 | Accounting      |
|      7 | riya     |   23 |  18000 |       6 |					|       7 | Manufacturing   |
|      8 | asmita   |   25 |  22000 |       5 |					|       8 | Sales           |
|      9 | michal   |   55 |  45000 |       3 |					+---------+-----------------+
|     10 | jack     |   36 |  31000 |       4 |					8 rows in set (0.00 sec)
|     11 | janani   |   23 |  50000 |       2 |
|     12 | sita     |   30 |  26000 |       5 |
|     13 | ram      |   35 |  47000 |       3 |
|     14 | modi     |   75 |  60100 |       1 |
|     15 | xyz      |   22 |  15000 |       6 |
|     16 | Dhanu    |   24 |  30000 |       9 |
|     17 | sandip   |   25 |  60000 |      10 |
|     18 | santosh  |   26 |  10000 |      11 |
+--------+----------+------+--------+---------+
18 rows in set (0.00 sec)
```
```
mysql> SELECT emp.emp_id as ID,emp.emp_name as Name,emp.salary as Salary,dept.dept_name as Department FROM emp LEFT JOIN dept ON emp.dept_id=dept.dept_id;
```
```
	
+----+---------+--------+-----------------+
| ID | Name    | Salary | Department      |
+----+---------+--------+-----------------+
|  1 | akash   |  20000 | Marketing       |
|  2 | aniket  |  21000 | Marketing       |
|  3 | akshay  |  19000 | Accounting      |
|  4 | amit    |  21000 | Marketing       |
|  5 | john    |  25000 | Marketing       |
|  6 | rock    |  30000 | Purchasing      |
|  7 | riya    |  18000 | Accounting      |
|  8 | asmita  |  22000 | Marketing       |
|  9 | michal  |  45000 | IT              |
| 10 | jack    |  31000 | Purchasing      |
| 11 | janani  |  50000 | Human Resources |
| 12 | sita    |  26000 | Marketing       |
| 13 | ram     |  47000 | IT              |
| 14 | modi    |  60100 | Administration  |
| 15 | xyz     |  15000 | Accounting      |
| 16 | Dhanu   |  30000 | NULL            |
| 17 | sandip  |  60000 | NULL            |
| 18 | santosh |  10000 | NULL            |
+----+---------+--------+-----------------+
18 rows in set (0.00 sec)

```

## RIGHT JOIN :
```
mysql> select * from emp;                                       mysql> select * from dept;
+--------+----------+------+--------+---------+                 +---------+-----------------+
| emp_id | emp_name | age  | salary | dept_id |					| dept_id | dept_name       |
+--------+----------+------+--------+---------+					+---------+-----------------+
|      1 | akash    |   24 |  20000 |       5 |                 |       1 | Administration  |
|      2 | aniket   |   25 |  21000 |       5 |					|       2 | Human Resources |
|      3 | akshay   |   23 |  19000 |       6 |					|       3 | IT              |
|      4 | amit     |   25 |  21000 |       5 |					|       4 | Purchasing      |
|      5 | john     |   34 |  25000 |       5 |					|       5 | Marketing       |
|      6 | rock     |   40 |  30000 |       4 |					|       6 | Accounting      |
|      7 | riya     |   23 |  18000 |       6 |					|       7 | Manufacturing   |
|      8 | asmita   |   25 |  22000 |       5 |					|       8 | Sales           |
|      9 | michal   |   55 |  45000 |       3 |					+---------+-----------------+
|     10 | jack     |   36 |  31000 |       4 |					8 rows in set (0.00 sec)
|     11 | janani   |   23 |  50000 |       2 |
|     12 | sita     |   30 |  26000 |       5 |
|     13 | ram      |   35 |  47000 |       3 |
|     14 | modi     |   75 |  60100 |       1 |
|     15 | xyz      |   22 |  15000 |       6 |
|     16 | Dhanu    |   24 |  30000 |       9 |
|     17 | sandip   |   25 |  60000 |      10 |
|     18 | santosh  |   26 |  10000 |      11 |
+--------+----------+------+--------+---------+
18 rows in set (0.00 sec)
```
```
mysql> SELECT emp.emp_id as ID,emp.emp_name as Name,emp.salary as Salary,dept.dept_name as Department FROM emp RIGHT JOIN dept ON emp.dept_id=dept.dept_id ;
```
```	
+------+--------+--------+-----------------+
| ID   | Name   | Salary | Department      |
+------+--------+--------+-----------------+
|   14 | modi   |  60100 | Administration  |
|   11 | janani |  50000 | Human Resources |
|    9 | michal |  45000 | IT              |
|   13 | ram    |  47000 | IT              |
|    6 | rock   |  30000 | Purchasing      |
|   10 | jack   |  31000 | Purchasing      |
|    1 | akash  |  20000 | Marketing       |
|    2 | aniket |  21000 | Marketing       |
|    4 | amit   |  21000 | Marketing       |
|    5 | john   |  25000 | Marketing       |
|    8 | asmita |  22000 | Marketing       |
|   12 | sita   |  26000 | Marketing       |
|    3 | akshay |  19000 | Accounting      |
|    7 | riya   |  18000 | Accounting      |
|   15 | xyz    |  15000 | Accounting      |
| NULL | NULL   |   NULL | Manufacturing   |
| NULL | NULL   |   NULL | Sales           |
+------+--------+--------+-----------------+
17 rows in set (0.00 sec)
```
## FULL OUTER JOIN :
```
mysql> select * from emp;                                       mysql> select * from dept;
+--------+----------+------+--------+---------+                 +---------+-----------------+
| emp_id | emp_name | age  | salary | dept_id |					| dept_id | dept_name       |
+--------+----------+------+--------+---------+					+---------+-----------------+
|      1 | akash    |   24 |  20000 |       5 |                 |       1 | Administration  |
|      2 | aniket   |   25 |  21000 |       5 |					|       2 | Human Resources |
|      3 | akshay   |   23 |  19000 |       6 |					|       3 | IT              |
|      4 | amit     |   25 |  21000 |       5 |					|       4 | Purchasing      |
|      5 | john     |   34 |  25000 |       5 |					|       5 | Marketing       |
|      6 | rock     |   40 |  30000 |       4 |					|       6 | Accounting      |
|      7 | riya     |   23 |  18000 |       6 |					|       7 | Manufacturing   |
|      8 | asmita   |   25 |  22000 |       5 |					|       8 | Sales           |
|      9 | michal   |   55 |  45000 |       3 |					+---------+-----------------+
|     10 | jack     |   36 |  31000 |       4 |					8 rows in set (0.00 sec)
|     11 | janani   |   23 |  50000 |       2 |
|     12 | sita     |   30 |  26000 |       5 |
|     13 | ram      |   35 |  47000 |       3 |
|     14 | modi     |   75 |  60100 |       1 |
|     15 | xyz      |   22 |  15000 |       6 |
|     16 | Dhanu    |   24 |  30000 |       9 |
|     17 | sandip   |   25 |  60000 |      10 |
|     18 | santosh  |   26 |  10000 |      11 |
+--------+----------+------+--------+---------+
18 rows in set (0.00 sec)
```
```
mysql> SELECT emp.emp_id as ID,emp.emp_name as Name,emp.salary as Salary,dept.dept_name as Department FROM emp LEFT JOIN dept ON emp.dept_id=dept.dept_id
    -> UNION ALL
    -> SELECT emp.emp_id as ID,emp.emp_name as Name,emp.salary as Salary,dept.dept_name as Department FROM emp RIGHT JOIN dept ON emp.dept_id=dept.dept_id;
```	
```	
+------+---------+--------+-----------------+
| ID   | Name    | Salary | Department      |
+------+---------+--------+-----------------+
|    1 | akash   |  20000 | Marketing       |
|    2 | aniket  |  21000 | Marketing       |
|    3 | akshay  |  19000 | Accounting      |
|    4 | amit    |  21000 | Marketing       |
|    5 | john    |  25000 | Marketing       |
|    6 | rock    |  30000 | Purchasing      |
|    7 | riya    |  18000 | Accounting      |
|    8 | asmita  |  22000 | Marketing       |
|    9 | michal  |  45000 | IT              |
|   10 | jack    |  31000 | Purchasing      |
|   11 | janani  |  50000 | Human Resources |
|   12 | sita    |  26000 | Marketing       |
|   13 | ram     |  47000 | IT              |
|   14 | modi    |  60100 | Administration  |
|   15 | xyz     |  15000 | Accounting      |
|   16 | Dhanu   |  30000 | NULL            |
|   17 | sandip  |  60000 | NULL            |
|   18 | santosh |  10000 | NULL            |
|   14 | modi    |  60100 | Administration  |
|   11 | janani  |  50000 | Human Resources |
|    9 | michal  |  45000 | IT              |
|   13 | ram     |  47000 | IT              |
|    6 | rock    |  30000 | Purchasing      |
|   10 | jack    |  31000 | Purchasing      |
|    1 | akash   |  20000 | Marketing       |
|    2 | aniket  |  21000 | Marketing       |
|    4 | amit    |  21000 | Marketing       |
|    5 | john    |  25000 | Marketing       |
|    8 | asmita  |  22000 | Marketing       |
|   12 | sita    |  26000 | Marketing       |
|    3 | akshay  |  19000 | Accounting      |
|    7 | riya    |  18000 | Accounting      |
|   15 | xyz     |  15000 | Accounting      |
| NULL | NULL    |   NULL | Manufacturing   |
| NULL | NULL    |   NULL | Sales           |
+------+---------+--------+-----------------+
35 rows in set (0.00 sec)
```
