# CLDMaker Agent Skills

Portable skills for researching, creating, and auditing causal loop diagrams with [CLDMaker](https://github.com/pearlmuter/cld-maker).

The repository follows the open [Agent Skills specification](https://agentskills.io/specification) and contains:

| Skill | Purpose |
| --- | --- |
| `cld-authoring` | Operate CLDMaker through MCP and create reliable diagram structure, layout, loop annotations, and saved artifacts. |
| `cld-research-to-diagram` | Turn evidence into an auditable CLD using an evidence ledger, feedback analysis, archetype checks, and an adversarial review. |

## Install

Install both skills into a supported agent:

```sh
npx skills add pearlmuter/cldmaker-skills
```

Install one skill:

```sh
npx skills add pearlmuter/cldmaker-skills --skill cld-authoring
npx skills add pearlmuter/cldmaker-skills --skill cld-research-to-diagram
```

The installer supports Codex, Claude Code, Qwen Code, OpenCode, Cursor, and other Agent Skills-compatible clients. Review the files before installation; skills are instructions executed with the permissions of their host agent.

For diagram operations, connect the CLDMaker MCP server and keep the CLDMaker application running. The research skill can still be used without CLDMaker for causal analysis, but it cannot create or edit a `.cld` document without the MCP tools.

## Manual installation

Copy either skill directory into the personal skills directory used by the agent:

| Agent | Personal directory |
| --- | --- |
| Codex | `~/.codex/skills/` |
| Claude Code | `~/.claude/skills/` |
| Qwen Code | `~/.qwen/skills/` |

Each skill is self-contained. Keep its directory name and `SKILL.md` together with any `references/` and `agents/` content.

## License

MIT
