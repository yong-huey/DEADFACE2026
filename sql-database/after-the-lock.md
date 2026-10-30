# After the Lock

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge asked for the subject code of a participant whose primary efficacy result was modified after the Veltrexa study’s data-lock date. Any change after that date would indicate a protocol violation and potential tampering.

## Solution

Since the challenge concerned clinical trial data, I selected aurora_trials and inspected the study records:

```sql
USE aurora_trials;
SELECT * FROM studies;
```

The Veltrexa study’s data_lock_date was 2025-12-01. I then retrieved the primary efficacy results:

```sql
SELECT * FROM results
WHERE measure = 'primary_efficacy_delta';
```

While reviewing the results, I found only one record with a populated modified_at value. Its timestamp was after the study’s data-lock date, identifying it as the suspicious modification. The record belonged to subject_id = 137.

I looked up the corresponding subject:

```sql
SELECT * FROM subjects WHERE subject_id = 137;
```

The result showed the subject code VELT-0137, which I submitted as the flag.

## Takeaway

Comparing a result’s modification timestamp against the official data-lock date revealed the suspicious record. Following its subject_id to the subjects table provided the required subject code.

[Back to challenge index](../README.md)
