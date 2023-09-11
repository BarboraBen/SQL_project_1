## Examples of altering tables
### Delete table
```DROP TABLE hotel;```

### Add new column
```
ALTER TABLE payment
ADD COLUMN total character varying;
```

### Rename column
```
ALTER TABLE payment
RENAME COLUMN total
TO total_amount;
```

### Change data type
```
ALTER TABLE payment
ALTER COLUMN total_amount TYPE integer
USING total_amount::integer;
```

### Set default value
```
ALTER TABLE payment 
ALTER COLUMN total_amount
SET DEFAULT 0;
```

### Delete column
```
ALTER TABLE payment
DROP COLUMN total_amount;
```
