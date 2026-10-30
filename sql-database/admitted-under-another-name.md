# Admitted Under Another Name

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge description mentioned that the patient was flagged as VIP, so I used that clue to guide my search.

## Solution

I started by listing the available databases through the SQL CLI:

```sql
SHOW DATABASES;
```

After exploring aurora_audits and aurora_ehr, I found a patients table in aurora_ehr. I displayed its contents with:

```sql
SELECT * FROM patients;
```

While reviewing the results, I noticed an is_vip column containing either 1 or 0. I interpreted 1 as indicating a VIP patient and filtered the records:

```sql
SELECT * FROM patients WHERE is_vip = 1;
```

The results included the patient's mrn (medical record number). I copied that value and submitted it as the flag.

## Takeaway

The key was translating the clue in the challenge description into a SQL filter. Identifying the is_vip column allowed me to narrow down the patient records and locate the MRN.

[Back to challenge index](../README.md)
