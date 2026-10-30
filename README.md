# DEADFACE CTF 2026 Writeups

**Status: In Progress**

A collection of my DEADFACE CTF 2026 writeups, documenting how I approached challenges, investigated clues, and recovered flags. Each writeup explains the objective, my solution process, relevant commands, and key takeaways.

## Types of Challenges Completed

This collection contains **15 solved challenges** across three categories. All medical-device challenges, including those involving web inspection and Linux, are grouped together.

| Category | Number | Types of Tasks |
|---|---:|---|
| SQL/Database | 8 | Finding records, linking tables, investigating audit logs, filtering prescriptions, and identifying modified trial data |
| Medical Device | 5 | Inspecting web interfaces, discovering default credentials, accessing diagnostics, exploring filesystems, and using debug functionality |
| Cryptography | 2 | Decoding a ROT13 message and solving a three-digit combination puzzle |

## Challenge Index

| Challenge | Category |
|---|---|
| [Admitted Under Another Name](sql-database/admitted-under-another-name.md) | SQL/Database |
| [Schedule of Concern](sql-database/schedule-of-concern.md) | SQL/Database |
| [The Attending](sql-database/the-attending.md) | SQL/Database |
| [Prying Eyes](sql-database/prying-eyes.md) | SQL/Database |
| [The Original Reading](sql-database/the-original-reading.md) | SQL/Database |
| [Heavy Hand](sql-database/heavy-hand.md) | SQL/Database |
| [Up the Throne](sql-database/up-the-throne.md) | SQL/Database |
| [After the Lock](sql-database/after-the-lock.md) | SQL/Database |
| [Bedside Manner](medical-device/bedside-manner.md) | Medical Device |
| [Factory Reset](medical-device/factory-reset.md) | Medical Device |
| [Second Opinion](medical-device/second-opinion.md) | Medical Device |
| [Live Boot](medical-device/live-boot.md) | Medical Device |
| [Dump It](medical-device/dump-it.md) | Medical Device |
| [Hail Caesar](cryptography/hail-caesar.md) | Cryptography |
| [DECODE-DLE](cryptography/decode-dle.md) | Cryptography |

## Skills Practised

### SQL and Database Investigation

- Enumerating databases and tables using `SHOW DATABASES` and `SHOW TABLES`.
- Filtering records using `SELECT`, `WHERE`, and date ranges.
- Following patient, provider, and user identifiers across related tables and databases.
- Investigating audit logs to identify patterns of patient-record access.
- Comparing original and modified values to investigate data tampering.
- Checking modification timestamps against a clinical trial's data-lock date.

### Medical Device Security

- Exploring exposed maintenance interfaces in a simulated medical device environment.
- Investigating patient information exposed through HDMI diagnostic displays.
- Finding and testing default technician credentials from device documentation.
- Inspecting page source and JavaScript files for developer strings and API endpoints.
- Accessing a Linux shell, mounting a partition, and navigating the filesystem.
- Locating hardcoded secrets in application configuration files.
- Using a Rubber Ducky USB-A tool to interact with kiosk maintenance functionality.
- Using an exposed debug function to dump patient data.

### Cryptography and Logical Reasoning

- Decoding Caesar ciphers by testing different rotations, including ROT13.
- Solving number puzzles through elimination and comparison of clues.
- Testing remaining candidates to confirm a solution.

### Technical Documentation

- Turning investigation notes into structured walkthroughs.
- Explaining why each command or technique was used.
- Recording unsuccessful attempts when they informed the next step.
- Connecting findings across related challenges.

## Tools and Techniques

- SQL CLI
- Browser developer tools and View Page Source
- Linux shell commands: `help`, `ls`, `cd`, `cat`, and `mount`
- Caesar cipher decoder
- Challenge-provided HDMI, Linux USB-A, and Rubber Ducky USB-A tools

## Repository Organisation

- `sql-database/` — eight SQL and database writeups.
- `medical-device/` — five medical-device writeups, including web and Linux tasks.
- `cryptography/` — two cryptography and logic writeups.

Each challenge has its own Markdown file. Open a link in the challenge index to read it.

## Work in Progress

- Adding screenshots and relevant command output.
- Recording exact submitted flags where they are not yet included in the notes.
- Reviewing explanations for clarity and reproducibility.
- Expanding lessons learned from each challenge.

The writeups preserve the findings recorded in my notes. Missing flag values have not been guessed. No screenshots were embedded in the source document used for this conversion.

## Scope

These activities were performed within the provided CTF environment. They do not describe testing against real hospital systems.
