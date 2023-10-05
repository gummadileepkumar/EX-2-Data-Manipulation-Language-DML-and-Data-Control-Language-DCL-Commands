# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
### QUERY:
UPDATE manager
SET SALARY = SALARY + (SALARY *10/100);
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/474a1e14-6cdd-4403-814a-6bc194c078ef)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
delete from manager
 where salary<2750;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/7d0ef3a1-bbac-40e7-bfc2-c25a897ef53a)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
 select ename as "Name",salary*12 as "Annual Salary" from manager;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/028e9357-3b99-4586-820b-a22aa46ad884)

### Q4)	List the names of Clerks from emp table.
### QUERY:
select ename from manager where designation='clerk';
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/f8673470-345f-4434-9bb6-89454b10b302)

### Q5)	List the names of employee who are not Managers.
### QUERY:
select ename from manager where designation <> 'manager';
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/af076f12-2ca7-4b52-b78e-fb7c8386c928)

### Q6)	List the names of employees not eligible for commission.
### QUERY:
select ename from manager where commission=0;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/e6607d0d-2495-4ccd-8249-c5ceb400f3e4)

### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
select ename from manager where ename like '%s' or ename like 's%';
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/c655969e-f890-4273-ac2e-aa10d27dd6f5)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
 select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/7f97057e-e030-49fd-a886-5b11b510edfe)

### Q9) List the Details of Employees who have joined before 30 Sept 8.
### QUERY:
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/2a1465fe-c2e5-4c01-8702-58f9095fcf8f)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
select ename,deptno,salary from manager order by deptno asc,salary desc;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/8a00fbd9-46a1-462e-9039-463193c8efbc)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
select ename from manager where deptno not in (30,40,10);
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/3afd2ad6-229f-4b20-9659-7eb45b3393d6)

### Q12) Find number of rows in the table EMP
### QUERY:
select count(*) from manager;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/bc7ea0f4-3802-429d-9f96-83e60cf1c3fd)

### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/368b0c3f-2575-41a6-b733-bc73fc7f2f15)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
 SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
### OUTPUT:
![image](https://github.com/Priya-Loganathan/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166075/72c4043e-ff24-46a3-9791-16b6cd70b178)
