# Chapter 2 Practice Questions — Virtual Warehouses & Compute

Original practice questions written from public Snowflake documentation. Not real exam questions.

---

**1.** Users report that individual dashboard queries are running slowly, but there's no significant queuing. What is the most direct fix?

A. Enable multi-cluster warehousing
B. Increase the warehouse size (scale up)
C. Decrease auto-suspend time
D. Switch to Economy scaling policy

---

**2.** Users report that queries are individually fast but are frequently queuing during peak hours because many analysts run reports at the same time. What is the most direct fix?

A. Increase the warehouse size (scale up)
B. Configure a multi-cluster warehouse (scale out)
C. Reduce the warehouse size
D. Disable the result cache

---

**3.** Which Snowflake edition is the minimum required to use multi-cluster warehouses?

A. Standard
B. Enterprise
C. Business Critical only
D. Multi-cluster warehouses are available on all editions

---

**4.** How are Snowflake virtual warehouse credits billed?

A. A flat monthly fee regardless of usage
B. Per-second, with a 60-second minimum, only while the warehouse is running
C. Per query executed, regardless of duration
D. Per gigabyte of data stored

---

**5.** What happens to a warehouse's local disk (warehouse) cache when the warehouse auto-suspends?

A. It is preserved indefinitely
B. It is cleared
C. It is moved to the result cache
D. It is archived to Time Travel

---

**6.** (Choose two) Which of the following are true about multi-cluster warehouse scaling policies?

A. "Standard" policy favors starting clusters quickly to minimize queuing
B. "Economy" policy favors conserving credits, accepting some queuing
C. "Economy" is the default policy
D. Scaling policy has no effect on cost or queuing behavior

---

**7.** Which of the following Snowflake features runs on serverless compute rather than a user-managed warehouse?

A. A standard SELECT query run by an analyst
B. Snowpipe continuous data loading
C. A manually triggered COPY INTO command using warehouse X
D. A stored procedure explicitly run using warehouse Y

---

**8.** Why might an organization use separate warehouses for ELT loading versus BI reporting, even though both access the same tables?

A. Because different warehouses can see different data
B. To isolate compute resources so a heavy load job doesn't starve reporting queries of performance
C. Because Snowflake requires one warehouse per workload type
D. Because storage is duplicated per warehouse

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | B | Slow individual queries without queuing point to a need for more compute per query — scale up. |
| 2 | B | Queuing from concurrent usage, not individually slow queries, is a concurrency problem — scale out via multi-cluster. |
| 3 | B | Multi-cluster warehouses require Enterprise edition or above. |
| 4 | B | Snowflake bills warehouse compute per-second with a 60-second minimum, only while running. |
| 5 | B | The local disk (warehouse) cache is tied to the running warehouse and clears on suspend. |
| 6 | A, B | Standard favors quick cluster starts (less queuing, more cost); Economy favors fewer clusters (more queuing tolerance, less cost). Standard, not Economy, is the default. |
| 7 | B | Snowpipe runs on Snowflake-managed serverless compute, not a warehouse you provision and size. |
| 8 | B | Separate warehouses give each workload dedicated compute so one doesn't starve another, since all warehouses share the same underlying storage layer. |

---

[← Back to Chapter 2 notes](README.md) · [Next chapter: Account Access, Security & Governance →](../03-account-access-security-governance/README.md)
