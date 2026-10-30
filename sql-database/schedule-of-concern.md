# Schedule of Concern

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge asked for the number of DEA Schedule II drugs. Its reference to the pharmacy pointed me toward aurora_pharmacy, which I had seen in the earlier database listing:

## Solution

```sql
SHOW DATABASES;
```

I selected the database and listed its tables:

```sql
USE aurora_pharmacy;
SHOW TABLES;
```

After locating the drugs table, I inspected its contents:

```sql
SELECT * FROM drugs;
```

I noticed a dea_schedule column, where the value II identified Schedule II drugs. I filtered the table to display those records:

```sql
SELECT * FROM drugs WHERE dea_schedule = 'II';
```

I counted the matching drugs and submitted that quantity as the flag. The same count could also be obtained directly using:

```sql
SELECT COUNT(*) FROM drugs WHERE dea_schedule = 'II';
```

## Takeaway

Translating the challenge’s wording into a filter on dea_schedule allowed me to isolate the relevant drugs and determine the quantity required for the flag.

[Back to challenge index](../README.md)
