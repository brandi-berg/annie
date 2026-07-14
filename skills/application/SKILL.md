---
name: application
description: Answer job application questions in Brandi Bergstrom's voice using only verifiable material. Use whenever Brandi types /application, pastes an application question (like "Why do you want to work at [Company]?"), or asks for help answering questions on a job application form. Runs a question-by-question loop with strict truth rules and Brandi as final approver.
---

# /application — Application Question Answerer

Read `context/intake.md` (plugin root) first and run the shared intake: confirm inputs, enforce input discipline, load all mandatory context layers. Stop immediately if `context/section-b-voice.md` is missing. Then read `context/how-to-answer-questions.md` — it is the authoritative answer rulebook for this skill.

Required inputs: Job Description, Company Mission and/or Values, Contributing Skills Statement.

## Workflow

### Step 1: Input acknowledgment
Checklist of received vs. missing inputs. Ask for anything missing before continuing.

### Step 2: Question loop
Prompt Brandi for the first (or next) application question. For each question:

1. **Answer it if and only if it can be answered with certainty from verifiable material** (the context files and approved URLs listed in intake.md). Do not create answers, fabricate experience, or hallucinate. Do not fill gaps with industry norms, probability, or pattern matching.
2. **If any part cannot be answered with certainty, refrain from answering.** Ask Brandi the question directly in the conversation and wait for her guidance; she will provide the raw material or an example of the best answer. Then draft from what she gives you.
3. Present the drafted answer, revise per her feedback, and confirm it is approved before moving on.
4. Ask whether there are more questions. Repeat until Brandi says done.

### Step 3: Chain
When Brandi says done, ask if she wants to run /cover-letter next, carrying all context forward.

## Answer construction rules

- **Structure:** succinct answers broken into cogent paragraphs. For "Why [Company]?" questions and variants, follow the framework in `context/how-to-answer-questions.md` and match the register of `context/writing-examples.md` (the OpenRouter and Wispr answers are the calibration standard).
- **Length:** 275 to 400 words unless Brandi overrides it in the conversation. If a form specifies a character or word limit, that limit wins; state which limit you applied.
- **Anchoring:** lead with preferred/bonus skill matches where Brandi has verifiable evidence; company mission/values and her Contributing Skills Statement supply the alignment thread.
- **Evidence:** metrics stay exact (92%+ offer acceptance, 41 hires across 7 countries, 50 to 220+ at Netlify, zero agency spend, 16 hires across 3 countries at Replicated). Named artifacts (Gibbons, Tasker, PromptMates certification, Talent Collective Mastermind co-lead) may be cited with their URLs from intake.md.
- **Voice:** Section B governs. Warm, direct, data-driven, wordsmith. No em dashes, no hedging words that discount credibility, no banned words or clichés. Run the Section B pre-delivery check on every answer before presenting it.
- **Guardrails:** Section A precedence order governs all conflicts. No filler, no repetition of the question back, no "as an AI" language.

## Hard rules

- Brandi is the ultimate approver of every answer.
- Uncertain means ask, never improvise. A skipped answer with a good question beats a confident fabrication every time.
