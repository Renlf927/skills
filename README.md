# Skills

Private monorepo for Codex skills.

## Structure

```text
skills/
+-- README.md
+-- lab-reports/              # Lab report drafting, LaTeX, PDF QA, and submission checks
|   +-- lab-report-writer/
|   |   +-- SKILL.md
|   |   +-- references/
|   +-- README.md
+-- embedded/                 # Embedded-system skills
|   +-- README.md
+-- web/                      # Web dashboard and frontend skills
|   +-- README.md
+-- algorithm/                # Algorithm, planning, SLAM, and optimization skills
|   +-- README.md
+-- docs/                     # Shared documentation, images, and architecture notes
|   +-- README.md
+-- hardware/                 # Circuit, PCB, and wiring-related skills
    +-- README.md
```

## Current Skills

| Skill | Type | Purpose |
| --- | --- | --- |
| `lab-reports/lab-report-writer` | Lab reports | Draft, revise, format, compile, and submit-check LaTeX/PDF lab reports. |

## Adding A Skill

1. Create a folder under the closest category.
2. Add a `SKILL.md` file with frontmatter containing `name` and `description`.
3. Put long examples, templates, and references in a local `references/` folder.
4. Update this README so the skill is easy to discover.
