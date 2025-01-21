
### Creating and Managing Databases
```sql
-- Create a new database
CREATE DATABASE database_name;

-- Show all databases
SHOW DATABASES;

-- Select a database to use
USE database_name;

-- Delete a database
DROP DATABASE database_name;
```

### Table Operations
```sql
-- Create a table
CREATE TABLE table_name (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Show all tables
SHOW TABLES;

-- View table structure
DESCRIBE table_name;

-- Delete a table
DROP TABLE table_name;

-- Modify table structure
ALTER TABLE table_name ADD COLUMN column_name VARCHAR(100);
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name MODIFY COLUMN column_name INT;
```

### Data Manipulation
```sql
-- Insert data
INSERT INTO table_name (column1, column2) VALUES ('value1', 'value2');

-- Update data
UPDATE table_name SET column1 = 'new_value' WHERE condition;

-- Delete data
DELETE FROM table_name WHERE condition;

-- Select data
SELECT * FROM table_name;
SELECT column1, column2 FROM table_name WHERE condition;
```

## Advanced Features

### Joins
```sql
-- Inner Join
SELECT * FROM table1
INNER JOIN table2 ON table1.id = table2.table1_id;

-- Left Join
SELECT * FROM table1
LEFT JOIN table2 ON table1.id = table2.table1_id;

-- Right Join
SELECT * FROM table1
RIGHT JOIN table2 ON table1.id = table2.table1_id;
```

### Aggregation Functions
```sql
-- Common aggregations
SELECT 
    COUNT(*) as total_count,
    SUM(column_name) as total_sum,
    AVG(column_name) as average,
    MAX(column_name) as maximum,
    MIN(column_name) as minimum
FROM table_name
GROUP BY category_column;
```

### Indexes
```sql
-- Create index
CREATE INDEX index_name ON table_name (column_name);

-- Create unique index
CREATE UNIQUE INDEX index_name ON table_name (column_name);

-- Show indexes
SHOW INDEX FROM table_name;

-- Drop index
DROP INDEX index_name ON table_name;
```

### Views
```sql
-- Create view
CREATE VIEW view_name AS
SELECT column1, column2
FROM table_name
WHERE condition;

-- Show views
SHOW FULL TABLES WHERE table_type = 'VIEW';

-- Drop view
DROP VIEW view_name;
```

### Performance Optimization
1. Use appropriate indexes for frequently queried columns
2. Avoid SELECT * when specific columns are needed
3. Use EXPLAIN to analyze query execution plans
4. Regularly optimize tables: `OPTIMIZE TABLE table_name;`

### Security
1. Use prepared statements to prevent SQL injection
2. Grant minimum necessary privileges to users
3. Regularly backup databases
4. Use encryption for sensitive data

### Backup and Restore
```sql
-- Backup database
mysqldump -u username -p database_name > backup.sql

-- Restore database
mysql -u username -p database_name < backup.sql
```

## Common Data Types

### Numeric Types
- INT: Regular integer
- BIGINT: Large integer
- DECIMAL(M,D): Exact decimal
- FLOAT: Approximate decimal

### String Types
- VARCHAR(n): Variable-length string
- TEXT: Long text
- CHAR(n): Fixed-length string
- ENUM: List of possible values

### Date/Time Types
- DATE: Date only
- TIME: Time only
- DATETIME: Date and time
- TIMESTAMP: Timestamp with timezone

### Binary Types
- BLOB: Binary Large Object
- BINARY: Fixed-length binary string
