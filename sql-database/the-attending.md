# The Attending

**Event:** DEADFACE CTF 2026  
**Category:** SQL/Database

## Challenge

The challenge directed me back to the VIP patient and asked for the username of the associated provider.

## Solution

I took note of the VIP patient’s ID and examined the corresponding records in the clinical_notes table. The notes stated that the patient was admitted under an alias according to VIP protocol, confirming the connection to the patient I was investigating.

The clinical notes also contained a provider_id field with the value 5. This gave me an identifier to trace back to the provider.

From the tables listed by SHOW TABLES;, I noticed a table named providers, which appeared likely to contain the provider’s details. I queried it using the ID found in the clinical notes:

```sql
SELECT * FROM providers WHERE provider_id = 5;
```

The result contained the provider’s details, including their username. Since the challenge requested that username, I submitted it as the flag.

## Takeaway

Linking the VIP patient’s clinical notes to the corresponding provider record through provider_id revealed the username needed to solve the challenge.

[Back to challenge index](../README.md)
