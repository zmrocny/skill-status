---
name: skill-status
description: 'Skill types (reference, task) and lifecycle statuses: draft, review, test, active, archived. Use when creating a skill, after human review, evals or field use, when a skill gets replaced or unused, or on "skill status", "skill type", "mark skill as …".'
license: MIT
metadata:
    type: reference
    status: active
---

| Name | Description |
|---|---|
| Skill status | Skill types and lifecycle statuses, when to move a skill between them. |

# Skill Status

Frontmatter of every `SKILL.md`, under `metadata` (per Agent Skills spec):

```yaml
metadata:
    type: reference | task
    status: draft | review | test | active | archived
```

## Types

| Type | What | Examples |
|---|---|---|
| `reference` | Knowledge base: terms, rules, references. No work of its own; read by other skills. | `domain-glossary`, `skill-status` |
| `task` | Does work or produces an artifact: changes code, data, files, runs a process, outputs a document or report. | `api-mock`, `translate`, `lint-fix` |

Skill both reads like a reference and does work or produces an artifact → `task`.

## Statuses

| Status | Meaning | Move here when |
|---|---|---|
| `draft` | Written with AI, wording and facts not checked by human. Snapshot of a conversation. | Skill created |
| `review` | Human read skill, wording and facts confirmed. | Human approved skill |
| `test` | Passes evals: scenarios run, results good enough to use. `task` only. | Evals passed |
| `active` | Used in real work for a period, worked, fixes minimal or none. | Period of use without notable fixes |
| `archived` | Not needed: replaced or unused. | Replaced by another skill or not used |

## Lifecycle

- `task`: `draft` → `review` → `test` → `active`.
- `reference`: `draft` → `review` → `active`. No evals: reference does no work to test. `active` = tasks used it for a period without fact corrections.
- `archived`: replaced by another skill or no longer used.
