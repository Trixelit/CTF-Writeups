# Counting STARs (150)

## Challenge Description
We know DEADFACE is trying to get their hands on STAR, so it makes sense that they will try to target the doctor who prescribes the most STAR from the Aurora database. Provide the first and last name and the type of doctor (position name) that prescribed the most STAR from the database.

Submit the flag as flag{FirstName LastName Position}.

For example: flag{John Doe Podiatrist}

Use the database dump from ***Aurora Compromise***.

## Solution

To count the number of times each doctor prescribed STAR, we can run this query:
```sql
SELECT doctor_id,drug_id,COUNT(doctor_id) AS 'value_occurence' FROM prescriptions WHERE drug_id = 26 GROUP BY doctor_id ORDER BY value_occurence DESC LIMIT 1;
```
This query results in:
```sql
+-----------+---------+-----------------+
| doctor_id | drug_id | value_occurence |
+-----------+---------+-----------------+
|      1957 |      26 |               8 |
+-----------+---------+-----------------+
```
This shows that doctor_id 1957 prescribed STAR on 8 separate occasions.
To get the rest of this doctor's information we can run:
```sql
SELECT first_name,last_name FROM staff WHERE staff_id = 1957;
-- The doctor's name is Alisa MacUchadair.
SELECT * FROM positions_assigned WHERE staff_id = 1957;
-- Position ID 18
SELECT * FROM positions WHERE position_id = 18;
-- Dermatologist
```

Our flag is ```flag{Alisa MacUchadair Dermatologist}```.