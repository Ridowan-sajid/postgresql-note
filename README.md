# postgresql-note

**DATA TYPE**
* BOOLEAN - to store TRUE/FALSE
* VARCHAR(n) - to store String type like name,any keyword. "n" means character length.
* INT - to store int value
* BIGSERIAL/SERIAL - to store int value incremently
* NUMERIC (3, 2) - can use 3 digit and 2 digit after decimal
* DATE -  stores the dates only
* TIME - stores the time of day values
* TIMESTAMP - stores both date and time values

**Two most useable command**
* \l - to see the list of all database
* \q - quit

**To Create database**
* CREATE DATABASE databasename;

**To connect with database**
* \c databasename

**To delete/drop a database**
* DROP DATABASE databasename;

**TO CREATE table**
      
      CREATE TABLE person(
      id INT NOT NULL PRIMARY KEY,
      first_name VARCHAR(20) NOT NULL,
      last_name VARCHAR(20) NOT NULL,
      gender VARCHAR(7) NOT NULL,
      join_date DATE NOT NULL,
      email VARCHAR(20)
      ):
  
  * id =variable
  * INT = data type
  * NOT NULL = id can't be null
  * PRIMARY_KEY = unique identifier (every primary key is unique)
 
 **To see Table list**
 * \d
 
 **To make auto-increment**
 
 * id SERIAL NOT NULL;
 
 **To see all table list**
 
 * \d
 
 **To see individual table**
 
 * \d tablename
 
 **To insert data into a table**
 
       INSERT INTO person( 
       id,first_name,last_name,gender,join_date,email
       )
       VALUES(
       1,'Chandler','Bing','MALE',DATE '2021-02-02', 'chandler@gmail.com'
       );
       
 * INSER INTO person() into this bracket we can specify what we will input
 * To insert DATE type values have to specify DATE before writting date,
 
 **To see everything from our Table**
 
    SELECT * FROM person;
   
**To see individual column**

    SELECT first_name FROM person;

**To see multiple column**
  
     SELECT first_name,last_name FROM person;

**Sorting data**

     SELECT * FROM person ORDER BY first_name ASC/DESC;

**To get unique value**
  
    SELECT DISTINCT join_date FROM person;
    
**To filter data based on condition**

    SELECT * FROM person
    WHERE first_name='Chandler';
    
* It will give us everything from person if first_name is Chandler

**To filter data based on multiple condition**

    SELECT * FROM person 
    WHERE first_name='Chandler' AND last_name='Bing';
    
* There are two condition base keyword AND & OR..
* AND = have to match both side.
* OR = have to match any of the side not both.
    
**Comparison operator**

* <	less than
* \>	greater than
* <=	less than or equal to
* \>=	greater than or equal to
* =	equal
* <> or !=	not equal

**To use arithmatic operation in cmd**

    SELECT 1=1; -> output TRUE
    SELECT 1<>1; -> output FALSE
    
    SELECT * FROM person WHERE id>5;
    
**TO filter a null value**

    SELECT * FROM person WHERE email IS NULL;
    
**To print a limited data**

    SELECT * FROM person
    LIMIT 2;

* Only first two row will be printed

**TO start from any row**

    SELECT * FROM person 
    OFFSET 5;
    
* It will print row from 5 number row.

**IN keyword**

    SELECT * FROM person 
    WHERE id in (2,3);
   
 * which people's id is 2 or 3 there everything will be printed.

**To select data from a range **
  
    SELECT * FROM person 
    WHERE join_date 
    BETWEEN '2019-02-02' AND '2021-03-02'

**Wild Card / Regular expression**

* % = any number of character
* _ = only one number of character

      SELECT * FROM person 
      WHERE email LIKE '%@gmail.com';
      
 * % = any number of character.
 * LIKE = equal. (work same way)
 * it will be matched by every perso whom has a email
 * because every email has some character before @.

        SELECT * FROM person 
        WHERE gender LIKE '__LE';
        
 * _ = only one character
 * there are two _ (unserscore) that 
 * means Before 'LE' there must be two character 
 * otherwise it won't print table's data
    
        SELECT * FROM person 
        WHERE gender ILIKE '__LE';
 
 * ILIKE means ignore case (that means either we put small letter or capital letter it will behave same)

**Aggregate Functions**

* AVG() – return the average value.
* COUNT() – return the number of values.
* MAX() – return the maximum value.
* MIN() – return the minimum value.
* SUM() – return the sum of all or distinct values.

      SELECT AVG(mark)
      FROM student;
      
* print average mark

      SELECT COUNT(*)
      FROM student;

* print how many student inserted in database

      SELECT MAX(mark)
      FROM student;
      
* print max mark from all student

      SELECT MIN(mark)
      FROM student;
      
* print min mark from all student

      SELECT SUM(mark)
      FROM student;

* print total sum of all student mark

 

**GROUPING BY**



      


    






























 
 
