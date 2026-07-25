# Chapter 6 Practice Questions — Performance Optimization & Querying

Original practice questions written from public Snowflake documentation. Not real exam questions.

---

**1.** What must be true for the result cache to serve a query's results?

A. The query only needs to be logically equivalent to a previous one
B. The query text must be identical and the underlying data unchanged since the cached result was produced
C. The warehouse must still be running
D. The table must have a clustering key defined

---

**2.** Which cache is cleared when a warehouse suspends?

A. Result cache
B. Metadata cache
C. Local disk (warehouse) cache
D. None of the caches are ever cleared

---

**3.** When is defining an explicit clustering key most appropriate?

A. On every table, regardless of size
B. On large tables (often multi-terabyte) with a well-defined, frequently filtered column
C. Only on tables smaller than 1GB
D. Clustering keys are deprecated and no longer used

---

**4.** A table has a high-cardinality column frequently queried with exact-match point lookups, and clustering alone isn't helping enough. What feature specifically targets this case?

A. Materialized views
B. Search Optimization Service
C. Result cache
D. Snowpipe

---

**5.** What is a materialized view, and what edition is required?

A. A precomputed, automatically maintained query result; requires Enterprise edition or above
B. A temporary in-memory table available on all editions
C. A synonym for a regular view with no performance difference
D. A feature only available for semi-structured data

---

**6.** In the Query Profile, a query shows significant spillage to remote storage during a large sort operation. What is the most direct fix?

A. Add a masking policy
B. Increase the warehouse size to provide more available memory
C. Enable Snowpipe
D. Create a network policy

---

**7.** What is the primary use case for the Query Acceleration Service?

A. Permanently replacing the need for warehouses
B. Offloading parts of eligible large-scan/filter queries to extra serverless compute, without permanently upsizing the warehouse
C. Managing user authentication
D. Encrypting data at rest

---

**8.** (Choose two) Which of the following run their maintenance on Snowflake-managed serverless compute rather than a user warehouse?

A. Automatic clustering (reclustering)
B. Materialized view maintenance
C. A manually run SELECT query
D. A COPY INTO command explicitly run on warehouse X

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | B | The result cache requires byte-for-byte identical query text and unchanged underlying data, not just logical equivalence. |
| 2 | C | The local disk (warehouse) cache is tied to the running warehouse and clears on suspend; result and metadata caches live in Cloud Services. |
| 3 | B | Clustering keys are recommended for large tables with a frequently filtered column, where pruning benefit outweighs background maintenance cost. |
| 4 | B | Search Optimization Service specifically targets highly selective point-lookup/equality queries, unlike clustering which helps broader scan/range pruning. |
| 5 | A | Materialized views precompute and auto-maintain query results and require Enterprise edition or above. |
| 6 | B | Remote spillage indicates insufficient warehouse memory for the operation; increasing warehouse size is the most direct fix. |
| 7 | B | Query Acceleration Service offloads eligible large-scan query portions to additional serverless compute without permanently resizing the warehouse. |
| 8 | A, B | Automatic clustering and materialized view maintenance both run on Snowflake-managed serverless compute in the background. |

---

[← Back to Chapter 6 notes](README.md) · [Next chapter: Data Protection, Sharing & Collaboration →](../07-data-protection-sharing-collaboration/README.md)
