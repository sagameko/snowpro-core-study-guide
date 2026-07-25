# Chapter 7 Practice Questions — Data Protection, Sharing & Collaboration

Original practice questions written from public Snowflake documentation. Not real exam questions.

---

**1.** What is the maximum Time Travel retention period available, and on which edition?

A. 7 days, available on Standard edition
B. 90 days, available on Enterprise edition and above
C. 365 days, available on all editions
D. Time Travel has no maximum retention period

---

**2.** Can a user self-service recover data during the Fail-safe period?

A. Yes, using the UNDROP command
B. No — Fail-safe recovery can only be performed by Snowflake support as a last resort
C. Yes, but only on Business Critical edition
D. Fail-safe and Time Travel are the same thing

---

**3.** In a direct Secure Data Sharing relationship where the consumer has their own Snowflake account, who pays for the compute used to query the shared data?

A. The provider account
B. The consumer account
C. Neither party — Snowflake absorbs the cost
D. Compute cost is split automatically 50/50

---

**4.** In a reader account sharing scenario, who pays for the compute?

A. The consumer, since they are querying the data
B. The provider, since they create and manage the reader account
C. Reader accounts do not use compute
D. The Snowflake Marketplace absorbs the cost

---

**5.** What makes zero-copy cloning and Secure Data Sharing both efficient in terms of storage?

A. They both compress data before sharing
B. Neither physically duplicates the underlying data — they reference the same micro-partitions/storage layer
C. They both require a separate storage account
D. They only work on tables smaller than 1GB

---

**6.** What is the difference between a public and a private Snowflake Marketplace listing?

A. Public listings are free and private listings always cost money
B. Public listings are broadly discoverable; private listings are shared only with specific named accounts/organizations
C. There is no difference
D. Private listings cannot use Secure Data Sharing

---

**7.** What problem do Data Clean Rooms solve?

A. They physically merge two companies' databases into one
B. They allow parties to collaboratively analyze combined data without either party directly exposing raw underlying data to the other
C. They are a synonym for reader accounts
D. They eliminate the need for RBAC

---

**8.** A company without its own Snowflake account needs to consume data shared by a provider. What is the appropriate mechanism?

A. A direct share, since it requires no setup
B. A reader account, created and paid for by the provider
C. Snowpipe
D. A masking policy

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | B | Up to 90 days of Time Travel retention requires Enterprise edition or above; Standard is limited to 0–1 day. |
| 2 | B | Fail-safe is a non-self-service, Snowflake-support-only recovery mechanism, distinct from user-facing Time Travel/UNDROP. |
| 3 | B | In direct shares to a consumer's own account, the consumer pays for their own compute to query shared data. |
| 4 | B | Reader accounts are created and funded by the provider specifically because the consumer lacks their own Snowflake account/compute. |
| 5 | B | Both features avoid physical data duplication by referencing shared underlying storage/micro-partitions rather than copying data. |
| 6 | B | Public listings are broadly discoverable on the Marketplace; private listings restrict visibility to specific named accounts. |
| 7 | B | Data Clean Rooms enable joint analysis of combined data while keeping each party's raw underlying data hidden from the other. |
| 8 | B | A reader account is specifically designed for consumers without their own Snowflake account, funded and managed by the provider. |

---

[← Back to Chapter 7 notes](README.md) · [Next chapter: AI, Iceberg, Notebooks & Git Integration →](../08-ai-cortex-iceberg-notebooks-git/README.md)
