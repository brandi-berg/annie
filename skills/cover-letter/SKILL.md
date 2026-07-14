---
name: cover-letter
description: Fill Brandi Bergstrom's cover letter template for a specific job application. Use whenever Brandi types /cover-letter, pastes a job description and asks for a cover letter, or asks to tailor, draft, or finalize a cover letter for a role. Produces an approved {{Company-why-statement}}, an approved "Where I add value" section, and a finished Word (.docx) cover letter built from the bundled template.
---

# /cover-letter — Cover Letter Builder

Read `context/intake.md` (plugin root) first and run the shared intake: confirm inputs, enforce input discipline, load all mandatory context layers. Stop immediately if `context/section-b-voice.md` is missing.

Required inputs: Job Description, Company Mission and/or Values, Contributing Skills Statement.

## Workflow — do not skip, collapse, or reorder steps. Each step produces its own labeled section.

### Step 1: Input acknowledgment
Checklist of received vs. missing inputs. Ask for anything missing before continuing.

### Step 2: Role read
From the JD, extract: company name, exact job title, core requirements, preferred/bonus skills. Map Brandi's verifiable experience to the preferred/bonus skills first (anchoring rule), then confirm core coverage. Cite only evidence present in the context files, per Section A candidate truth rules.

### Step 3: Draft the {{Company-why-statement}} — APPROVAL GATE
A polished, compelling statement of why Brandi is drawn to this organization, built from her Contributing Skills Statement and the company's mission/values. Constraints:

- 1 to 2 sentences. It is inserted as a standalone sentence in the letter's opening paragraph, immediately after "...I bring over 15 years of experience building and scaling high-performance recruiting functions at AI-native and developer-focused startups." and immediately before "I am excited to bring my expertise in full-cycle recruiting, AI-enabled talent operations, and strategic leadership to accelerate your growth." It must read naturally between those two sentences.
- Specific to this company. The test: if it could be sent to any other company unchanged, rewrite it.
- Section B voice, Section A formatting guardrails. No em dashes. Run the Section B pre-delivery check.

Present the draft and wait for Brandi's explicit approval. Iterate until approved. Do not continue to Step 4 without approval.

### Step 4: Draft Section 3 "Where I add value to {{Company Name}}" — APPROVAL GATE
The template's Section 3 sits between the markers `[This Section To Be Edited]` and `[End Edit Section]` and contains one framing paragraph plus three bullets. Treat these as tailorable defaults:

- Rewrite the framing paragraph and the three bullets to target this company's specific hiring environment, stage, and the JD's priorities.
- Keep exactly three bullets unless Brandi asks otherwise (preserves template layout).
- Every claim must trace to the resumes, LinkedIn, or writing examples. Metrics stay exact (92%+ offer acceptance, 41 hires across 7 countries, 50 to 220+, zero agency spend). Never invent or round up.
- Full letter body must land between 350 and 450 words (Section A verbosity spec). Count and state the word count when presenting.

Present the draft and wait for explicit approval before touching the template.

### Step 5: Fill the template and deliver the .docx
Template: `assets/TEMPLATE_Cover_Letter_v4.dotx` (relative to this skill). Never edit the template in place; copy it to a working directory first.

Mechanics (the .dotx is a ZIP of XML):

1. Copy the template to the working directory and unzip it.
2. In `[Content_Types].xml`, change the main document override from `application/vnd.openxmlformats-officedocument.wordprocessingml.template.main+xml` to `application/vnd.openxmlformats-officedocument.wordprocessingml.document.main+xml` so the output is a document, not a template.
3. In `word/document.xml`, replace tokens with approved values, XML-escaping the replacements (`&` → `&amp;`, `<` → `&lt;`, `>` → `&gt;`):
   - `{{Company Name}}` — appears 3 times (greeting, Section 3 heading, closing paragraph). Replace all.
   - `{{Job Title}}` — exact title from the JD.
   - `{{Company-why-statement}}` — the approved statement from Step 3, without surrounding quotes. The template supplies the trailing period only if the statement lacks one; do not produce a double period.
4. Replace the Section 3 content between the marker paragraphs with the approved Step 4 wording, editing text inside existing `<w:t>` elements to preserve formatting. Then delete the `[This Section To Be Edited]` and `[End Edit Section]` marker paragraphs entirely. No marker text may survive into the deliverable.
5. Verify zero `{{` or `}}` sequences and zero marker text remain in `word/document.xml`.
6. Rezip and name the file `Brandi-Bergstrom-Cover-Letter-{Company-Name}.docx`.
7. If rendering tools are available, render to PDF and visually check one page of clean layout before delivering. Deliver the .docx to Brandi.

### Step 6: Chain
Ask if Brandi wants to run /application next, carrying all context forward.

## Hard rules

- Brandi approves all wording before it enters the document. Two gates, no exceptions.
- Section A precedence order governs conflicts. Section B governs voice.
- Only verifiable claims from the context files or approved URLs. If evidence is missing, say "not stated" and ask.
