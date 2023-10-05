![dbms_2 2](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/ccc26943-d7bc-4eb7-b87f-03ebc8a257ec)# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
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

![dbms_2 1](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/e5ff46b5-f9e3-499e-bcab-69617812c65d)


### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
delete from manager
 where salary<2750;
### OUTPUT:

![dbms_2 2](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/2e0f8822-c44a-44d6-b44f-b14027328cb3)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
 select ename as "Name",salary*12 as "Annual Salary" from manager;
### OUTPUT:

![dbms_2 3](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/aa887aa2-273c-4759-881f-9c06a8a99238)


### Q4)	List the names of Clerks from emp table.
### QUERY:
select ename from manager where designation='clerk';
### OUTPUT:

![dbms_2 4](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/cd06bd1b-b045-446d-a3df-4027b2587721)


### Q5)	List the names of employee who are not Managers.
### QUERY:
select ename from manager where designation <> 'manager';
### OUTPUT:

![dbms_2 5](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/91ec7559-bbda-47e1-8498-05ebbcc59d0f)


### Q6)	List the names of employees not eligible for commission.
### QUERY:
select ename from manager where commission=0;
### OUTPUT:

![dbms_2 6](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/80bff215-58a2-460c-85b1-6e2c73d0456e)


### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
select ename from manager where ename like '%s' or ename like 's%';
### OUTPUT:

![dbms_2 7](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/054494e8-d7d3-4217-bf0f-c99366635a89)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
 select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
### OUTPUT:


![dbms_2 8](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/9f0ef1d3-348e-4d00-b36b-f9c075160783)


### Q9) List the Details of Employees who have joined before 30 Sept 8.
### QUERY:
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
### OUTPUT:

![dbms_2 9](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/c968429c-c15e-497d-8ccc-b37590d028df)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
select ename,deptno,salary from manager order by deptno asc,salary desc;
### OUTPUT:

![dbms_2 10](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/2e80f876-5cd1-40e8-a935-ad671c4ee1a2)


### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
select ename from manager where deptno not in (30,40,10);
### OUTPUT:

![dbms_2 11](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/bee6d970-437e-4928-aa61-af14e601d16c)


### Q12) Find number of rows in the table EMP
### QUERY:
select count(*) from manager;
### OUTPUT:

![dbms_2 12](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/6c758b30-6fdd-4721-879c-b5dc4c9772db)



### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
### OUTPUT:

![dbms_2 13](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/aa299c9e-ed5c-45f7-b7a4-76f539e2e505)



### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
 SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
### OUTPUT:

![dbms_2 14](https://github.com/gummadileepkumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707761/793906b9-8689-4f36-b65e-b6b810a26012)

