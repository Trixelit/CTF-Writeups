# Starypax (50)

## Challenge Description
Starypax (street name STAR) is a controlled substance and is in high demand on the Dark Web. DEADFACE might leverage this database to find out which patients currently carry STAR.

How many patients in the Aurora database have an active prescription for Starypax as of Oct 20, 2023? And whose prescription expires first?

Submit the flag as flag{#_firstname lastname}.

Use the database dump from ***Aurora Compromise***.

## Solution
Several SQL Queries are required for this challenge:
```sql
SELECT drug_id FROM drugs WHERE drug_name = 'Starypax' -- Drug ID 26.

SELECT * FROM prescriptions WHERE drug_id = 26 AND expiration > '2023-10-20' ORDER BY expiration; -- Results in 7 entries, the first expiry being patient 10042's prescription.

SELECT first_name,last_name FROM patients WHERE patient_id = 10042; -- Renae Allum
```

Our flag is ```flag{7_Renae Allum}```.