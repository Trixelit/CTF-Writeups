# Credit Compromise (15)

## Challenge Description
How many credit cards were exposed in the Aurora database hack?

Submit the flag as flag{#}.

Use the database dump from ***Aurora Compromise***.

## Solution
We can list the number of credit cards with the query:
```sql
SELECT DISTINCT card_num FROM billing;
```
Which results in ```10391 rows in set```.

Our flag is ```flag{10391}```.