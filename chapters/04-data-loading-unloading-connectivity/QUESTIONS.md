# Chapter 4 Practice Questions — Data Loading, Unloading & Connectivity

Original practice questions written from public Snowflake documentation. Not real exam questions.

---

**1.** Which internal stage type cannot be granted to other roles for shared access?

A. Named internal stage
B. Table stage
C. External stage
D. User stage granted to a role

---

**2.** What happens if you run the exact same `COPY INTO <table>` command twice against the same file in the same stage?

A. The data is loaded twice, duplicating rows
B. Snowflake uses load metadata to avoid reloading the same file again by default
C. The second run always fails with an error
D. The table is truncated automatically before the second load

---

**3.** A company needs files that periodically land in an S3 bucket to be loaded into Snowflake automatically, without a scheduled batch job. What is the best fit?

A. Manual `COPY INTO` run on a schedule
B. Snowpipe
C. GET command
D. Table stage

---

**4.** A company needs individual application events streamed into Snowflake tables with minimal latency, without first writing files to a stage. What is the best fit?

A. Snowpipe Streaming
B. PUT command
C. COPY INTO <location>
D. User stage

---

**5.** What is the purpose of a storage integration object?

A. To physically move data files into Snowflake storage
B. To allow Snowflake to securely access external cloud storage without embedding raw credentials in stage definitions
C. To define a warehouse's compute size
D. To replace the need for stages entirely

---

**6.** Which command is used to unload query results or table data to files in a stage?

A. COPY INTO <table>
B. COPY INTO <location>
C. PUT
D. GET

---

**7.** Which commands are used specifically to move files between a local machine and an internal stage?

A. COPY INTO <table> and COPY INTO <location>
B. PUT and GET
C. Snowpipe and Snowpipe Streaming
D. CREATE STAGE and DROP STAGE

---

**8.** (Choose two) Which of the following are valid file formats supported for loading data into Snowflake?

A. Parquet
B. JSON
C. DOCX
D. Avro

---

**9.** A data engineer wants to run a `COPY INTO` statement as part of an automated nightly shell script, with no browser involved. Which tool is the standard fit?

A. Snowsight
B. SnowSQL
C. Partner Connect
D. Snowflake Marketplace

---

**10.** A team wants to connect their Snowflake account to a third-party BI tool with a guided, one-click setup rather than manually configuring credentials and grants. Which feature is designed for this?

A. Partner Connect
B. SnowSQL
C. Snowpipe
D. Storage integration

---

**11.** How does Snowflake CLI (`snow`) differ from SnowSQL?

A. They are the same tool with two different names
B. SnowSQL is a SQL client for running statements; Snowflake CLI is oriented around managing Snowflake objects and deploying Snowpark/Streamlit applications
C. SnowSQL only works with external stages, while Snowflake CLI only works with internal stages
D. Snowflake CLI replaces Snowsight entirely

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | B | A table stage is tied 1:1 to its table and cannot be independently granted to other roles, unlike named internal stages. |
| 2 | B | COPY INTO is idempotent by default per file/stage combination via Snowflake's load metadata tracking. |
| 3 | B | Snowpipe provides automated, event-driven continuous loading without a manually scheduled batch job. |
| 4 | A | Snowpipe Streaming ingests rows directly without requiring files to be staged first, suited for low-latency use cases. |
| 5 | B | Storage integrations let Snowflake securely authenticate to external cloud storage without embedding raw credentials in the stage object. |
| 6 | B | COPY INTO <location> is the unload command; COPY INTO <table> is for loading. |
| 7 | B | PUT uploads local files to an internal stage; GET downloads from an internal stage to a local machine. |
| 8 | A, D | Parquet and Avro are supported semi-structured/columnar file formats (along with CSV, JSON, ORC, and XML); DOCX is not a supported load format. |
| 9 | B | SnowSQL is the command-line SQL client, the standard fit for running SQL statements like COPY INTO from an automated script without a browser. |
| 10 | A | Partner Connect provides guided, one-click connection setup to partner tools directly from Snowsight, avoiding manual credential/grant configuration. |
| 11 | B | SnowSQL is a SQL client for running statements; Snowflake CLI is a broader tool for managing Snowflake objects and deploying Snowpark/Streamlit applications. |

---

[← Back to Chapter 4 notes](README.md) · [Next chapter: Data Transformation & Semi-Structured Data →](../05-data-transformation-semi-structured/README.md)
