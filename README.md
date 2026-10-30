# DEADFACE CTF 2026 Writeups

**Status: In Progress**

A collection of my writeups for DEADFACE CTF 2026, documenting how I approached challenges, investigated clues, and recovered flags.

This repository is being updated as I organise my notes and complete the writeups. Each writeup covers the challenge objective, my investigation process, relevant commands, and key takeaways.

## Types of Challenges Completed

I have solved **16 challenges** across three categories:

| Category | Number | Types of Tasks |
|---|---:|---|
| SQL/Database | 8 | Finding records, linking tables, investigating audit logs, filtering prescriptions, and identifying modified trial data |
| Medical Device | 6 | Inspecting web interfaces, discovering default credentials, accessing diagnostics, exploring filesystems, and using debug functionality |
| Cryptography | 2 | Decoding a ROT13 message and solving a three-digit combination puzzle |

## Skills Practised

### SQL and Database Investigation

- Enumerating databases and tables using `SHOW DATABASES` and `SHOW TABLES`.
- Filtering records using `SELECT`, `WHERE`, and date ranges.
- Following patient, provider, and user identifiers across related tables.
- Investigating audit logs to identify patterns of patient-record access.
- Comparing original and modified values to investigate data tampering.
- Checking modification timestamps against a clinical trial’s data-lock date.
- Connecting related records across multiple databases.

### Medical Device Security

- Exploring exposed maintenance interfaces in a simulated medical device environment.
- Investigating patient information exposed through HDMI diagnostic displays.
- Finding and testing default technician credentials from device documentation.
- Inspecting page source and JavaScript files for developer strings and API endpoints.
- Accessing a Linux shell, mounting a partition, and navigating the device’s filesystem.
- Locating hardcoded secrets in application configuration files.
- Using a Rubber Ducky USB-A tool to interact with kiosk maintenance functionality.
- Using an exposed debug function to dump patient data.

### Cryptography and Logical Reasoning

- Decoding Caesar ciphers by testing different rotations, including ROT13.
- Solving number puzzles through elimination and comparison of clues.
- Testing remaining candidates to confirm a solution.

### Technical Documentation

- Turning investigation notes into reproducible walkthroughs.
- Explaining why each command or technique was used.
- Recording unsuccessful attempts when they informed the next step.
- Connecting findings across related challenges.

## Challenges Covered

| Challenge | Category | Main Focus |
|---|---|---|
| Admitted Under Another Name | SQL/Database | Identifying a VIP patient and retrieving their MRN |
| Schedule of Concern | SQL/Database | Filtering and counting Schedule II drugs |
| The Attending | SQL/Database | Linking clinical notes to a provider’s username |
| Prying Eyes | SQL/Database | Tracing patient-record access through audit logs |
| The Original Reading | SQL/Database | Recovering an original value from change history |
| Heavy Hand | SQL/Database | Investigating prescriptions within a date range |
| Up the Throne | SQL/Database | Matching handler references across databases |
| After the Lock | SQL/Database | Identifying trial results modified after data lock |
| Bedside Manner | Medical Device | Finding a developer string in page source |
| Factory Reset | Medical Device | Accessing a technician account using default credentials |
| Second Opinion | Medical Device | Recovering information through HDMI diagnostics |
| Live Boot | Medical Device | Inspecting a mounted filesystem for hardcoded secrets |
| Dump It | Medical Device | Using kiosk debug functionality to dump data |
| Hail Caesar | Cryptography | Decoding a ROT13 message |
| DECODE-DLE | Cryptography | Determining a three-digit code through logical elimination |

## Tools and Techniques

- SQL CLI
- Browser developer tools and View Page Source
- Linux shell commands: `help`, `ls`, `cd`, `cat`, and `mount`
- Caesar cipher decoder
- Challenge-provided HDMI, Linux USB-A, and Rubber Ducky USB-A tools

## Scope

These activities were performed within the provided CTF environment. The writeups document my learning and approach to the challenges; they do not describe testing against real hospital systems.

## Work in Progress

- Organising individual challenge writeups.
- Adding screenshots and relevant command output.
- Reviewing explanations for clarity and reproducibility.
- Expanding lessons learned from each challenge.
