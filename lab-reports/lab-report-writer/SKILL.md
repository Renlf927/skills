---
name: lab-report-writer
description: Token-efficient drafting, revision, formatting, and submit-checking for lab reports, especially LaTeX/PDF electronics experiment reports with reference reports, PPT instructions, figures, measured data, equations, comparison tables, and final PDF checks. Use when the user asks to write or revise an experiment report, imitate a reference report, insert/resize figures, reconcile theory/simulation/hardware values, fix LaTeX pagination, or check whether a report is ready to submit.
---

# Lab Report Writer

Produce correct, readable, submission-ready lab reports while spending as little context as practical. Preserve the user's existing style and reference format. Prefer targeted edits over rewrites.

## Token Policy

- Start small: list files, identify the active `.tex`/PDF/PPT/images, then read only the relevant source sections.
- Do not load whole PDFs, PPTs, logs, or image sets by default. Extract/search targeted text first; inspect images only when needed for values or layout.
- If a report already exists, patch the existing report. Avoid regenerating the whole document unless the user asks.
- Keep reasoning in the report, not in chat. Final replies should be short: changed files, compile/check status, and any uncertainty.
- Use approximate values when only screenshots are available; label them as estimated from plots/screenshots.

## Workflow

1. Inspect context cheaply.
   - List PDFs, PPTX, images, `.tex`, generated PDFs, and obvious reference reports.
   - Read current section headings and nearby text before editing.
   - Read reference reports only for format cues or missing required calculations.

2. Match format.
   - Preserve title style, author block, section order, captions, language, and existing macros.
   - For electronics labs, default sections are `Experimental Objectives`, `Experimental Equipment`, `Experimental Principle`, `Experimental Procedure and Results`, `Error Analysis`, and `Conclusion`.
   - A useful results order is `DC Operating Point`, `Transient Analysis`, then `Small-Signal AC Analysis`.

3. Build from evidence.
   - Include circuit purpose, component values, simulation commands, measurement setup, formulas, computed values, and comparison with hardware.
   - Distinguish theory, LTspice simulation, and oscilloscope/hardware results.
   - If theory and measurement differ, mention likely causes: device variation, resistor/capacitor tolerance, loading, parasitics, probe effects, and measurement conditions.

4. Cover required calculations.
   - Use consistent notation: \(A_v\), \(R_i\), \(R_o\), \(R_s\), \(R_L\), \(V_i\), \(V_s\), \(V_O\), \(V_L\).
   - Show formulas before results.
   - For gain: \(A_v=V_o/V_i\), \(A_v(\mathrm{dB})=20\log_{10}|A_v|\).
   - For input resistance with known source resistance:
     \[
     R_i=R_s\frac{V_i}{V_s-V_i}.
     \]
   - For output resistance from no-load and loaded output:
     \[
     R_o=R_L\left(\frac{V_O}{V_L}-1\right).
     \]
   - Use `~\mathrm{}` for units, e.g. `49~\mathrm{k}\Omega`.

5. Arrange figures and tables.
   - Group circuit, operating point, transient, AC response, oscilloscope, and resistance measurements semantically.
   - Pair related oscilloscope/input-output images when they share a condition.
   - Prefer compact comparison tables only when they add information not already clear from text.
   - If a summary table lists a value, make sure the derivation or reading method appears nearby.

## Layout And QA

Use normal readability before page-count optimization.

- Keep `12pt` and `1in` margins unless the user asks for compact layout.
- Prefer existing macros. Add new LaTeX helpers only when repeated figures/tables need them.
- Avoid random `\clearpage`; use `[H]` only when order matters.
- Use local fixes first: reduce figure height slightly, move a table, or use `\enlargethispage{...}`.
- For detailed snippets and page-break patterns, read `references/latex-layout.md` only when layout is failing or new helpers are needed.

Before saying the report is ready:

1. Compile at least twice after LaTeX edits: `pdflatex -interaction=nonstopmode -halt-on-error`.
2. Check the log for `Overfull`, `Underfull`, `Undefined`, `Warning`, and `Error`.
3. Render and inspect only the affected or final pages unless the user asks for full visual QA.
4. Verify conclusion values also appear in a table, formula, or calculation.

## Common Fixes

- Missing analysis: add a short paragraph near the relevant figure or in Summary; avoid rewriting the whole section.
- Missing required values: add formulas plus a small comparison table.
- Table on a blank page: move it near discussion, reduce column width, or use `[H]`.
- Figure pushed away from text: reduce image height or use a paired figure.
- Lonely final page: shorten repetitive conclusion or adjust local layout without deleting core interpretation.
- User dislikes style: restore the closest previous style and fix only the requested issue.

