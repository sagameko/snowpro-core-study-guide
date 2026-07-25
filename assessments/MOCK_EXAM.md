# SnowPro Core (COF-C03) Full Mock Exam

**40 original practice questions spanning all 8 chapters of this study guide**, weighted roughly proportional to the real COF-C03 domain weights. This is a knowledge check to take **after** completing all chapters — not a replacement for the real exam's difficulty or format guarantees.

- **Format:** 40 multiple-choice / multiple-select questions (multi-select questions are marked "Choose two" or "Choose three")
- **Suggested time limit:** 46 minutes (scaled down proportionally from the real exam's 115 minutes for 100 questions)
- **Target score before booking your real exam:** 80%+ (32/40 or better)
- **Answer key with explanations:** at the end of this document

Every question here is original, written from public Snowflake documentation for this study guide. These are **not** real exam questions — using leaked/memorized real exam content violates Snowflake's certification agreement.

---

## Domain 1: Architecture (Chapters 1, 2, 8) — Questions 1–13

**1.** What is the foundational architectural principle that separates Snowflake from traditional on-premises data warehouses?

A. NoSQL document storage
B. Separation of storage and compute into independently scaling layers
C. Mandatory manual indexing
D. Single-cluster-only compute

**2.** Which Snowflake layer handles query parsing, optimization, and RBAC enforcement?

A. Storage layer
B. Compute layer
C. Cloud Services layer
D. Client layer

**3.** (Choose two) Which statements about micro-partitions are true?

A. They are immutable
B. They are updated in place
C. They typically hold 50MB–500MB of uncompressed data
D. They require manually defined partition keys

**4.** A team needs 60 days of Time Travel retention. What is required?

A. Standard edition is sufficient
B. Enterprise edition or above
C. This is not possible on any edition
D. A resource monitor must be configured

**5.** What makes zero-copy cloning near-instant regardless of table size?

A. Data is compressed before cloning
B. Clones reference existing micro-partitions via metadata rather than physically copying data
C. Cloning happens asynchronously over hours
D. Only empty tables can be cloned

**6.** Users report individually slow, complex queries with no queuing. What's the most direct fix?

A. Enable multi-cluster warehousing
B. Increase the warehouse size
C. Decrease auto-suspend time
D. Enable Search Optimization

**7.** Users report queuing during peak concurrent usage, with individually fast queries. What's the most direct fix?

A. Increase warehouse size
B. Configure a multi-cluster warehouse
C. Decrease warehouse size
D. Disable the result cache

**8.** Which edition is the minimum required for multi-cluster warehouses?

A. Standard
B. Enterprise
C. Business Critical only
D. Available on all editions

**9.** How are Snowflake warehouse credits billed?

A. Flat monthly fee
B. Per-second, 60-second minimum, only while running
C. Per query
D. Per gigabyte stored

**10.** Which of these runs on Snowflake-managed serverless compute rather than a user warehouse?

A. A manually run SELECT statement
B. Snowpipe continuous loading
C. A COPY INTO explicitly run on a named warehouse
D. A stored procedure explicitly called with a warehouse specified

**11.** What is the primary benefit of Cortex AI functions over exporting data to an external AI service?

A. They are always faster
B. AI processing happens inside Snowflake's governance boundary without moving data out
C. They eliminate the need for warehouses
D. They only work on numeric data

**12.** Why might a team choose an Iceberg table over a native Snowflake table?

A. Iceberg tables require no compute
B. Interoperability with other compute engines (Spark, Trino) reading/writing the same data
C. Iceberg tables are always cheaper
D. Native tables cannot store structured data

**13.** What does Snowflake's Git integration actually sync into the account?

A. A live, real-time mount of the external Git service
B. A Snowflake-managed clone of the repository that objects can reference
C. Nothing — Git integration is purely cosmetic
D. Only compiled binaries, never source files

---

## Domain 2: Account Access & Governance (Chapter 3) — Questions 14–21

**14.** How are privileges typically assigned to a Snowflake user?

A. Directly to the user account
B. Granted to roles, which are granted to users
C. Inherited automatically from department
D. Assigned per warehouse only

**15.** Which role is the recommended parent for custom roles managing day-to-day objects?

A. ACCOUNTADMIN
B. USERADMIN
C. SYSADMIN
D. PUBLIC

**16.** Which role is dedicated to creating and managing users and roles?

A. SYSADMIN
B. USERADMIN
C. ACCOUNTADMIN exclusively
D. PUBLIC

**17.** What's the recommended authentication method for automated scripts and service accounts?

A. Shared plaintext password
B. Key pair authentication
C. No authentication
D. A single shared admin account

**18.** What does a dynamic data masking policy do?

A. Permanently deletes sensitive data
B. Conditionally masks column values at query time based on role, without altering stored data
C. Encrypts the whole table at rest
D. Blocks all table access

**19.** How do row access policies differ from masking policies?

A. Row access controls column visibility; masking controls row visibility
B. Row access controls which rows are returned; masking controls/obscures column values — both dynamic
C. They're identical features
D. Row access physically deletes unauthorized rows

**20.** (Choose two) What can a resource monitor do at a defined credit threshold?

A. Send a notification
B. Automatically suspend associated warehouses
C. Automatically upgrade the account edition
D. Permanently delete the warehouse

**21.** What is the scope of Snowflake's PUBLIC role?

A. Granted only to ACCOUNTADMIN
B. Automatically available to every user and role in the account
C. Has no practical effect
D. Grants ACCOUNTADMIN-level privileges

---

## Domain 3: Data Loading, Unloading & Connectivity (Chapter 4) — Questions 22–28

**22.** Which internal stage type cannot be granted to other roles for shared access?

A. Named internal stage
B. Table stage
C. External stage
D. User stage granted to a role

**23.** What happens when the same COPY INTO \<table\> command is run twice on the same file in the same stage?

A. Data loads twice
B. Snowflake's load metadata prevents reloading the same file by default
C. The command always errors
D. The table auto-truncates first

**24.** Files periodically land in an S3 bucket and need automated loading without a scheduled batch job. Best fit?

A. Manual scheduled COPY INTO
B. Snowpipe
C. GET command
D. Table stage

**25.** Individual application events need streaming into Snowflake with minimal latency, without staging files first. Best fit?

A. Snowpipe Streaming
B. PUT command
C. COPY INTO <location>
D. User stage

**26.** What is the purpose of a storage integration object?

A. Physically moves files into Snowflake storage
B. Lets Snowflake securely access external cloud storage without embedding raw credentials in the stage
C. Defines warehouse compute size
D. Replaces the need for stages

**27.** Which command unloads query results or table data to files in a stage?

A. COPY INTO <table>
B. COPY INTO <location>
C. PUT
D. GET

**28.** (Choose two) Which are valid Snowflake-supported file formats for loading?

A. Parquet
B. DOCX
C. Avro
D. PPTX

---

## Domain 4: Performance & Transformation (Chapters 5, 6) — Questions 29–36

**29.** Which data type is the universal container for any semi-structured value in Snowflake?

A. OBJECT
B. ARRAY
C. VARIANT
D. TEXT

**30.** What does the FLATTEN table function do?

A. Compresses a table
B. Explodes an ARRAY or OBJECT into multiple rows, one per element
C. Converts a table into VARIANT
D. Merges two tables

**31.** What does querying a Stream object return?

A. A full copy of the table
B. Row-level changes since the stream was last consumed, with metadata columns
C. Only the schema
D. Aggregated statistics

**32.** How do Dynamic Tables differ from a manual Streams + Tasks pipeline?

A. They require more manual orchestration
B. They let you declare a target query and Snowflake automatically manages incremental refresh
C. They cannot be incrementally refreshed
D. They are unrelated to Streams and Tasks

**33.** What must be true for Snowflake's result cache to serve a query's results?

A. The query only needs to be logically equivalent
B. Query text must be identical and underlying data unchanged since caching
C. The warehouse must still be running
D. A clustering key must exist

**34.** When is defining an explicit clustering key most appropriate?

A. On every table regardless of size
B. On large tables with a well-defined, frequently filtered column
C. Only on tables under 1GB
D. Never — clustering is deprecated

**35.** A high-cardinality column is frequently queried with exact-match point lookups, and clustering isn't enough. What targets this specifically?

A. Materialized views
B. Search Optimization Service
C. Result cache
D. Snowpipe

**36.** A Query Profile shows significant spillage to remote storage during a sort. Most direct fix?

A. Add a masking policy
B. Increase the warehouse size
C. Enable Snowpipe
D. Create a network policy

---

## Domain 5: Data Collaboration (Chapter 7) — Questions 37–40

**37.** What is the maximum Time Travel retention, and on which edition?

A. 7 days on Standard
B. 90 days on Enterprise and above
C. 365 days on all editions
D. No maximum exists

**38.** Can a user self-service recover data during Fail-safe?

A. Yes, using UNDROP
B. No — only Snowflake support can recover data during Fail-safe
C. Yes, on Business Critical only
D. Fail-safe and Time Travel are identical

**39.** In a direct share to a consumer with their own Snowflake account, who pays for compute to query the shared data?

A. The provider
B. The consumer
C. Neither — Snowflake absorbs it
D. Split 50/50 automatically

**40.** A company without its own Snowflake account needs to consume shared data. What's the appropriate mechanism?

A. A direct share
B. A reader account, created and paid for by the provider
C. Snowpipe
D. A masking policy

---

## Answer Key

| # | Ans | # | Ans | # | Ans | # | Ans |
|---|---|---|---|---|---|---|---|
| 1 | B | 11 | B | 21 | B | 31 | B |
| 2 | C | 12 | B | 22 | B | 32 | B |
| 3 | A, C | 13 | B | 23 | B | 33 | B |
| 4 | B | 14 | B | 24 | B | 34 | B |
| 5 | B | 15 | C | 25 | A | 35 | B |
| 6 | B | 16 | B | 26 | B | 36 | B |
| 7 | B | 17 | B | 27 | B | 37 | B |
| 8 | B | 18 | B | 28 | A, C | 38 | B |
| 9 | B | 19 | B | 29 | C | 39 | B |
| 10 | B | 20 | A, B | 30 | B | 40 | B |

### Scoring guide

| Score | Interpretation |
|---|---|
| 36–40 (90%+) | Strong readiness — book your exam |
| 32–35 (80–89%) | Good readiness — review missed domains, then book |
| 26–31 (65–79%) | Not yet — revisit the specific chapters behind your misses before scheduling |
| Below 26 (<65%) | Return to the [study plan](../STUDY_PLAN.md) and work through weak chapters again before attempting another mock |

### Domain-level review guide

If you missed multiple questions in one section, go back to the matching chapter before your next attempt:

- **Missed mostly Q1–13?** Revisit [Chapter 1](../chapters/01-architecture-fundamentals/README.md), [Chapter 2](../chapters/02-virtual-warehouses-compute/README.md), and [Chapter 8](../chapters/08-ai-cortex-iceberg-notebooks-git/README.md).
- **Missed mostly Q14–21?** Revisit [Chapter 3](../chapters/03-account-access-security-governance/README.md).
- **Missed mostly Q22–28?** Revisit [Chapter 4](../chapters/04-data-loading-unloading-connectivity/README.md).
- **Missed mostly Q29–36?** Revisit [Chapter 5](../chapters/05-data-transformation-semi-structured/README.md) and [Chapter 6](../chapters/06-performance-optimization-querying/README.md).
- **Missed mostly Q37–40?** Revisit [Chapter 7](../chapters/07-data-protection-sharing-collaboration/README.md).

---

[← Back to root README](../README.md) · [Back to Study Plan](../STUDY_PLAN.md)
