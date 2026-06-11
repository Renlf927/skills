# Skills

Monorepo for Codex skills, grouped by the skill's actual use case or name.

## Structure

```text
skills/
+-- README.md
+-- lab-report-writing/       # Lab report drafting, LaTeX, PDF QA, and submission checks
|   +-- lab-report-writer/
|   |   +-- SKILL.md
|   |   +-- references/
|   +-- README.md
+-- ppt-reviewer/             # Exam revision notes from past papers and lecture/PPT content
|   +-- SKILL.md
|   +-- agents/
|   +-- references/
```

## Current Skills

| Skill | Type | Purpose |
| --- | --- | --- |
| `lab-report-writing/lab-report-writer` | Lab report writing | Draft, revise, format, compile, and submit-check LaTeX/PDF lab reports. |
| `ppt-reviewer` | Exam revision | Map past-paper questions back to lecture/PPT content and produce question-driven revision notes. |

## Naming Rule

Use the skill's name or actual workflow as the top-level module. For example:

| Skill area | Top-level folder |
| --- | --- |
| Paper reading | `paper-reading/` |
| Lab report writing | `lab-report-writing/` |
| LTspice lab assistant | `ltspice-lab-assistant/` |

Do not group skills by unrelated project components such as `embedded/`, `web/`, `algorithm/`, `hardware/`, or `docs/` unless the skill itself is specifically about that workflow.

## Adding A Skill

1. Create a top-level folder from the skill's name or use case.
2. Add a `SKILL.md` file with frontmatter containing `name` and `description`.
3. Put long examples, templates, and references in a local `references/` folder.
4. Update this README so the skill is easy to discover.
