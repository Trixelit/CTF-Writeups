# Transaction Approved (100)

## Challenge Description
Turbo Tactical wants you to determine how many credit cards are still potentially at risk of being used by DEADFACE. How many credit cards in the Aurora database are NOT expired as of Oct 2023?

Submit the flag as ```flag{#}```.

Use the database dump from ***Aurora Compromise***.

## Solution
```sql
SELECT DISTINCT card_num FROM billing WHERE exp > '2023-10';
```

This results in ```8785 rows in set```, so our flag is ```flag{8785}```.