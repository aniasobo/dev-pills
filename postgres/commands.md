# Basic Postgres in command line

### Connect to pg in terminal:

1. have the pg server running (should be default but check pg app), then `psql`  
2. `\l` lists existing databases
3. `\c test` connects to the test db  
4. `\d tablename` shows just this table
5. `\dt` lists all tables

### single-line connect: `~ psql -h localhost -p 5432 -U username databasename`  

### delete db with `DROP DATABASE dbname;`  

[Postgres data types documentation](https://www.postgresql.org/docs/9.5/datatype.html)  

