# sql-queries
queries of sql
--WAQTD NAMES OF EMPLOYEES HIRED AFTER 81 INTO DEPT 10 OR 30
 
SQL> SELECT ENAME
     FROM EMP
     WHERE HIREDATE >'31-DEC-81' AND (DEPTNO=10 OR DEPTNO=30);

ENAME
------------
MILLER

--WAQTD NAMES OF EMPLOYEES ALONG WITH ANNUAL SALARY FOR THE EMPLOYEES
 WORKING AS MANAGER OR CLERK INTO DEPT 10 OR 30 

SQL> SELECT ENAME,SAL*12
     FROM EMP
     WHERE (JOB='MANAGER' OR JOB='CLERK') AND (DEPTNO=10 OR DEPTNO=30);

ENAME          SAL*12
---------- ----------
BLAKE           34200
CLARK           29400
JAMES           11400
MILLER          15600

--WAQTD ALL THE DETAILS ALONG WITH ANNUAL SALARY IF SAL IS BETWEEN
 1000 AND 4000 ANNUAL SALARY MORE THAN 15000

SQL> SELECT EMP.*,SAL*12
     FROM EMP
     WHERE(SAL>1000 AND SAL>4000)AND(SAL*12)>15000;

     EMPNO ENAME      JOB              MGR HIREDATE         SAL       COMM     DEPTNO     SAL*12
---------- ---------- --------- ---------- --------- ---------- ---------- ---------- ----------
      7839 KING       PRESIDENT            17-NOV-81       5000                    10      60000
      WAQTD DETAILS OF ALL THE EMPLOYEES EXCEPT THE EMPS WORKING IN DEPT 
	10 OR 30 
SQL> SELECT *
     FROM EMP
     WHERE DEPTNO!=10 AND DEPTNO!=30;

     EMPNO ENAME      JOB              MGR HIREDATE         SAL       COMM     DEPTNO
---------- ---------- --------- ---------- --------- ---------- ---------- ----------
      7369 SMITH      CLERK           7902 17-DEC-80        800                    20
      7566 JONES      MANAGER         7839 02-APR-81       2975                    20
      7788 SCOTT      ANALYST         7566 19-APR-87       3000                    20
      7876 ADAMS      CLERK           7788 23-MAY-87       1100                    20
      7902 FORD       ANALYST         7566 03-DEC-81       3000                    20

22. WAQTD DETAILS OF ALL EMPS ALONG WITH ANNUAL SALARY EXCEPT THE 
	EMPLOYEES WORKING AS ANALYST OR MANAGER . 
SQL> SELECT EMP.*,SAL*12
     FROM EMP
     WHERE JOB!='ANALYST' AND JOB!='MANAGER';

     EMPNO ENAME      JOB              MGR HIREDATE         SAL       COMM     DEPTNO     SAL*12
---------- ---------- --------- ---------- --------- ---------- ---------- ---------- ----------
      7369 SMITH      CLERK           7902 17-DEC-80        800                    20       9600
      7499 ALLEN      SALESMAN        7698 20-FEB-81       1600        300         30      19200
      7521 WARD       SALESMAN        7698 22-FEB-81       1250        500         30      15000
      7654 MARTIN     SALESMAN        7698 28-SEP-81       1250       1400         30      15000
      7839 KING       PRESIDENT            17-NOV-81       5000                    10      60000
      7844 TURNER     SALESMAN        7698 08-SEP-81       1500          0         30      18000
      7876 ADAMS      CLERK           7788 23-MAY-87       1100                    20      13200
      7900 JAMES      CLERK           7698 03-DEC-81        950                    30      11400
      7934 MILLER     CLERK           7782 23-JAN-82       1300                    10      15600



