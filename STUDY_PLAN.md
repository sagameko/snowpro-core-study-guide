# SnowPro Core (COF-C03) Study Plan — 2-Week Intensive & 4-Week Part-Time Tracks

This is the day-by-day companion to the [root README](README.md). It assumes you've already read the domain breakdown and the honest timeline assessment there. If you haven't, go do that first — it explains *why* this plan is shaped the way it is.

## 30-second self-check: which track should you use?

Answer honestly:

1. Have you used Snowflake hands-on for 3+ months (built pipelines, managed roles/warehouses, written non-trivial SQL against it)?
2. Can you dedicate 5+ hours a day to studying for the next two weeks, with no major interruptions?
3. Have you at least heard of Cortex AI, Iceberg tables, Snowflake Notebooks, and Git integration in Snowflake (even if you haven't used them)?

**Answered "yes" to all three?** Use the **2-Week Intensive Track**.

**Answered "no" to any of them?** Use the **3–4 Week Part-Time Track** instead. Forcing the 2-week plan without the time or background is the most common way people either fail or pass without retaining anything useful.

---

## 2-Week Intensive Track (full-time)

**Target: 5–7 hours/day, 14 days, ~80–95 total hours.** This is a genuinely intensive schedule — treat it like a full-time short course, not something you fit around a full-time job.

| Day | Focus | Chapter(s) | Activities |
|---|---|---|---|
| 1 | Architecture fundamentals | [Ch. 1](chapters/01-architecture-fundamentals/README.md) | Read notes, study the 3-layer diagram, sign up for a Snowflake free trial, explore the UI |
| 2 | Virtual warehouses & compute | [Ch. 2](chapters/02-virtual-warehouses-compute/README.md) | Read notes, create warehouses of different sizes in your trial account, test auto-suspend/resume |
| 3 | Architecture + warehouses review | Ch. 1–2 | Take both `QUESTIONS.md` quizzes, re-read anything you scored under 75% on, do hands-on cloning + Time Travel restore |
| 4 | Account access, security & governance (part 1) | [Ch. 3](chapters/03-account-access-security-governance/README.md) | Read notes on RBAC, system roles, authentication; create custom roles in your trial account |
| 5 | Account access, security & governance (part 2) | Ch. 3 | Read notes on masking policies, row access policies, network policies; take `QUESTIONS.md` quiz |
| 6 | Data loading, unloading & connectivity | [Ch. 4](chapters/04-data-loading-unloading-connectivity/README.md) | Read notes, load a CSV via `COPY INTO`, set up a Snowpipe, take `QUESTIONS.md` quiz |
| 7 | **Rest / catch-up day** | — | Re-take any chapter quiz you scored below 75% on; do NOT skip this — burnout kills 2-week plans |
| 8 | Data transformation & semi-structured data | [Ch. 5](chapters/05-data-transformation-semi-structured/README.md) | Read notes, practice `FLATTEN` on JSON, build a Stream + Task pipeline, try a dynamic table |
| 9 | Performance optimization & querying | [Ch. 6](chapters/06-performance-optimization-querying/README.md) | Read notes, examine a query profile, experiment with clustering keys, take `QUESTIONS.md` quiz |
| 10 | Data protection, sharing & collaboration | [Ch. 7](chapters/07-data-protection-sharing-collaboration/README.md) | Read notes on Time Travel/Fail-safe depth, secure data sharing, Marketplace, take `QUESTIONS.md` quiz |
| 11 | AI, Iceberg, Notebooks & Git (what's new in COF-C03) | [Ch. 8](chapters/08-ai-cortex-iceberg-notebooks-git/README.md) | Read notes, run a Cortex AI function, create a basic Iceberg table, open a Notebook, take `QUESTIONS.md` quiz |
| 12 | Full review pass | All chapters | Skim every chapter README again, focused only on sections you flagged as weak; redo weak quizzes |
| 13 | Mock exam #1 | [`assessments/MOCK_EXAM.md`](assessments/MOCK_EXAM.md) | Take the full mock exam timed. Review every miss and trace it back to the relevant chapter/doc link |
| 14 | Targeted fixes + light mock review | — | Re-study only your weak domains from Day 13; skim the mock exam explanations once more; do NOT cram new material the night before a real exam |

**After Day 14:** if your mock score is comfortably above ~80%, book your Pearson VUE slot. If it's below that, take a few more days on your weak domains before scheduling — there's no shame in a 16- or 18-day plan instead of a rigid 14.

---

## 3–4 Week Part-Time Track (alternative)

**Target: 1.5–2.5 hours/day, most days of the week, ~70–90 total hours spread over 22–28 days.** This is the more realistic default for most people, especially if you're newer to Snowflake or studying around a full-time job.

### Week 1 — Architecture & Compute
- Days 1–2: [Chapter 1 — Architecture Fundamentals](chapters/01-architecture-fundamentals/README.md), notes + free-trial exploration
- Days 3–4: [Chapter 2 — Virtual Warehouses & Compute](chapters/02-virtual-warehouses-compute/README.md), notes + hands-on warehouse sizing/scaling
- Days 5–7: Quizzes for both chapters, hands-on cloning/Time Travel, light review

### Week 2 — Governance & Data Movement
- Days 8–10: [Chapter 3 — Account Access, Security & Governance](chapters/03-account-access-security-governance/README.md), notes + RBAC/masking hands-on
- Days 11–13: [Chapter 4 — Data Loading, Unloading & Connectivity](chapters/04-data-loading-unloading-connectivity/README.md), notes + `COPY INTO`/Snowpipe hands-on
- Day 14: Quizzes for both chapters, review weak spots

### Week 3 — Transformation, Performance & Protection
- Days 15–17: [Chapter 5 — Data Transformation & Semi-Structured Data](chapters/05-data-transformation-semi-structured/README.md), notes + Streams/Tasks/dynamic tables hands-on
- Days 18–19: [Chapter 6 — Performance Optimization & Querying](chapters/06-performance-optimization-querying/README.md), notes + query profile/clustering hands-on
- Days 20–21: [Chapter 7 — Data Protection, Sharing & Collaboration](chapters/07-data-protection-sharing-collaboration/README.md), notes + quizzes for all three chapters

### Week 4 — What's New in C03, Review & Exam Readiness
- Days 22–23: [Chapter 8 — AI, Iceberg, Notebooks & Git](chapters/08-ai-cortex-iceberg-notebooks-git/README.md), notes + labs (Cortex function, Iceberg table, Notebook, Git sync)
- Days 24–25: Full review pass across all 8 chapters, redo any quiz scored under 75%
- Day 26: Mock exam #1 ([`assessments/MOCK_EXAM.md`](assessments/MOCK_EXAM.md)), timed, review every miss
- Days 27–28: Targeted review of weak domains only, then book your exam once your score is comfortably above ~80%

**If you need more time, take it.** Extending Week 4 by a few days costs nothing; failing the real exam costs $175 and a mandatory 7-day wait before you can retake it.

---

## General study tips (both tracks)

- **Hands-on beats reading.** COF-C03 tests platform behavior, not trivia. For every concept, actually run it in a free trial account if you can.
- **Keep a "wrong answers" log.** Every time you miss a practice question, write the concept in your own words with a link to the relevant doc. Re-test yourself on that log 48 hours later.
- **Multi-select questions matter.** SnowPro Core includes "choose two" style questions. Practicing to select the *exact* right number of answers (not one extra "just in case") is a real skill worth building during practice, not on exam day.
- **Don't chase exam dumps.** Using leaked or memorized real exam questions violates Snowflake's certification agreement and risks your credential being revoked. Every practice question in this repo's `QUESTIONS.md` files is original.
