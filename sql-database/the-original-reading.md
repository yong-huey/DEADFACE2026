# The Original Reading

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge asked for the original reading of a drug trial result that had been modified to make the drug appear effective.

## Solution

Since the question concerned a trial drug, I investigated the aurora_trials database:

```sql
USE aurora_trials;
```

I examined the data_changes table to look for records of modified trial data:

```sql
SELECT * FROM data_changes;
```

The results contained only one old/new value pair. This showed the reading before and after the modification, allowing me to identify the original result.

Since the challenge requested the reading before it was changed, I submitted the old value as the flag.

## Takeaway

The change history preserved the original reading, making it possible to recover the value even after the trial result had been modified.

[Back to challenge index](../README.md)
