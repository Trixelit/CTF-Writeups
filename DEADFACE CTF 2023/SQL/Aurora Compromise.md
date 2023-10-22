## Challenge Description  

DEADFACE has taken responsibility for a partial database hack on a pharmacy tied to Aurora Pharmaceuticals. The hacked data consists of patient data, staff data, and information on drugs and prescriptions.

We’ve managed to get a hold of the hacked data. Provide the first and last name of the patient that lives on a street called Hansons Terrace.

Submit the flag as: flag{First Last}.

## Solution

Running the query:
```sql
SELECT first_name,last_name FROM patients WHERE street LIKE '%Hansons Terrace%';
```
Will result in an output of
```sql
+------------+-----------+
| first_name | last_name |
+------------+-----------+
| Sandor     | Beyer     |
+------------+-----------+
```

This means our flag is ```flag{Sandor Beyer}```.