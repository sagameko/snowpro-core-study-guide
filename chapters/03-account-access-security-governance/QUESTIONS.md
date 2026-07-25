# Chapter 3 Practice Questions — Account Access, Security & Data Governance

Original practice questions written from public Snowflake documentation. Not real exam questions.

---

**1.** In Snowflake's RBAC model, how are privileges typically assigned to a user?

A. Directly to the user account
B. Privileges are granted to roles, and roles are granted to users
C. Privileges are inherited automatically based on the user's department
D. Privileges are assigned per warehouse only

---

**2.** Which system-defined role is best practice as the parent for custom roles that manage day-to-day database objects?

A. ACCOUNTADMIN
B. USERADMIN
C. SYSADMIN
D. PUBLIC

---

**3.** Which role is dedicated specifically to creating and managing users and roles?

A. SYSADMIN
B. USERADMIN
C. ACCOUNTADMIN
D. SECURITYADMIN only, never USERADMIN

---

**4.** What is the recommended authentication method for automated scripts and service accounts (rather than embedding a password)?

A. Username/password stored in plaintext
B. Key pair authentication
C. Shared account credentials
D. No authentication is required for service accounts

---

**5.** What does a dynamic data masking policy do?

A. Permanently deletes sensitive data from the table
B. Conditionally masks column values at query time based on the querying role, without altering stored data
C. Encrypts the entire table at rest
D. Blocks all access to a table entirely

---

**6.** How do row access policies differ from masking policies?

A. Row access policies restrict which columns are visible; masking restricts which rows are visible
B. Row access policies restrict which rows are returned; masking policies restrict/obscure column values — both are dynamic and don't alter stored data
C. They are the same feature with different names
D. Row access policies physically delete unauthorized rows

---

**7.** (Choose two) What can a resource monitor do when a defined credit threshold is reached?

A. Send a notification
B. Automatically suspend the associated warehouse(s)
C. Automatically upgrade the account's Snowflake edition
D. Automatically delete the warehouse permanently

---

**8.** What is the purpose of Snowflake's PUBLIC role?

A. It is granted only to ACCOUNTADMIN
B. It is automatically available to every user and role in the account
C. It has no practical effect and can be ignored
D. It grants ACCOUNTADMIN-level privileges

---

## Answer Key

| # | Answer | Why |
|---|---|---|
| 1 | B | Snowflake RBAC grants privileges to roles, and roles to users — not privileges directly to users. |
| 2 | C | Best practice is to create custom roles as children of SYSADMIN so administrators retain visibility over all objects. |
| 3 | B | USERADMIN is dedicated to creating/managing users and roles (SECURITYADMIN inherits this and can also manage grants globally). |
| 4 | B | Key pair authentication is the standard recommendation for service accounts, scripts, and connectors. |
| 5 | B | Masking policies dynamically mask column values at query time based on role, without changing the underlying stored data. |
| 6 | B | Row access policies control row visibility; masking policies control column value visibility — both are dynamic, not physical changes. |
| 7 | A, B | Resource monitors can trigger notifications and/or automatically suspend warehouses at defined thresholds — they cannot change editions or delete warehouses. |
| 8 | B | PUBLIC is implicitly available to every user and role; anything granted to it is available account-wide. |

---

[← Back to Chapter 3 notes](README.md) · [Next chapter: Data Loading, Unloading & Connectivity →](../04-data-loading-unloading-connectivity/README.md)
