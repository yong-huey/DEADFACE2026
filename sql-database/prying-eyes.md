# Prying Eyes

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge asked for the username of the person who accessed the VIP patient’s record.

## Solution

I returned to aurora_ehr and retrieved the VIP patient’s details:

```sql
SELECT * FROM patients WHERE is_vip = 1;
```

I noted the patient’s MRN, AH-0044719, then investigated the aurora_audit database for access logs associated with that patient.

I filtered the audit_log table using the MRN:

```sql
SELECT * FROM audit_log WHERE mrn = 'AH-0044719';
```

While reviewing the matching entries, I noticed that user_id = 10 appeared most frequently, indicating that this user had accessed the patient’s record the most.

The same database contained a users table, so I looked up that user:

```sql
SELECT * FROM users WHERE user_id = 10;
```

The result showed the user’s details, including their username, which I submitted as the flag.

## Takeaway

The patient’s MRN linked their clinical record to the audit entries, while user_id linked those entries to the account responsible for the access.

[Back to challenge index](../README.md)
