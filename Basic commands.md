
## PostgreSQL Basic Commands

### How to List Existing Databases
```sql
\list or \l
```

### Clear Console or SQL Shell Display
```sql
\! cls
```

### How to Create a Database in PostgreSQL Using SQL Shell
```sql
CREATE DATABASE "DATABASE_NAME";
```

### How to List Database Names Only
```sql
SELECT datname FROM pg_database;
```

### Switching Between Databases
Suppose you have two databases named `students` and `employee`. If you are in the `students` database but need to switch to `employee`, use:
```sql
\c employee;
```

### How to Delete a Database
```sql
DROP DATABASE "database_name";
```
**Note:** The database should not be running on the server; stop it first before deleting.
