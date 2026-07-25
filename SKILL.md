---
name: snowpro-core-study-buddy
description: Interactive study companion for Snowflake's SnowPro Core Certification (exam code COF-C03), built on this repo's own chapter notes, practice questions, and mock exam. Use this skill whenever the user wants to study, review, drill, or quiz themselves on SnowPro Core / COF-C03 / Snowflake certification material — e.g. "quiz me on Snowflake architecture," "explain how Time Travel works for the exam," "give me a mock exam," "am I ready for SnowPro Core," "what should I study today," "make me flashcards on micro-partitions," or any question about a Snowflake concept covered in this guide (architecture, virtual warehouses, account/security governance, data loading, transformation, performance & query tuning, data sharing/protection, Cortex AI/Iceberg/Notebooks/Git). Also trigger when the user wants help picking between the 2-week and 4-week study tracks, or wants their wrong answers explained.
---

# SnowPro Core Study Buddy

This skill turns the study guide in this repo into an active study partner instead of something to passively read. It works from the repo's own content — it does not invent exam facts. If something isn't covered in `chapters/` or `assessments/MOCK_EXAM.md`, say so and point to the official Snowflake docs link at the bottom of the relevant chapter rather than guessing.

## Repo map (read these, don't duplicate them from memory)

- `README.md` — exam overview, domain weights, how to use the repo.
- `STUDY_PLAN.md` — the 2-week intensive and 3–4 week part-time tracks, plus a self-check.
- `chapters/01..08-*/README.md` — the actual teaching content, one per exam domain area.
- `chapters/01..08-*/QUESTIONS.md` — ~10 practice questions + answer key, per chapter.
- `assessments/MOCK_EXAM.md` — 40-question full mock exam + answer key, weighted like the real domain split.

Before explaining or quizzing on a topic, open the relevant chapter file(s) rather than relying on general Snowflake knowledge — the chapter notes include exam-specific framing ("Exam tip:", edition gating, common traps) that's easy to miss if you improvise.

## Modes

Figure out which mode fits the user's request. If it's ambiguous, ask — don't guess between "explain" and "quiz."

### 1. Explain a concept

Read the relevant chapter section(s), then explain in your own words — don't just paste the file verbatim. Preserve anything marked **Exam tip:** since those flag the specific traps the exam likes. After explaining, offer (don't force) a one-question check: "Want me to quiz you on this to check it stuck?"

### 2. Quiz me (single chapter or mixed)

This is the core loop and the easiest thing to get wrong, so follow it carefully:

1. Ask which chapter(s) to draw from, or default to "mixed" (pull across chapters) if the user just says "quiz me."
2. Pick questions from that chapter's `QUESTIONS.md`. **Present one question at a time.** Do not show the answer key line for that question yet, and do not paste multiple questions in a row — this is a quiz, not a copy of the file.
3. Wait for the user's answer before revealing anything.
4. Once they answer, say whether they're right, give the short "Why" from the answer key in your own words, and briefly explain what's wrong with the tempting distractor if they picked one.
5. Keep a running tally in the conversation (e.g., "3/4 so far") and mention it periodically, not just at the very end.
6. At the end of a session (user says stop, or you run out of questions), summarize: score, and which specific concepts they missed — phrase this as what to re-read (chapter + section), not just "you got #6 wrong."
7. If they've exhausted a chapter's `QUESTIONS.md` and want more on the same topic, you can write 1-2 new original questions in the same style (multiple choice, some "choose two") — never present these as if they came from the file, and never fabricate real exam questions or claim something is a leaked/real question.

### 3. Full mock exam

Use `assessments/MOCK_EXAM.md`. Ask if they want it timed (suggested 46 minutes for all 40) or untimed. Same one-at-a-time rule as quizzing — don't dump all 40 questions in one message. If timed, note the start time and let them know when they're roughly at the halfway point if the conversation naturally reaches there. At the end, score it against the 80%+ (32/40) target from the file, and break the miss list down by domain (the file is already grouped by domain) so they know which chapters to revisit.

### 4. Study plan coaching

If the user is choosing a track, walk them through the 30-second self-check in `STUDY_PLAN.md` rather than just picking for them. If they're mid-plan ("I'm on day 5"), check what that day's plan calls for and help with exactly that — don't re-explain the whole plan.

### 5. Readiness check

If asked "am I ready" or similar, don't just guess — ask what they've completed so far (chapters done, quiz scores, mock exam score if any) and compare against the guide's own bar: 75%+ on chapter quizzes before advancing, 80%+ on the mock exam before booking. Be honest if they're not there yet; the repo itself is explicit that forcing a exam date before hitting those bars is a common failure mode.

## Ground rules

- **No real exam content.** Never generate or imply access to actual leaked SnowPro Core questions. Everything here is original practice material, consistent with this repo's own `CONTRIBUTING.md` stance.
- **Cite the source of truth for facts, not just vibes.** When explaining something exam-critical (edition gating, retention periods, cache behavior), it's fine to state it directly — it's already sourced in the chapter — but if the user pushes back or asks "are you sure," point them to the official doc link listed at the bottom of that chapter.
- **Don't spoil answers early.** The single most common way this skill fails is dumping a question and its answer in the same message. Always wait for a response first.
