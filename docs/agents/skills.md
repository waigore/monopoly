---
title: Agent skills
tags: [docs, agents, skills, cursor, grok, opencode]
last_edited: 2026-10-07
---

# Agent skills

## Quick start

Each project skill has exactly one definition, at `.agents/skills/<skill-name>/SKILL.md`. Vendor directories may only point to that tree. They must never contain a skill definition.

1. Create `.agents/skills/<skill-name>/SKILL.md` with `name` and `description` frontmatter. `name` must match the folder name.
2. Put scripts and reference files in the same folder as `SKILL.md`.
3. Stop there. Cursor, OpenCode, and Grok already reach the new skill. See [How each agent finds the skills](#how-each-agent-finds-the-skills).

## Layout

```text
.agents/skills/                     Skill definitions, the only source
  <skill-name>/
    SKILL.md
    scripts/, references/           Optional supporting files
.grok/skills -> ../.agents/skills   Symlink so Grok sees the same tree
```

## How each agent finds the skills

| Agent | How it reaches `.agents/skills/` |
| --- | --- |
| Cursor | Reads `.agents/skills/` natively. Keep `.cursor/skills/` empty. |
| OpenCode | Reads `.agents/skills/` natively. Keep `.opencode/skills/` empty. |
| Grok | Uses `.grok/skills`, a committed symlink to `../.agents/skills`. |

Do not mirror skills into `.cursor/skills/` or `.opencode/skills/`, whether by copying or by symlinking. Those agents already read `.agents/skills/`, so a mirror would load each skill twice.

Grok Build documents `.grok/skills/` as its project skill directory. Because the whole directory is a symlink rather than one link per skill, new skills appear there automatically. Some Grok versions also scan `.agents/skills/`. They deduplicate skills by name, so the symlink does no harm.

To support another agent:

- If it reads `.agents/skills/`, add a row to the table and change nothing else.
- If it reads only its own directory, add a symlink from that directory to `.agents/skills` and a row to the table.
- Never copy a skill into a vendor directory.

## Writing a skill

Use the open [Agent Skills](https://agentskills.io) format so every agent can load the same file:

- `name`: lowercase letters, digits, and hyphens, at most 64 characters, identical to the folder name.
- `description`: what the skill does and when to use it, at most 1024 characters. Agents decide whether to load the skill from this text.
- Vendor-only frontmatter keys, such as Cursor's `disable-model-invocation`, are allowed. Other agents ignore them, so the skill must still work without them.
- Keep `SKILL.md` under 500 lines. Link supporting files one level deep, with paths relative to the skill folder.

`SKILL.md` follows the Agent Skills format, not the docs Markdown conventions in [AGENTS.md](../../AGENTS.md#markdown). Leave out the `title`, `tags`, and `last_edited` frontmatter.

## Symlinks on Windows

Git checks out `.grok/skills` as a symlink only when `core.symlinks` is enabled. On Windows, turn on Developer Mode, then clone with `git clone -c core.symlinks=true`. Without that setting, Git writes `.grok/skills` as a plain text file and Grok finds no project skills.
