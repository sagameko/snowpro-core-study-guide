# SnowPro Core Certification Study Guide (COF-C03) — Snowflake Exam Prep 2026

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Exam](https://img.shields.io/badge/exam-COF--C03-29B5E8)](https://learn.snowflake.com/en/certifications/snowpro-core-c03/)
[![Last commit](https://img.shields.io/github/last-commit/sagameko/snowpro-core-study-guide)](https://github.com/sagameko/snowpro-core-study-guide/commits/main)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill%20included-6A5ACD)](SKILL.md)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A free, comprehensive, self-paced **SnowPro Core Certification study guide** for Snowflake's foundational credential. Covers architecture, account governance, data loading, transformation, performance, and data collaboration — with a day-by-day study plan, chapter notes, original diagrams, and practice questions with answer keys for the current **COF-C03** exam. Also installable as a [Claude Skill](SKILL.md) for interactive quizzing.

**Last verified against official Snowflake sources:** July 26, 2026

---

## Table of contents

- [Which certification does this repo target, and why](#which-certification-does-this-repo-target-and-why)
- [Exam snapshot](#exam-snapshot)
- [Who this guide is for](#who-this-guide-is-for)
- [Exam domains — the real COF-C03 blueprint](#exam-domains--the-real-cof-c03-blueprint)
- [Repository structure](#repository-structure)
- [Use this as a Claude Skill](#use-this-as-a-claude-skill)
- [How to use this repo](#how-to-use-this-repo)
- [Is 2 weeks actually realistic?](#is-2-weeks-actually-realistic-an-honest-timeline-assessment)
- [Start here](#start-here)
- [Official Snowflake resources](#official-snowflake-resources)
- [Unofficial resources](#unofficial-resources-courses-videos-books-practice-tests)
- [Credits](#credits)

---

## Which certification does this repo target, and why

Snowflake renames and re-versions its exams periodically, so this is worth stating plainly up front: **this repo targets the SnowPro Core Certification, exam code `COF-C03`.**

Here's why, and how that was confirmed:

- Snowflake's previous SnowPro Core exam, **COF-C02**, was **retired on May 14, 2026**.
- Its replacement, **COF-C03**, went live for English on **February 16, 2026** (localized versions like French and Korean followed on March 30, 2026), and is the **only active version of SnowPro Core** as of this writing.
- This was verified directly against Snowflake's own certification page ([learn.snowflake.com/en/certifications/snowpro-core-c03](https://learn.snowflake.com/en/certifications/snowpro-core-c03/)) and corroborated by multiple independent, dated third-party exam-prep sources describing the same domain weights, question count, and passing score.
- If you were handed a study plan, PDF, or Udemy course that still talks about COF-C02, **it is out of date** — COF-C02 is no longer bookable. Some of the content still transfers (Snowflake's core architecture hasn't changed), but COF-C03 adds meaningful new material: **Snowflake Cortex AI functions, Apache Iceberg tables, Snowflake Notebooks, and Git integration**. None of that appeared on COF-C02.

**Not what you're looking for?** If you already have Core and are aiming for a role-based credential instead, Snowflake also offers six **SnowPro Advanced** certifications — Architect, Security Engineer, Data Engineer, Data Scientist, Administrator, and Data Analyst — plus a newer MLOps Engineer beta track. SnowPro Core is the mandatory prerequisite for all of them. This repo is Core-only; the Advanced tracks assume you already know this material and test it through scenario-based questions instead of factual recall.

---

## Exam snapshot

| Detail | Value |
|---|---|
| Certification | SnowPro Core Certification |
| Exam code | COF-C03 |
| Format | 100 multiple-choice / multiple-select questions |
| Duration | 115 minutes |
| Passing score | 750 / 1000 (scaled score) |
| Cost | $175 USD per attempt |
| Delivery | Pearson VUE — online proctored (OnVUE) or test center |
| Validity | 2 years, with a recertification exam option |
| Retake policy | 7-day wait after a fail; up to 4 attempts per 12 months; full fee each time |
| Recommended background | 6+ months of hands-on Snowflake experience |
| Prerequisite for | All 6 SnowPro Advanced certifications |

Sources: [Snowflake official COF-C03 certification page](https://learn.snowflake.com/en/certifications/snowpro-core-c03/), [FlashGenius COF-C03 guide](https://flashgenius.net/blog-article/snowpro-core-cof-c03-certification-guide-2026-exam-topics-cost-practice-questions-study-plan).

---

## Who this guide is for

- **Data engineers, analysts, and analytics engineers** who use Snowflake day-to-day and want to formalize that knowledge with a credential.
- **Cloud/BI professionals moving into the Snowflake ecosystem** from another warehouse (Redshift, BigQuery, Synapse) who need a structured way to learn Snowflake-specific concepts rather than generic SQL.
- **Career switchers or students** targeting data platform roles, using SnowPro Core as a portfolio credential — note that Snowflake recommends 6+ months of hands-on experience first; this guide assumes you can get trial-account hands-on time even if you lack production experience.
- **Anyone re-certifying** after the COF-C02 → COF-C03 transition who needs a refresher on what's new (Cortex AI, Iceberg tables, Notebooks, Git integration).

This is **not** a zero-to-hero SQL course. You should be comfortable with basic SQL (SELECT, JOIN, aggregate functions) before starting.

---

## Exam domains — the real COF-C03 blueprint

Snowflake organizes COF-C03 into **five weighted domains**. This repo splits the two heaviest domains (Architecture and Performance/Transformation) into two chapters each for teachability, and adds a dedicated chapter for the AI/Iceberg/Notebooks/Git content that's new to COF-C03 — but every chapter is mapped back to its official domain below so you always know what you're studying and how much it's worth.

| # | Official Domain | Exam Weight | Covered in |
|---|---|---|---|
| 1 | Snowflake AI Data Cloud Features & Architecture | **31%** | [Ch. 1](chapters/01-architecture-fundamentals/README.md), [Ch. 2](chapters/02-virtual-warehouses-compute/README.md), [Ch. 8](chapters/08-ai-cortex-iceberg-notebooks-git/README.md) |
| 2 | Account Management & Data Governance | **20%** | [Ch. 3](chapters/03-account-access-security-governance/README.md) |
| 3 | Data Loading, Unloading & Connectivity | **18%** | [Ch. 4](chapters/04-data-loading-unloading-connectivity/README.md), [Ch. 8](chapters/08-ai-cortex-iceberg-notebooks-git/README.md) (Git integration) |
| 4 | Performance Optimization, Querying & Transformation | **21%** | [Ch. 5](chapters/05-data-transformation-semi-structured/README.md), [Ch. 6](chapters/06-performance-optimization-querying/README.md) |
| 5 | Data Collaboration | **10%** | [Ch. 7](chapters/07-data-protection-sharing-collaboration/README.md) |

**Domain weight confidence note:** these percentages come from independently cross-checked third-party exam guides (FlashGenius, and two separate search syntheses) that agree with each other and are consistent with Snowflake's own candidate-overview language, but Snowflake does not publish an official downloadable PDF with the exact percentage table at the time of writing. Treat the weights as a strong planning signal, not a guaranteed scoring formula, and always sanity-check against the live [official certification page](https://learn.snowflake.com/en/certifications/snowpro-core-c03/) before your exam date in case Snowflake publishes updates.

Domains 1 and 4 together make up **52%** of the exam — start there if you're short on time.

---

## Repository structure

```
snowpro-core-study-guide/
├── README.md                  <- you are here
├── SKILL.md                    <- makes this repo installable as a Claude Skill (study buddy mode)
├── STUDY_PLAN.md               <- day-by-day study plans (2-week and 4-week)
├── LICENSE                     <- MIT license
├── CONTRIBUTING.md             <- how to improve this repo
├── chapters/
│   ├── 01-architecture-fundamentals/
│   │   ├── README.md
│   │   ├── QUESTIONS.md
│   │   └── images/
│   ├── 02-virtual-warehouses-compute/
│   ├── 03-account-access-security-governance/
│   ├── 04-data-loading-unloading-connectivity/
│   ├── 05-data-transformation-semi-structured/
│   ├── 06-performance-optimization-querying/
│   ├── 07-data-protection-sharing-collaboration/
│   └── 08-ai-cortex-iceberg-notebooks-git/
└── assessments/
    └── MOCK_EXAM.md            <- full-length mock exam + answer key spanning all chapters
```

Each chapter folder follows the same pattern: a `README.md` that teaches the concept with explanations, examples, and links to official docs; an `images/` folder with an original diagram; and a `QUESTIONS.md` with practice questions and an answer key for that chapter only.

---

## Use this as a Claude Skill

This repo also ships as a [Claude Skill](SKILL.md) — an interactive study buddy layered on top of the same chapter notes and questions, so you can be quizzed one question at a time (no answer-dumping, no spoilers), get concepts explained on demand, run a timed mock exam, or get coached through the study plan, instead of just reading static markdown.

To use it: clone this repo into your Claude Skills directory (e.g. `~/.claude/skills/snowpro-core-study-guide/` for Claude Code), or upload the folder as a Skill in claude.ai. Then just ask things like *"quiz me on chapter 3"*, *"explain zero-copy cloning for the exam,"* or *"give me a timed mock exam."*

---

## How to use this repo

1. **Start here:** read this README fully, then open [`STUDY_PLAN.md`](STUDY_PLAN.md) and pick the 2-week or 4-week track based on your available time (see the honest timeline verdict below).
2. **Work chapter by chapter, in order.** They're numbered 01–08 deliberately — architecture concepts in Chapter 1 are assumed knowledge by Chapter 6, for example.
3. **For each chapter:** read the `README.md` notes, follow the official doc links for anything unfamiliar, then take the `QUESTIONS.md` quiz before moving on. If you score below ~75%, re-read before advancing.
4. **Get hands-on.** This guide explains concepts, but SnowPro Core tests practical understanding. Sign up for a [Snowflake free trial account](https://signup.snowflake.com/) and actually run the SQL in each chapter — don't just read it.
5. **Finish with the mock exam.** Once all 8 chapters are done, take the full [`assessments/MOCK_EXAM.md`](assessments/MOCK_EXAM.md) under timed conditions (aim for ~70 minutes for the shorter mock) before booking your real exam.
6. **Book with margin.** Don't schedule your Pearson VUE slot until your mock exam score is comfortably above the 750/1000 passing bar (roughly 80%+ on practice material, since real exam questions tend to feel harder than practice questions).

---

## Is 2 weeks actually realistic? An honest timeline assessment

**Short answer: two weeks is achievable, but only under specific conditions — and Snowflake's own guidance leans against it.**

Here's the honest breakdown:

- **Snowflake's own candidate profile recommends 6+ months of hands-on platform experience** before attempting COF-C03. That's not the same as 6 months of *studying* — it reflects that the exam rewards intuition about how Snowflake actually behaves (caching, pruning, cost tradeoffs) that's hard to fake from reading alone.
- Third-party prep guides converge on **80–140 hours of total prep time** for candidates without much prior Snowflake exposure, and several structure their default plans as **30 days**, not 14.
- COF-C03 specifically added new surface area (Cortex AI, Iceberg, Notebooks, Git integration) that even experienced Snowflake users may not have touched yet, which adds real study time regardless of general SQL/data warehousing background.

**So, does 2 weeks work?**

- **Yes, if:** you already have real hands-on Snowflake experience (built pipelines, managed roles, tuned warehouses) and can study **intensively, full-time** — realistically 5–7 hours/day for 14 days (70–100 hours total, in range with the 80–140 hour estimate). The [2-week plan in STUDY_PLAN.md](STUDY_PLAN.md#2-week-intensive-track-full-time) is built for this profile.
- **Probably not, if:** you're new to Snowflake, can only study part-time (1–2 hours/day), or have never used Cortex/Iceberg/Notebooks/Git integration in Snowflake. For this profile, **3–4 weeks part-time is the more honest target**, and that's the [alternative track also included in STUDY_PLAN.md](STUDY_PLAN.md#3-4-week-part-time-track-alternative).
- **The risk of forcing 2 weeks when you're not ready** isn't just failing — it's the $175 fee, a mandatory 7-day wait before retaking, and (more importantly) walking away without the practical intuition the exam is actually trying to validate.

**Bottom line:** treat "2 weeks" as the floor for an already-experienced candidate studying full-time, not a default expectation. Be honest with yourself about your starting point before committing to it — [STUDY_PLAN.md](STUDY_PLAN.md) has a short self-check to help you pick the right track.

---

## Start here

New to this repo? Do this, in order:

1. Read the domain table above so you know what's being tested.
2. Open [`STUDY_PLAN.md`](STUDY_PLAN.md), take the 30-second self-check, and pick your track (2-week intensive or 3–4 week part-time).
3. Begin with [**Chapter 1: Snowflake Architecture Fundamentals**](chapters/01-architecture-fundamentals/README.md) — everything else in this guide builds on it.

---

## Official Snowflake resources

Always treat these as the source of truth. Third-party material (including this repo) should supplement, not replace, official docs.

| Resource | Type | Cost | Link |
|---|---|---|---|
| SnowPro Core Certification (COF-C03) official page | Exam overview, registration | Free to view | [learn.snowflake.com/en/certifications/snowpro-core-c03](https://learn.snowflake.com/en/certifications/snowpro-core-c03/) |
| Snowflake Documentation | Official technical docs | Free | [docs.snowflake.com](https://docs.snowflake.com/) |
| SnowPro Core Certification Prep Course (OD-COREPREP) | Official on-demand review course | Paid | [learn.snowflake.com/en/courses/OD-COREPREP](https://learn.snowflake.com/en/courses/OD-COREPREP/) |
| Hands-On Essentials Track | Free guided labs + badges in a real Snowflake trial environment | Free | [learn.snowflake.com/en/pages/hands-on-essentials-track](https://learn.snowflake.com/en/pages/hands-on-essentials-track/) |
| SnowPro Practice Exams (official) | Official practice questions | Paid | [learn.snowflake.com/en/certifications/snowpro-practice-exams](https://learn.snowflake.com/en/certifications/snowpro-practice-exams/) |
| Snowflake free trial account | Hands-on practice environment | Free (trial credits) | [signup.snowflake.com](https://signup.snowflake.com/) |
| SnowPro Continuing Education Program | Recertification info | Free to view | [learn.snowflake.com/en/snowpro-continuing-education](https://learn.snowflake.com/en/snowpro-continuing-education/) |

## Unofficial resources (courses, videos, books, practice tests)

These are reputable, commonly recommended third-party resources found during research for this guide. **Paid/free status is noted for each** — verify current pricing yourself, as it changes. Avoid any resource that markets itself as an "exam dump" or claims to have leaked real exam questions; using those violates Snowflake's certification agreement and can get your certification revoked.

### Video courses

| Resource | Format | Cost | Notes |
|---|---|---|---|
| [Training for Snowflake SnowPro Core Certification (COF-C03)](https://www.udemy.com/course/ultimate-snowpro-core-certification-course-exam/) | Udemy video course, 7+ hrs | Paid | Broad coverage including architecture, security, performance, loading, and Cortex AI |
| [SnowPro Core Certification (COF-C03) Latest 2026](https://www.udemy.com/course/snowpro-core-certification-cof-c03-latest-2026/) | Udemy video course | Paid | Explicitly covers new COF-C03 material: Git/CI-CD, Cortex AI, FinOps, secondary roles |
| [Snowflake SnowPro Core COF-C03 Mock Exams 2026](https://www.udemy.com/course/snowflake-snowpro-core-cof-c03-mock-exams-2026/) | Udemy, 6 full mock exams | Paid | Scenario-based questions on performance tuning, RBAC, and cost management |
| [Snowflake Core COF-C03 Certification Practice Tests](https://www.udemy.com/course/snowflake-core-cof-c03-certification-practice-tests/) | Udemy practice tests | Paid | Aligned to the official exam blueprint domains |
| [Essentials for Snowflake SnowPro Core Certification](https://www.datacamp.com/tracks/essentials-for-snowflake-snowpro-core-certification) | DataCamp track | Paid (subscription) | Structured skill track building toward Core exam topics |
| [Snowflake SnowPro Core Certification — Complete Guide, Practice Test & Question Dump](https://www.youtube.com/playlist?list=PLba2xJ7yxHB6-w7PHPi-wvj1SdbrIjxk2) | YouTube playlist | Free | Broad walkthrough; verify recency against COF-C03 domains before relying on it |
| [Snowflake SnowPro Core Certification Exam Prep](https://www.youtube.com/playlist?list=PL8ZkL0DLAM2qZ6CJ4zcJr16QprNq0UgSp) | YouTube playlist | Free | Free alternative to paid video courses |

### Books

| Resource | Publisher | Cost | Notes |
|---|---|---|---|
| [SnowPro Core Certification Study Guide](https://www.packtpub.com/en-us/product/snowpro-core-certification-study-guide-9781835884676) by Jatin Verma | Packt | Paid | Includes practice tests and flashcards; covers SQL, governance, transformations, and query optimization |
| [SnowPro Core Certification Study Guide](https://www.oreilly.com/library/view/snowflake-snowpro-core/9781119824442/) | Wiley/Sybex (via O'Reilly) | Paid (or O'Reilly subscription) | Comprehensive topic coverage with online practice tests and flashcards |
| [SnowPro™ Core Certification Companion: Hands-on Preparation and Practice](https://www.oreilly.com/library/view/snowprotm-core-certification/9781484290781/) | Apress (via O'Reilly) | Paid (or O'Reilly subscription) | Structured chapter-by-chapter around the official exam domains |
| [PacktPublishing/SnowPro-Core-Certification-Study-Guide](https://github.com/PacktPublishing/SnowPro-Core-Certification-Study-Guide) | GitHub companion repo | Free | Code samples accompanying the Packt book |

### Practice question sites / blogs

| Resource | Cost | Notes |
|---|---|---|
| [FlashGenius SnowPro Core practice test](https://flashgenius.net/sample-tests/snowpro-core) | Free | 450+ COF-C03-aligned practice questions with explanations |
| [CertStud SnowPro Core study guide](https://certstud.com/certifications/snowflake/snowpro-core/study-guide) | Free | Domain checklists and study notes; cross-check dates/domain names against the official page since third-party domain breakdowns vary |
| [OpenExamPrep SnowPro Core practice test](https://open-exam-prep.com/practice/snowflake-core) | Free, no signup | Quick low-friction knowledge checks |

**A word of caution on unofficial resources:** third-party sites sometimes lag behind exam version changes (several still reference COF-C02 domain names) or vary slightly on exact domain-weight percentages. This repo cross-checked multiple independent sources before settling on the domain table above, and you should apply the same skepticism — when in doubt, official Snowflake documentation wins.

---

## SEO / discovery notes

This repository is written to be useful both as a local folder and, if published, as a browsable documentation site or GitHub repo. Keywords like "SnowPro Core Certification study guide," "COF-C03 exam prep," and "Snowflake certification 2026" are used naturally throughout headers and text (not stuffed) to help this guide surface for people researching the same exam.

---

## Credits

Created by **Jack** (nguyenduongha2000@gmail.com) with Claude.

Content is original, written from publicly available Snowflake documentation and cross-checked third-party research current as of **July 26, 2026**. Snowflake evolves quickly — if you spot something stale, see [`CONTRIBUTING.md`](CONTRIBUTING.md).
