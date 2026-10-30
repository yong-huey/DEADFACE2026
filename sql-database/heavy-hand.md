# Heavy Hand

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge asked for the DEA number of the prescriber associated with the most Schedule II drugs during the specified date range.

## Solution

I first identified the Schedule II drugs in the drugs table:

```sql
SELECT * FROM drugs WHERE dea_schedule = 'II';
```

The matching drugs had IDs from 1 to 9. I then used those IDs to filter the prescriptions table, restricting the results to the period from October 1 to December 31, 2025:

```sql
SELECT * FROM prescriptions
WHERE (drug_id BETWEEN 1 AND 9)
  AND (written_date BETWEEN '2025-10-01' AND '2025-12-31');
```

After reviewing the matching records, I identified prescriber_id = 2 as the prescriber associated with the most Schedule II drugs during that period.

I looked up their details in the prescribers table:

```sql
SELECT * FROM prescribers WHERE prescriber_id = 2;
```

The result included the prescriber’s DEA number, which I submitted as the flag.

## Takeaway

Linking drug IDs to prescription records and filtering by date narrowed the investigation to the relevant activity. The resulting prescriber ID then led to the DEA number.

[Back to challenge index](../README.md)
