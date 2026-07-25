# Chapter 5 Practice Questions — Data Transformation & Semi-Structured Data

Original practice questions written from public Snowflake documentation. Not real exam questions.

---

**1.** Which Snowflake data type is the universal container for any semi-structured value (object, array, or scalar)?

A. OBJECT
B. ARRAY
C. VARIANT
D. TEXT

---

**2.** What is the purpose of the `::` operator when querying semi-structured data, as in `raw_data:name::string`?

A. It deletes the field
B. It casts the extracted value to a concrete data type
C. It flattens an array
D. It creates a new column permanently

---

**3.** What does the `FLATTEN` table function do?

A. Compresses a table to save storage
B. Explodes an ARRAY or OBJECT into multiple rows, one per element
C. Converts a table into a VARIANT column
D. Merges two tables into one

---

**4.** What does querying a Stream object return?

A. A full copy of the entire table every time
B. The row-level changes (inserts/updates/deletes) made to the table since the stream was last consumed, with metadata columns describing the change type
C. Only the schema of the table, not data
D. Aggregated statistics about the table

---

**5.** What is a common pattern for triggering a Task only when there's actually new data to process?

A. Running the task every second regardless of data
B. Using SYSTEM$STREAM_HAS_DATA() to conditionally trigger the task based on its associated stream
C. Manually running the task by hand every time
D. Tasks cannot be conditionally triggered

---

**6.** How do Dynamic Tables differ from a manual Streams + Tasks pipeline?

A. Dynamic Tables require more manual orchestration code
B. Dynamic Tables let you declare a target query and have Snowflake automatically manage incremental refresh, without manually wiring streams and tasks
C. Dynamic Tables cannot be incrementally refreshed
D. Dynamic Tables and Streams + Tasks are unrelated features

---

**7.** What is the key difference between a UDF and a stored procedure in Snowflake?

A. UDFs return a value and are used inline in expressions; stored procedures run multi-step procedural logic and are explicitly called
B. UDFs can only be written in SQL, while stored procedures can only be written in Python
C. There is no functional difference
D. Stored procedures cannot contain loops or conditionals

---

**8.** Which SQL command performs an "upsert" (insert or update depending on whether a match exists)?

A. INSERT
B. MERGE
C. CLONE
D. FLATTEN

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | C | VARIANT is Snowflake's universal semi-structured container type, able to hold objects, arrays, or scalars. |
| 2 | B | The `::` operator casts an extracted (untyped) VARIANT value to a specific concrete type like string or int. |
| 3 | B | FLATTEN is a table function that turns each element of an ARRAY or OBJECT into its own row. |
| 4 | B | Streams return the delta of row-level changes since last consumption, along with METADATA$ columns describing the change. |
| 5 | B | SYSTEM$STREAM_HAS_DATA() lets a Task run conditionally only when its stream actually has unconsumed changes. |
| 6 | B | Dynamic Tables are a declarative alternative — you define the target query and Snowflake handles incremental refresh automatically. |
| 7 | A | UDFs return values used inline in SQL expressions; stored procedures encapsulate procedural, multi-statement logic and are called explicitly. |
| 8 | B | MERGE performs conditional insert-or-update (upsert) logic based on whether a matching row exists. |

---

[← Back to Chapter 5 notes](README.md) · [Next chapter: Performance Optimization & Querying →](../06-performance-optimization-querying/README.md)
