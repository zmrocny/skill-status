# skill-status

A lifecycle for [agent skills](https://agentskills.io): from AI draft to proven in real work.

```yaml
metadata:
    type: reference | task
    status: draft | review | test | active | archived
```

- **Types:** `reference` is a knowledge base read by other skills; `task` does work or produces an artifact.
- **Statuses:** `draft` → `review` → `test` (task only) → `active`; `archived` when no longer needed.

See [`skills/skill-status/SKILL.md`](skills/skill-status/SKILL.md) for the full rules.

## Install

### Any agent (skills CLI)

Works with Claude Code, Codex, Cursor, OpenCode and other agents that support Agent Skills:

```sh
npx skills add zmrocny/skill-status
```

The CLI detects installed agents and asks where to put the skill.

### APM

With [APM](https://github.com/microsoft/apm) (Agent Package Manager):

```sh
apm install zmrocny/skill-status       # current project
apm install -g zmrocny/skill-status    # user scope, all projects
```

APM detects your agents automatically; pick specific ones with `--target`, e.g. `--target claude,cursor`.

### Claude Code (plugin)

```
/plugin marketplace add zmrocny/skill-status
/plugin install skill-status@skill-status
```

### Manually

Copy `skills/skill-status/` into your agent's skills directory, for example `~/.claude/skills/` or `.agents/skills/`.

## License

[MIT](LICENSE)
