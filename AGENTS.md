# AGENTS.md

This repo ships one Agent Skill, `skill-status`, installable through several channels. `README.md` is for users; this file is for agents maintaining the repo.

## Layout

| Path | Purpose |
|---|---|
| `skills/skill-status/SKILL.md` | The skill's main file, read by the user's agent. |
| `apm.yml` | APM package manifest. |
| `.claude-plugin/plugin.json` | Claude Code plugin manifest. |
| `.claude-plugin/marketplace.json` | Claude Code marketplace listing this repo as one plugin. |
| .claude-plugin/icon.png | Plugin icon for Anthropic's directory. Fixed after first submission. |
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
