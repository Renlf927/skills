---
name: ppt-reviewer
description: Create exam revision notes by reading past papers first, mapping every knowledge-bearing sub-question back to lecture/PPT content, and producing a question-to-source map plus exam-ready knowledge modules. Use when Codex is asked to revise for a course exam from past papers, lecture slides/PDFs/PPTs, Moodle downloads, or similar folders, especially when the user wants notes organised by exam-tested topics rather than ordinary slide summaries.
---

# PPT Reviewer

Use this skill to turn past papers and lecture materials into revision notes that are driven by what the exam actually asks.

## Core Rule

Read past papers first. Extract every sub-question that contains a knowledge point. Then return to the lectures to locate and reconstruct the corresponding knowledge module. Do not summarise the PPT in lecture order, and do not collapse the result into a list of short answers.

## Workflow

1. Inventory the workspace.
   - Locate exam folders such as `exam/`, `exams/`, `past_papers/`.
   - Locate lecture folders such as `lecture/`, `lectures/`, `slides/`.
   - Preserve the user's requested output paths and overwrite policy.

2. Extract source text with page/slide references.
   - Reuse existing extracted text caches when available.
   - For PDFs/PPTs, keep page or slide numbers in the extracted representation.
   - Render or visually inspect pages that contain diagrams, timing charts, code screenshots, waveform figures, datasheet snippets, or tables that text extraction may miss.

3. Decompose the past papers.
   - Split by paper, question, sub-question and sub-sub-question.
   - Keep only knowledge-bearing prompts: definitions, comparisons, calculations, protocols, code explanation, diagrams, testing/design questions, scenario justification.
   - Record ambiguous or figure-dependent items explicitly.

4. Build a question-to-source map.
   - Required columns unless the user asks otherwise:
     `Past Paper | Question | What it asks for | Related Lecture | PPT content to extract | Confidence`.
   - Use concrete lecture/page references where possible.
   - Mark `Uncertain` when the lecture match is weak, absent, or the question depends mainly on an exam-provided figure/datasheet/API table.

5. Write the revision notes by knowledge module.
   - Organise by topic clusters implied by the papers, not by lecture order.
   - For every major module include:
     - Past-paper triggers
     - PPT sources
     - Related exam questions by knowledge point
     - Definitions and full lecture-derived knowledge block
     - Tables for comparisons or categories
     - Step tables for protocols/processes
     - Formula tables for calculations
     - Code syntax, meaning and common traps for code questions
     - Typical answer structure when useful
   - Keep the level of detail high enough that the student can revise the concept, not just memorise one answer.

6. Match the exam language.
   - If the exam is in English, write the formal notes in English-first style.
   - Use Chinese only for brief explanatory hints if the user requests it.
   - Keep technical terms in the exam language.

7. Validate the notes.
   - Check that every recurring past-paper knowledge point appears in the revision notes.
   - Check that each module has specific question numbers, not just vague paper references.
   - Check that tables render correctly, especially code containing `|` characters.
   - Check that uncertain mappings are labelled rather than invented.
   - Verify output files exist and report their paths.

## Formatting Rules

- Prefer Markdown tables for comparisons, classifications, pros/cons, definitions with examples, and formula summaries.
- Prefer ordered step tables for protocols such as I2C, SPI, UART, interrupt servicing, lifecycle, scheduling calculations and code workflows.
- Use code fences for reusable code skeletons.
- Keep notes dense, exam-oriented and scannable.
- Avoid long copied passages from slides; reconstruct the knowledge module in original wording.

## Quality Bar

Good output:

- Starts from paper questions and links each knowledge point back to lecture content.
- For a prompt like "write two types of black-box testing", extracts black-box testing definition, purpose, aspects/examples, differences from white-box testing, advantages/disadvantages and exam wording.
- For a prompt like "polling vs interrupt", gives a comparison table plus scenario-selection logic.
- For a prompt like "I2C/SPI/UART", gives signal lines, transaction steps, address/framing rules, API skeletons and traps.
- For a prompt like "MCU vs MPU", gives a complete comparison table plus scenario KPI reasoning, not a one-line answer.

Bad output:

- Average slide summaries.
- A flat "Answer-ready notes" table where each topic is only one short answer.
- A list of isolated exam answers without the surrounding PPT knowledge module.
- Unsupported details without an `Uncertain` label.

## Previous-Thread Context

When the user asks to preserve or reuse previous conversation lessons, use Codex thread tools if available:

1. Search with `list_threads` using the course name, folder name and task keywords.
2. Read relevant threads with `read_thread`.
3. Extract process lessons, user preferences and rejected output patterns.
4. Do not rely on memory alone when the user explicitly asks to read previous thread records.

For the Embedded Processors case that motivated this skill, read [evaluation-lessons.md](references/evaluation-lessons.md) if the user asks for the same style or complains about answer-list notes.
