# CRUD Operations in PostgreSQL

CRUD stands for **Create**, **Read**, **Update**, and **Delete**, which are the four basic operations that you can perform on any database. In PostgreSQL, these operations are executed using SQL commands. Below are the details of each CRUD operation.

## 1. **Create**  
   The **Create** operation is used to insert new records into a table.  
   - **Syntax:**
     ```sql
     INSERT INTO <table_name> (column1, column2, column3)
     VALUES (value1, value2, value3);
     ```

   - **Example:**
     ```sql
     INSERT INTO students (id, name, address)
     VALUES (1, 'Sharwan', 'Kathmandu');
     ```

## 2. **Read**  
   The **Read** operation is used to retrieve data from the table. You can select all or specific columns, or even apply conditions using a `WHERE` clause.  
   - **Syntax to select all records:**
     ```sql
     SELECT * FROM <table_name>;
     ```

   - **Syntax to select specific columns:**
     ```sql
     SELECT column1, column2 FROM <table_name>;
     ```

   - **Example:**
     ```sql
     SELECT * FROM students;
     SELECT name, address FROM students WHERE id = 1;
     ```

## 3. **Update**  
   The **Update** operation is used to modify existing data in a table. You should always use a `WHERE` clause to specify which record(s) to update.  
   - **Syntax:**
     ```sql
     UPDATE <table_name>
     SET column1 = value1, column2 = value2
     WHERE condition;
     ```

   - **Example:**
     ```sql
     UPDATE students
     SET address = 'Bhaktapur'
     WHERE id = 1;
     ```

## 4. **Delete**  
   The **Delete** operation is used to remove records from a table. Again, it's important to use a `WHERE` clause to avoid deleting all records from the table.  
   - **Syntax:**
     ```sql
     DELETE FROM <table_name>
     WHERE condition;
     ```

   - **Example:**
     ```sql
     DELETE FROM students
     WHERE id = 1;
     ```

## Summary of CRUD Operations:

| Operation | SQL Command | Example |
|-----------|-------------|---------|
| Create    | `INSERT INTO <table_name> (column1, column2) VALUES (value1, value2);` | `INSERT INTO students (id, name) VALUES (1, 'Sharwan');` |
| Read      | `SELECT column1, column2 FROM <table_name>;` | `SELECT * FROM students;` |
| Update    | `UPDATE <table_name> SET column1 = value1 WHERE condition;` | `UPDATE students SET address = 'Kathmandu' WHERE id = 1;` |
| Delete    | `DELETE FROM <table_name> WHERE condition;` | `DELETE FROM students WHERE id = 1;` |

CRUD operations are essential for managing and manipulating data in PostgreSQL databases. By mastering these operations, you can efficiently interact with your database and perform data management tasks.
