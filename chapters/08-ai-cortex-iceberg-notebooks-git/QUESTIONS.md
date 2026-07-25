# Chapter 8 Practice Questions — AI, Iceberg, Notebooks & Git Integration

Original practice questions written from public Snowflake documentation. Not real exam questions.

---

**1.** What is the primary benefit of using Cortex AI functions instead of exporting data to an external AI service?

A. Cortex functions are always faster than any external service
B. AI processing happens inside Snowflake's existing security/governance boundary, without moving data externally
C. Cortex functions eliminate the need for warehouses entirely
D. Cortex functions can only be used with semi-structured data

---

**2.** What is the main reason to choose an Iceberg table over a native Snowflake table?

A. Iceberg tables are always faster for every workload
B. Interoperability — multiple compute engines outside Snowflake can read/write the same underlying data
C. Iceberg tables don't require any compute to query
D. Native tables cannot store structured data

---

**3.** What powers the compute behind a Snowflake Notebook?

A. The user's local laptop CPU
B. Snowflake compute (a warehouse or container-based compute), so code runs where the data lives
C. A separate, unrelated cloud account
D. Notebooks require no compute at all

---

**4.** How does Snowflake's Git integration make repository files available to Snowflake objects?

A. It creates a live, real-time mount of the external Git service
B. It maintains a Snowflake-managed synced clone of the repository that objects can reference
C. It requires manually copying files into a stage every time
D. Git integration is unrelated to Snowflake objects like stored procedures

---

**5.** A team needs a Snowflake table that must also be readable and writable by Spark and Trino outside of Snowflake. What is the best fit?

A. A native Snowflake table
B. An Iceberg table
C. A materialized view
D. A Snowpipe object

---

**6.** Which of the following is a text-based Cortex AI capability?

A. Warehouse auto-suspend
B. Summarization of text data via a SQL-callable function
C. Zero-copy cloning
D. Row access policies

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | B | Cortex AI's core advantage is applying AI/LLM capability without data leaving Snowflake's governance/security boundary. |
| 2 | B | Iceberg's open table format enables cross-engine interoperability outside Snowflake, at some cost to Snowflake-native convenience. |
| 3 | B | Notebooks execute using Snowflake compute (warehouse or container-based), keeping computation where the data resides. |
| 4 | B | Git integration works through a Snowflake-managed synced clone of the repository, not a live external mount. |
| 5 | B | Iceberg tables are purpose-built for multi-engine read/write interoperability outside Snowflake. |
| 6 | B | Summarization is one of Cortex AI's SQL-callable text functions. |

---

[← Back to Chapter 8 notes](README.md) · [Next: Full Mock Exam →](../../assessments/MOCK_EXAM.md)
