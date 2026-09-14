# Learning Memory

Use one workspace-local file named `.llm-teacher.yml`. Keep it compact, human-readable, and private by default.

## Initialize

Create the file only after an explicit `init` request. Never replace an existing file.

```yaml
version: 1
preferences:
  teaching_enabled: true
  teaching_level: balanced
topics: []
```

Use a boolean for `teaching_enabled` and `light`, `balanced`, or `deep` for `teaching_level`. Add `.llm-teacher.yml` to the workspace `.gitignore` by default while preserving all existing entries. If no `.gitignore` exists, create one containing that entry.

When `AGENTS.md` is used by the active agent environment, add the following marked block while preserving all unrelated content. Replace only an existing block with the same markers.

```markdown
<!-- LLM-TEACHER:START -->
When `.llm-teacher.yml` exists, use the `llm-teacher` skill for substantive development and learning tasks. Keep explanations proportional to the request and update only meaningful learning topics.
<!-- LLM-TEACHER:END -->
```

Initialization is complete when the memory exists, is ignored by Git, and any applicable instruction block has been installed.

## Topic Format

Store topics directly under `topics`:

```yaml
- id: database-transactions
  title: Database transactions
  parent: databases
  mastery: practicing
  last_seen: 2026-09-14
  last_reviewed: null
  weak_points:
    - Confuses atomicity with isolation
  notes:
    - Applied while implementing an order workflow
```

Rules:

- Use a stable lowercase kebab-case `id` and a concise English `title`.
- Use `parent: null` when no useful parent exists. Do not build a deep taxonomy.
- Allowed mastery values are `introduced`, `practicing`, and `understood`.
- Use ISO `YYYY-MM-DD` dates.
- Keep `weak_points` specific and actionable. Do not use a generic `weak: true` flag.
- Keep `notes` short and durable. Never store full prompts, transcripts, secrets, personal data, or substantial source code.
- Omit stale notes and resolved weak points instead of accumulating history.

## When to Update

Add or update a topic only when at least one condition applies:

- the concept is central to understanding the task;
- the agent explained it substantially;
- the user requested clarification;
- the user demonstrated understanding or a misconception;
- the concept was assessed in a quiz;
- the concept is reusable beyond the immediate implementation detail.

Do not create a topic for every technology name, command, file, function, or incidental fact. Before adding one, compare its meaning with existing topic titles, IDs, parents, weak points, and notes.

## Mastery Updates

- A newly taught topic starts as `introduced`.
- Move to `practicing` when the user partially explains, reasons about, or applies it.
- Move to `understood` only after clear independent evidence of understanding.
- A minor isolated mistake does not automatically downgrade an understood topic. Add a weak point or downgrade only when the error reveals a material gap.
- Remove a weak point when the user clearly resolves that exact misconception.
- Set `last_seen` whenever a meaningful update is made. Set `last_reviewed` only after assessment.

Write updates after the substantive response or after each answered quiz question. Preserve unknown fields for forward compatibility.

## Progress Requests

Summarize the memory rather than reproducing the YAML. Report:

- topics grouped by mastery;
- active weak points;
- topics that have never been reviewed or were reviewed least recently;
- one or two useful next learning actions.

If the file is missing or malformed, explain the issue briefly. Do not fabricate prior learning state or silently replace corrupted content.
