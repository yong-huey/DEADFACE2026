# Up the Throne

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge asked for the insider’s handler_ref, with the clue that their codename appeared in both the users table in aurora_audit and the providers table in aurora_ehr.

## Solution

From previous challenges, I had noted the relevant usernames and user IDs. To investigate their handler references, I first displayed the user records:

```sql
USE aurora_audit;
SELECT * FROM users;
```

I then switched to aurora_ehr and displayed the provider records:

```sql
USE aurora_ehr;
SELECT * FROM providers;
```

Using the identifiers from my earlier findings, I located the relevant entries and compared their handler_ref values. Both contained REVENANT-7, linking the records across the two databases.

I submitted REVENANT-7 as the flag.

## Takeaway

Tracking identifiers across challenges helped me locate related records, while comparing their handler references revealed the connection between them.

[Back to challenge index](../README.md)
