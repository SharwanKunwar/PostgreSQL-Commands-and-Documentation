# PostgreSQL Database Deletion Guide

## Overview
This document explains what happens when all databases in a PostgreSQL instance are deleted and provides guidance on recovery.

## List of Default Databases
### User-Created Databases
- **Love** (User-created)
- **friends_list** (User-created)

### System Databases
- **postgres**: Default administrative database.
- **template0**: System template, used for creating databases.
- **template1**: Default template for new databases.

## Consequences of Deleting All Databases

### 1. Deleting User-Created Databases
- Data stored in `Love` and `friends_list` will be permanently lost.
- Applications relying on these databases will stop functioning.

### 2. Deleting `postgres`
- This is required for administrative tasks.
- Removing it may break `psql` and prevent PostgreSQL from functioning properly.

### 3. Deleting `template0` and `template1`
- **template1** is the default template for creating new databases. Without it, new databases cannot be created.
- **template0** is a pristine template. Deleting it can make recovery more difficult.

## Worst-Case Scenario
If all databases, including `postgres`, `template0`, and `template1`, are deleted:
- PostgreSQL may become non-functional.
- Creating new databases may not be possible without manual intervention.
- You might need to reinstall PostgreSQL and reinitialize the database cluster.

## Recovery Steps
### If PostgreSQL is still running:
1. Manually recreate `template1` and `postgres`.
2. Restore backups if available.

### If PostgreSQL is broken:
1. Reinstall PostgreSQL.
2. Reinitialize the database cluster using:
   ```bash
   initdb -D /var/lib/postgresql/data
   ```
3. Restore databases from backups if available.

## Recommendations
- **Do not delete `template0`, `template1`, or `postgres` unless absolutely necessary.**
- If resetting the database, only drop user-created databases (`Love`, `friends_list`).
- Always create a backup before deleting critical databases.

## Additional Resources
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Backup and Restore Guide](https://www.postgresql.org/docs/current/backup.html)

