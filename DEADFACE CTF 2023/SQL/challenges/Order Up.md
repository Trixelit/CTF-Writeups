# Order Up (125)

## Challenge Description
Dr. Flegg prescribed Automeda to a patient in June 2023. What is the order number for this prescription?

Submit the flag as ```flag{order_num}```.

Use the database dump from ***Aurora Compromise***.

## Solution

To get Dr. Flegg's staff ID, we run
```sql
SELECT staff_id FROM staff where last_name = 'Flegg'; -- Staff ID 1953
```

Using Flegg's staff ID, we can query a list of every medication he prescribed, and filter the data based on the information in the challenge description.

```sql
SELECT drug_id FROM drugs WHERE drug_name = 'Automeda' -- Drug ID 9

SELECT * FROM prescriptions WHERE drug_id = 9 
AND date_prescribed > '2023-05-31' 
AND date_prescribed < '2023-07-01' 
AND doctor_id = 1953; 
-- Prescription ID 7170
```

To get the order number, we can run this query:
```sql
SELECT * FROM orders WHERE prescription_id = 7170; -- Order number DYP8AXK3QG9OTPWB
```

Our flag is ```flag{DYP8AXK3QG9OTPWB}```.