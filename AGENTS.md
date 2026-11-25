# AGENTS.md

This repo ships an Agent Skill for tracking skill types and lifecycle statuses.

## Layout

| Path | Purpose |
|---|---|
| `skills/skill-status/SKILL.md` | The skill's main file, read by the user's agent. |
| `apm.yml` | APM package manifest. |
| `.claude-plugin/` | Claude Code plugin metadata, marketplace listing and icon. |
| `README.md` | User-facing description and install instructions. |
| `LICENSE` | MIT. |

## Rules

- Never commit, tag or push for the maintainer.
- Keep the skill in `skills/skill-status/`, do not move it to `.apm/`.

## Release

Versions follow semver. Each release gets a git tag `vX.Y.Z`.

1. Bump `version` in `apm.yml` and `.claude-plugin/plugin.json`; both must match.
2. Run `claude plugin validate . --strict` and `apm pack --dry-run`.
3. Give the maintainer the release commands:
   ```sh
   git add -A
   git commit -m "Release vX.Y.Z"
   git tag vX.Y.Z
   git push origin main vX.Y.Z
   ```
