# Chapter 1 Practice Questions — Snowflake Architecture Fundamentals

Original practice questions written from public Snowflake documentation. Not real exam questions. Choose the best answer(s) for each; some are multi-select as noted.

---

**1.** What is the primary architectural principle that distinguishes Snowflake from traditional on-premises data warehouses?

A. Snowflake uses a NoSQL document model
B. Snowflake separates storage and compute into independently scaling layers
C. Snowflake requires manual index creation for performance
D. Snowflake only supports a single compute cluster per account

---

**2.** Which Snowflake layer is responsible for query parsing, optimization, and access control enforcement?

A. Storage layer
B. Compute layer (virtual warehouses)
C. Cloud Services layer
D. Client layer

---

**3.** (Choose two) Which of the following are true about Snowflake micro-partitions?

A. They are mutable and updated in place
B. They typically hold 50MB–500MB of uncompressed data
C. They are stored in a columnar format
D. They require the user to manually define partition keys before data can be loaded

---

**4.** A company on Snowflake's Standard edition wants to query data as it existed 30 days ago using Time Travel. What happens?

A. This works exactly as requested, no changes needed
B. This is not possible on Standard edition because default/maximum Time Travel is 1 day; Enterprise+ is required for up to 90 days
C. Time Travel is not available on any edition
D. Time Travel only works for semi-structured data

---

**5.** What makes zero-copy cloning fast, even for very large tables?

A. Snowflake compresses the table before cloning
B. Cloning only copies metadata/pointers to existing micro-partitions rather than physically duplicating data
C. Clones are created asynchronously in the background over several hours
D. Cloning only works on empty tables

---

**6.** Which caching layer is cleared when a virtual warehouse is suspended?

A. Result cache
B. Metadata cache
C. Local disk (warehouse) cache
D. None of the caches are ever cleared

---

**7.** (Choose two) Which Snowflake editions support multi-cluster warehouses?

A. Standard
B. Enterprise
C. Business Critical
D. None — multi-cluster warehouses are a paid add-on regardless of edition

---

**8.** In Snowflake's object hierarchy, which of the following is the correct top-to-bottom order?

A. Schema → Database → Account → Table
B. Account → Database → Schema → Table
C. Table → Schema → Account → Database
D. Database → Account → Schema → Table

---

**9.** What enables Snowflake's query pruning, where entire micro-partitions are skipped during a scan?

A. Manual index hints written into SQL
B. Metadata (min/max values, distinct counts) collected automatically per micro-partition
C. A separate indexing service that must be manually enabled
D. Pruning is not possible in Snowflake

---

**10.** What is Fail-safe, and how does it differ from Time Travel?

A. Fail-safe is a self-service 90-day recovery window available to all users
B. Fail-safe is a non-configurable 7-day period after Time Travel expires, used only by Snowflake itself for disaster recovery — it is not self-service
C. Fail-safe and Time Travel are the same feature with different names
D. Fail-safe only applies to Standard edition accounts

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | B | Separation of storage and compute is Snowflake's foundational architectural difference from traditional warehouses. |
| 2 | C | Query parsing, optimization, and RBAC enforcement happen in the Cloud Services layer. |
| 3 | B, C | Micro-partitions are immutable (not A), columnar, and ~50–500MB uncompressed; no manual partition key definition is required (not D). |
| 4 | B | Standard edition's Time Travel is limited to 1 day by default/maximum; 90-day retention requires Enterprise or above. |
| 5 | B | Clones share underlying micro-partitions via metadata pointers until data diverges, making the operation near-instant. |
| 6 | C | The local disk (warehouse) cache is tied to a running warehouse and is cleared on suspend; result and metadata caches live in Cloud Services and persist independently. |
| 7 | B, C | Multi-cluster warehouses require Enterprise edition or above (Enterprise, Business Critical, and VPS); not available on Standard. |
| 8 | B | Account → Database → Schema → Table is the correct hierarchy (Organization sits above Account). |
| 9 | B | Automatically collected micro-partition metadata (min/max, distinct values) is what enables the query optimizer to prune irrelevant partitions. |
| 10 | B | Fail-safe is a non-configurable, Snowflake-managed 7-day recovery period after Time Travel expires — not a user-facing feature like Time Travel is. |

---

[← Back to Chapter 1 notes](README.md) · [Next chapter: Virtual Warehouses & Compute →](../02-virtual-warehouses-compute/README.md)
