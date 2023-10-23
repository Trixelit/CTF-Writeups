# City Hoard (100)

## Challenge Description
Aurora is asking for help in determining which city has the facility with the largest inventory of Remizide based on the Aurora database.

Submit the flag as flag{city}.

Use the database dump from ***Aurora Compromise***.

## Solution

We can run these queries to obtain the data we need:

```sql
SELECT drug_id FROM drugs WHERE drug_name = 'Remizide'; -- Drug ID 13

SELECT * FROM inventory WHERE drug_id = 13 
ORDER BY qty DESC LIMIT 1; -- Facility 531 has the largest amount, 2999.

SELECT city FROM facilities WHERE facility_id = 531; -- Miami
```

Our flag is ```flag{Miami}```.